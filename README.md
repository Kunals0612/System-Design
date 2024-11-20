# What is Load Balancing ?

A load balancer is a crucial component in system design that distributes incoming network traffic across multiple servers. Its main purpose is to ensure that no single server is overburdened with too many requests, which helps improve the performance, reliability, and availability of applications.

![LoadBalancer](https://github.com/user-attachments/assets/cc8a171f-8075-4d8b-9f33-31f2bfe0f79b)

Load balancers are highly used in cloud computing domains, data centers, and large-scale web applications where traffic flow needs to be managed.
It simply distributes the set of requested operations effectively across multiple servers and ensures that no single server bears too many requests.

## What will happen if there is NO Load Balancer?

There are three main problems with this model:

Single Point of Failure: 
If the server goes down or something happens to the server the whole application will be interrupted and it will become unavailable for the users for a certain period. It will create a bad experience for users which is unacceptable for service providers.
Overloaded Servers: 
There will be a limitation on the number of requests that a web server can handle. If the business grows and the number of requests increases the server will be overloaded.
Limited Scalability:
Without a load balancer, adding more servers to share the traffic is complicated. All requests are stuck with one server, and adding new servers won’t automatically solve the load issue.

