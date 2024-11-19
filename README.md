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




