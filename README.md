# k3s-nginx

**1. Set up K3s Cluster with Vagrant & Ansible**

Project Structure
vagrant-k3s/
├── Vagrantfile
├── inventory.ini
└── site.yml

Vagrantfile

Ansible Inventory inventory.ini

**2. Deploy Nginx Hello World App on K3s**

Kubernetes Manifest nginx-hello.yaml

**3. Set Up Jenkins CI/CD Pipeline**

Installed Jenkins ( Docker)
Allowed Jenkins to SSH into the K3s master using Jenkins Credentials
Created Jenkins Pipeline Job with inline script:

**4. GitHub → Poll SCM for every minute**

●​ Configured poll SCM to check every minute in the repo for changes​

**5. Tested the application**
