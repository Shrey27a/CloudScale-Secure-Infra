# Scalable & Secure 2-Tier Architecture on AWS

This project demonstrates the deployment of a production-ready, highly available 2-tier application on AWS. It showcases professional cloud networking, security, and automation.


##  Architecture
The application is hosted on AWS using a secure 2-tier design:
- **Public Tier:** Application Load Balancer (ALB) and CloudFront (CDN) to handle external traffic.
- **Private Tier:** EC2 instances (App) and RDS (Database) are isolated in private subnets, hidden from the public internet for security.

---

##  Key Features
- **VPC Networking:** Custom VPC with 2 Public and 2 Private subnets across multiple AZs.
- **Auto Scaling:** Configured ASG with a **Golden AMI** to automatically scale instances based on traffic.
- **Security:** Layered Security Groups and **NAT Gateway** for secure outbound internet access.
- **Secrets Management:** Used **AWS Systems Manager (SSM) Parameter Store** for DB credentials (no hardcoding).
- **Edge Delivery:** Content served through **Amazon CloudFront** with SSL from **ACM** for the domain `system-monitor.live`.

---

##  Project Structure
- **frontend**: React.js application source code.
- **backend**: Node.js backend application.
- **mysql**: SQL scripts and configuration for the database layer.

---

##  Deployment Steps (AWS)

### 1. Networking Setup
- Create a VPC, Subnets, and Route Tables.
- Configure an Internet Gateway and NAT Gateway.
  <img width="502" height="238" alt="Picture1" src="https://github.com/user-attachments/assets/ef71ddc8-113f-440f-a2c3-6ae2cf3ea890" />

### 2. Database (RDS) Setup
- Launch an RDS MySQL instance in private subnets.
- Store database host and credentials in **AWS Parameter Store**.
  
<img width="624" height="281" alt="Picture3" src="https://github.com/user-attachments/assets/1fd8bf72-ad94-4ba7-861e-6086d0575c9a" />

### 3. Application Deployment
- Configure an EC2 instance with Nginx, Node.js, and PM2.
- Create a **Golden AMI** from the configured instance.
- Set up an **Application Load Balancer** and **Auto Scaling Group**.

   <img width="516" height="509" alt="Picture4" src="https://github.com/user-attachments/assets/31a9a9aa-2648-48ba-9048-b8400d4b1b60" />


  <img width="742" height="145" alt="Picture5" src="https://github.com/user-attachments/assets/36bd8ffd-a7a5-47ef-8725-a941d2e2c797" />

### 4. Domain & Caching
- Point your domain via **Route 53**.
- Set up **CloudFront** with an **ACM SSL Certificate** for HTTPS.

  ![afa58e03-f199-44e8-b034-32c4d166d2ad](https://github.com/user-attachments/assets/c712b912-03fd-4170-9c28-1bc561aedab5)



## 🤝 Connect with Me
- **LinkedIn:** Shreya Sharma -- https://www.linkedin.com/in/shreya-sharma-a514092a2/
- **Live Project:** [https://system-monitor.live](https://system-monitor.live)
