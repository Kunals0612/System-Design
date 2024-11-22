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


