# Wishlist Warden

## Description

Wishlist Warden is an App which enables a user to monitor the price and availability for a list of items.

## Application Requirements

- Users will be able to login to the App in order to...
  - Perform CRUD operations to their wishlist
    - Add items
    - Remove items
    - Update items
    - View wishlist items and details
      - Current Price
      - Price History
      - Current Availability
      - Historical Availability
  - Setup notifications for individual items or a group of items
    - Notifications for when an item goes back in stock
    - Notifications for when an item's price drops (can be user-specified)
    - Notification method (Email / SMS / Push) TBD

## Architecture

The architecture will be based on microservices

### Microservices Components

- Web Scraper Microservice: Responsible for scraping website data and extracting relevant item info on price and availability.
- Monitoring Microservice: Responsible for monitoring changes in item prices and availability.
- Notification Microservice: Responsible for sending notifications to users.
- Authentication / Authorization Microservice: Manages user authentication and authorization for accessing APIs and data
- API Gateway Microservice: Acts as a single entry point for clients to interact with the application's APIs
- Logging Microservice: Provides centralized logging used by all microservices in the App
- Database Microservice: Handles storing and retrieving data from the database. QUESTION: IS IT BETTER FOR EACH MICROSERVICE TO HAVE ITS OWN DATA STORE INSTEAD OF A CENTRALIZED DATA STORE?

### Containerization with Docker

Each microservice will be encapsulated by a Docker Container.

### Microservice Communications

Communication between micro-services can be accomplished via:
- HTTP/REST
- gRPC
- Message Queues (Apache Kafka)

### Load Balancing / Scaling

Load balancing may be implemented in order to enable distribution of incoming requests across multiple instances of microservices.

### Caching

Caching mechanisms (such as Redis) can be used to store frequently accessed data, reducing the load on the database

### Monitoring / Logging

Monitoring tools (such as Prometheus and Grafana) may be used to track the performance and health of microservices.

A centralized logging system may be implemented to help with debugging and issue resolution.

### Deployment and Orchestration

Container orchestration via Kubernetes can be used to manage the deployment, scaling and availability of microservices.
