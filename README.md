# 3-Tier-Architecture
---

## 🧠 **What This Project Really Does (In Simple Words)**

This project builds a **real-world cloud system** where:

- 👨‍💻 **Users open a website**  
- ⚙️ **Backend processes the request**  
- 🗄️ **Database stores & returns data**

All running **securely on AWS cloud ☁️**

👉 Instead of putting everything in one place (**bad idea ❌**), we split it into **3 layers (good practice ✅)**

---

### 🧱 **3-Tier Architecture Breakdown**

| **Layer** | **What it does** | **Where it runs** |
|----------|----------------|------------------|
| 🌐 **Web (Frontend)** | Shows UI to users | **Public EC2** |
| ⚙️ **App (Backend)** | Processes logic | **Private EC2** |
| 🗄️ **Database** | Stores data | **AWS RDS (Private)** |

---

---

## 🏗️ Architecture Overview

This is not just a project — it’s how real companies build scalable systems 🚀

📌 Flow:

User → Load Balancer → Web Tier → App Tier → Database (RDS)

---

---

## ⚙️ **Step-by-Step Implementation**

---

### 1️⃣ **Create VPC**

- Go to **VPC Dashboard**
- Click **Create VPC**
- Set:
  - CIDR Block → `140.0.0.0/16`
  - Name → `Project-VPC`
- Click **Create**

---

### 2️⃣ **Create Subnets**

- Create:
  - ✅ **2 Public Subnets**
  - ✅ **4 Private Subnets**
- Use different **Availability Zones**
- Assign different **CIDR blocks**

---

### 3️⃣ **Create Internet Gateway**

- Go to **Internet Gateway**
- Click **Create**
- Attach it to your **VPC**

---

### 4️⃣ **Create Route Tables**

- Create:
  - 🌐 **Public Route Table**
  - 🔒 **Private Route Table**

- Public Route Table:
  - Add route → `0.0.0.0/0 → Internet Gateway`

- Associate:
  - Public subnets → Public route table
  - Private subnets → Private route table

---

### 5️⃣ **Create NAT Gateway**

- Go to **NAT Gateway**
- Select a **Public Subnet**
- Allocate **Elastic IP**
- Click **Create**

---

### 6️⃣ **Launch EC2 Instances**

- Launch:
  - 🌐 **2 Public EC2 (Web Tier)**
  - 🔒 **2 Private EC2 (App Tier)**

- Choose:
  - Amazon Linux / Ubuntu
- Configure:
  - Key Pair
  - Security Groups
  - VPC & Subnets

---

### 7️⃣ **Install NGINX (Web Server Setup)**

```bash
sudo -i
apt update
apt install nginx -y
cd /usr/share/nginx/html
rm index.html
vi index.html
systemctl restart nginx
systemctl status nginx
