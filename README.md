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

