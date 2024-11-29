# What is an API?

API stands for **Application Programming Interface**. It is a set of rules and protocols that allow different software applications to communicate with each other. APIs act as intermediaries between different systems, enabling them to exchange data or perform operations without knowing each other's internal details.

## **Types of APIs**
1. **Web APIs**: Communicate over HTTP/HTTPS (e.g., REST, GraphQL, SOAP).
2. **Library APIs**: Provide access to specific functionality in a library or framework.
3. **Operating System APIs**: Allow interaction with OS features.
4. **Hardware APIs**: Facilitate communication between hardware and software.

### **Examples**
- **Google Maps API**: Used to integrate maps into applications.
- **Twitter API**: Allows developers to interact with Twitter data.

---

# How to Design an API

Designing a robust API involves a systematic approach to ensure usability, scalability, and maintainability.

---

## **1. Understand the Requirements**
- Define the purpose of the API.
- Identify the target users (developers, applications, etc.).
- Determine the data and functionality to be exposed.

---

## **2. Choose the API Type**
- **REST**: Simple, stateless, resource-based (most popular).
- **GraphQL**: Flexible querying and fetching of data.
- **SOAP**: Protocol-based, suitable for enterprise-level security.

---

## **3. Design Resources and Endpoints**
- **Identify Resources**: Think of the entities (e.g., `Users`, `Orders`, `Products`) as resources.
- **Define Endpoints**: Use meaningful URLs.
  - Example:
    - `GET /users` → Fetch a list of users.
    - `POST /users` → Create a new user.
    - `GET /users/{id}` → Fetch details of a specific user.

---

## **4. Use HTTP Methods Correctly**
- **GET**: Retrieve data.
- **POST**: Create new resources.
- **PUT**: Update existing resources.
- **DELETE**: Remove resources.

---

## **5. Structure API Responses**
- **Use JSON or XML**: JSON is the most common format.
- **Standardized Response**:
  ```json
  {
    "status": "success",
    "data": {
      "id": 1,
      "name": "John Doe"
    }
  }
```
