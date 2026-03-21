# AWS Key Terms & Glossary

> Updated progressively as modules are documented. Currently, covers **Modules 1–2: Introduction to the Cloud & Compute in the Cloud**.

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

## E

**EC2 (Elastic Compute Cloud)**
- AWS service providing on-demand virtual servers (instances) in the cloud
- Offers flexible compute capacity that scales up or down based on needs
- Key features: multiple instance types, various pricing models, Auto Scaling integration

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

## L

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

## V

**Vertical Scaling**
- Adding more power (CPU, memory, storage) to an existing instance
- Makes an instance "bigger"
- Limited by maximum instance size available
- Simpler but less flexible than horizontal scaling

---

**Note**: This glossary grows as modules are documented. New terms added from Module 2 onwards.
