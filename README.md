# Task-3 :  Basic Vulnerability Scan on Your PC

### Objective: Use free tools to identify common vulnerabilities on your computer.
### Tools:  OpenVAS / Greenbone Vulnerability Management (GVM), Ubuntu Seed VM (VirtualBox)

This task specifies performing a vulnerability scan on our host PC. For safety reasons, I am performing the scan on my Ubuntu Seed virtual machine (VM) instead of my host PC.
Scanning a host PC can potentially expose sensitive files or create system changes. Using a VM ensures isolation and reversibility. I have also taken a snapshot of the VM prior to the scan to safely revert to its original state after completing this task.

### Step 1 : Update ubuntu
sudo apt update && sudo apt upgrade -y

### Step 2 : Installing OpenVAS Using Docker on Ubuntu Seed VM
sudo apt update <br>
sudo apt install -y docker.io <br>
sudo systemctl enable --now docker <br>
Verification <br>
docker --version

### Step 3 : Pull the Official Greenbone Community Edition Docker Image
Greenbone provides official Docker images for the Community Edition. These images are self-hosted and maintained by Greenbone.
sudo docker pull registry.community.greenbone.net/community/gvmd:stable
