# Key Concepts in System Design and Databases

## Pull vs. Push

### **Pull**
- **Definition**: In the pull model, the client requests data from the server when it needs it.
- **Example**: A client polls an API at regular intervals for new data.
- **Use Case**: Ideal for scenarios where the client needs to actively request updates (e.g., checking for new emails).

### **Push**
- **Definition**: In the push model, the server sends data to the client as soon as new information is available, without the client needing to request it.
- **Example**: Real-time notifications or live data feeds.
- **Use Case**: Suitable for real-time applications like messaging or stock trading.

---

## Memory vs. Latency

### **Memory**
- **Definition**: Refers to the amount of data that can be stored and accessed rapidly by the system. It is usually associated with **RAM** (Random Access Memory).
- **Performance**: More memory allows a system to handle larger amounts of data quickly, improving performance.

### **Latency**
- **Definition**: The time it takes for data to travel between two points in a system, often measured as the delay between a request and the response.
- **Performance**: Lower latency is crucial for real-time applications (e.g., video streaming, gaming).

### Key Difference:
- **Memory** affects how much data can be processed in parallel, while **latency** impacts how quickly data can be accessed or transmitted.

---

## Throughput vs. Latency

### **Throughput**
- **Definition**: The amount of data processed in a given period (e.g., requests per second, bandwidth).
- **Performance**: Higher throughput is essential for systems that need to process large volumes of data (e.g., large-scale data pipelines, high-traffic websites).

### **Latency**
- **Definition**: The delay in processing a single request.
- **Performance**: Low latency is critical for tasks where quick responses are necessary (e.g., online gaming, financial trading).

### Key Difference:
- **Throughput** measures the system's capacity to handle data, while **latency** focuses on how fast a single transaction or request is processed.

---

## Consistency vs. Availability (CAP Theorem)

### **Consistency**
- **Definition**: Every read operation will return the most recent write. All nodes in a distributed system reflect the same data at any given time.
- **Use Case**: Used when it’s critical that all data copies are up-to-date and synchronized (e.g., bank transactions).

### **Availability**
- **Definition**: Every request to the system will receive a response, either with the requested data or an error message, even if some of the data may be out of sync.
- **Use Case**: Used in systems where it’s more important for the system to always be responsive (e.g., e-commerce sites).

### CAP Theorem:
- A distributed system can only guarantee two out of three properties: **Consistency, Availability, and Partition Tolerance**. You can’t have all three at the same time in the presence of network partitions.

---

## Latency vs. Accuracy

### **Latency**
- **Definition**: The delay between initiating a request and receiving the response. 
- **Trade-off**: Lower latency improves system responsiveness but might sometimes sacrifice processing complexity or accuracy.

### **Accuracy**
- **Definition**: How correct or precise the system’s outputs are.
- **Trade-off**: Achieving high accuracy can introduce delays due to more complex computations or checks.

### Key Trade-off:
- Reducing **latency** may lead to quicker results but potentially lower **accuracy** (e.g., approximations or shortcuts in computation). Conversely, higher **accuracy** may result in longer processing times.

---

## SQL vs. NoSQL Databases

### **SQL Databases**
- **Definition**: Structured Query Language (SQL) databases store data in a predefined schema (tables with rows and columns).
- **Features**:
  - **ACID** (Atomicity, Consistency, Isolation, Durability) compliance.
  - Ideal for complex queries, transactional systems, and relational data.
  - Examples: MySQL, PostgreSQL, Oracle.

### **NoSQL Databases**
- **Definition**: Not Only SQL (NoSQL) databases are designed for unstructured data and can store data in key-value pairs, documents, graphs, or columns.
- **Features**:
  - **Eventual consistency** (rather than strict ACID).
  - Designed for scalability, high throughput, and flexibility with large volumes of data.
  - Ideal for big data, real-time applications, and semi-structured data.
  - Examples: MongoDB, Cassandra, Redis.

### Key Differences:
- **SQL** is better for complex relationships and structured data, while **NoSQL** is optimized for scalability, flexibility, and handling large volumes of unstructured or semi-structured data.
