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

# 2️⃣ Configure AWS IAM for Migration

  1) Created an IAM user for migration purposes
  2) Attached custom IAM policy with required permissions:

     {
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "ec2:DescribeInstances",
                "ec2:DescribeVolumes",
                "ec2:DescribeInstanceTypes",
                "ec2:DescribeSnapshots",
                "ec2:CreateTags",
                "ec2:CreateSnapshots",
                "ec2:StopInstances"
            ],
            "Resource": "*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "ebs:ListSnapshotBlocks",
                "ebs:ListChangedBlocks",
                "ebs:GetSnapshotBlock",
                "ec2:DeleteSnapshot",
                "ec2:DeleteTags"
            ],
            "Resource": "*",
            "Condition": {
                "StringEquals": {
                    "aws:ResourceTag/m2vm-resource": "snapshot"
                }
            }
        }
    ]
}

  3) Generated Access Key & Secret Key
  4) Secured credentials using IAM security best practices

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<img width="1920" height="1080" alt="Screenshot (458)" src="https://github.com/user-attachments/assets/aa0ce60e-0085-4b65-9817-3b7f980933a7" />

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<img width="1920" height="1080" alt="Screenshot (459)" src="https://github.com/user-attachments/assets/1c663c38-1187-464c-820e-531286cf4ffc" />

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<img width="1920" height="1080" alt="Screenshot (460)" src="https://github.com/user-attachments/assets/2b2ccc69-bfb8-4b27-a347-2007f39ad8eb" />

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<img width="1920" height="1080" alt="Screenshot (461)" src="https://github.com/user-attachments/assets/7a6e8fab-121d-454e-8739-835dba05d8fb" />

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# 3️⃣ Start Migration Setup in GCP

  1) Enabled VM Migration API
  2) Deployed VM Migration Manager
  3) Installed migration agent on AWS VM
  4) Authenticated migration with AWS IAM Access Keys
     
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<img width="1920" height="1080" alt="Screenshot (457)" src="https://github.com/user-attachments/assets/c7e5854a-da32-48e4-9cee-8e50cb669925" />

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<img width="1920" height="1080" alt="Screenshot (473)" src="https://github.com/user-attachments/assets/7ae72477-12b9-4b8d-b5d7-d5b8255d0bf9" />

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# 4️⃣ VM Replication & Cutover

       1) Initiated replication process → disk data copied to GCP
Monitored replication status until 100%
Executed Cutover:

      Stopped source VM → Created a final sync snapshot
      Booted the migrated VM automatically on Google Compute Engine

Validated same OS + same Apache configuration after migration
