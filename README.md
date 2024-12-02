# Microservices Application with Spring Boot

This repository contains a microservices-based application developed using Spring Boot. The application is designed with multiple independent services, an API gateway, and support for distributed tracing and service discovery.

---

## 🏗️ Architecture Overview

The microservices architecture comprises the following components:

- **API Gateway**: Acts as an entry point to route requests to appropriate microservices.
- **Config Server**: Centralized configuration management for all microservices.
- **Eureka Server**: Service discovery for microservices.
- **Eureka Clients**:
  - `Department Service`: Manages department-related information.
  - `Employee Service`: Manages employee-related information.
  - `Other Service`: [Description of the functionality for the service.]
- **Zipkin**: Distributed tracing for monitoring and debugging across services.
- **Registry**: Centralized service registry for managing microservices.

---

## 📋 Prerequisites

Before running this application, ensure you have the following installed:

- [Java 17+](https://www.oracle.com/java/technologies/javase-jdk17-downloads.html)
- [Maven 3.8+](https://maven.apache.org/)
- [Docker](https://www.docker.com/) (optional, for containerized deployment)
- [Postman](https://www.postman.com/) or any API testing tool for testing the endpoints.

---

## 🚀 Getting Started

### Clone the Repository

```bash
git clone https://github.com/<your-username>/<repository-name>.git
cd <repository-name>
```

### Build the Project

```bash
mvn clean install
```

### Start the Services

Start the services in the following order to ensure proper initialization:

1. **Config Server**:
   ```bash
   cd config-server
   mvn spring-boot:run
   ```

2. **Eureka Server**:
   ```bash
   cd eureka-server
   mvn spring-boot:run
   ```

3. **API Gateway**:
   ```bash
   cd api-gateway
   mvn spring-boot:run
   ```

4. **Microservices**:
    - Department Service
    - Employee Service
    - Other Service
      Each can be started using:
   ```bash
   cd <service-folder>
   mvn spring-boot:run
   ```

5. **Zipkin**:
   Run the Zipkin server. If you have Docker installed, you can use the official Zipkin image:
   ```bash
   docker run -d -p 9411:9411 openzipkin/zipkin
   ```

---

## 🛠️ Features

### 1. **API Gateway**
- Routes incoming requests to the appropriate microservice.
- Handles authentication and rate-limiting (optional).

### 2. **Config Server**
- Centralized configuration management.
- Fetches configuration files from a Git repository.

### 3. **Eureka Server**
- Service discovery for microservices.
- Dynamic registration and deregistration of services.

### 4. **Microservices**
- **Department Service**: CRUD operations for departments.
- **Employee Service**: CRUD operations for employees.
- **Other Service**: [Define functionality].

### 5. **Distributed Tracing**
- Zipkin integration for end-to-end tracing of requests.

---

## 📊 Monitoring and Tracing

### Access Eureka Dashboard
- URL: `http://localhost:<eureka-server-port>`

### Access Zipkin Dashboard
- URL: `http://localhost:9411`

---

## 📂 Directory Structure

```plaintext
.
├── api-gateway/
├── config-server/
├── eureka-server/
├── department-service/
├── employee-service/
├── other-service/
├── README.md
```

---

## 📜 API Endpoints

| Service           | Endpoint                         | Method | Description                  |
|--------------------|----------------------------------|--------|------------------------------|
| **Department**     | `/api/departments`              | GET    | Get all departments          |
|                    | `/api/departments/{id}`         | GET    | Get department by ID         |
|                    | `/api/departments`              | POST   | Create a new department      |
|                    | `/api/departments/{id}`         | PUT    | Update department details    |
|                    | `/api/departments/{id}`         | DELETE | Delete a department          |
| **Employee**       | `/api/employees`                | GET    | Get all employees            |
|                    | `/api/employees/{id}`           | GET    | Get employee by ID           |
|                    | `/api/employees`                | POST   | Create a new employee        |
|                    | `/api/employees/{id}`           | PUT    | Update employee details      |
|                    | `/api/employees/{id}`           | DELETE | Delete an employee           |

---

## 🤝 Contributing

Contributions are welcome! Please fork the repository and submit a pull request.

1. Fork the repository
2. Create a new branch: `git checkout -b feature-branch-name`
3. Commit your changes: `git commit -m "Add a new feature"`
4. Push to the branch: `git push origin feature-branch-name`
5. Submit a pull request

---

## 📃 License

This project is licensed under the [MIT License](LICENSE).

---
 