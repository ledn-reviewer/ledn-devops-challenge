# Ledn DevOps Challenge

# Introduction

Thank you for your interest in working at Ledn. We’re looking forward to meeting you.  
To guide our technical conversation, we’d like you to complete a small practical project.

The goal is to see how you think, how you structure infrastructure, and how you reason about trade-offs. This is **not** about building something “perfect”, but about showing your judgment.

**Why a take-home challenge?**

In-person coding interviews can be stressful and may hide your full potential. A take-home gives you a chance to work in a less stressful environment and showcase your talent.

# Overview

Design and implement a small, highly-available web service on AWS using Infrastructure as Code and containers.

When designing the solution, please:

* Follow AWS and industry best practices where reasonable.  
* Design for **high availability** and **scalability**.  
* Use a **modular** approach and clear separation of concerns.  
* Automate as much as is practical (build, deploy, infra).

# Objective

Launch a simple website in a **load-balanced** and **highly available** manner on AWS, using containers and IaC, with:

* CI/CD pipeline  
* Basic monitoring and scaling  
* Security considerations and proposals for improvement

The web application itself can be very simple. The focus is on **infrastructure**, **automation**, and **operations**.

## Scope & Constraints

To keep the scope realistic and costs low:

* Target **one environment** (e.g., `prod` or `demo`) is enough.  
* Use **low-cost** instances / services. Although we ask for 2 AZs, services can scale in 1 AZ only to reduce cross-AZ cost if needed.  
* You’re responsible for **tearing down all resources** when you’re done.  
* You may use an existing AWS account; don’t share any credentials with us.

## Requirements

### **1\. Application**

* Simple HTTP service returning:  
  * “Hello World”  
  * Your name  
  * Environment name  
  * Build, version or commit ID  
* Provide the `Dockerfile`.

### **2\. Infrastructure (Terraform)**

Use **Terraform** to provision the infrastructure. If you strongly prefer another IaC tool, you may use it **but you must explain why** and what trade-offs you see compared to Terraform.

Provision infrastructure following AWS best practices:

* VPC with at least 2 AZs  
* Public or ALB-facing subnets  
* Load balancer routing to your containerized service  
* Compute of your choice: **EC2,** **ECS**, **EKS**, or **Lambda with container**  
* Everything defined as IaC using Terraform (modular structure preferred)

### **3\. CI/CD**

A pipeline that:

* Builds & tests the application  
* Builds & pushes the image to ECR (or alternative)  
* Deploys the new version using Terraform or another method you justify

Any CI system is acceptable (GitHub Actions, GitLab CI, CircleCI, CodePipeline, etc.).

### **4\. Monitoring & Scaling**

* Basic monitoring (CloudWatch or equivalent): at least 1 metric, 1 alarm  
* Autoscaling of the container based on CPU, requests, or another metric  
* Brief explanation or screenshot of how you tested scaling

### **5\. Deliverables**

A Git repository containing:

* Application code \+ Dockerfile  
* Terraform code  
* CI/CD configuration  
* A brief **README** with:  
  * Architecture summary \+ tiny diagram  
  * How to deploy & destroy  
  * Design choices & trade-offs  
  * Monitoring & scaling notes  
  * Security improvement plan

### **6\. Bonus (Optional)**

* EKS deployment  
* Lambda-based version  
* Extra observability (dashboards, tracing)

# Evaluation Criteria

We will evaluate based on:

1. **Architecture & HA**  
   * Clear multi-AZ setup, load balancing, stateless design.  
2. **Terraform Quality**  
   * Clean structure, modularity, variable use, readability.  
3. **CI/CD Implementation**  
   * Completeness of build/test/push/deploy stages.  
4. **Monitoring & Scaling**  
   * Reasonable metrics, alarms, and functional autoscaling.  
5. **Security Hygiene**  
   * Sensible defaults, least privilege, secure patterns.  
6. **Documentation & Clarity**  
   * README quality, ability to explain choices and trade-offs.  
7. **Bonus Features**  
   * Kubernetes, serverless, or advanced observability.

**Important**: During the interview process, you may be asked to explain any part of your solution, including sections where AI was used. Be prepared to discuss your decision-making process and demonstrate understanding of all implemented solutions.

# Submission

* Please host your repository on GitHub and make it private.  
* Include this README file in your repo.  
  * Add any documentation / steps to be followed to the README.md file  
* Invite **Ledn-Reviewer** to your project once it is ready.  
* Email us to confirm that **Ledn-Reviewer** has been added as a contributor and your project is ready for review.

# Following Steps

Upon submission of the challenge, we will review your code and reach out to you with comments. If your submission passes our criteria, a following interview will be scheduled to discuss your implementation in further detail. On the day of the technical interview, the infrastructure should be already instantiated and running.

We feel this is another great way to assess your understanding rather than on the spot coding exercises\!  
We want you to succeed as much as you do, so we wish you the best of luck\! Looking forward to your submission\!
