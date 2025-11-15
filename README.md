# personal-web-page

My personal web server setup

Since it's an educational project, I want to try various ways to build and deliver static content

## Ways to serve static content

|Option|Tech Stack|Learnings|Good For|
|------|----------|---------|--------|
|🔹 S3 Static Hosting|S3 + Route53 + (optional CloudFront)|DNS, public access control, bucket policies, HTTP basics|Beginners, cloud intro|
|🔹 CloudFront + S3 + ACM|CDN + SSL + caching|CDN config, SSL/TLS, performance tuning|Real-world hosting, HTTPS|
|🔹 Netlify / Vercel|Git repo → deploy|GitOps, CI/CD, auto-deploy, env vars|Modern frontend workflows|
|🔹 GitHub Pages|Git + static files|GitHub Actions, Jekyll (optional)|Personal portfolios|
|🔹 ECS Fargate + NGINX|Docker + ECS + ALB + Route53|Containers, task definitions, IAM, networking, Load Balancer|DevOps container orchestration|
|🔹 **6. EC2 with NGINX**|**Manual VM + NGINX**|**Linux, SSH, web server config, firewall**|**Ground-level sysadmin skills**|
|🔹 Kubernetes (EKS / K3s)|Helm, Ingress, LoadBalancer, CertManager|Cluster concepts, services, scaling|Advanced DevOps learning|

## Learning Milestones

This project is organized around real-world DevOps workflows. Each milestone focuses on a set of tools and practices, with clear learning goals and completion criteria.

### ~~Milestone 1: Serve a Static Website Manually~~

#### Learning Goals

- Understand Linux basics (firewall, SSH, systemd)
- Configure a basic Nginx web server

#### Tools

- EC2, Nginx, Linux, SSH

#### Done When

- Static site is served via Nginx on EC2
- SSH and firewall are correctly configured

---

### ~~Milestone 2: Containerize the Application~~

#### Learning Goals

- Learn how to build and run Docker containers
- Understand how to push images to a container registry

#### Tools

- Docker, Docker Hub

#### Done When

- Site runs from a containerized Nginx setup
- Image pushed to remote registry

---

### Milestone 3: Add CI/CD Pipeline

#### Learning Goals

- Automate Docker builds and deployments with GitHub Actions
- Use secrets and deploy keys securely

#### Tools

- GitHub Actions, SSH, Docker

#### Done When

- Commits trigger pipeline that builds & deploys container to EC2

---

### Milestone 4: TLS & HTTPS

#### Learning Goals

- Understand TLS certificates and secure web hosting
- Automate issuance and renewal with Let's Encrypt

#### Tools

- Let's Encrypt, Certbot, Nginx TLS config

#### Done When

- HTTPS enabled with automatic certificate renewal

---

### Milestone 5: Infrastructure as Code

#### Learning Goals

- Provision and manage infrastructure using Terraform

#### Tools

- Terraform, AWS (EC2, Route53)

#### Done When

- EC2, DNS, and security groups are created via Terraform scripts

---

### Milestone 6: Configuration as Code

#### Learning Goals

- Automate server configuration and deployments using Ansible

#### Tools

- Ansible, SSH

#### Done When

- Server configuration fully managed by Ansible playbooks

---

### Milestone 7: Monitoring and Observability

#### Learning Goals

- Collect and visualize system metrics
- Explore logs, traces, and alerts

#### Tools

- Prometheus, Grafana, Node Exporter, Docker Compose

#### Done When

- Grafana dashboard displays live metrics

## Current state

- Simple static site
- Containerized with Nginx
- Delivered to AWS EC2 (plain virtual machine)
- Simple CI/CD that builds container and pushes it to VM on commit to main branch
- Some new step

## Next steps

- [ ] Configure TLS via Let's Encrypt
- [ ] Add linter to CI stage
- [ ] Add Prometheus & Grafana for monitoring
- [ ] Move to Configuration as Code with Ansible
