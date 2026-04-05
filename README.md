# 3-Tier-Architecture
🧠 What This Project Really Does (In Simple Words)

This project builds a real-world cloud system where:

👨‍💻 Users open a website
⚙️ Backend processes the request
🗄️ Database stores & returns data

All running securely on AWS cloud.

👉 Instead of putting everything in one place (bad idea), we split it into 3 layers:

Layer	What it does	Where it runs
🌐 Web (Frontend)	Shows UI to users	Public EC2
⚙️ App (Backend)	Processes logic	Private EC2
🗄️ Database	Stores data	AWS RDS
🏗️ Architecture Overview

This is not just a project — it’s how real companies build scalable systems.

📌 Based on your implementation
(see full architecture diagram in your PDF , page 2)

Flow:
User → Load Balancer → Web Tier → App Tier → Database (RDS)

⚙️ Step-by-Step Implementation (Feynman Style)
1️⃣ Create Network (Foundation)
Create VPC
Add:
2 Public Subnets
4 Private Subnets
Attach Internet Gateway

👉 Think of this as building a city map.

2️⃣ Control Traffic (Road Rules)
Create Route Tables:
Public → Internet access
Private → Internal only
Add NAT Gateway

👉 Private servers can go out, but outsiders can’t come in.

3️⃣ Launch Servers (Compute Layer)
Create EC2 instances:
Public → Web servers
Private → App servers

Install NGINX:

sudo -i
apt update
apt install nginx
systemctl start nginx
4️⃣ Load Balancing (Traffic Manager)
Create:
Public Load Balancer
Private Load Balancer
Attach Target Groups

👉 Like a traffic police distributing requests.

5️⃣ Auto Scaling (Self-Healing System)
Automatically:
Adds servers when traffic increases
Removes servers when not needed

👉 Your system becomes elastic.

6️⃣ Database Layer (Secure Storage)
Create RDS (MySQL)
Keep it in private subnet
Add read replica

👉 Data is safe + scalable.

7️⃣ Connect & Test Database
CREATE DATABASE Devops;

CREATE TABLE details (
  ID INT NOT NULL,
  Firstname VARCHAR(255),
  Lastname VARCHAR(255),
  Age INT
);

INSERT INTO details VALUES (1,'Karthik','Reddy',22);

SELECT * FROM details;
