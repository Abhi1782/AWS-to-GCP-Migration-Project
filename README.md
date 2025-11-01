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

"C:\Users\Lenovo\OneDrive\Documents\Project\Server Migration (AWS to GCP)\Screenshot 2025-10-31 194903.png"

