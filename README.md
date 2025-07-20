# Project 8: Creating a VPC Peering Connection between two VPCs

## 📌 Overview
In this project, we will learn how to create a **VPC Peering Connection** between two Virtual Private Clouds (VPCs) to allow them to communicate with each other using private IP addresses.

---

## 🎯 Objectives

- Create two separate VPCs.
- Launch EC2 instances in each VPC.
- Create a VPC Peering Connection.
- Update route tables to enable communication.
- Test the connectivity between EC2 instances.

---
![Final Architecture](https://github.com/fadykaram88/Creating-a-VPC-Peering-Connection-between-two-VPCs/blob/main/module-8-guided-lab-final-architecture.png?raw=true)

## 🛠️ Tools & Services Used

- **Amazon VPC**
- **Amazon EC2**
- **VPC Peering**
- **Route Tables**
- **Security Groups**
- **AWS Management Console**

---

---

## 🚀 Steps

### 1. Create Two VPCs
- VPC A: 10.0.0.0/16
- VPC B: 20.0.0.0/16

### 2. Create Subnets
- Subnet A1 in VPC A (10.0.1.0/24)
- Subnet B1 in VPC B (20.0.1.0/24)

### 3. Launch EC2 Instances
- Launch one EC2 instance in each subnet with Amazon Linux 2.
- Enable SSH and ICMP in security groups.

### 4. Create VPC Peering Connection
- Navigate to **VPC Console → Peering Connections**.
- Create a peering connection between VPC A and VPC B.
- Accept the peering connection from the accepter side.

### 5. Update Route Tables
- Add a route in VPC A’s route table to reach VPC B.
- Add a route in VPC B’s route table to reach VPC A.

### 6. Test Connectivity
- SSH into one instance.
- Ping the private IP of the second instance to test connection.

---

## ✅ Results

- Instances in separate VPCs were able to communicate privately.
- Successfully created and tested a VPC Peering Connection.

---

## 📎 GitHub Repository

🔗 [Creating a VPC Peering Connection between two VPCs](https://github.com/fadykaram88/Creating-a-VPC-Peering-Connection-between-two-VPCs)

---

## 🧠 Lessons Learned

- VPC Peering is useful for interconnecting environments.
- Route tables and security groups play a critical role in cross-VPC communication.
- No transitive peering — each connection must be explicitly defined.

---
