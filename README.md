# AWS EC2 Web Server Deployment & Monitoring

## Overview

I deployed a publicly accessible website on an Amazon EC2 instance running Amazon Linux 2023. I installed Apache HTTP Server, created a custom HTML page, configured AWS Systems Manager Session Manager for remote administration, and created a CloudWatch alarm to monitor CPU utilization.

## AWS Services and Technologies

- Amazon EC2
- Amazon Linux 2023
- Apache HTTP Server
- AWS Systems Manager Session Manager
- AWS Identity and Access Management (IAM)
- Amazon CloudWatch
- Amazon VPC and security groups
- HTML

## Architecture

1. A user accesses the website through a browser over HTTP on port 80.
2. An EC2 instance runs Amazon Linux 2023 and Apache.
3. A security group allows inbound HTTP traffic on port 80.
4. Systems Manager Session Manager provides remote administration without inbound SSH access.
5. CloudWatch monitors EC2 CPU utilization and evaluates it against a configured alarm threshold.

## Implementation Steps

1. Launched an EC2 instance running Amazon Linux 2023.
2. Configured the instance's networking and security group.
3. Created an IAM role for Systems Manager access.
4. Connected using Systems Manager Session Manager.
5. Installed Apache using `sudo dnf install httpd -y`.
6. Enabled Apache using `sudo systemctl enable --now httpd`.
7. Created a custom webpage at `/var/www/html/index.html`.
8. Tested the page with `curl http://localhost` and verified it in a browser.
9. Configured a CloudWatch alarm for CPU utilization.

## Skills Practiced

- Linux command-line administration
- EC2 deployment and management
- AWS networking and security groups
- IAM roles and permissions
- Systems Manager remote administration
- Apache web server configuration
- CloudWatch monitoring and alarms
- Troubleshooting connectivity issues

## Security Considerations

- Used Systems Manager Session Manager for remote administration.
- Removed the inbound SSH rule when it was no longer needed.
- Allowed HTTP traffic for the demo website. HTTP is unencrypted and should not be used for sensitive information.
- Reviewed IAM permissions and security group rules.

## Future Improvements

- Configure HTTPS using a domain name and TLS certificate.
- Create a CloudWatch dashboard.
- Explore automated deployment and infrastructure as code.

## Project Purpose

This hands-on project helped me practice deploying, administering, and monitoring a basic web server on AWS.
