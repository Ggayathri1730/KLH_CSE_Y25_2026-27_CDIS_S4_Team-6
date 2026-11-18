# KLH_CSE_Y25_2026-27_CDIS_S4_Team-6
# Blue-Green Deployment and Rollback Management System

A cloud-based application deployment system designed to minimize downtime, reduce deployment risks, and enable faster recovery using the Blue-Green Deployment strategy on AWS.

---

## 📌 Project Overview

The **Blue-Green Deployment and Rollback Management System** is a cloud-based DevOps project that aims to make application deployment safer and more reliable.

Traditional application deployment may cause downtime or unexpected errors when a new application version replaces an existing version.

To overcome this challenge, our project uses two separate environments:

- **Blue Environment:** Hosts the currently stable application version.
- **Green Environment:** Hosts the newly deployed application version.

The new version is deployed and tested in the Green environment before production traffic is switched to it. If the new version fails validation, traffic can be redirected to the previous stable Blue environment through a rollback mechanism.

The project uses AWS cloud services, Docker, and CI/CD automation to support a controlled deployment workflow.

---

## 🎯 Objectives

- Minimize application downtime during software updates.
- Reduce risks associated with deploying new application versions.
- Maintain separate Blue and Green environments.
- Automate application deployment using CI/CD.
- Perform health checks before switching production traffic.
- Enable rollback to the previous stable version.
- Monitor application health and performance using AWS services.

---

## ⚙️ Key Features

1. **Blue-Green Environment Management**
   - Maintain two independent application environments.
   - Keep the stable and new application versions separate.

2. **Docker Containerization**
   - Package applications and dependencies into Docker containers.
   - Maintain versioned container images.

3. **Automated Deployment**
   - Integrate GitHub Actions for CI/CD workflows.
   - Build and test application versions before deployment.

4. **Health Check and Validation**
   - Verify whether the new application version is working correctly.
   - Validate application health before traffic switching.

5. **Traffic Switching**
   - Use AWS Application Load Balancer (ALB).
   - Route incoming user requests to the selected environment.

6. **Rollback Management**
   - Redirect traffic to the previous stable version if deployment fails.
   - Support faster recovery from unsuccessful releases.

7. **Monitoring and Logging**
   - Monitor application performance and infrastructure health.
   - Use Amazon CloudWatch for metrics, logs, and alarms.

---

## 🏗️ Proposed System Architecture

The proposed architecture consists of the following components:

```text
             Developer
                 |
                 v
               GitHub
                 |
                 v
          GitHub Actions
             (CI/CD)
                 |
                 v
          Docker Image Build
                 |
                 v
             Amazon ECR
                 |
                 v
          AWS EC2 Instances
                 |
          +------+------+
          |             |
          v             v
     BLUE ENV        GREEN ENV
    (Version 1)     (Version 2)
          |             |
          +------+------+
                 |
                 v
       Application Load Balancer
                 |
                 v
               Users

       Amazon CloudWatch
       (Monitoring & Alerts)
```

**Architecture Explanation:**

- GitHub stores the application source code.
- GitHub Actions automates the build and deployment workflow.
- Docker packages the application into container images.
- Amazon ECR stores the container images.
- Amazon EC2 hosts the application containers.
- The Application Load Balancer routes incoming traffic to the active environment.
- Amazon CloudWatch monitors application health and performance.

The deployment automation manages traffic switching and rollback decisions.

---

## ☁️ AWS Services Used

| AWS Service | Purpose |
|---|---|
| Amazon EC2 | Hosts application containers |
| Amazon VPC | Provides isolated cloud networking |
| Application Load Balancer | Distributes and switches application traffic |
| EC2 Auto Scaling Groups | Manages application instance capacity |
| Amazon ECR | Stores Docker container images |
| Amazon CloudWatch | Monitors metrics, logs and alarms |
| AWS IAM | Manages access and permissions |
| Amazon S3 | Stores deployment artifacts when required |

---

## 💻 Technology Stack

| Technology | Usage |
|---|---|
| Java / Spring Boot | Backend application |
| HTML, CSS, JavaScript | Frontend development |
| Docker | Application containerization |
| Git & GitHub | Version control |
| GitHub Actions | CI/CD automation |
| AWS EC2 | Application hosting |
| Amazon ECR | Container image storage |
| AWS ALB | Traffic management |
| Amazon CloudWatch | Monitoring |

---

## 🔄 Deployment Workflow

1. The developer pushes application code to GitHub.
2. GitHub Actions triggers the CI/CD workflow.
3. The application is built, tested and packaged using Docker.
4. The Docker image is stored in Amazon ECR.
5. The new application version is deployed in the Green environment.
6. Health checks and validation tests are performed.
7. If validation succeeds, the Application Load Balancer switches traffic to Green.
8. Amazon CloudWatch monitors application health and performance.
9. If the new version fails, deployment automation redirects traffic to the previous stable Blue environment.

---

## 🔙 Rollback Mechanism

Rollback is an important feature of this project.

If the newly deployed Green environment encounters errors or fails validation:

- The deployment workflow identifies the failure.
- The rollback mechanism updates the Application Load Balancer routing.
- User traffic is redirected to the previous stable Blue environment.
- The application can continue serving users while the failure is investigated.

**Note:** CloudWatch provides monitoring and alarms. The deployment automation is responsible for executing the rollback.

---

## 🚀 Future Enhancements

- Intelligent failure detection and automated rollback.
- Canary deployment strategy.
- Advanced application performance monitoring.
- Integration with Amazon ECS or Amazon EKS.
- Automated deployment notifications.
- Deployment history and reporting dashboard.
- Advanced security and access management.

---

## 📚 Learning Outcomes

Through this project, we aim to gain practical knowledge of:

- Cloud computing using AWS.
- DevOps and CI/CD pipelines.
- Docker containerization.
- Application deployment strategies.
- Load balancing and traffic management.
- Application monitoring and logging.
- Deployment failure handling and rollback mechanisms.

---

## 👩‍💻 Team Members

**KL University – Bachupally Campus, Hyderabad**  
Department of Computer Science & Engineering

| Name | Registration Number |
|---|---|
| Guttikonda Gayathri | 2520030465 |
| Bhavana D. | 2520030242 |
| M. Hasini | 2520030228 |

**Section:** 4  
**Team Number:** 6

**Project Guide:** Dr. V. Siressha

**Academic Year:** 2026–2027

---

## 📌 Project Status

Currently in the planning and proposed architecture stage. Implementation, integration, testing and deployment will be carried out as part of the project development process.

---

## ⭐ Conclusion

The Blue-Green Deployment and Rollback Management System aims to provide a safer and more reliable approach to application deployment.

By maintaining two independent environments and controlling production traffic through an AWS Application Load Balancer, the proposed system helps minimize deployment risks and supports faster recovery from failed releases.

This project demonstrates the practical application of AWS cloud services, Docker, and DevOps automation concepts.
