# 🔐 cybers-dumps

A repository documenting my cybersecurity learning through real-world architecture design and security-first thinking.

---

## 📌 Overview

This repository focuses on **secure architecture design** based on practical experience.

The architecture demonstrates a simple and secure setup using:
- AWS WAF for filtering malicious traffic  
- Application Load Balancer (ALB) as the only public entry point  
- Private EC2 instance running application components  
- MongoDB secured internally (not exposed to internet)  

The goal is to keep it:
- Simple  
- Secure  
- Easy to understand  

---

## 🏗️ Architecture Diagram

![Architecture Diagram](./assets/architecture.png)

---

## 🔄 Request Flow

User → Domain (DNS)  
→ AWS WAF  
→ Application Load Balancer (HTTPS 443)  
→ EC2 (Private Subnet)  
→ NGINX (Reverse Proxy)  
→ / → Frontend  
→ /api → Backend (Node.js - localhost:3000)  
→ MongoDB (localhost:27017)  

---

## 🔐 Security Design

- Only ALB is publicly accessible  
- EC2 is in a private subnet (no public IP)  
- Backend is not exposed  
- MongoDB is bound to localhost  
- All traffic passes through WAF  
- Security groups follow least privilege  

---

## 🧠 Key Learnings

- Working system does not mean secure system  
- Avoid exposing database and backend ports  
- Use reverse proxy to hide internal services  
- Always design with security in mind  
- Small misconfigurations can lead to big risks  

---

## ⚠️ Scope

This architecture is suitable for:
- Learning  
- POC (Proof of Concept)  
- Small applications  

Not designed for:
- High availability  
- Large-scale production systems  

---

## 📖 About This Project

This setup is inspired by a real incident where a database was exposed due to misconfiguration.

This repository is part of my learning journey:
Mistakes → Understanding → Secure Design  

---

## 📁 Repository Structure

cybers-dumps/  
│── README.md  
│── assets/  
│    └── architecture.png  

---

## ⭐ Support

If you find this useful, consider giving a ⭐ to the repository.
