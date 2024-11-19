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





