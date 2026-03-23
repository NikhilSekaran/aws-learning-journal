# AWS Key Terms & Glossary

> Updated progressively as modules are documented. Currently, covers **Modules 1–3: Introduction to the Cloud, Compute in the Cloud & Exploring Compute Services**.

---

## A

**Auto Scaling**
- AWS service that automatically adjusts the number of EC2 instances based on demand
- Defined by minimum, desired, and maximum capacity
- Can scale dynamically (real-time) or predictively (ML-based)
- Reduces costs by scaling down when demand is low

**Availability Zone (AZ)**
- A physically distinct, isolated location within an AWS Region
- Each Region has 3 or more AZs
- Separated to protect against localized disasters (floods, power failures, etc.)
- Connected to other AZs in the same Region via low-latency links

## C

**Client-Server Model**
- Fundamental computing architecture where a client makes a request and a server responds
- Cloud computing is built on this model
- Example: a browser (client) requests a webpage from a web server

**Cloud Computing**
- The on-demand delivery of IT resources over the internet with pay-as-you-go pricing
- Eliminates the need to own or manage physical data centres

**Cloud Deployment**
- A deployment model where all components are hosted and managed in the cloud
- Also called Public Cloud
- Best for new applications and teams wanting to minimize infrastructure management

**Compute**
- The processing power needed to run applications, manage data, and perform calculations
- In the cloud, delivered on-demand through services like EC2

**Container**
- A lightweight, portable package that bundles application code with all its runtime dependencies (libraries, configs)
- Ensures consistent behaviour across environments (dev, staging, production)
- Shares the host OS kernel — more efficient than full VMs
- Standard format is OCI (Open Container Initiative)

**Container Orchestration**
- Automated management of containerized workloads: deployment, scaling, scheduling, and health monitoring
- Required when running many containers across multiple hosts
- AWS tools: ECS (proprietary) and EKS (Kubernetes-based)

**Container Registry**
- A repository for storing, versioning, and distributing container images
- AWS service: Amazon ECR (Elastic Container Registry)
- Works like a Git repository, but for container images

## E

**EC2 (Elastic Compute Cloud)**
- AWS service providing on-demand virtual servers (instances) in the cloud
- Offers flexible compute capacity that scales up or down based on needs
- Key features: multiple instance types, various pricing models, Auto Scaling integration

**ECR (Elastic Container Registry)**
- Fully managed container image registry for storing Docker/OCI images
- Integrates natively with ECS, EKS, and Fargate
- Role in the workflow: store → push/pull images for deployment

**ECS (Elastic Container Service)**
- Fully managed container orchestration service for running Docker containers
- Launch types: EC2 (you manage hosts) or Fargate (serverless)
- AWS-native; simpler to operate than Kubernetes

**EKS (Elastic Kubernetes Service)**
- Fully managed Kubernetes service for deploying and scaling containerized applications
- Uses upstream Kubernetes; compatible with the open-source Kubernetes ecosystem
- Launch types: EC2 or Fargate; preferred for Kubernetes-familiar teams or hybrid deployments

**Elastic Beanstalk (AWS Elastic Beanstalk)**
- Fully managed PaaS for deploying web applications
- Upload code → Beanstalk handles provisioning (EC2, Auto Scaling, ELB, monitoring)
- Retains full access to underlying AWS resources
- Supports: Java, .NET, Python, Node.js, Ruby, Go, Docker

**Elastic Load Balancing (ELB)**
- AWS service that automatically distributes incoming traffic across multiple EC2 instances
- Acts as single entry point for applications
- Prevents bottlenecks and improves availability
- Decouples frontend and backend tiers, enabling independent scaling

**Elasticity**
- The ability to automatically scale resources up or down in response to real-time demand
- Resources adjust dynamically (minute-by-minute or hour-by-hour)
- Enables cost efficiency by paying only for resources used

**EventBridge**
- Serverless event bus service that routes events from sources to targets based on rules
- Enables event-driven architectures
- Integrates AWS services and third-party applications

## F

**Fargate (AWS Fargate)**
- Serverless compute engine for containers; works as a launch type for ECS and EKS
- Removes the need to manage EC2 instances — AWS handles host provisioning, patching, scaling
- Pay for vCPU and memory used; no idle infrastructure costs
- Key distinction: Fargate is compute, not an orchestrator; ECS/EKS provide orchestration

**Function as a Service (FaaS)**
- Cloud execution model where developers upload individual functions rather than full servers
- Runtime infrastructure is fully managed by the cloud provider
- Key characteristics: event-driven, stateless, scales automatically, pay-per-execution
- AWS implementation: AWS Lambda

**Fault Tolerance**
- System design that allows continued operation even when multiple components fail simultaneously
- Achieved by spreading workloads across multiple AZs and Regions with redundant infrastructure
- Goes beyond high availability — the system doesn't just recover quickly, it keeps running

## H

**High Availability**
- Ensuring applications remain accessible with minimal downtime
- Achieved by distributing resources across multiple AZs so if one fails, others pick up
- If one AZ has an outage, workloads in other AZs continue uninterrupted

**Hybrid Deployment**
- A deployment model combining cloud-based resources and on-premises infrastructure
- Best for organizations with legacy systems that cannot fully move to the cloud

**Horizontal Scaling**
- Adding more instances (machines) to distribute the workload
- Best for stateless applications and web servers
- Can scale out indefinitely (limited by AWS account limits)

**Hypervisor**
- Software that manages multi-tenancy by isolating EC2 instances from each other
- Allocates physical resources to virtual machines
- Ensures one instance doesn't interfere with others on the same physical host

## I

**Instance Type**
- Classification of EC2 instances based on hardware capabilities
- **General Purpose** — Balanced compute, memory, networking (default choice)
- **Compute Optimized** — High-performance CPUs for compute-intensive work
- **Memory Optimized** — High memory for in-memory databases and caches
- **Accelerated Computing** — GPUs for graphics and ML acceleration
- **Storage Optimized** — High I/O for databases and data warehousing

## K

**Kubernetes**
- Open-source container orchestration platform for automating deployment, scaling, and management of containerized applications
- Organizes containers into logical units called pods; pods are grouped into clusters
- AWS managed offering: Amazon EKS (Elastic Kubernetes Service)
- Key advantage over ECS: ecosystem portability — same workloads can run on any cloud or on-prem Kubernetes cluster

## L

**Lambda (AWS Lambda)**
- Serverless compute service (FaaS) that runs code in response to events without managing servers
- Event-driven: triggered by S3, SQS, API Gateway, EventBridge, etc.
- Maximum execution duration: 15 minutes per invocation
- Shared Responsibility: AWS manages OS, runtime, scaling; customer manages code and IAM

**Lightsail (Amazon Lightsail)**
- Simplified cloud platform offering VPS, storage, databases, and networking at fixed monthly pricing
- Designed for lower complexity use cases and teams new to cloud
- Best for: small websites, blogs, dev/test environments, simple web apps

**Loosely Coupled Architecture**
- System where components communicate through intermediaries (queues, buses) rather than direct connections
- Failures in one component don't cascade to others
- Components can scale independently
- Enables flexibility and resilience

## M

**Machine Image (AMI)**
- Pre-configured template for launching EC2 instances
- Contains: operating system, storage configuration, architecture type, pre-installed software
- Ensures all instances launched from the same AMI are identical
- Can be AWS-provided, custom-built, or purchased from AWS Marketplace

**Managed Service**
- AWS service where AWS handles operational tasks like OS patching, scaling, availability, and backups
- Customer still configures and uses the service but doesn't manage underlying infrastructure
- Spectrum: EC2 (unmanaged) → ECS/Lambda (managed/fully managed)
- Examples: Amazon RDS, ECS, Lambda, SQS

**Multi-Tenancy**
- Infrastructure design where multiple customer instances share physical hardware
- Hypervisor provides isolation so instances can't interfere with each other
- Enables AWS to maximize resource utilization and offer lower costs

## O

**On-Demand**
- Resources available for use at any time without pre-planning or pre-purchasing
- A core characteristic of cloud computing

**On-Demand Instances**
- EC2 pricing model where you pay per hour/second for compute capacity
- No upfront commitment or long-term contract required
- Most flexible but highest per-unit cost
- Best for unpredictable workloads and development/testing

**On-Premises Deployment**
- Resources deployed in a company's own data center using virtualization tools
- Provides full infrastructure control but misses most cloud benefits

**Outposts (AWS Outposts)**
- Fully managed hybrid cloud solution extending AWS infrastructure to on-premises data centers
- Run AWS services locally with the same APIs and operational models as AWS regions
- Use cases: data residency/compliance requirements, low-latency local processing, regulated industries

## P

**Pay-as-You-Go**
- Cost model where you only pay for resources during actual consumption
- No upfront investment; billing varies month to month based on usage
- Contrasts with traditional fixed-cost data center spending

**Pricing Models (EC2)**
- **On-Demand** — Pay per hour; maximum flexibility
- **Reserved Instances** — Commit 1–3 years; up to 75% discount
- **Spot Instances** — Bid on spare capacity; up to 90% discount; interruption risk
- **Savings Plans** — Commit to hourly spend; up to 72% discount; flexible across instance types
- **Dedicated Hosts** — Exclusive physical server; for compliance and licensing

## R

**Region**
- A physically separate geographic location where AWS maintains clusters of data centres
- Examples: us-east-1 (N. Virginia), eu-west-1 (Ireland), ap-southeast-1 (Singapore)
- Regions are isolated from each other; businesses can operate across multiple Regions for resilience

**Reserved Instances (RI)**
- EC2 pricing model requiring 1–3 year commitment
- Provides up to 75% discount compared to On-Demand
- Best for predictable, steady-state workloads (e.g., production databases)
- Inflexible; bound to specific instance family and Region

## S

**Scalability**
- The ability of a system to handle increased load by adding resources over time
- Long-term capacity planning for anticipated growth
- Can be achieved through vertical scaling (bigger instance) or horizontal scaling (more instances)

**Serverless Computing**
- Cloud execution model where the provider fully manages the underlying infrastructure
- Developer focuses solely on application code — no servers to provision, patch, or scale
- AWS implements serverless at different levels: Lambda (functions), Fargate (containers), Aurora Serverless (databases)
- Key benefit: automatic scaling, pay-per-use, no idle capacity costs

**Shared Responsibility Model**
- Security framework dividing responsibilities between AWS and the customer
- **AWS**: Security *of* the cloud — hardware, networking, facilities, hypervisor
- **Customer**: Security *in* the cloud — OS, applications, data, access control
- **Shared**: Server-side encryption, network traffic protection, firewall config (varies by service)

**SNS (Simple Notification Service)**
- AWS messaging service for sending notifications to multiple subscribers
- Pub-Sub model where publishers send messages to topics and subscribers receive instantly
- Supports multiple endpoints: email, SMS, mobile push, Lambda, SQS
- Real-time delivery to many recipients from a single message

**Spot Instances**
- EC2 pricing model that bids on spare AWS capacity
- Up to 90% discount compared to On-Demand
- AWS can reclaim instance with 2-minute warning when capacity needed by On-Demand customers
- Best for batch processing, data analysis, ML training—any interruption-tolerant work

**SQS (Simple Queue Service)**
- AWS message queuing service that decouples application components
- Stores messages reliably until receiver processes them
- Receiver pulls messages at its own pace (asynchronous)
- Messages persist until explicitly deleted; guarantees "at least once" delivery

## T

**Tightly Coupled Architecture**
- System where components communicate directly (no intermediaries)
- Failure in one component cascades to others
- Difficult to scale or modify
- Contrasts with loosely coupled architecture

## U

**Unmanaged Service**
- AWS service where the customer is responsible for all operational tasks: OS patching, security hardening, scaling, and availability
- Provides maximum control and flexibility at the cost of operational overhead
- Primary example: Amazon EC2 — AWS provides the hypervisor and hardware; everything above is the customer's responsibility

## V

**Vertical Scaling**
- Adding more power (CPU, memory, storage) to an existing instance
- Makes an instance "bigger"
- Limited by maximum instance size available
- Simpler but less flexible than horizontal scaling

---

**Note**: This glossary grows as modules are documented. New terms added as each module is completed. Currently includes all conceptual and service-level terms from Modules 1–3.
