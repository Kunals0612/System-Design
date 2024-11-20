# What is Load Balancing ?

A load balancer is a crucial component in system design that distributes incoming network traffic across multiple servers. Its main purpose is to ensure that no single server is overburdened with too many requests, which helps improve the performance, reliability, and availability of applications.

![LoadBalancer](https://github.com/user-attachments/assets/cc8a171f-8075-4d8b-9f33-31f2bfe0f79b)

Load balancers are highly used in cloud computing domains, data centers, and large-scale web applications where traffic flow needs to be managed.
It simply distributes the set of requested operations effectively across multiple servers and ensures that no single server bears too many requests.

## What will happen if there is NO Load Balancer?

![NoBalancer](https://github.com/user-attachments/assets/8347ac6d-acbe-4737-a279-640c29a368eb)

### **There are three main problems with this model:**

**Single Point of Failure:**

If the server goes down or something happens to the server the whole application will be interrupted and it will become unavailable for the users for a certain period. It will create a bad experience for users which is unacceptable for service providers.

**Overloaded Servers:** 

There will be a limitation on the number of requests that a web server can handle. If the business grows and the number of requests increases the server will be overloaded.

**Limited Scalability:**

Without a load balancer, adding more servers to share the traffic is complicated. All requests are stuck with one server, and adding new servers won’t automatically solve the load issue.



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
