# Azure App Service (AZ-204 Important Notes)

## Overview

Azure App Service is a **fully managed Platform-as-a-Service (PaaS)** offering used to build, deploy, and scale **web applications, REST APIs, and mobile backends**.

Developers can deploy applications without managing:

- Servers
- Operating systems
- Infrastructure
- Load balancing
- Patching

Azure handles these responsibilities automatically.

Because of this, developers can **focus on application development rather than infrastructure management**.

---

# Why Azure App Service is Important for AZ-204

Azure App Service is one of the **most important compute services** in the AZ-204 exam.

You must understand:

- How web apps are hosted
- Deployment options
- Configuration and environment variables
- Security and authentication
- Deployment slots
- Scaling strategies
- Monitoring and logging

---

# App Service Architecture

A web application in Azure App Service runs inside an **App Service Plan**.

Architecture hierarchy:
Resource Group
└── App Service Plan
└── App Service (Web App / API App)


### Explanation

Resource Group  
Logical container for Azure resources.

App Service Plan  
Defines the **compute resources** used by your web app.

Web App  
The actual **application being hosted**.

Multiple web apps can run in the same **App Service Plan**, sharing compute resources.

---

# Supported Application Types

Azure App Service supports multiple types of applications.

### Web Apps
Used to host traditional web applications.

Example:
- ASP.NET
- Node.js
- Python
- Java

### API Apps
Used to host **REST APIs**.

### Web Apps for Containers
Used to run **Docker containers**.

### Static Web Apps
Used for frontend applications like:

- React
- Angular
- Vue

---

# Supported Programming Languages

Azure App Service supports multiple runtimes.

- .NET
- Java
- Node.js
- Python
- PHP
- Ruby
- Go
- Custom containers

Because of this flexibility, it can support **most modern backend technologies**.

---

# App Service Plan (Very Important for AZ-204)

An **App Service Plan** defines the compute resources for your application.

It determines:

- Region
- Pricing tier
- VM size
- Scaling limits

All apps in the same App Service Plan **share the same compute resources**.

---

## App Service Plan Pricing Tiers

Common tiers include:

Free  
Shared  
Basic  
Standard  
Premium  
Isolated

### Important Differences

Free / Shared
- Limited resources
- No scaling
- Used for development/testing

Basic
- Dedicated VM
- Manual scaling

Standard
- Autoscaling
- Deployment slots
- Production use

Premium
- Better performance
- Faster scaling
- Advanced networking

Isolated
- Runs inside **Azure Virtual Network**

---

# Scaling in Azure App Service

Scaling is crucial for handling traffic.

Two types of scaling exist.

---

## Vertical Scaling (Scale Up)

Increasing the **size of the VM**.

Example: B1 → S1 → P1


Benefits:

- More CPU
- More RAM

Use when:
- Application requires more memory or CPU power.

---

## Horizontal Scaling (Scale Out)

Increasing the **number of instances**.

Example: 1 instance → 3 instances → 10 instances


Traffic is distributed using **Azure load balancer**.

Benefits:

- Better handling of high traffic
- Improved availability

---

## Autoscaling

Azure App Service supports **automatic scaling** based on rules.

Example rules:
If CPU > 70% → Add instance
If CPU < 30% → Remove instance


Autoscaling ensures:

- High availability
- Cost optimization

---

# Deployment Methods

Azure App Service supports multiple deployment methods.

---

## GitHub Deployment

Direct deployment from a GitHub repository.

CI/CD pipelines automatically deploy code when pushed.

---

## Azure DevOps

Used for advanced CI/CD pipelines.

Common workflow: Build → Test → Deploy

---

## Local Git Deployment

Developers can push code directly to Azure using Git.

---

## Zip Deployment

Upload a ZIP file containing application code.

---

## FTP Deployment

Legacy deployment method.

---

# Deployment Slots (Important AZ-204 Concept)

Deployment slots allow **safe deployments without downtime**.

Default slot: Production


Additional slots: 
Staging
Testing
Development


---

## Deployment Slot Workflow

1. Deploy application to **Staging slot**
2. Test the application
3. Swap with **Production slot**
Staging ↔ Production


Benefits:

- Zero downtime deployment
- Easy rollback
- Safe testing environment

---

## Slot Swap Behavior

During swap:

- Production traffic moves to staging
- Staging version becomes production

Important concept for AZ-204.

---

# Application Configuration

Application settings allow configuration **without modifying code**.

These values are stored as **environment variables**.

Example: 
DATABASE_CONNECTION_STRING
API_KEY
ENVIRONMENT=Production


Benefits:

- Secure configuration
- Environment-specific settings
- No redeployment required

---

# Connection Strings

Azure App Service allows storing connection strings securely.

Example services:

- Azure SQL Database
- MySQL
- PostgreSQL

Connection strings are injected as **environment variables**.

---

# Security and Authentication

Azure App Service provides **built-in authentication**.

This feature is called: Easy Auth

Developers do not need to write authentication code.

---

## Supported Identity Providers

- Azure Active Directory
- Microsoft Accounts
- Google
- Facebook
- Twitter

Benefits:

- Simplifies authentication
- Reduces security risks
- Integrates easily with Azure services

---

# TLS and HTTPS

Azure App Service supports secure communication using HTTPS.

Security features include:

- TLS/SSL encryption
- Custom domain certificates
- Managed certificates

You can configure: HTTPS Only Mode


This forces all traffic to use **secure connections**.

---

# Custom Domains

Applications can be mapped to custom domains.

Example: myapp.azurewebsites.net


Custom domain example: www.mycompany.com


Azure supports automatic SSL for custom domains.

---

# Logging and Monitoring

Azure App Service supports built-in logging.

Types of logs:

- Application logs
- Web server logs
- Detailed error logs
- Failed request tracing

Logs help developers **debug issues and monitor application health**.

---

# Application Insights Integration

Application Insights is used for **performance monitoring**.

Features include:

- Request tracking
- Exception tracking
- Performance metrics
- Dependency tracking

Example metrics:

- Response time
- Failure rate
- Request count

This helps identify **performance bottlenecks**.

---

# Networking Features

Azure App Service provides networking capabilities.

---

## VNet Integration

Allows web apps to connect to:

- Azure SQL Database
- Private APIs
- Internal services

---

## Access Restrictions

Restrict access to the application based on:

- IP address
- Virtual network

Example: Allow only company network


---

# Backup and Restore

Azure App Service supports automatic backups.

Backups can include:

- Application files
- Database connections
- Configuration settings

Backups help with **disaster recovery**.

---

# Containers in Azure App Service

Azure App Service supports **Docker containers**.

Images can be pulled from:

- Azure Container Registry
- Docker Hub
- Private registries

This allows developers to run **containerized applications**.

---

# Key AZ-204 Exam Takeaways

Important concepts that frequently appear in the exam:

- App Service vs App Service Plan
- Scaling (Scale Up vs Scale Out)
- Deployment slots
- CI/CD deployment
- Application settings
- Built-in authentication
- HTTPS configuration
- Application Insights monitoring
- Autoscaling
- Container deployment

Understanding these concepts is essential for both:

- **AZ-204 certification**
- **Real-world Azure application development**







