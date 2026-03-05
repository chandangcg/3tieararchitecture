# Designing and implementing a 3-tier architecture consisting of 1 Load Balancer and 2 Web Servers 


## Project Overview
This project demonstrates how to build a 3-tier architecture using Terraform for infrastructure provisioning and Ansible for configuration management.

The setup includes:
- 1 Load Balancer
- 2 Web Servers
- Ubuntu 22.04 Virtual Machines
- Nginx Web Server

## Tools & Technologies
- Terraform
- Ansible
- VirtualBox
- Ubuntu 22.04
- Nginx

## Architecture
Load Balancer distributes traffic between two web servers.

Client → Load Balancer → Web1 / Web2

## Project Structure

project/
│
├── terraform/
│   └── main.tf
│    └── outputs.tf
│    └──variables.tf
|   
│
├── ansible/
│   ├── ansible.cfg
│   ├── ping.yml
│   ├── inventory.ini
│   ├── site.yml
│   └── roles/
│       └── ping_role
│       │   └── tasks
│       │      └── main.yml
│       └── lb 
│       └── tasks
│       │      └── main.yml                   
│       └── templates
│       │       └── index.html.j2
│       │ 
│       └── web  
│            └── tasks
│               └── main.yml
│
└── README.md


# Git Configuration with SSH 

# 1. Check Git installation

git --version

# 2. Configure Git username and email

git config --global user.name " User name"

# 3. Generate SSH key

ssh-keygen -C "[Emailid]

# 4. Start SSH agent

eval "$(ssh-agent -s)"

# 5. Add SSH key to agent

ssh-add ~/.ssh/id_ed25519

# 6. Display public SSH key (copy this and add to GitHub)

cat ~/.ssh/id_ed25519.pub

# ---- Add this key to GitHub ----

# Go to GitHub → Settings → SSH and GPG Keys → New SSH Key → Paste key

# 7. Test SSH connection

ssh -T 

# 8. Initialize Git repository

git init

# 9. Add README file

git add README.md

# 10. Commit the file

git commit -m "Initial commit"

# 11. Set main branch

git branch -M main

# 12. Connect GitHub repository

git remote add origin [Emailid]

# 13. Push project to GitHub

git push -u origin main


1. Install Terraform
brew tap hashicorp/tap
brew install hashicorp/tap/terraform

2. Verify installation
terraform -version

3. Create Terraform project folder
mkdir terraform
cd terraform

4. Create Terraform configuration file
touch main.tf

5. Initialize Terraform
terraform init

6. Check execution plan
terraform plan

7. Apply configuration (create infrastructure)
terraform apply

8. Verify resources
terraform state list


![/vbinstance.png]


1. Install Ansible
brew install ansible

2. Verify installation
ansible --version

3. Create Ansible project folder
mkdir ansible
cd ansible

4. Create inventory file
touch inventory.ini

5. Add server IPs to inventory
nano inventory.ini

Example:

[web]
192.168.1.125
192.168.1.126

[loadbalancer]
192.168.1.127

6. Test connection to servers
ansible all -i inventory.ini -m ping

7. Create Ansible configuration file
touch ansible.cfg

8. Create playbook
touch playbook.yml

9. Run Ansible playbook
ansible-playbook -i inventory.ini playbook.yml





