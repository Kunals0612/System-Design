# What is Load Balancing ?

A load balancer is a crucial component in system design that distributes incoming network traffic across multiple servers. Its main purpose is to ensure that no single server is overburdened with too many requests, which helps improve the performance, reliability, and availability of applications.

![LoadBalancer](https://github.com/user-attachments/assets/cc8a171f-8075-4d8b-9f33-31f2bfe0f79b)

Load balancers are highly used in cloud computing domains, data centers, and large-scale web applications where traffic flow needs to be managed.
It simply distributes the set of requested operations effectively across multiple servers and ensures that no single server bears too many requests.

## How Load Balancer Works?

Let us see how a load balancer works in simple steps:

1. **Receives Incoming Requests:** When users try to access a website or application, their requests first go to the load balancer instead of directly to a server.
2. **Checks Server Health:** The load balancer continuously monitors the status of all servers. It checks which servers are healthy and ready to handle requests.
3. **Distributes Traffic:** Based on factors like server load, response time, or proximity, the load balancer forwards each request to the most appropriate server. This helps avoid any server getting overloaded.
4. **Handles Server Failures:** If a server goes down or becomes unresponsive, the load balancer automatically stops sending traffic to that server and redirects it to others that are still functioning properly.
5. **Optimizes Performance:** By spreading traffic efficiently and using healthy servers, load balancers improve overall performance and reduce delays.

## What will happen if there is NO Load Balancer?

![NoBalancer](https://github.com/user-attachments/assets/8347ac6d-acbe-4737-a279-640c29a368eb)

### **There are three main problems with this model:**

**Single Point of Failure:**

If the server goes down or something happens to the server the whole application will be interrupted and it will become unavailable for the users for a certain period. It will create a bad experience for users which is unacceptable for service providers.

**Overloaded Servers:** 

There will be a limitation on the number of requests that a web server can handle. If the business grows and the number of requests increases the server will be overloaded.

**Limited Scalability:**

Without a load balancer, adding more servers to share the traffic is complicated. All requests are stuck with one server, and adding new servers won’t automatically solve the load issue.

![WithLoadBalancer](https://github.com/user-attachments/assets/7364b7d8-0650-4b36-8b97-68566f86def5)

Below are some of the key characteristics of Load Balancers:

1. **Traffic Distribution:** To keep any one server from becoming overburdened, load balancers divide incoming requests evenly among several servers.
2. **High Availability:** Applications’ reliability and availability are improved by load balancers, which divide traffic among several servers. The load balancer reroutes traffic to servers that are in good condition in the event that one fails.
3. **Scalability:** By making it simple to add servers or resources to meet growing traffic demands, load balancers enable horizontal scaling.
4. **Optimization:** Load balancers optimize resource utilization, ensuring efficient use of server capacity and preventing bottlenecks.
5. **Health Monitoring:** Load balancers often monitor the health of servers, directing traffic away from servers experiencing issues or downtime.
6. **SSL Termination:** Some load balancers can handle SSL/TLS encryption and decryption, offloading this resource-intensive task from servers.

## Key Features
- **Traffic Distribution:** Balances incoming requests across multiple servers using efficient algorithms.
- **Fault Tolerance:** Automatically redirects traffic to healthy servers in case of server failure.
- **Scalability:** Allows seamless scaling of applications by adding or removing servers.
- **Improved Performance:** Reduces latency by routing traffic to servers with less load.
- **Health Monitoring:** Continuously checks the status of servers to ensure only healthy ones receive traffic.
- **SSL Termination:** Offloads SSL/TLS decryption from backend servers, improving their efficiency.

## Types of Load Balancers
1. **Hardware Load Balancers:** Physical devices that provide high-performance traffic distribution (e.g., F5, Citrix).
2. **Software Load Balancers:** Applications installed on servers (e.g., HAProxy, Nginx, Apache).
3. **Cloud-based Load Balancers:** Managed services provided by cloud providers (e.g., AWS Elastic Load Balancer, Google Cloud Load Balancer).

## Load Balancing Algorithms

We need a load-balancing algorithm to decide which request should be redirected to which backend server. Different systems use different ways to select the servers from the load balancer. Companies use a variety of load-balancing algorithm techniques depending on the configuration. Load balancing algorithms can be broadly categorized into two types: **Static Load Balancing** and **Dynamic Load Balancing**.

### 1. Static Load Balancing Algorithms
Static load balancing involves predetermined assignment of tasks or resources without considering real-time variations in the system. This approach relies on a fixed allocation of workloads to servers or resources, and it doesn’t adapt to changes during runtime.

**Types of Static Load Balancing Algorithms:**
- **Round Robin:** Distributes requests sequentially across servers.
- **Weighted Round-Robin:** Assigns requests to servers based on predefined weights.
- **Source IP Hash:** Uses a hash of the client’s IP address to determine the server.

### 2. Dynamic Load Balancing Algorithms
Dynamic load balancing involves making real-time decisions regarding the distribution of incoming network traffic or computing burden among several servers or resources. This method adjusts to the system’s shifting circumstances, including changes in resource availability, network traffic, and server load.

**Types of Dynamic Load Balancing Algorithms:**
- **Least Connection Method:** Sends requests to the server with the fewest active connections.
- **Least Response Time Method:** Routes requests to the server with the fastest response time.

## Round Robin Algorithm: 

![RoundRobin](https://github.com/user-attachments/assets/8ac10653-86fa-4ecb-b64d-7922a9840560)

## Weighted Round Robin:

![weighted](https://github.com/user-attachments/assets/0211cc73-54c4-4aca-ba14-16a689e36ab3)

## Source IP Hash Based Algorithm:

![HashIP](https://github.com/user-attachments/assets/480a023e-1b90-4a94-9b36-5147d79d48aa)

## Least Connection Based Algorithm:

![LeastConnection](https://github.com/user-attachments/assets/5cfe098c-5ce9-4802-b3bd-8bf84eea4c6c)

## Least Response Time Based Algorithm: 

![LeastResponseTime ](https://github.com/user-attachments/assets/6ed153dc-4a45-4377-a4f5-1d89b0fcba17)

# Consistent Hashing

Consistent hashing is a distributed hashing technique used in computer science and distributed systems to achieve load balancing and minimize the need for rehashing when the number of nodes in a system changes. It is particularly useful in distributed hash tables (DHTs), distributed caching systems, and other distributed storage systems.

![ConsistentHashing](https://github.com/user-attachments/assets/2d7ef2c7-e825-4bc0-8c0a-a97aa581edfa)

### **What is the use of Consistent Hashing?**

Consistent hashing is a popular technique used in distributed systems to address the challenge of efficiently distributing keys or data elements across multiple nodes/servers in a network. Consistent hashing’s primary objective is to reduce the number of remapping operations necessary when adding or removing nodes from the network, which contributes to the stability and dependability of the system.

- Consistent hashing can be used in to share the burden among nodes and lessen the effects of node failures.
- For example, when a new node is added to the network, only a small number of keys are remapped to the new node, which helps to reduce the overhead associated with the addition.
- Similarly, when a node fails, only a small number of keys are affected, which helps to minimize the impact of the failure on the system as a whole.  
- Consistent hashing is also useful in ensuring data availability and consistency in a distributed system.

## After Failure of any server

![ConsistentHashingRemoving](https://github.com/user-attachments/assets/60a377b4-eebb-4a59-b076-7354b12149a2)

## To Reduce the ReHashing (Replica Server)

![ReplicaServer](https://github.com/user-attachments/assets/eff26ca7-62e5-41c9-b2d6-61d194b3241b)

## After removing server

![ReplicaServerRemoving](https://github.com/user-attachments/assets/d2d7892e-11d2-497a-aaad-d5e00d8f3ed1)


# What is Sharding ?

Sharding is a very important concept that helps the system to keep data in different resources according to the sharding process. The word “Shard” means “a small part of a whole“. Hence Sharding means dividing a larger part into smaller parts. In DBMS, Sharding is a type of DataBase partitioning in which a large database is divided or partitioned into smaller data and different nodes. These shards are not only smaller, but also faster and hence easily manageable. 

![sharding](https://github.com/user-attachments/assets/b5d1b1a0-234d-4742-84ad-783bd429cc42)

## **Features of Sharding:**

  - Sharding makes the Database smaller
  - Sharding makes the Database faster
  - Sharding makes the Database much more easily manageable
  - Sharding can be a complex operation sometimes
  - Sharding reduces the transaction cost of the Database
  - Each shard reads and writes its own data.
  - Many NoSQL databases offer auto-sharding.
  - Failure of one shard doesn’t effect the data processing of other shards.

## **Benefits of Sharding:**
- **Improved Scalability:** Sharding allows the system to scale horizontally by adding more servers or nodes as the data grows. This improves the system’s capacity to handle large volumes of data and requests.
- **Increased Performance:** Sharding distributes the data across multiple servers or nodes, which improves the system’s performance by reducing the load on each server or node. This results in faster response times and better throughput.
- **Fault Tolerance:** Sharding provides a degree of fault tolerance as the system can continue to function even if one or more servers or nodes fail. This is because the data is replicated across multiple servers or nodes, and if one        fails, the others can continue to serve the requests.
- **Reduced Costs:** Sharding allows the system to scale horizontally, which can be more cost-effective than scaling vertically by upgrading hardware. This is because horizontal scaling can be done using commodity hardware, which is          typically less expensive than high-end servers.

# Key-Based Sharding

**Key-based sharding**, also known as **hash-based sharding**, is a technique used to distribute data across multiple shards (or partitions) in a database or distributed system. It ensures efficient and predictable data distribution based on a hash value derived from a key.

---

## How It Works

1. **Key Selection**:
   - Each record or piece of data has a key (e.g., user ID, product ID).
   - This key uniquely identifies the data.

2. **Hash Function**:
   - A hash function is applied to the key to generate a numeric value (hash value).
   - Common hash functions include MD5, SHA-256, or simpler functions like modulo arithmetic.

3. **Shard Assignment**:
   - The hash value is used to determine which shard the data should be stored in.  
   - For example:
     ```
     Shard Index = (Hash(Key) % Number of Shards)
     ```

4. **Data Storage and Retrieval**:
   - The calculated shard index points to a specific shard where the data is stored.
   - To retrieve data, the same hash function is applied to the key, and the corresponding shard is queried.

---

## Advantages

- **Even Distribution**: Ensures data is evenly distributed across shards, minimizing hotspots.
- **Scalability**: Shards can be located on different servers, allowing horizontal scaling.
- **Quick Lookup**: Efficient computation of shard index using the hash function.
- **Deterministic**: Guarantees that the same key will always map to the same shard.

---

## Challenges

- **Resharding**: Adding or removing shards requires rehashing, which can be resource-intensive.
- **Hash Collisions**: Rare with good hash functions but must be handled appropriately.
- **Uneven Key Distribution**: Poorly designed hash functions or key distributions can lead to imbalances.
- **Join Queries**: Performing cross-shard queries (e.g., joins) can be complex and slower.

---

## Applications

- **Databases**: Distributed systems like MongoDB, Cassandra, and DynamoDB.
- **Caching Systems**: Systems like Redis and Memcached.
- **Large-scale Applications**: Social networks, e-commerce platforms, etc.

---

## Example

Imagine you have **4 shards** (Shard 0 to Shard 3) and want to store data for `UserID = 12345`.

1. Apply the hash function:
2. Calculate the shard index:
3. Store the data in **Shard 2**.

For retrieval, the same process maps `UserID = 12345` to **Shard 2**.

---

# Range-Based Sharding

**Range-based sharding** is a data distribution technique in which data is divided across multiple shards (or partitions) based on the value of a key. The key values are grouped into predefined ranges, and each range is assigned to a specific shard.

---

## How It Works

1. **Key Selection**:
   - A key (e.g., user ID, date, product price) is chosen to partition the data.
   - This key is used to determine which shard the data belongs to.

2. **Define Ranges**:
   - The key space is divided into non-overlapping ranges.
   - Each range is assigned to a specific shard.

3. **Shard Assignment**:
   - When inserting or querying data, the key's value is checked against the defined ranges to determine the appropriate shard.

---

## Example

Imagine we are sharding data for a database storing user information, with user IDs ranging from `1` to `1000`. The ranges and shard assignments could look like this:

| Range       | Shard    |
|-------------|----------|
| 1 - 250     | Shard 0  |
| 251 - 500   | Shard 1  |
| 501 - 750   | Shard 2  |
| 751 - 1000  | Shard 3  |

### Data Insert Example:
- For `UserID = 345`:  
  - `345` falls in the range `251 - 500`, so the data is stored in **Shard 1**.

### Data Retrieval Example:
- To retrieve `UserID = 800`:  
  - `800` falls in the range `751 - 1000`, so the data is retrieved from **Shard 3**.

---

## Advantages

- **Simplicity**:
  - Easy to implement and understand.
  - Efficient when the key distribution is uniform and ranges are well-balanced.

- **Predictability**:
  - Knowing the key's range allows direct access to the appropriate shard.

---

## Challenges

- **Imbalanced Shards**:
  - If the key distribution is skewed, some shards may hold more data than others, causing hotspots.

- **Range Overlaps**:
  - Incorrect range definitions or key assignments can lead to overlaps or gaps.

- **Scalability**:
  - Adding new shards requires redefining ranges and redistributing data, which can be resource-intensive.

---

## Applications

- **Time-series Data**: Storing logs or events where the key is a timestamp (e.g., ranges based on months or years).
- **Financial Data**: Dividing data based on numeric ranges, like customer IDs or account numbers.
- **E-commerce**: Partitioning data by product price ranges or order IDs.

---

## Example Use Case

Suppose an e-commerce platform uses **Range-Based Sharding** to store product prices:

| Price Range ($) | Shard    |
|------------------|----------|
| 0 - 100          | Shard 0  |
| 101 - 500        | Shard 1  |
| 501 - 1000       | Shard 2  |
| 1001+            | Shard 3  |

- **Insert Product**:  
  A product priced at `$750` will be stored in **Shard 2**.

- **Query Product**:  
  To find products in the `$101 - $500` range, the query is sent to **Shard 1**.

---

# Directory-Based Sharding

**Directory-based sharding** is a sharding technique where a central directory maps keys (or key ranges) to specific shards. This directory acts as an intermediary that helps determine the shard where a particular piece of data resides.

---

## How It Works

1. **Central Directory**:
   - A central lookup table (directory) maintains mappings of keys or key ranges to shards.
   - Example: `Key → Shard` or `Range → Shard`.

2. **Shard Assignment**:
   - When data needs to be stored or retrieved, the directory is consulted to identify the correct shard.

3. **Data Storage and Retrieval**:
   - The directory guides operations like insertion, update, and retrieval by directing requests to the appropriate shard.

---

## Example

Imagine a system storing data for user accounts. The central directory contains the following mappings:

| Key/Range        | Shard    |
|-------------------|----------|
| 1 - 1000          | Shard 0  |
| 1001 - 2000       | Shard 1  |
| 2001 - 3000       | Shard 2  |
| 3001 - 4000       | Shard 3  |

### Data Insert Example:
- For `UserID = 2345`:  
  - The directory maps the range `2001 - 3000` to **Shard 2**.  
  - Data is stored in **Shard 2**.

### Data Retrieval Example:
- To retrieve `UserID = 950`:  
  - The directory maps the range `1 - 1000` to **Shard 0**.  
  - Data is retrieved from **Shard 0**.

---

## Advantages

- **Flexibility**:
  - The directory allows custom and dynamic shard assignments, unlike rigid methods like key-based or range-based sharding.

- **Easily Scalable**:
  - Adding or removing shards is straightforward; the directory is updated to reflect new mappings.

- **Handles Complex Distributions**:
  - Useful when keys or data distribution is irregular or uneven.

---

## Challenges

- **Single Point of Failure**:
  - The central directory becomes a critical component; its failure can disrupt the entire system.

- **Performance Overhead**:
  - Frequent lookups to the directory may introduce latency.

- **Directory Maintenance**:
  - Keeping the directory updated and consistent requires effort, especially in dynamic environments.

---

## Applications

- **Dynamic Systems**: Systems where data distribution changes frequently.
- **Irregular Distributions**: Scenarios where keys or ranges are not uniformly distributed.
- **Complex Partitioning Rules**: Systems with customized sharding rules based on data characteristics.

---

## Example Use Case

Imagine a global content delivery platform where shards are located in different regions:

| Region           | Shard    |
|-------------------|----------|
| North America     | Shard 0  |
| Europe            | Shard 1  |
| Asia              | Shard 2  |
| Australia         | Shard 3  |

- **Insert Data**:  
  A user from **Asia** is assigned to **Shard 2** based on the directory.

- **Retrieve Data**:  
  A lookup for a user in **Europe** consults the directory, which directs the query to **Shard 1**.

---

# Directory-Based Sharding

## Overview
**Directory-Based Sharding** provides flexibility by allowing custom mappings between data and shards based on the characteristics of the data. It can dynamically handle uneven data distributions, which is a significant advantage when compared to other sharding methods like **Key-Based** or **Range-Based** sharding.

## Key Features of Directory-Based Sharding That Provide Flexibility

### 1. Custom Shard Mapping:
With **Directory-Based Sharding**, you can map data to shards based on any attribute or characteristic of the data (e.g., user location, product category, customer tier).  
Unlike **Key-Based Sharding**, which uses a hashing function that doesn’t account for data characteristics, or **Range-Based Sharding**, which splits data into fixed ranges, **Directory-Based Sharding** allows the assignment of shards based on the actual data distribution patterns. This means you can allocate resources where they are needed most.

### 2. Dynamic Data Rebalancing:
As the data grows and changes, the directory can be updated to redistribute the load dynamically. If a particular shard is experiencing a disproportionate load, you can shift some data to other shards by updating the directory.  
This is particularly useful for handling uneven distributions, such as when some regions (e.g., North America) have more users than others (e.g., Asia). The system can map those high-demand regions to multiple shards, balancing the load effectively.

### 3. Tailored Shard Allocation:
**Directory-Based Sharding** allows you to allocate multiple shards to a particular data set based on its need. For example, if you have a large number of users in **North America**, the directory can map them to several shards (instead of just one shard). Similarly, if **Asia** has fewer users, they can all fit within a single shard.  
You can even combine different data attributes. For instance, a user might be assigned to a particular shard based on both **region** and **age group**, ensuring even distribution and better load balancing.

### 4. Avoiding Hotspots:
A common issue with **Key-Based Sharding** is hotspots, where data is hashed in such a way that some shards become overloaded (e.g., if a large number of users are concentrated in one geographical area).  
With **Directory-Based Sharding**, you can manually assign regions or user types to different shards, avoiding hotspots. For example, rather than letting users from all regions be hashed randomly to any shard, you could directly assign all **North American** users to a specific set of shards with high resource capacity.

### 5. Custom Load Balancing:
The directory can be updated in real-time to ensure that the system is always optimally balanced. If one shard starts receiving too much traffic (e.g., due to increased users from a particular region), the directory can be adjusted to distribute some of the data to other, less-loaded shards. This flexibility in load balancing ensures that all shards are used efficiently.

## Example: Geographical Distribution of Users

Let’s say a system is sharding **user data** based on **geography**, but users are unevenly distributed across regions:

- **North America**: High number of users.
- **Europe**: Moderate number of users.
- **Asia**: Low number of users.

### How Directory-Based Sharding Handles This:
1. **Custom Mapping**:
   - The directory can map users from **North America** to multiple shards (say Shard 0 and Shard 1) because there are a lot of them.
   - It can map **Europe** to **Shard 2**, as the user base is smaller.
   - It can assign **Asia** to **Shard 3**, since there are fewer users from this region.

   **Directory Example**:
   - **North America** → Shard 0, Shard 1
   - **Europe** → Shard 2
   - **Asia** → Shard 3

2. **Rebalancing**:
   - As the number of users in **Asia** grows over time, the directory can **reassign** users to different shards, such as mapping them to an additional shard (**Shard 4**) if needed.
   - If **North America's** user base decreases, the directory can **reduce** the number of shards allocated to that region.

3. **Dynamic Shard Addition**:
   - If there is a sudden influx of users in one region (e.g., **North America**), the directory allows for **scalability** by dynamically adding more shards dedicated to **North America**, thus avoiding overloading a single shard. This process is seamless and controlled without the need to change the entire sharding architecture.

## Comparison with Other Sharding Techniques

### Key-Based Sharding:
- **Hashing**: In **Key-Based Sharding**, the data is hashed and mapped to shards. This method doesn’t consider the underlying data distribution, so if one region has a large number of users, it could overload a single shard.
- **No Flexibility**: There’s no way to optimize or tailor the mapping based on the data’s nature (like geography). All users are treated the same, and the system might face performance bottlenecks due to uneven distributions.

### Range-Based Sharding:
- **Fixed Ranges**: With **Range-Based Sharding**, data is divided into fixed ranges. For example, users with IDs in the range `1-1000` are mapped to **Shard 0**, `1001-2000` to **Shard 1**, and so on. This can lead to uneven data distribution, especially when the distribution of user IDs doesn’t match the actual regional distribution of users.
- **Rebalancing Challenges**: Rebalancing can be difficult when the ranges become skewed, causing some shards to be overloaded while others remain underutilized.

## Conclusion: Why Directory-Based Sharding is Better for Uneven Data Distribution

- **Flexibility in Data Distribution**: You can map data to shards based on specific criteria, such as **geographical regions**, allowing more effective handling of uneven data distributions.
- **Avoid Hotspots and Overloading**: **Directory-Based Sharding** allows you to dynamically allocate resources to regions or user groups that need them most, ensuring **load balancing** across the system and avoiding hotspots.
- **Dynamic Rebalancing**: As data distribution changes over time (e.g., more users from Asia), the directory can be updated to rebalance the system without the need for drastic changes or data migrations.

By allowing this level of **customization** and **real-time management**, **Directory-Based Sharding** provides the most flexibility for handling uneven data distributions compared to other techniques.


