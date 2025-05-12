# 🛒 Containerization and Deployment of eCommerce Microservices Application

This project demonstrates the containerization and deployment of a microservices-based eCommerce application using Docker and Docker Compose on an AWS EC2 instance. The application encompasses various services such as user management, product catalog, cart, and order processing, each running in its own container for modularity and scalability.

---

## 📦 Architecture Overview

The application follows a microservices architecture, where each core functionality is encapsulated within its own service:

- **User Service**: Handles user authentication and profile management.
- **Product Service**: Manages product listings and details.
- **Cart Service**: Manages shopping cart operations.
- **Order Service**: Processes orders and payments.

Each service is developed independently and communicates with others through RESTful APIs. Docker is used to containerize these services, and Docker Compose orchestrates them, ensuring seamless inter-service communication and simplified deployment.

---

## ☁️ Deployment on AWS EC2

The application is deployed on an AWS EC2 instance running Ubuntu. The deployment process involves:

1. **Launching an EC2 Instance**: A t2.medium Ubuntu instance is recommended.
2. **Installing Docker and Docker Compose**: Set up the containerization environment.
3. **Cloning the Repository**: Obtain the application code from GitHub.
4. **Building and Running Containers**: Use Docker Compose to build and start all services.

---

## ⚙️ Technologies Used

- **Backend**: Spring Boot (Java)
- **Database**: MySQL
- **Containerization**: Docker
- **Orchestration**: Docker Compose
- **Cloud Platform**: AWS EC2 (Ubuntu)

---

## 🚀 Getting Started

### 1. Launch EC2 Instance

- Use the AWS Management Console to launch an Ubuntu EC2 instance.
- Configure the security group to allow inbound traffic on ports 22 (SSH), 80 (HTTP), 8080 (Application), and 3306 (MySQL).

### 2. Connect to EC2 via SSH

```bash
ssh -i /path/to/your-key.pem ubuntu@<your-ec2-public-ip>
```

### 3. Install Docker and Docker Compose

```bash
sudo apt update
sudo apt install -y docker.io docker-compose
sudo usermod -aG docker $USER
newgrp docker
```

### 4. Clone the Repository

```bash
git clone https://github.com/Harishkumarnimmala/containerization-and_testing-of-ecommerce-microservices-application.git
cd containerization-and_testing-of-ecommerce-microservices-application
```

### 5. Build and Run Containers

```bash
docker-compose build
docker-compose up -d
```

---

## ✅ Accessing the Application

- **Frontend**: `http://<your-ec2-public-ip>`
- **Backend APIs**: Accessible via respective ports defined in `docker-compose.yml`
- **MySQL Database**: Accessible on port 3306 (ensure security group settings allow this)

---

## 📁 Project Structure

```
.
├── client/                 # Frontend application
├── javaapi/                # Java-based backend services
├── nodeapi/                # Node.js-based backend services
├── nginx/                  # Nginx configuration for reverse proxy
├── Dockerfile              # Dockerfile for building images
├── docker-compose.yml      # Docker Compose configuration
├── Jenkinsfile             # Jenkins pipeline configuration
└── README.md               # Project documentation
```

---

## 🧪 Testing

After deployment, ensure all services are running correctly:

```bash
docker ps
```

You should see containers for each service listed. Access the frontend via the EC2 public IP to interact with the application.

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙋‍♂️ Author

**Harish Kumar Nimmala**  
GitHub: [@Harishkumarnimmala](https://github.com/Harishkumarnimmala)

---

Feel free to contribute to this project by submitting issues or pull requests.
