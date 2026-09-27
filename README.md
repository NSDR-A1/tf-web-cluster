# Highly Available Web Cluster on AWS

A load-balanced, self-healing web server cluster built with Terraform.

## Architecture

- **Application Load Balancer** on port 80, the single public entry point
- **Auto Scaling Group** running 2–4 Ubuntu servers across multiple availability zones
- **Launch template** defining each server, with a `user_data` startup script
- **Target group health checks**, so unhealthy servers are replaced automatically
- **Security groups** that allow traffic to the servers only from the load balancer, not directly from the internet

## Usage

```bash
terraform init
terraform apply
```

Visit the `alb_dns_name` output in a browser. Refreshing shows responses from different servers.

```bash
terraform destroy
```

Note: the load balancer is not free-tier. Destroy when finished.

## What I learned

- (write your own observations here)
