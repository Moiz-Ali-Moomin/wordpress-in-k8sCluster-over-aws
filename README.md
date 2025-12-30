# wordpress-in-k8sCluster-over-aws
Install Wordpress Website With MySQL in AWS Inside Kubernetes k8s Cluster Using Ansible

# ☁️ Deploy WordPress with MySQL on AWS using Kubernetes & Ansible

## 📌 Overview
This project demonstrates how to **deploy a WordPress website backed by MySQL on AWS**, running inside a **Kubernetes (K8s) cluster**, with the entire infrastructure and application setup **automated using Ansible**.

It showcases **end-to-end DevOps automation** — from provisioning cloud infrastructure to configuring Kubernetes master/worker nodes and deploying a production-ready WordPress application.

---

## 🧠 Problem Statement
Manually deploying WordPress with MySQL on cloud infrastructure is:
- Time-consuming
- Error-prone
- Difficult to scale and reproduce

Managing Kubernetes clusters and applications across cloud environments adds further complexity.

This project solves these challenges by:
- Automating AWS infrastructure provisioning
- Setting up a Kubernetes cluster using Ansible
- Deploying WordPress and MySQL in Kubernetes
- Providing a repeatable, scalable deployment strategy

---

## 🏗️ Architecture & Workflow
User
↓
Ansible Automation
↓
AWS EC2 Instances
↓
Kubernetes Cluster (Master + Workers)
↓
WordPress Pod + MySQL Pod
↓
WordPress Service (External Access)

yaml
Copy code

---

## 🛠️ Tech Stack
- **Cloud Provider:** AWS
- **Container Orchestration:** Kubernetes
- **Automation / Config Management:** Ansible
- **Application:** WordPress
- **Database:** MySQL
- **CI (Optional):** Travis CI
- **OS:** Linux

---

## ⚙️ Key Features
- Automated AWS EC2 provisioning using Ansible
- Kubernetes cluster setup (master & worker nodes)
- WordPress deployment inside Kubernetes
- MySQL database deployment and integration
- Modular Ansible roles for reusability
- Secure credential management using Ansible vars
- CI configuration using Travis CI

---

## 📂 Project Structure

```text
install-wordpress-k8s-ansible/
├── master_node/
│   ├── defaults/
│   ├── files/
│   ├── handlers/
│   ├── meta/
│   ├── tasks/
│   ├── tests/
│   └── vars/
│
├── slave_node/
│   ├── defaults/
│   ├── files/
│   ├── handlers/
│   ├── meta/
│   ├── tasks/
│   ├── tests/
│   └── vars/
│
├── wordpress/
│   ├── defaults/
│   ├── files/
│   ├── handlers/
│   ├── meta/
│   ├── tasks/
│   ├── tests/
│   └── vars/
│
├── cluster.yml            # Kubernetes cluster setup
├── ec2.yml                # AWS EC2 provisioning
├── credential.yml         # AWS & application credentials
├── final_setup.yml        # End-to-end automation playbook
├── .travis.yml
├── README.md
└── LICENSE
🚀 How to Run the Project

1️⃣ Prerequisites

AWS account

IAM user with EC2 permissions

Ansible installed

Python installed

SSH key pair for AWS EC2

kubectl installed (optional for verification)

2️⃣ Clone the repository

bash
Copy code
git clone https://github.com/your-username/install-wordpress-k8s-ansible.git
cd install-wordpress-k8s-ansible

3️⃣ Configure credentials

Update credential.yml with:

AWS access keys

SSH key details

MySQL credentials

WordPress configuration variables

4️⃣ Provision AWS EC2 instances

bash
Copy code
ansible-playbook ec2.yml

5️⃣ Setup Kubernetes cluster

bash
Copy code
ansible-playbook cluster.yml

6️⃣ Deploy WordPress & MySQL

bash
Copy code
ansible-playbook final_setup.yml

7️⃣ Verify Deployment

bash
Copy code
kubectl get nodes
kubectl get pods
kubectl get svc
Access WordPress using the service external IP.

**📊 Outcome / Results**

Fully automated WordPress deployment on AWS

Kubernetes cluster running master and worker nodes

MySQL database integrated with WordPress

Scalable and reproducible infrastructure setup

Reduced manual effort and configuration drift

**🧪 What I Learned**

Automating AWS infrastructure with Ansible

Deploying and managing Kubernetes clusters

Running stateful applications in Kubernetes

Managing secrets and credentials securely

Applying DevOps best practices in production-like environments

**🔮 Future Enhancements**

Add Terraform for infrastructure provisioning

Use Kubernetes Secrets instead of plain vars

Add persistent storage using EBS / EFS

Implement monitoring with Prometheus & Grafana

Add CI/CD pipeline for WordPress updates

Secure application using Ingress and TLS


