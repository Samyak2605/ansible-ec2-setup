# 🛠️ Ansible EC2 Server Setup

This project demonstrates how to configure an Ubuntu EC2 instance using **Ansible** for automated setup and deployment of a static website.

## 🔧 Technologies Used

- 🐧 Linux (Ubuntu 24.04)
- 📦 Ansible
- ☁️ AWS EC2
- 🌐 Nginx (Web Server)
- 🔐 SSH Key Management

---
This is the project link:https://roadmap.sh/projects/configuration-management

## 📁 Project Structure

ansible-ec2-setup/
├── inventory.ini # Ansible inventory file
├── setup.yml # Main Ansible playbook
└── roles/
├── base/ # Basic server configuration
│ └── tasks/main.yml
├── nginx/ # Installs and starts Nginx
│ └── tasks/main.yml
├── app/ # Deploys static site from tarball
│ ├── files/website.tar.gz
│ └── tasks/main.yml
└── ssh/ # Adds public SSH key to server
├── tasks/main.yml
└── tasks/public_key.pub


---

## ✅ Features

- Updates & configures an EC2 instance
- Installs essential utilities & fail2ban
- Installs & starts Nginx server
- Deploys a static website from a `website.tar.gz` tarball
- Adds your custom SSH key to the authorized users

---

## ⚙️ Usage

### 1. 🔑 Prerequisites

- An AWS EC2 Ubuntu server running
- Your SSH private key (e.g., `ec2-instance.pem`)
- A static site archived in `roles/app/files/website.tar.gz`

---

### 2. 📦 Setup Inventory

```ini
inventory.ini
[web]
<your-ec2-ip> ansible_user=ubuntu ansible_ssh_private_key_file=/path/to/ec2-instance.pem



3. ▶️ Run the Playbook

ansible-playbook -i inventory.ini setup.yml
Use tags to run specific roles:


ansible-playbook -i inventory.ini setup.yml --tags "app"

