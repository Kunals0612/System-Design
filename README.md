# What is System Design ?

System design is the process of defining the architecture, components, modules, interfaces, and data for a system to satisfy specified requirements. It is a high-level blueprint of how different parts of a system will work together to achieve a given goal. This discipline is commonly applied to software systems but can also encompass hardware or a combination of both.

# Horizontal and Vertical Scaling
![clientServer](https://github.com/user-attachments/assets/7222cb6f-1ffb-483d-8757-b6062efee62b)

**Horizontal Scaling**: Adding more machines or servers to a system to distribute the load and increase capacity (e.g., adding more servers to a cluster). It improves scalability by working across multiple nodes.

**Vertical Scaling**: : Upgrading the resources (CPU, RAM, storage) of a single machine or server to handle increased demand. It enhances performance but is limited by hardware capacity.

Buy Bigger Machine: Vertical Scaling.

Buy More Machine: Horizontal Scaling.

## Difference between Horizontal Scaling and Vertical Scaling

| **Aspect**              | **Horizontal Scaling**                          | **Vertical Scaling**                           |
|--------------------------|------------------------------------------------|-----------------------------------------------|
| **Definition**           | Adding more servers or machines to a system.   | Upgrading the resources of a single machine.  |
| **Capacity Expansion**   | Increases capacity by adding more nodes.       | Increases capacity by enhancing a single node.|
| **Scalability**          | Virtually unlimited (can add more nodes).      | Limited by hardware capacity.                 |
| **Cost**                 | Requires additional machines or cloud instances.| Involves upgrading hardware, which may be costly. |
| **Examples**             | Adding multiple servers in a cluster.          | Upgrading RAM or CPU of an existing server.   |
| **Fault Tolerance**      | Higher (failure in one server doesn’t stop the system). | Lower (single point of failure).     |
| **Implementation**       | Needs load balancers and distributed systems.  | Easier to implement; just upgrade the machine.|

# What is Capacity Estimation ?

Capacity estimation is the process of determining the resources (such as storage, bandwidth, processing power, and memory) required to handle the workload of a system or application efficiently. This helps in planning infrastructure to ensure smooth performance under expected or peak loads.

## Steps for Capacity Estimation 
1. **Understand the system's Requirements:**
   - Define the scope (e.g., storage, bandwidth, compute power).
   - Identify the expected load (e.g., number of users, requests, data size).
2. **Analyze Workload:**
   - Estimate the average and peak usage patterns.
   - Measure key metrics like requests per second (RPS), data size, and latency.
3. **Break Down Resource Usage:**
   - Calculate storage for data (e.g., videos, metadata).
   - Compute processing power for operations (e.g., transcoding, analytics).
4. **Plan for Scalability:**
   - Allow headroom for future growth.
   - Decide on horizontal or vertical scaling.
## Capacity Estimation of YouTube.

1. **Storage Capacity:**
   - **Uploads:** Assume YouTube receives 500 hours of video per minute.
        - *Duration per Day:* 500 hours/minute × 60 minutes/hour × 24 hours/day = 720,000 hours/day.
   - **Video Quality:** Assume an average of 1080p resolution (~1 GB per hour).
        - *Storage per Day:*  720,000 hours/day × 1GB/hour=720,000GB/day (720 TB/day).
        - *Annual Storage:* 720 TB/day × 365 days/year = 262,800 TB/year (~263 PB/year).
          
2. **Bandwidth Capacity:**
   - **Average Users:** Assume 2 billion users watch videos daily.
   - **Average Watch Time:** Assume each user watches 1 hour of video daily.
        - *Daily Video Playback:* 2 billion users×1 hour/user=2 billion hours/day.
   - **Data Transfer:** At 1080p (~1 GB/hour):
        - 2 billion hours/day×1 GB/hour = 2,000,000TB/day (~2 EB/day).
          
3. **Compute Power:**
   - **Transcoding:** Every uploaded video is transcoded into multiple resolutions (e.g., 240p, 360p, 720p, 1080p).
        - If one upload is transcoded into 4 formats, compute power must handle 4×720,000=2.88million hours/day.
   - **Analytics:** Real-time analytics for 2 billion users require significant compute resources.
     
4. **Database and Metadata:**
  - **Metadata:** Store information like video titles, descriptions, tags, and user interactions.
      - Assume each video has 1 KB of metadata. For 720,000×1KB=720MB/day.

# What are HTTP and HTTPS protocols ?
   - HyperText Transfer Protocol(HTTP) is an application layer protocol that is used to access and transfer data(text, images, video, multimedia, etc) over the world wide web.
   - HTTP is a client-server protocol that runs on top of the TCP/IP family of protocols and uses the request/response protocol.
   - HTTP uses port number 80. 
   - In HTTP, the client sends a request message to the server. After the client responds, HTTP establishes a TCP connection between the client and the server. HTTP delivers a request to the server, which collects the data that was 
     requested. After the server sends data to the client, the connection will be terminated.
   - If we want something else from the server, we should have to re-establish the connection between client and server
     
## Features of HTTP :
   - **HTTP is connectionless:** After serving a single HTTP request, the client-server connection is closed and that same connection is never used again.
   - **HTTP is media independent:** It means that HTTP can send any sort of data as long as both the client and the server understand how to process the data.
   - **HTTP is stateless:** The client and server only know about each other during the current request, and when the connection is disconnected, both the client and the server forget about each other.

# HTTPS
Hypertext Transfer Protocol Secure is a secure extension or version of HTTP that is used for providing security to the data sent over the world wide web.

This protocol allows transferring the data in an encrypted form which is particularly important when users transmit sensitive data such as login credentials.

To encrypt communications HTTPS uses an encryption protocol called Transport Layer Security (TLS), formerly known as Secure Sockets Layer (SSL). 

HTTPS protocol uses the 443 port number for communicating the data.
  
# TCP/IP Protocol
TCP is a set of communication protocols that supports network communication.

The TCP model is subdivided into five layers, each containing specific protocols.

![TCP](https://github.com/user-attachments/assets/5d293b10-fde0-4796-832e-271fd4bbe9ea)

## **Layers of TCP model**
1. **Physical Layer**
   - The physical layer translates message bits into signals for transmission on a medium, i.e. the physical layer is the place where the real communication takes place.
   - Signals are generated depending on the type of media used to connect two devices. For example, electrical signals are generated for copper cables, light signals are generated for optical       fibers, and radio waves are generated for air or vacuum.
   - Physical layer also specifies characteristics like topology(bus,star,hybrid,mesh,ring), line configuration(point-to-point, multipoint) and transmission mode(simplex, half-duplex, full-         duplex).
     
2. **Data Link Layer(DLL)**
   - The DLL is subdivided into 2 layers: MAC(Media Access Control), LLC(Logical Link Control)
   - The MAC layer is responsible for data encapsulation(Framing) of IP packets from the network layer into frames. Framing means DLL adds a header(which contains the MAC address of source and      destination) and a trailer(which contains error-checking data) at the beginning and end of IP packets.
   - LLC deals with flow control and error control.
   - Flow control: Limits how much data a sender can transfer without overwhelming the receiver.
   - Error Control: Error in the data transmission can be detected by checking the error detection bits in the trailer of the frame.
     
3. **Network Layer**
   
   The network layer adds IP address/logical address to the data segments to form IP packets and finds the best possible path for data delivery. IP addresses are addresses allocated to a 
   device to uniquely identify it on a global scale. Common protocols used in the Network layer are
   - IP(Internet Protocol): IP uses the receiver’s IP address to determine the best path for the proper delivery of packets to the destination.
     When a packet is too large to send over a network medium, the sender host's IP splits it up into smaller fragments. The fragments are reassembled into the original packet on the receiving 
     host. IP is unreliable since it does not ensure delivery or check for errors.
   - ARP(Address Resolution Protocol): ARP is used to find MAC/physical Addresses from the IP address.
   - ICMP(Internet Control Message Protocol): ICMP is responsible for error reporting.
     
4. **Transport Layer**
   
   The transport layer is in charge of flow control (controlling the rate at which data is transferred), end-to-end connectivity, and error-free data transmission. Protocols used in the           Transport layer:
   
   TCP(Transmission Control Protocol): 
      - TCP is a connection-oriented protocol, which means it requires the formation and termination of connections between devices in order to transmit data.
      - TCP segmentation means that at the sending node, TCP breaks the entire message into segments, assigns a sequence number to each segment, then reassembles the segments into the original         message at the receiving end based on the sequence numbers.
      - TCP is a reliable protocol because it identifies errors and retransmits the damaged frames, and ensures data delivery in the correct order.
        
   UDP(User Datagram Protocol):
      - UDP is a connectionless protocol, which means it does not require the establishment and termination of connections between devices.
      - UDP does not support segmentation and lacks error checking and correction which makes it less reliable but more cost-efficient.
        
5. **Application Layer**
   
   This is the uppermost layer, which combines the OSI model's session, presentation, and application layers. Users can interact with the application and access network resources through this     layer.
   
   Protocols used in the Application layer:
    - HTTP(Hypertext Transfer Protocol): Protocol used to access data on the World Wide Web.
    - DNS(Domain Name System): This protocol translates domain names to IP addresses.
    - SMTP(Simple Mail Transfer Protocol): This protocol is used to send Email messages.
    - FTP(File Transfer Protocol): This protocol is used to transfer files between computers.
    - TELNET(Telecommunication Network): It is a two-way communication protocol connecting a local machine to a remote machine.

# What happens when you enter “google.com”?

- What is a WebPage  -> Before getting started, I want to first explain what a webpage is. A webpage is basically a text file formatted a certain way so that your browser (ie. Chrome, Firefox, 
  Safari, etc) can understand it; this format is called HyperText Markup Language (HTML). These files are located in computers that provide the service of storing said files and waiting for 
  someone to need them to deliver them. They are called servers because they serve the content that they hold to whoever needs it.

- Servers -> These servers can vary in classes, the most common and the one that we'll be talking about in the main portion of this article is a web server, the one that serves web pages. We 
  can also find application servers, which are the ones that hold an application base code that will then be used to interact with a web browser or other applications. Database servers are 
  also out there, which are the ones that hold a database that can be updated and consulted when needed.

- IP Addresses -> These servers in order to deliver their content, much like in physical courier services, need to have an address so that the person needing to be said content can make a 
  "letter" requesting the delivery; the person requesting the content in turn also has an address where the server can deliver the content to. These addresses are called IP (Internet Protocol) 
  Addresses, a set of 4 numbers that range from 0 to 255 (one byte) separated by periods (ie. 127.0.0.1).

- Protocols for Delivery -> Another concept that is important to know is that the courier service traffic for the delivery can be one of two: Transmission Control Protocol (TCP) and User 
  Datagram Protocol (UDP). Each one determines the way the content of a server is served or delivered.

**What Actually happens….**

So back to the main question of what happens when you type www.google.com or any other URL (Uniform Resource Locator) in your web browser and press Enter. 

- So the first thing that happens is that your browser looks up in its cache to see if that website was visited before and the IP address is known. 

- If it can't find the IP address for the URL requested then it asks your operating system to locate the website. The first place your operating system is going to check for the address of the 
  URL you specified is in the host file. If the URL is not found inside this file, then the OS will make a DNS request to find the IP Address of the web page.

- The first step is to ask the Resolver (or Internet Service Provider) server to look up its cache to see if it knows the IP Address, if the Resolver does not know then it asks the root server 
  to ask the .COM TLD (Top Level Domain) server - if your URL ends in .net then the TLD server would be .NET and so on - the TLD server will again check in its cache to see if the requested IP 
  Address is there. 

- If not, then it will have at least one of the authoritative name servers associated with that URL, and after going to the Name Server, it will return the IP Address associated with your URL. 
  All this was done in a matter of milliseconds WOW!
  
- After the OS has the IP Address and gives it to the browser, it then makes a GET (a type of HTTP Method) to said IP Address. When the request is made the browser again makes the request to 
  the OS which then, in turn, packs the request in the TCP traffic protocol we discussed earlier, and it is sent to the IP Address.
  
- On its way, it is checked by both the OS' and the server's firewall to make sure that there are no security violations. And upon receiving the request the server (usually a load balancer 
  that directs traffic to all available servers for that website) sends a response with the IP Address of the chosen server along with the SSL (Secure Sockets Layer) certificate to initiate a 
  secure session (HTTPS). 

- Finally, the chosen server then sends the HTML, CSS, and Javascript files (If any) back to the OS who in turn gives it to the browser to interpret it. And then you get your website as you 
  know it.

# What are Relational Databases ?

Relational databases are a type of database that organizes data into tables (also known as relations) with rows and columns. Each table stores data about a specific entity, and relationships between these tables are established through keys.

![RelationalDB](https://github.com/user-attachments/assets/e56481f8-e528-4764-aa89-77853411985c)

**Key Characteristics of Relational Databases:**

1. **Data Organization:**
   Data is stored in tables, where each table represents a specific type of information (e.g., customers, products).
   Rows represent records or individual entries.
   Columns represent attributes or fields of the records.
2. **Keys:**
   
   **Primary Key:** A unique identifier for each row in a table.
   
   **Foreign Key:** A field in one table that refers to the primary key in another table, establishing a relationship.
   
   **Schema:** Relational databases follow a well-defined structure or schema that specifies how tables are related and the types of data stored.
4. **SQL (Structured Query Language):**
   Used for querying and manipulating data in relational databases.
5. **Data Integrity:**
   Ensured through constraints such as primary keys, foreign keys, and rules to maintain consistency and accuracy.
   
**Advantages:**
   - Data Accuracy and Consistency: Enforced through schema and constraints.
   - Flexibility: Easy to update, delete, and query data.
   - Scalability: Supports large-scale data management.
   - Relationships: Enables complex queries across related tables.
   
**Examples of Relational Database Management Systems (RDBMS):**
   - MySQL
   - PostgreSQL
   - Oracle Database
   - Microsoft SQL Server
   - SQLite

# What are database Indexes ?

A database index is a data structure that improves the speed of data retrieval operations on a database table. Think of it as a lookup mechanism that allows the database to find rows more quickly, similar to an index in a book that helps you locate specific content.

## Key Concepts of Database Indexes:

- **Structure:**

   Typically implemented as a balanced tree (e.g., B-Tree) or hash table.
   Stores a mapping between the indexed column(s) and the locations of the corresponding rows in the table.
   
- **Indexed Columns:**

   An index is created on one or more columns of a table. These columns are used frequently in search queries or sorting.

- **Types of Indexes:**

   - Primary Index: Automatically created on the primary key of a table.
   - Unique Index: Ensures all values in the indexed column(s) are unique.
   - Clustered Index: Reorganizes the table's data to match the index, resulting in faster access but limited to one per table.
   - Non-clustered Index: Points to the actual data rather than reorganizing it. Multiple non-clustered indexes can exist on a table.
   - Composite Index: Includes two or more columns to optimize queries that use all of these columns.
     
## Benefits of Indexes:
   - Faster Data Retrieval: Speeds up SELECT queries, especially for large datasets.
   - Efficient Sorting: Accelerates queries with ORDER BY clauses.
   - Improved Search: Optimizes searches with conditions like WHERE, JOIN, and GROUP BY.

## Drawbacks of Indexes:
   - Storage Overhead: Additional space is needed to store the index structure.
   - Slower Write Operations: INSERT, UPDATE, and DELETE operations can take longer because the index must also be updated.
   - Maintenance: Indexes require maintenance and recalibration as the data changes.


# NoSQL Databases

A **NoSQL database** is a type of database designed to handle large volumes of unstructured or semi-structured data that doesn't fit neatly into the tabular rows and columns of traditional relational databases. **NoSQL** stands for "Not Only SQL," indicating that it offers flexible alternatives to the structured query language used in relational databases.

---

## Key Characteristics of NoSQL Databases

### Flexible Data Models
- Supports data types like JSON, key-value pairs, documents, graphs, and wide-column structures.
- Schema-less or dynamic schemas allow for easy adjustments as data needs evolve.

### Horizontal Scalability
- Can distribute data across multiple servers (nodes) easily, making them ideal for handling massive datasets and high traffic.

### High Performance
- Optimized for specific use cases such as real-time applications, caching, and analytics.

### Variety of Data Types
- Can store complex, hierarchical, or irregularly structured data efficiently.

### Eventual Consistency (in some systems)
- Prioritizes availability and scalability over strict ACID compliance (Atomicity, Consistency, Isolation, Durability).

---

## Types of NoSQL Databases

### Key-Value Stores
- **Description**: Store data as key-value pairs.
- **Examples**: Redis, Amazon DynamoDB.
- **Use Case**: Caching, session management.

### Document Stores
- **Description**: Store data as documents (e.g., JSON, BSON).
- **Examples**: MongoDB, CouchDB.
- **Use Case**: Content management systems, catalogs.

### Wide-Column Stores
- **Description**: Organize data into rows and dynamic columns.
- **Examples**: Apache Cassandra, HBase.
- **Use Case**: Analytics, logging.

### Graph Databases
- **Description**: Store data as nodes and relationships (edges).
- **Examples**: Neo4j, Amazon Neptune.
- **Use Case**: Social networks, recommendation engines.

---

## Advantages of NoSQL Databases

- **Flexibility**: Schema-less design allows for rapid changes in data models.
- **Scalability**: Horizontal scaling makes them suitable for distributed systems.
- **Speed**: Optimized for specific queries, reducing latency.
- **Big Data Handling**: Efficiently manages vast amounts of data.

---

## Drawbacks of NoSQL Databases

- **Lack of Standardization**: No unified query language like SQL.
- **Limited ACID Transactions**: Many prioritize eventual consistency over strict transactional integrity.
- **Learning Curve**: Requires understanding specific database types and their query methods.

---

## Examples of NoSQL Databases

1. **MongoDB**: A document store known for its flexibility and JSON-like data model.
2. **Cassandra**: A wide-column store optimized for write-heavy applications.
3. **Redis**: A key-value store used for caching and real-time applications.
4. **Neo4j**: A graph database for analyzing relationships in data.

---

NoSQL databases are particularly suited for modern applications that require flexibility, scalability, and efficient handling of diverse data types.

# What is Cache Memory ?

![Cache](https://github.com/user-attachments/assets/51046b0e-4953-4688-9dc8-66ce3429df11)



