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
Greenbone provides official Docker images for the Community Edition. These images are self-hosted and maintained by Greenbone. <br>
sudo docker pull registry.community.greenbone.net/community/gvmd:stable

### Step 4 : Run the OpenVAS Container
sudo docker run -d -p 8080:9392 --name openvas registry.community.greenbone.net/community/gvmd:stable

This command runs the container in detached mode (-d), maps port 8080 on your host to port 9392 in the container, and names the container openvas.

### Step 5 : Accessing the OpenVAS Web Interface
After successfully running the OpenVAS container in Step 4: <br>
sudo docker run -d -p 8080:9392 --name openvas registry.community.greenbone.net/community/gvmd:stable
I attempted to access the OpenVAS / GVM web interface via: <br>
http://localhost:8080<br>
or<br>
https://localhost:8080

### Issues faced:
#### Port Mapping and Service Availability<br>
Although the container is running, the web interface did not load.
#### Progress Summary
✅ Step 1: Updated Ubuntu successfully.<br>
✅ Step 2: Installed Docker and verified it works.<br>
✅ Step 3: Pulled the official Greenbone Community Edition Docker image.<br>
✅ Step 4: Ran the OpenVAS container successfully.<br>
⚠️ Step 5 and beyond: Unable to access the web interface to configure scans due to container service initialization issues and port/SSL complexities.<br>

Additional Notes/Nessus Attempt<br>
I also attempted to perform this vulnerability scan using Nessus Essentials on Windows.<br>
I successfully downloaded and installed Nessus Essentials on my Windows PC.<br>
However, I encountered difficulties in understanding the steps to proceed, including how to create a scan target, configure the scan, and interpret the results.<br>
##### Due to this, I was unable to complete the task using Nessus.
I apologize for not completing the Nessus-based scan. With proper guidance or step-by-step instructions, I am confident that I can successfully set up Nessus, perform the vulnerability scan, and analyze the results.
