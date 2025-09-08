# self-cloud

## 🌎 Overview
**Self-Cloud** is a hobbyist full-stack web app cloud storage platform. This project serves as a benchmark for a long  
journey of learning **SBAC (Scope-Based Access Control)** and experimenting with **cloud-native services**.

**Key Highlights:**  
* 🔐 HTTPS support using self-signed TLS certificates (or proper TLS if you have one)  
* 🗄️ Self-hosted storage, with easy deployability on the cloud (see [Tech Stack](#tech-stack) and [Codebase](#codebase))  
* 🔒 Application authentication powered by Scope-Based Access Control (SBAC)  
* 📊 Dashboard access with API insights, logs, and metrics  

## Codebase
This project includes the full backend, frontend, and deployment configurations required to run Self-Cloud locally or in the cloud.
```
self-cloud
|
|----> backend  # Contain backend microservices code
|      |
|      |----> idp-microservice  # Contain IDP microservice code
|      |----> storage-microservice # Contain Storage API microservice code
|      |----> metrics-service   # Contain metrics dashboard microservice code
|      |----> nginx.conf    # NGINX API Gateway configuration file
|
|----> frontend # Contain forntend code
|----> docker-compose.yaml  # Docker compose manifest
```

## 💻 Tech Stack
* **Backend**
    * **Language**: TypeScript
    * **Libraries**:
        * **`fastify`** - HTTP API server implementation library used by the backend
        * **`@aws-sdk/client-s3`** - AWS Simple Storage Service APIs
        * **`kafkajs`** - Required to produce and consume events and publish to Kafka stream
    * **Docker** – used to deploy all infrastructure resources locally
    * **MinIO** – storage manager, chosen for its native support of AWS S3 APIs
    * **Apache Kafka** - _De facto_ choice when it comes to event streaming and 
* Frontend
    * **Language** TypeScript
    * **Libraries**
        * **React** - Frontend library powering the UI
        * **Axios** - Used by the frontend to communicate with the backend
