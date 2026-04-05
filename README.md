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

## 🏗️ **Architecture Overview**

This is not just a project — it’s how **real companies build scalable systems 🚀**

📌 **Flow:**
```text
User → Load Balancer → Web Tier → App Tier → Database (RDS)
