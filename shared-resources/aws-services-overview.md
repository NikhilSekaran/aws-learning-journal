# AWS Services Overview

> Quick reference for AWS services encountered in courses. Updated progressively as modules are documented. Currently covers **Modules 1–4**.

---

## Module 1: Introduction to the Cloud Concepts
Module 1 focuses on foundational cloud concepts rather than specific AWS services. Services are introduced in detail from Module 2 onwards.

**Source Notes**: [Module 1 Notes](../courses/aws-cloud-practitioner-essentials/modules/module-01-introduction-to-the-cloud/notes.md)

### Key Historical Services Mentioned

**Amazon SQS (Simple Queue Service)**
- AWS's first publicly launched service (November 2004)
- Message queuing service enabling decoupled application components

---

## Module 2: Compute Services

**Source Notes**: [Module 2 Notes](../courses/aws-cloud-practitioner-essentials/modules/module-02-compute-in-the-cloud/notes.md)

### Amazon EC2 (Elastic Compute Cloud)
**What it is**: On-demand virtual servers in the cloud with flexible computing capacity

**Key Features**:
- Launch, scale, and terminate instances on-demand
- Choose from various instance types optimized for different workloads
- Multiple pricing models (On-Demand, Reserved, Spot, Savings Plans, Dedicated)
- Auto Scaling capability to automatically adjust capacity based on demand

**Instance Types**:
- **General Purpose** (m5, m6) — Balanced compute, memory, networking; default choice
- **Compute Optimized** (c5, c6) — High-performance CPUs for compute-intensive work
- **Memory Optimized** (r5, r6) — High memory for large in-memory databases and caches
- **Accelerated Computing** (p3, g4) — GPUs for graphics and ML acceleration
- **Storage Optimized** (i3, h1) — High I/O performance for locally stored data

**Pricing Models**:
- **On-Demand** — Pay by the hour/second; no commitment; most flexible
- **Reserved Instances** — 1–3 year commitment; up to 75% discount
- **Spot Instances** — Bid on spare capacity; up to 90% discount; interruption risk
- **Savings Plans** — Commit to hourly spend; up to 72% discount; flexible across instance types/regions
- **Dedicated Hosts** — Entire physical server for exclusive use; compliance and licensing control

**Use Cases**: Web servers, application servers, batch processing, machine learning training, databases

---

### Amazon EC2 Auto Scaling
**What it is**: Automatically adjusts the number of EC2 instances to maintain application performance and availability

**Key Concepts**:
- **Minimum Capacity** — Least number of instances always running
- **Desired Capacity** — Target number AWS aims to maintain
- **Maximum Capacity** — Upper limit to control costs

**Scaling Types**:
- **Dynamic Scaling** — Real-time adjustment based on current demand 
- **Predictive Scaling** — ML-based, anticipates demand from historical patterns

**Benefits**: Cost efficiency (pay only for what you use), high availability, automatic response to demand changes

---

### Elastic Load Balancing (ELB)
**What it is**: Automatically distributes incoming application traffic across multiple EC2 instances or other targets

**Key Features**:
- Single entry point for all traffic
- Intelligent routing strategies (Round Robin, Least Connections, IP Hash, Least Response Time)
- Works seamlessly with Auto Scaling
- Enables architectural decoupling (tiers scale independently)

**Routing Methods**:
- **Round Robin** — Equal distribution across servers
- **Least Connections** — Routes to server with fewest active connections
- **IP Hash** — Session persistence based on client IP
- **Least Response Time** — Routes to fastest responding server

**Benefits**: Prevents bottlenecks, improves availability, decouples frontend/backend tiers, simplifies architecture

---

### Amazon SQS (Simple Queue Service)
**What it is**: Fully managed message queue service that decouples application components

**Key Features**:
- Stores messages reliably in a queue
- Receivers process messages at their own pace
- Messages persist until explicitly deleted
- Guarantees "at least once" delivery
- Automatically scales to handle any volume

**Use Cases**: 
- Order processing
- Task queues
- Batch processing
- Decoupling microservices

**Benefits**: Prevents message loss, enables asynchronous processing, decouples sender and receiver

---

### Amazon SNS (Simple Notification Service)
**What it is**: Fully managed pub-sub messaging service for sending notifications to multiple subscribers

**Key Features**:
- Publish messages to topics
- Multiple subscribers receive messages instantly
- Supports multiple endpoints (email, SMS, mobile push, Lambda, SQS)
- Fan-out capability (one message → many subscribers)

**Use Cases**:
- Email notifications
- SMS alerts
- Mobile push notifications
- Broadcasting to multiple systems

**Benefits**: Real-time delivery, multi-channel support, flexible subscribers

---

### Amazon EventBridge
**What it is**: Serverless event bus that routes events from sources to targets based on rules

**Key Features**:
- Routes events between AWS services and third-party applications
- Rule-based event routing
- Supports configured retry, DLQ, and archive/replay patterns depending on setup
- Serverless (no infrastructure to manage)

**Use Cases**:
- Event-driven architectures
- Coordinating microservices
- Integration between applications
- Responding to AWS resource changes

**Benefits**: Simple event routing, serverless, reliable delivery, flexible routing rules

---

## Module 3: Exploring Compute Services

**Source Notes**: [Module 3 Notes](../courses/aws-cloud-practitioner-essentials/modules/module-03-exploring-compute-services/notes.md)

### AWS Lambda
**What it is**: Serverless compute service (Function as a Service) that runs code in response to events without provisioning or managing servers

**Key Features**:
- Event-driven: code runs only when triggered (S3 upload, SQS message, HTTP request, etc.)
- Automatically scales from 1 to thousands of concurrent executions
- Maximum execution duration: 15 minutes per invocation
- Billed per millisecond of compute time; cost depends on memory allocated

**Key Components**:
- **Lambda function** — your code package
- **Trigger** — event source that initiates execution
- **Runtime** — language environment (Python, Java, Node.js, or custom)
- **Execution role** — IAM role granting permissions to other AWS services

**Shared Responsibility**: AWS owns OS patching, scaling, and availability; customer owns application code security and IAM permissions

**Use Cases**: API backends, real-time file processing, stream processing, scheduled automation, event-driven microservices

---

### Amazon ECS (Elastic Container Service)
**What it is**: Fully managed container orchestration service for running Docker containers on AWS

**Key Features**:
- Manages container lifecycle: deployment, scaling, health monitoring
- Two launch types: EC2 (full infrastructure control) or Fargate (serverless)
- Integrates natively with ECR, ELB, IAM, and CloudWatch

**Use Cases**: Microservices, API backends, containerized web applications

---

### Amazon EKS (Elastic Kubernetes Service)
**What it is**: Fully managed Kubernetes service for deploying, managing, and scaling containerized applications

**Key Features**:
- Runs upstream Kubernetes — open-source ecosystem compatible
- Two launch types: EC2 (full control) or Fargate (serverless)
- Best for teams requiring Kubernetes portability or large-scale/hybrid deployments

**Use Cases**: Large-scale containerized workloads, hybrid cloud Kubernetes clusters, teams migrating from on-prem Kubernetes

---

### Amazon ECR (Elastic Container Registry)
**What it is**: Fully managed container image registry for storing, managing, and deploying container images

**Key Features**:
- Supports OCI (Open Container Initiative) standard images
- Integrates natively with ECS, EKS, and Fargate
- Push/pull images using standard container CLI tools
- Secure, versioned image storage

**Use Cases**: Store and version container images as part of CI/CD pipelines

---

### AWS Fargate
**What it is**: Serverless compute engine for containers — provides the server infrastructure for ECS tasks and EKS pods without requiring you to manage servers

**Key Features**:
- Works with both Amazon ECS and Amazon EKS
- No EC2 instances to provision, patch, or manage
- Pay only for the vCPU and memory used by containers

**Distinction**: Fargate is compute; ECS/EKS are orchestration. Fargate is a launch type option, not a standalone orchestrator.

**Use Cases**: Serverless containerized workloads, variable-traffic microservices, teams wanting operational simplicity

---

### AWS Elastic Beanstalk
**What it is**: Fully managed platform-as-a-service (PaaS) for deploying and scaling web applications

**Key Features**:
- Upload code → Beanstalk provisions environment automatically (EC2, scaling, ELB, monitoring)
- Supports: Java, .NET, Python, Node.js, Ruby, Go, Docker, and more
- Save and reuse environment configurations
- Retains full visibility and control over underlying AWS resources

**Use Cases**: Web applications, REST APIs, mobile backends, microservices with simple deployment needs

---

### AWS Batch
**What it is**: Fully managed service for running large-scale batch computing workloads

**Key Features**:
- Automatically provisions and scales compute resources (EC2/Spot) based on job queue
- Schedules and distributes jobs across compute fleets
- No infrastructure management required

**Use Cases**: Scientific simulations, financial analysis, media transcoding, genomics, ML training data processing

---

### Amazon Lightsail
**What it is**: Simplified cloud platform providing VPS, storage, databases, and networking at predictable monthly pricing

**Key Features**:
- Pre-configured virtual private servers
- Simple management interface — lower complexity than full AWS Console
- Predictable, fixed monthly pricing

**Use Cases**: Small websites, blogs, dev/test environments, basic web apps, beginners learning cloud

---

### AWS Outposts
**What it is**: Fully managed hybrid cloud solution that extends AWS infrastructure and services to on-premises data centers

**Key Features**:
- Run AWS services locally with the same APIs, tools, and operational models as AWS regions
- Provides compute, storage, and networking on-premises
- Consistent hybrid cloud experience

**Use Cases**: Low-latency applications, data residency/compliance requirements, remote/edge processing, migrating legacy applications

---

## Module 4: Going Global

**Source Notes**: [Module 4 Notes](../courses/aws-cloud-practitioner-essentials/modules/module-04-going-global/notes.md)

### AWS CloudFormation
**What it is**: Infrastructure as code (IaC) service that models and provisions AWS resources from declarative templates

**Key Features**:
- Define infrastructure in version-controlled text templates
- Consistent, repeatable provisioning across accounts and Regions
- Automates API calls in the background to create required resources
- Helps reduce manual configuration drift and deployment errors

**Use Cases**: CI/CD infrastructure pipelines, multi-Region rollout consistency, repeatable environment setup

---

### Amazon CloudFront
**What it is**: Content delivery network (CDN) that caches and serves content from edge locations close to end users

**Key Features**:
- Delivers images, videos, APIs, and application content with low latency
- Uses AWS global edge network outside standard Region boundaries
- Improves user experience by reducing content retrieval time

**Use Cases**: Global web content delivery, media distribution, API acceleration

---

### AWS Global Accelerator
**What it is**: Networking service that improves performance by routing traffic through the AWS global network

**Key Features**:
- Improves path selection from users to application endpoints
- Supports globally distributed application entry patterns
- Complements edge and global deployment architectures

**Use Cases**: Global applications requiring improved performance and availability routing

---

### Amazon Route 53
**What it is**: Managed DNS service that routes user requests to internet applications

**Key Features**:
- Translates human-readable domain names into machine-readable IP addresses
- Supports global traffic routing patterns
- Integrates with other AWS services for resilient endpoint resolution

**Use Cases**: Domain management, global DNS routing, highly available application endpoints

---

## Service Comparison Matrix

| **Service** | **Type** | **Use Case** | **Key Benefit** |
|:---|:---|:---|:---|
| **EC2** | Compute (IaaS) | Virtual servers | Maximum control & flexibility |
| **Auto Scaling** | Scaling | Dynamic capacity adjustment | Cost efficiency + HA |
| **ELB** | Load Balancing | Traffic distribution | Decouples tiers, prevents bottlenecks |
| **SQS** | Messaging | Queue-based processing | Reliable, asynchronous decoupling |
| **SNS** | Messaging | Pub-Sub notifications | Real-time multi-subscriber delivery |
| **EventBridge** | Event Bus | Event routing | Serverless, rule-based routing |
| **Lambda** | Serverless Compute | Event-driven functions | No servers; pay per invocation |
| **ECS** | Container Orchestration | Docker container management | AWS-native, fully managed |
| **EKS** | Container Orchestration | Kubernetes workloads | Open-source Kubernetes on AWS |
| **ECR** | Container Registry | Container image storage | OCI-compliant, integrated with ECS/EKS |
| **Fargate** | Serverless Container Compute | Run containers without servers | Works with ECS & EKS |
| **Elastic Beanstalk** | PaaS | Web app deployment | Auto-provisions infra from code |
| **AWS Batch** | Batch Compute | Large-scale scheduled jobs | Auto-scales; no infrastructure management |
| **Lightsail** | Simplified Cloud | VPS + storage + networking | Predictable pricing; simple setup |
| **Outposts** | Hybrid Cloud | AWS on-premises | Consistent AWS experience locally |
| **CloudFormation** | IaC / Automation | Template-based infrastructure provisioning | Repeatable and consistent deployments |
| **CloudFront** | CDN / Edge | Low-latency global content delivery | Cached delivery from edge locations |
| **Global Accelerator** | Networking | Global traffic acceleration | Improved path performance and availability |
| **Route 53** | DNS | Domain routing to applications | Global DNS with resilient routing |

---

## Key Architecture Patterns

### Pattern 1: Auto Scaling + ELB
```
ELB (Single Entry Point)
  ↓
Auto Scaling Group
  ├─ Instance 1
  ├─ Instance 2
  ├─ Instance 3 (added dynamically)
  └─ Instance 4 (added dynamically)
```
**Benefit**: Automatic scaling with even traffic distribution

### Pattern 2: Loosely Coupled Messaging
```
Producer (EC2)
  ↓
SQS Queue
  ↓
Consumer (EC2)
```
**Benefit**: Producer and consumer scale independently; no message loss

### Pattern 3: Event-Driven Architecture
```
Event Source (EC2, S3, etc.)
  ↓
EventBridge
  ↓
Multiple Targets (Lambda, SQS, SNS, EC2)
```
**Benefit**: Serverless event routing; decoupled components

---

**Note**: This is a growing reference. Services are added as modules are documented.
