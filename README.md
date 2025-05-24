# personal-web-page

My personal web server setup

Since it's an educational project, I want to try various ways to build and deliver static content

## Ways to serve static content

|Option|Tech Stack|Learnings|Good For|
|------|----------|---------|--------|
|🔹 1. S3 Static Hosting|S3 + Route53 + (optional CloudFront)|DNS, public access control, bucket policies, HTTP basics|Beginners, cloud intro|
|🔹 2. CloudFront + S3 + ACM|CDN + SSL + caching|CDN config, SSL/TLS, performance tuning|Real-world hosting, HTTPS|
|🔹 3. Netlify / Vercel|Git repo → deploy|GitOps, CI/CD, auto-deploy, env vars|Modern frontend workflows|
|🔹 4. GitHub Pages|Git + static files|GitHub Actions, Jekyll (optional)|Personal portfolios|
|🔹 5. ECS Fargate + NGINX|Docker + ECS + ALB + Route53|Containers, task definitions, IAM, networking, Load Balancer|DevOps container orchestration|
|🔹 6. EC2 with NGINX|Manual VM + NGINX|Linux, SSH, web server config, firewall|Ground-level sysadmin skills|
|🔹 7. Kubernetes (EKS / K3s)|Helm, Ingress, LoadBalancer, CertManager|Cluster concepts, services, scaling|Advanced DevOps learning|

## Currrent state

- Simple static site
- Encapsuled in container with nginx
- Delivered to AWS EC2 (plain virtual machine)
