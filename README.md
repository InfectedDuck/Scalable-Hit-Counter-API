# Hit Counter Service API

A **Flask-based RESTful API** designed to manage named hit counters. This service allows users to create, update, list, and delete counters efficiently. It’s designed with scalability and performance in mind, making it suitable for production-level use cases that require counting services such as analytics, click tracking, or any incremental counter-based system.

## Key Features

- **Robust REST API:** Supports CRUD operations for hit counters.
- **Scalability:** Designed to handle multiple counters concurrently.
- **Simple Architecture:** Lightweight and flexible service structure.
- **Containerization:** Easily deployable via Docker.
- **Health Monitoring:** Includes a health check endpoint to monitor service status.
- **Automated Testing:** Unit test coverage with `unittest` for each key functionality.
- **Extensible Design:** Can be easily integrated into larger microservice ecosystems.

## Technology Stack

- **Backend:** Flask (Python)
- **Data Handling:** In-memory Python dictionary (can be extended to Redis or other databases)
- **Testing:** `unittest` with `nose` for test discovery and `coverage` for test coverage.
- **Containerization:** Docker for simplified deployment and portability.
- **Version Control:** Git for managing source code.
- **CI/CD Pipeline (Optional):** Configurable for integration into Jenkins, GitHub Actions, or other CI/CD systems.
  
## Architecture

The Hit Counter Service API follows a simple **Model-View-Controller (MVC)** architecture pattern, which makes it easy to extend, debug, and maintain.

### Request Flow

1. **HTTP Request:** The client sends an HTTP request (GET, POST, PUT, DELETE) to manage counters.
2. **Controller:** Flask routes handle the request and pass it to the appropriate logic.
3. **Business Logic:** The logic for handling counter operations (create, update, delete, list) is executed. 
4. **Response:** The service returns a JSON response with the result or error message.

This architecture allows for separation of concerns and makes the application modular, extensible, and easy to scale.

## Installation and Setup

1. **Clone the repository:**
```bash
git clone <repository_url>
cd <repository_folder>
```

2. **Create a virtual environment:**
  ```bash
python3 -m venv venv
  ```

3. **Activate the virtual environment:**
  ```bash
source venv/bin/activate
```
4. **Install the dependencies from the requirements file:**
```bash
pip install -r requirements.txt
```
5. **Run the Flask application:**
```bash
flask run
```
6. **The service will be available at:**
```bash
http://localhost:5000
```

## Scalability & Performance

This service can scale both horizontally and vertically:

### Horizontal Scaling:
* The application can be containerized and deployed in a Kubernetes cluster or Docker Swarm for auto-scaling based on traffic.
* Using a Redis or Memcached backend instead of an in-memory dictionary allows the service to scale across multiple instances seamlessly.

### Vertical Scaling:
* Memory usage can be optimized by switching from in-memory data storage to a more efficient database system (e.g., Redis or MongoDB), allowing handling of millions of counters.
* The service can be deployed on larger instances (e.g., AWS EC2, Google Cloud Compute Engine) to increase computational power for high-traffic environments.

## Extensibility

The current version of the service uses in-memory storage for simplicity and rapid prototyping. However, it’s designed with flexibility in mind:

* **Database Integration:** Easily switch from in-memory to a persistent database like Redis, MongoDB, MySQL, or PostgreSQL by modifying the data access layer.
* **Custom Counter Logic:** If you need specialized counter behavior (e.g., time-based expiration, complex aggregation), the service logic can be extended.
* **Authentication & Authorization:** Integrate OAuth2, JWT, or API key-based authentication for restricted access.
* **Load Balancing:** When deployed in production, you can use Nginx or HAProxy to manage multiple instances of the service for load balancing.

## Deployment

This project is designed to be deployable in various environments, from local testing to production.

### Production Deployment Options:
* **Docker + Kubernetes:** Use Kubernetes for orchestrating multiple containers, making it easy to scale the service based on traffic.
* **AWS Elastic Beanstalk:** For simple, scalable cloud deployment with automatic load balancing and scaling.
* **Heroku:** A quick and easy way to deploy Flask applications using Heroku’s Git-based deployment model.

## CI/CD Integration

The application is CI/CD-ready, with the following features that can be integrated:

* **Automated Testing:** `unittest` framework can be integrated into CI pipelines to run tests on each push.
* **Docker Image Build:** Automatic builds and deployment through DockerHub.
* **Code Quality Checks:** Integrate `flake8` for linting and `pytest` for advanced testing during the CI process.

## License
This project is licensed under the Apache License 2.0. See the [LICENSE](LICENSE) file for details. <br>
This project is made as a part of IBM Course.
