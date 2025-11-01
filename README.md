# 🚀 AWS → GCP Server Migration Project (Apache Web Server)

This project demonstrates the migration of a running server workload from Amazon Web Services (AWS) to Google Cloud Platform (GCP) using Google’s VM Migration service. The source server hosted a web application using Apache2, and the migration ensured minimal downtime with full replication and cutover.


# 🏗️ Project Objectives

  1) Deploy and configure a server in AWS (Source)
  2) Install & configure Apache2 web server
  3) Implement IAM & security policies on AWS
  4) Migrate the server to GCP using VM Migration
  5) Configure IAM & network firewall in GCP (Destination)
  6) Validate web server availability post-migration


# 🔧 Technologies & Cloud Services Used

<img width="642" height="147" alt="image" src="https://github.com/user-attachments/assets/24e5992f-16f5-4dc9-8c65-37ff9ee60a3c" />

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# 📌 Step-by-Step Implementation

# 1️⃣ Create Source Server in AWS
  1) Launched an EC2 instance (Ubuntu Linux)
  2) Connected using SSH (Port 22 opened in Security Group)
  3) Installed Apache Web Server:
     sudo apt update
     sudo apt install apache2 -y
     sudo systemctl enable apache2
     sudo systemctl start apache2
  4) Verified HTTP access via browser

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<img width="1920" height="1080" alt="Screenshot (454)" src="https://github.com/user-attachments/assets/395f1b88-988d-4781-8cb5-8f625453eb54" />

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<img width="1920" height="1080" alt="Screenshot (455)" src="https://github.com/user-attachments/assets/0cd1c644-2280-4c52-a221-8bb5c8822a8b" />

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<img width="1920" height="1080" alt="Screenshot (456)" src="https://github.com/user-attachments/assets/f33ba481-c72c-4df8-9e1e-12ecac985f85" />

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

