# AWS Services Overview

> Quick reference for AWS services encountered in courses. Updated progressively as modules are documented. Currently covers **Modules 1–2**.

---

## Module 1: Introduction to the Cloud Concepts
Module 1 focuses on foundational cloud concepts rather than specific AWS services. Services are introduced in detail from Module 2 onwards.

### Key Historical Services Mentioned

**Amazon SQS (Simple Queue Service)**
- AWS's first publicly launched service (November 2004)
- Message queuing service enabling decoupled application components

---

## Module 2: Compute Services

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

**Documentation**: [EC2 in Module 2](../courses/aws-cloud-practitioner-essentials/modules/module-02-compute-in-the-cloud/notes.md#5-amazon-ec2-pricing)

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

**Documentation**: [Auto Scaling in Module 2](../courses/aws-cloud-practitioner-essentials/modules/module-02-compute-in-the-cloud/notes.md#6-scaling-amazon-ec2)

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

**Documentation**: [ELB in Module 2](../courses/aws-cloud-practitioner-essentials/modules/module-02-compute-in-the-cloud/notes.md#7-directing-traffic-with-elastic-load-balancing)

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

**Documentation**: [SQS in Module 2](../courses/aws-cloud-practitioner-essentials/modules/module-02-compute-in-the-cloud/notes.md#8-messaging-and-queuing)

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

**Documentation**: [SNS in Module 2](../courses/aws-cloud-practitioner-essentials/modules/module-02-compute-in-the-cloud/notes.md#8-messaging-and-queuing)

---

### Amazon EventBridge
**What it is**: Serverless event bus that routes events from sources to targets based on rules

**Key Features**:
- Routes events between AWS services and third-party applications
- Rule-based event routing
- Stores undelivered events for replay
- Serverless (no infrastructure to manage)

**Use Cases**:
- Event-driven architectures
- Coordinating microservices
- Integration between applications
- Responding to AWS resource changes

**Benefits**: Simple event routing, serverless, reliable delivery, flexible routing rules

**Documentation**: [EventBridge in Module 2](../courses/aws-cloud-practitioner-essentials/modules/module-02-compute-in-the-cloud/notes.md#8-messaging-and-queuing)

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
