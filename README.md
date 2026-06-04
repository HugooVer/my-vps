# Automated Secure VPS Deployment (Ansible & Docker)

An **Infrastructure as Code (IaC)** repository to automate the provisioning, hardening, and deployment of web services on an Ubuntu VPS. It sets up a secure reverse proxy and network isolation for containerized applications, including a [CI/CD resume/CV](https://github.com/HugooVer/Resume-CI-CD).

## 🛠️ Tech Stack

- **Automation:** Ansible
- **Containerization:** Docker & Docker Compose
- **Reverse Proxy / Routing:** Traefik v3
- **Web Server:** Nginx (Alpine)
- **Security:** iptables (Netfilter)

## 🏗️ Architecture & Roles

- **`common`**: System updates, Docker installation, and strict firewall configuration (Default `DROP` policy; open only 22, 80, 443).
- **`traefik`**: Deploys Traefik v3 as an edge router, forces HTTP-to-HTTPS redirection, and handles automated **Let's Encrypt** SSL/TLS certificates.
- **`website_cv`**: Serves my static resume, which is dynamically deployed via GitHub Actions and Ansible from the [Resume-CI-CD](https://github.com/HugooVer/Resume-CI-CD) repository.
- **`webtest`**: A placeholder container (`nginxdemos/hello`) to quickly validate routing and DNS configuration.