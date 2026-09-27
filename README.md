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

- so far as of 9/27, I use Claude to help me however I am learning the general idea of everything, from creating main.tf file and adding the needed content. To creating an output and variables file and adding relevant content. Then having terraform run everything while it make sures the code stays idempotent. I also learnt how to push everything online to be made accessible and also load balancing to make sure traffic is managed well to maintain uptime. I need to learn next how to expand and create my code from scratch and also how to store remotely.
