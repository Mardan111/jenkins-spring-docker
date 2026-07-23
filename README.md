# 🍃 Will of Fire Marketplace - Spring Boot Docker CI/CD Project

![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.3.4-brightgreen)
![Java](https://img.shields.io/badge/Java-21-orange)
![MySQL](https://img.shields.io/badge/MySQL-8-blue)
![Docker](https://img.shields.io/badge/Docker-Containerized-blue)
![Jenkins](https://img.shields.io/badge/Jenkins-CI%2FCD-red)

## 📖 Project Overview

**Will of Fire Marketplace** is a Spring Boot based web application inspired by the Naruto universe.

The application provides an anime-themed product marketplace where users can explore ninja-inspired products while experiencing a modern animated UI.

The project demonstrates a complete DevOps workflow:

* Spring Boot application development
* MySQL database integration
* Thymeleaf frontend development
* Docker containerization
* Docker Compose orchestration
* Jenkins CI/CD automation
* Automated build and deployment process

---

# ✨ Features

## 🍥 Application Features

* User authentication
* Product listing
* Product image rendering using Base64 encoding
* Dynamic Thymeleaf pages
* Responsive Bootstrap UI
* Naruto inspired animated interface
* Hidden Leaf Village theme
* Chakra animations
* Sharingan inspired login page

---

# 🛠️ Technology Stack

## Backend

| Technology      | Version |
| --------------- | ------- |
| Java            | 21      |
| Spring Boot     | 3.3.4   |
| Spring MVC      | Latest  |
| Spring Data JPA | Latest  |
| Maven           | 3.x     |

## Frontend

* Thymeleaf
* Bootstrap 5
* HTML5
* CSS3
* Font Awesome

## Database

* MySQL 8.0

## DevOps Tools

* Docker
* Docker Compose
* Jenkins
* GitHub

---

# 🏗️ Application Architecture

```
                 User
                  |
                  |
             Browser
                  |
                  |
          Spring Boot App
                  |
        -------------------
        |                 |
    Thymeleaf          JPA/Hibernate
        |                 |
        |                 |
        -------- MySQL --------



CI/CD Flow


Developer
    |
    |
 GitHub Repository
    |
    |
 Jenkins Pipeline
    |
    |
 Maven Build
    |
    |
 Docker Image Build
    |
    |
 Docker Compose Deploy
    |
    |
 Running Containers

```

---

# 📂 Project Structure

```
spring_app_sak
│
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com.sak
│   │   │
│   │   └── resources
│   │       ├── templates
│   │       │   ├── home.html
│   │       │   ├── login.html
│   │       │   └── signup.html
│   │       │
│   │       ├── static
│   │       │
│   │       └── application.properties
│
├── Dockerfile
├── docker-compose.yml
├── Jenkinsfile
└── pom.xml

```

---

# ⚙️ Spring Boot Configuration

Example database configuration:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/myapplication

spring.datasource.username=root

spring.datasource.password=1234


spring.jpa.hibernate.ddl-auto=update

spring.jpa.show-sql=true

```

---

# 🐳 Docker Setup

## Dockerfile

The application is packaged into a Docker image.

Example:

```dockerfile
FROM openjdk:21-jdk

WORKDIR /app

COPY target/*.jar app.jar

EXPOSE 8080

ENTRYPOINT ["java","-jar","app.jar"]

```

---

# 🐬 Docker Compose Setup

The application runs with two containers:

```
+---------------------+
| Spring Boot App     |
| Port: 8085          |
+----------+----------+
           |
           |
+----------v----------+
| MySQL Database      |
| Port:3306           |
+---------------------+

```

Start application:

```bash
docker compose up --build -d
```

Stop application:

```bash
docker compose down
```

Remove unused images:

```bash
docker image prune -af
```

---

# 🚀 Jenkins CI/CD Pipeline

The Jenkins pipeline automates:

## Build Stage

```bash
mvn clean package
```

Creates Spring Boot JAR file.

---

## Deployment Stage

```bash
docker compose up --build -d
```

Builds Docker image and starts containers.

---

## Remove Stage

```bash
docker compose down

docker image prune -af
```

Stops containers and cleans Docker resources.

---

# 🔐 Jenkins Setup

## Required Jenkins Plugins

Install:

* Pipeline Plugin
* Git Plugin
* Docker Pipeline Plugin
* Maven Integration Plugin

---

# Docker Permission Setup for Jenkins

Add Jenkins user to Docker group:

```bash
sudo usermod -aG docker jenkins
```

Restart Jenkins:

```bash
sudo systemctl restart jenkins
```

Verify:

```bash
sudo -u jenkins docker ps
```

---

# ☕ Java Configuration Issue

If Maven shows:

```
release version 21 not supported
```

Check:

```bash
java -version

javac -version

mvn -version
```

Jenkins requires JDK installation, not only JRE.

Install:

```bash
sudo apt install openjdk-21-jdk
```

Configure JAVA_HOME in Jenkins.

---

# 🧪 Running Locally

Clone repository:

```bash
git clone <repository-url>
```

Move into project:

```bash
cd spring_app_sak
```

Build:

```bash
mvn clean package
```

Run:

```bash
java -jar target/*.jar
```

Application:

```
http://localhost:8080
```

---

# 🎨 UI Theme

The application UI is inspired by:

🍃 Hidden Leaf Village
🔥 Will of Fire
🍥 Naruto Universe
⚔️ Shinobi Marketplace

Implemented features:

* Animated chakra particles
* Fire themed buttons
* Shinobi login interface
* Anime marketplace cards
* Responsive design

---

# 🐳 Docker Hub Deployment Flow

Pipeline flow:

```
Spring Boot Code

        |

     Maven Build

        |

   Docker Image

        |

 Docker Registry

        |

 Docker Compose

        |

 Production Container

```

---

# 📝 Future Enhancements

* Kubernetes deployment
* AWS EC2 hosting
* Terraform infrastructure
* SonarQube code quality checks
* Prometheus monitoring
* Grafana dashboards
* Role-based authentication
* Payment integration

---

# 👨‍💻 Author

**Mardan Ali**

Spring Boot Developer | DevOps Enthusiast

---

# 🔥 "A shinobi's true power comes from protecting what matters." 🍃
