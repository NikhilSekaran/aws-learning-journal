# Module 2: Q&A Review

**Purpose:** Quick reference guide for reviewing all Q&A from Module 2 Compute in the Cloud. Use this for self-testing and exam prep.

**How to Use:**
1. Read each question and try to answer without looking
2. Check your answer against the provided explanation
3. Mark ✅ if correct, ⏳ if it needs more review
4. Focus on ⏳ questions for final study

**Reference Notes:** [notes.md](notes.md)

---

## Topic 1: EC2 Fundamentals & Instance Types

### Q1: EC2 vs On-Premises Comparison

**Question:**
How does Amazon EC2 compare to running servers on premises?

**Options:**
- A) More expensive but offers more control
- B) Requires more time to set up and maintain
- C) Only useful for large businesses
- D) More flexible, cost-effective, and quicker to get started

**Answer:** **D) More flexible, cost-effective, and quicker to get started**

**Why not the others:**
- A) More expensive ✗ EC2 is actually less expensive; no upfront hardware costs
- B) Requires more time ✗ On-premises requires more time; EC2 launches within minutes
- C) Only for large businesses ✗ EC2 is used by startups, individuals, and large enterprises alike

**Explanation:**
EC2 eliminates upfront hardware costs, launches in minutes rather than weeks, and allows you to scale dynamically. AWS manages the infrastructure, giving you flexibility without operational burden. This applies to startups and enterprises alike.

---

### Q2: Multi-Tenancy Concept

**Question:**
What is multi-tenancy in the context of Amazon EC2 instances?

**Options:**
- A) Multiple servers run in the same data center
- B) Only one user can use the instance at a time
- C) A server can only run one type of application
- D) Each VM is isolated but shares resources from a host

**Answer:** **D) Each VM is isolated but shares resources from a host**

**Why not the others:**
- A) Multiple servers in same data center ✗ Multi-tenancy is about VMs sharing a physical host, not data center co-location
- B) Only one user at a time ✗ Multiple VMs from different customers can share the same physical host
- C) Server runs one type of application ✗ Instances can run any application regardless of multi-tenancy

**Explanation:**
Multi-tenancy means multiple customer instances run on the same physical server. The hypervisor provides isolation so instances can't interfere with each other, while sharing underlying hardware to maximize resource utilization.

---

### Q3: EC2 Instance Billing on Stop/Terminate

**Question:**
A company uses EC2 instances to deploy their application. What happens if they need to stop or terminate instances?

**Options:**
- A) You continue to be charged for compute while instances are stopped
- B) Stopped instances automatically restart after 24 hours at no additional charge
- C) Terminated instances can be recovered from backup within the same billing cycle
- D) Pay only for running instances; billing stops immediately when stopped or terminated

**Answer:** **D) Pay only for running instances; billing stops immediately**

**Explanation:**
Billing stops immediately when an instance is stopped or terminated. This is a key cost-optimization feature—you don't continue paying for idle resources.

**Why not the others:**
- Still charged while stopped ✗ Charges stop immediately; you only pay for running instances
- Auto-restart after 24 hours ✗ Stopped instances require manual action or Auto Scaling to restart
- Terminated instances recoverable ✗ Terminated instances are permanently deleted; only stopped instances can be restarted

---

### Q4: Required EC2 Launch Configurations

**Question:**
What must be specified when preparing to launch an EC2 instance?

**Options:**
- A) The amount of storage and the number of concurrent users
- B) The instance's geographic location and backup plan
- C) The network bandwidth and data transfer limit
- D) The instance type and the operating system (via AMI)

**Answer:** **D) The instance type and the operating system (via AMI)**

**Explanation:**
These two are essential:
- **Instance Type** determines hardware resources (CPU, memory)
- **AMI (OS)** determines the operating system and pre-installed software
Other configurations (storage, security groups) are important but not "must-have" at launch.

**Why not the others:**
- Storage and user count ✗ Storage is optional at launch; user count is not an EC2 configuration
- Location and backup plan ✗ A default Region is used if not specified; backup plans are not required
- Network bandwidth and data transfer ✗ These are determined by the instance type, not specified separately

---

### Q5: Memory-Optimized Instance Use Case

**Question:**
A financial institution is running a real-time analytics application that processes large datasets stored across multiple servers to provide quick query results. Which EC2 instance type would be BEST?

**Options:**
- A) General Purpose
- B) Compute Optimized
- C) Memory Optimized
- D) Storage Optimized

**Answer:** **C) Memory Optimized**

**Explanation:**
Memory-optimized instances are designed for workloads requiring fast in-memory processing of large datasets. This is ideal for analytics applications needing quick query results from massive data volumes.

**Why not the others:**
- General Purpose ✗ Balanced resources; not optimized for memory-heavy workloads
- Compute Optimized ✗ Best for CPU-intensive tasks like gaming/HPC, not large in-memory datasets
- Storage Optimized ✗ Best for locally stored data with high I/O, not in-memory processing

---

### Q6: Storage-Optimized Instance Use Case

**Question:**
A retail company is analyzing historical sales data stored locally with demands for fast access and high disk throughput. Which instance type is MOST suitable?

**Options:**
- A) General Purpose
- B) Compute Optimized
- C) Accelerated Computing
- D) Storage Optimized

**Answer:** **D) Storage Optimized**

**Explanation:**
Storage-optimized instances provide high-performance access to locally stored data with exceptional I/O throughput. They're perfect for databases and data warehousing workloads requiring consistent, fast access to large datasets.

**Why not the others:**
- General Purpose ✗ Balanced resources; not designed for high disk throughput
- Compute Optimized ✗ Best for CPU-intensive tasks; needs fast local disk access, not raw compute
- Accelerated Computing ✗ Uses GPU hardware; not relevant for disk-based data retrieval

---

## Topic 2: AWS Provisioning Methods

### Q7: AWS CLI Advantage

**Question:**
What is a primary advantage of using the AWS CLI over the Management Console?

**Options:**
- A) Provides a visual, drag-and-drop interface for managing resources
- B) Only available for Windows users, giving extra platform benefits
- C) Uses automation and scripting, reducing manual steps and errors
- D) Ideal for one-time manual provisioning tasks with no learning curve

**Answer:** **C) Uses automation and scripting, reducing manual steps and errors**

**Explanation:**
The CLI enables you to programmatically provision resources, script repetitive tasks, and integrate AWS operations into automation pipelines. The Console is visual but manual-intensive for complex operations.

**Why not the others:**
- Visual interface ✗ That's the Management Console; CLI is text-based command-line
- Windows only ✗ AWS CLI works on Windows, macOS, and Linux
- One-time manual provisioning ✗ Opposite is true; CLI excels at repeatable automation

---

### Q8: AWS Shared Responsibility Model (EC2)

**Question:**
What is the customer's responsibility when using EC2 according to the Shared Responsibility Model?

**Options:**
- A) AWS manages the infrastructure and also manages the customer's OS, networking, and applications
- B) The customer is responsible for securing the physical hardware underlying EC2
- C) AWS is responsible for managing OS, networking, and application configurations
- D) The customer is responsible for configuring, securing, and managing the OS, networking, and applications

**Answer:** **D) The customer is responsible for configuring, securing, and managing the OS, networking, and applications**

**Explanation:**
EC2 is an unmanaged service. AWS provides the infrastructure; you handle:
- OS patching and updates
- Security groups and firewalls
- Application security
- Data encryption
- Access control

**Why not the others:**
- AWS manages OS/networking/applications ✗ EC2 is unmanaged; customers handle all of these
- Customer secures physical hardware ✗ AWS handles physical hardware security ("security of the cloud")
- AWS manages OS configuration ✗ This is the inverse; customers are responsible for their own OS

---

## Topic 3: Amazon Machine Images (AMI)

### Q9: EC2 Launch Requirements (Multi-Select)

**Question:**
What are the required configurations when launching an EC2 instance for a web server? (Select THREE)

**Options:**
- A) AMI, Storage, and Load Balancing configuration
- B) AMI, Instance Type, and Storage
- C) Instance Type, Permissions, and Termination Behavior
- D) AMI, Network Bandwidth limit, and Backup Plan

**Answer:** **B) AMI, Instance Type, and Storage**

**Explanation:**
These three are essential:
- **AMI** — Defines OS and pre-installed software
- **Instance Type** — Determines hardware resources
- **Storage** — Defines disk space and performance

**Why not the others:**
- Load Balancing ✗ Only needed if distributing traffic across multiple instances
- Permissions ✗ Security groups handle network access; not required at initial launch
- Termination Behavior ✗ Defaults exist; not required to specify at launch
- Network Bandwidth ✗ Determined by instance type; not specified separately
- Backup Plan ✗ Not required to launch an instance

---

### Q10: Purpose of AMI

**Question:**
What is an AMI used for when launching an EC2 instance?

**Options:**
- A) To choose the instance size and compute power (CPU/memory)
- B) To configure networking settings and security groups
- C) To pre-configure the operating system and software
- D) To store persistent application data for the instance

**Answer:** **C) To pre-configure the operating system and software**

**Explanation:**
An AMI is a template that contains everything needed to launch an instance: the OS, storage setup, architecture type, and pre-installed applications. It ensures all instances launched from the same AMI are identical.

**Why not the others:**
- Instance size ✗ Instance type is a separate selection from the AMI
- Networking settings ✗ Security groups and VPC settings are configured separately
- Store instance data ✗ EBS volumes or other storage services store data; AMIs are launch templates

---

## Topic 4: EC2 Pricing Models

### Q11: Dedicated Hosts for Compliance

**Question:**
A financial services company needs complete control over the physical server, including instance placement and resource allocation, for compliance. Which pricing option should they choose?

**Options:**
- A) Savings Plans
- B) On-Demand Instances
- C) Spot Instances
- D) Dedicated Hosts

**Answer:** **D) Dedicated Hosts**

**Explanation:**
Dedicated Hosts provide exclusive physical server access, allowing the company to:
- Control instance placement
- Meet compliance requirements
- Handle specialized licensing (Windows, SQL Server)

**Why not the others:**
- Savings Plans ✗ Offers cost savings but no physical server isolation or placement control
- On-Demand ✗ Instances share physical hosts; no control over server placement
- Spot Instances ✗ No server control, and instances can be interrupted with 2-minute notice

---

### Q12: Spot Instances for Batch Processing

**Question:**
A startup wants to minimize costs for batch processing workloads that can tolerate occasional interruptions. Which pricing option offers the most savings?

**Options:**
- A) On-Demand Instances
- B) Reserved Instances
- C) Savings Plans
- D) Spot Instances

**Answer:** **D) Spot Instances**

**Explanation:**
Spot Instances offer up to 90% savings by bidding on spare capacity. Perfect for:
- Batch processing
- Data analysis
- ML training
Any workload that can tolerate interruptions with a 2-minute warning.

**Why not the others:**
- On-Demand ✗ Standard pricing with no discounts; most expensive option
- Reserved Instances ✗ Require 1-3 year commitment; better for steady, predictable workloads
- Savings Plans ✗ Require commitment to hourly spend but don't offer the same 90% discount

---

### Q13: Pricing for New Application

**Question:**
A customer is building a new application with uncertain usage patterns but expects growth. They want to start without long-term commitment. Which pricing option?

**Options:**
- A) Reserved Instances for a 3-year commitment to lock in low rates
- B) Spot Instances to maximize cost savings from day one
- C) On-Demand to start without commitment and scale freely
- D) Savings Plans with committed hourly usage for flexibility

**Answer:** **C) On-Demand to start without commitment and scale freely**

**Explanation:**
On-Demand is ideal for:
- Unknown usage patterns
- Development and testing
- Applications too new to predict demand

Once usage patterns stabilize, you can switch to Reserved Instances or Savings Plans for cost optimization.

**Why not the others:**
- Reserved Instances ✗ Require 1-3 year commitment; unsuitable for uncertain demand
- Spot Instances ✗ Risk of interruption makes them unsuitable for new production applications
- Savings Plans ✗ Require commitment to consistent hourly usage; not ideal for unknown patterns

---

## Topic 5: Scaling & Elasticity

### Q14: Scalability and Elasticity Benefits

**Question:**
What is the primary benefit of scalability and elasticity in AWS?

**Options:**
- A) The ability to manually adjust resources based on anticipated peak usage
- B) The ability to create fixed resources that never change in size
- C) The ability to grow and shrink resources dynamically based on real-time demand
- D) The ability to permanently increase capacity for long-term growth planning

**Answer:** **C) The ability to grow and shrink resources dynamically based on real-time demand**

**Explanation:**
- **Scalability** = long-term capacity planning (prepare for growth)
- **Elasticity** = automatic, real-time adjustment

Together, they allow you to pay only for resources you use, improving cost efficiency and customer experience.

**Why not the others:**
- Manual adjustment ✗ Manual scaling is slower and less efficient than automatic elasticity
- Fixed resources ✗ Fixed resources waste money during low-demand periods
- Permanently increase ✗ That describes scalability alone; elasticity adds the ability to scale back down

---

### Q15: Multi-AZ Deployment Reason

**Question:**
What is the main reason for deploying EC2 instances across multiple Availability Zones?

**Options:**
- A) To increase the processing power and speed of each individual instance
- B) To decrease costs by distributing workloads across cheaper AZs
- C) To provide high availability by allowing instances in different AZs to handle traffic if one AZ fails
- D) To automatically scale the number of instances based on usage patterns

**Answer:** **C) To provide high availability by allowing instances in different AZs to handle traffic if one AZ fails**

**Explanation:**
Multi-AZ deployment ensures that if one AZ experiences an outage, your application continues running in other AZs. This is the foundation of high availability and zero-downtime operations.

**Why not the others:**
- Increase instance power ✗ Deploying across AZs doesn't change an individual instance's hardware
- Decrease costs via AZs ✗ Cost savings come from right-sizing and Auto Scaling, not AZ selection
- Automatically scale instances ✗ Auto Scaling handles instance count; multi-AZ provides redundancy

---

### Q16: Meeting Fluctuating Demand

**Question:**
How does AWS help businesses meet fluctuating demand without over-provisioning?

**Options:**
- A) By providing fixed resources that are always available at full capacity
- B) By requiring businesses to purchase excess resources to handle any future spikes
- C) By allowing resources to automatically scale based on demand
- D) By offering resources that always run at maximum capacity regardless of usage

**Answer:** **C) By allowing resources to automatically scale based on demand**

**Explanation:**
EC2 Auto Scaling automatically adjusts instance count:
- Adds instances during demand spikes
- Removes instances during low demand
- Costs align with actual usage, not peak capacity
This prevents paying for unused capacity and ensures optimal resource utilization.

**Why not the others:**
- Fixed resources ✗ Fixed resources waste money during low-demand periods
- Purchase excess resources ✗ Over-provisioning is exactly what AWS Auto Scaling avoids
- Always run at max ✗ Running maximum capacity continuously eliminates any cost savings from cloud

---

## Topic 6: Elastic Load Balancing

### Q17: How ELB Improves Scalability

**Question:**
How does Elastic Load Balancing improve scalability in AWS?

**Options:**
- A) It manually adjusts the number of EC2 instances based on detected load
- B) It directly increases the size (vertical scaling) of overloaded EC2 instances
- C) It automatically routes traffic to instances based on various routing methods
- D) It creates new EC2 instances for each individual incoming request

**Answer:** **C) It automatically routes traffic to instances based on various routing methods**

**Explanation:**
ELB distributes traffic using intelligent routing strategies:
- **Round Robin** — Equal distribution
- **Least Connections** — Based on active connections
- **IP Hash** — Session persistence
- **Least Response Time** — Performance optimization

This prevents any single instance from becoming bottlenecked.

**Why not the others:**
- Manually adjusts instances ✗ That's Auto Scaling's role; ELB only distributes traffic to existing instances
- Increases instance size ✗ ELB handles traffic routing, not vertical scaling
- New instance per request ✗ Extremely inefficient; ELB routes to existing healthy instances

---

### Q18: ELB Primary Function

**Question:**
Which task does ELB perform?

**Options:**
- A) Automatically adjusts the number of EC2 instances based on demand
- B) Removes unneeded instances when demand is low
- C) Distributes a workload across several EC2 instances
- D) Adds new instances during high-traffic periods like popular sales events

**Answer:** **C) Distributes a workload across several EC2 instances**

**Explanation:**
ELB is fundamentally a traffic distribution mechanism. It:
- Receives incoming requests
- Routes them to available instances
- Monitors instance health
- Automatically adapts as instances are added/removed

Auto Scaling handles instance count; ELB handles traffic distribution.

**Why not the others:**
- Adjusts instance count ✗ That's Auto Scaling's responsibility; ELB only routes traffic
- Removes unneeded instances ✗ Auto Scaling handles instance termination
- Adds new instances ✗ Adding instances is Auto Scaling's job; ELB distributes to existing ones

---

## Topic 7: Messaging and Queuing

### Q19: Tightly vs Loosely Coupled Architectures

**Question:**
What BEST describes the key difference between tightly coupled and loosely coupled architectures?

**Options:**
- A) Tightly coupled systems are more flexible and easier to modify than loosely coupled ones
- B) Tightly coupled systems are designed for better scalability and independent scaling
- C) In tightly coupled systems, components depend on each other; in loosely coupled systems, components operate independently
- D) Loosely coupled systems require direct data sharing between all components

**Answer:** **C) In tightly coupled systems, components depend on each other; in loosely coupled systems, components operate independently**

**Explanation:**

| **Aspect**       | **Tightly Coupled**          | **Loosely Coupled**                 |
|:-----------------|:-----------------------------|:------------------------------------|
| **Dependencies** | Direct; failures cascade     | Indirect; failures isolated         |
| **Flexibility**  | Difficult to modify          | Easy to add/remove components       |
| **Scalability**  | Harder to scale              | Each component scales independently |
| **Resilience**   | Single failure breaks system | System continues despite failures   |

**Why not the others:**
- Tightly coupled is more flexible ✗ Tightly coupled systems are harder to modify; loosely coupled is more flexible
- Tightly coupled scales better ✗ Loosely coupled systems scale better due to independent components
- Loosely coupled requires direct sharing ✗ Loosely coupled avoids direct sharing; components communicate via queues or events

---

### Q20: SQS for Banking

**Question:**
In a banking system, transaction details are sent to a fraud detection service. Sometimes the service is temporarily down. What is the MAIN advantage of using SQS?

**Options:**
- A) It guarantees immediate approval of all bank transactions in real time
- B) It speeds up fraud detection by bypassing message buffers
- C) It stores transaction details until the fraud detection service can process them, even if temporarily down
- D) It forces tight dependencies so transactions are rejected when the fraud service is unavailable

**Answer:** **C) It stores transaction details until the fraud detection service can process them**

**Explanation:**
SQS decouples the systems:
- Transaction service puts message in queue
- Fraud service processes when ready
- No messages are lost
- System continues operating even if one component fails

This is loosely coupled resilience at its core.

**Why not the others:**
- Immediate approval ✗ SQS queues messages for processing; it doesn't approve transactions
- Speeds up by bypassing buffers ✗ The queue IS the buffer; it enables reliable async processing
- Tight dependencies ✗ SQS does the opposite—it decouples services so each can operate independently

---

## Topic 8: Interview & Certification Prep Questions

### Q21: Cost Optimization Strategy

**Question:**
Your company runs predictable workloads requiring 10 EC2 instances 24/7. After 3 months, you've identified stable usage. What cost optimization strategy saves the most?

**Options:**
- A) Keep all as On-Demand for maximum flexibility
- B) Use Reserved Instances or Savings Plans for baseline (10 instances)
- C) Convert all instances to Spot to maximize savings
- D) Use Dedicated Hosts for all instances

**Answer:** **B) Use Reserved Instances or Savings Plans for baseline**

**Explanation:**
With predictable, stable workloads:
- **Reserved Instances:** Up to 75% savings on committed 10 instances
- **Savings Plans:** Up to 72% savings with flexibility
- Use **On-Demand** for any additional scaling above baseline
This hybrid approach saves 70-75% versus all On-Demand.

**Why not the others:**
- All On-Demand ✗ No savings; paying full price for stable workload
- All Spot ✗ Instances can be interrupted; unsuitable for 24/7 production
- Dedicated Hosts ✗ More expensive; only needed for compliance

---

### Q22: Architecture Decoupling with ELB

**Question:**
What advantage does Elastic Load Balancing provide for backend scaling?

**Options:**
- A) Frontend must know and update all backend IP addresses when instances change
- B) Frontend only knows load balancer URL; backend can scale without frontend changes
- C) ELB prevents scaling from happening at all
- D) Each frontend must manage its own load balancing logic

**Answer:** **B) Frontend only knows load balancer URL; backend scales independently**

**Explanation:**
ELB creates architectural decoupling:
- **Without ELB:** Frontend knows all backend IPs; adding/removing instances requires coordination
- **With ELB:** Frontend only contacts load balancer; backend scales independently
This separation allows backend to scale from 5 to 100 instances without frontend changes.

**Why not the others:**
- Frontend must know all IPs ✗ That's the problem ELB solves
- ELB prevents scaling ✗ ELB enables independent scaling
- Each frontend manages load balancing ✗ That's inefficient; ELB manages it centrally

---

### Q23: Auto Scaling vs Manual Scaling

**Question:**
Compare Auto Scaling (automatic) vs manual instance scaling for handling demand changes:

**Options:**
- A) Both take the same time; choose based on cost preference
- B) Auto Scaling is immediate (minutes); manual is delayed (hours/days)
- C) Manual scaling is cheaper but requires 24/7 monitoring
- D) Auto Scaling requires human operators to make changes

**Answer:** **B) Auto Scaling is immediate (minutes); manual is delayed (hours/days)**

**Explanation:**
| **Aspect** | **Auto Scaling** | **Manual Scaling** |
|:---|:---|:---|
| **Response Time** | Minutes | Hours/days |
| **Cost Efficiency** | Excellent (scales with demand) | Poor (over-provision peaks) |
| **Operational Overhead** | Low (automatic) | High (manual + monitoring) |
| **Reliability** | Optimal capacity always | Risk missing peaks |

Auto Scaling automatically adjusts capacity in response to demand changes.

**Why not the others:**
- Same time ✗ Auto takes minutes; manual takes hours
- Manual is cheaper ✗ Auto saves on wasted capacity
- Auto requires operators ✗ Auto is fully automatic

---

### Q24: Instance Types Selection Decision Tree

**Question:**
You need to choose instance types for multiple workloads. Which pairing is CORRECT?

**Options:**
- A) Web servers ➔ Memory Optimized; Databases ➔ Compute Optimized
- B) Machine learning ➔ General Purpose; Data warehousing ➔ Storage Optimized
- C) Web servers ➔ General Purpose; Machine learning ➔ Compute Optimized
- D) Analytics processing ➔ Accelerated Computing; Email service ➔ Storage Optimized

**Answer:** **C) Web servers ➔ General Purpose; Machine learning ➔ Compute Optimized**

**Explanation:**
| **Workload** | **Best Instance Type** | **Why** |
|:---|:---|:---|
| Web servers | **General Purpose** | Balanced CPU, memory, networking |
| Machine learning | **Compute Optimized** | CPU-intensive ML training |
| Databases | **Memory Optimized** | Large datasets in memory |
| Data warehousing | **Storage Optimized** | High I/O throughput |

**Why not the others:**
- Web servers = Memory ✗ Not needed for typical web apps
- Databases = Compute ✗ Need memory, not just CPU
- Analytics = Accelerated ✗ GPU not needed for analytics
- Action: Change instance type anytime if wrong choice

---

### Q25: Pricing Model Decision Matrix

**Question:**
Match the workload to the best EC2 pricing option:

**Scenario:** New startup building a web app with uncertain growth

**Options:**
- A) Reserved Instances for 3 years to lock in pricing
- B) Spot Instances to maximize cost savings
- C) On-Demand to avoid upfront commitment
- D) Dedicated Hosts for maximum control

**Answer:** **C) On-Demand to avoid upfront commitment**

**Explanation:**
For unpredictable demand with unknown usage patterns:
- **On-Demand** allows flexibility without commitment
- No upfront costs or long-term contracts
- Once patterns stabilize (months 3-6), switch to Reserved/Savings Plans
- Can scale up or down without penalty

**Why not the others:**
- Reserved Instances ✗ Require 3-year commitment when demand is uncertain
- Spot Instances ✗ Instances can be interrupted; unsuitable for production apps
- Dedicated Hosts ✗ Expensive; only needed for compliance requirements

---

### Q26: Scaling Strategy for Growing Startup

**Question:**
A startup expects 500% traffic growth in 12 months. Which strategy is BEST?

**Options:**
- A) Purchase 6x servers now to prepare for growth
- B) Use Auto Scaling with ELB; start small and scale on-demand
- C) Use Reserved Instances for all expected growth
- D) Use only Spot Instances to minimize costs

**Answer:** **B) Use Auto Scaling with ELB; start small and scale on-demand**

**Explanation:**
Auto Scaling with ELB provides:
- Start with 2-3 instances; grow to 20 as demand increases
- Pay only for current usage, not anticipated usage
- Combine: Reserved Instances (baseline) + On-Demand (variable) + Spot (batch)
- Costs scale with revenue, not upfront equipment purchases

**Cost over 12 months:**
- Month 1-3: $1.5K/month (2 instances)
- Month 4-6: $3K/month (5 instances)
- Month 7-12: $5K/month (15-20 instances scaled up)

**Why not the others:**
- Buy 6x servers now ✗ Wastes money on idle capacity; no flexibility
- Reserved for all growth ✗ Commits to unused capacity for 3 years
- All Spot ✗ Instances interrupted during peak demand

---

### Q27: HA vs FT Architecture

**Question:**
A healthcare company needs continuous availability for patient records. Which architectural approach is appropriate?

**Options:**
- A) Single instance in one AZ (cheapest)
- B) 2 instances across 2 AZs, auto-failover (High Availability)
- C) 3+ instances per AZ, across 3 AZs, real-time replication (Fault Tolerance)
- D) Multi-region deployment only

**Answer:** **C) 3+ instances per AZ, across 3 AZs, real-time replication**

**Explanation:**
Mission-critical healthcare systems require **Fault Tolerance:**
- Accepts zero downtime (patient records cannot unavailable)
- Continues operation even with multiple component failures
- Requires redundancy at multiple levels (AZs, instances, data)
- Real-time replication ensures data consistency

**Why not the others:**
- Single instance ✗ No redundancy; any failure = downtime
- 2 AZs (HA) ✗ Accepts brief downtime; patient records need zero downtime
- Multi-region only ✗ Still need multi-AZ redundancy within region

---

### Q28: Messaging Service Comparison

**Question:**
A food delivery app needs: (1) Queue customer orders reliably, (2) Send SMS/email notifications, (3) Trigger payment and inventory updates. Which services are best?

**Options:**
- A) SQS for all three services
- B) SNS for queuing; SQS for notifications
- C) SQS for orders; SNS for notifications; EventBridge for orchestration
- D) All three services do the same thing; pick any

**Answer:** **C) SQS for orders; SNS for notifications; EventBridge for orchestration**

**Explanation:**
| **Service** | **Best For** | **This Scenario** |
|:---|:---|:---|
| **SQS** | Reliable buffering | Queue customer orders |
| **SNS** | Multi-channel notifications | Send SMS/email confirmations |
| **EventBridge** | Intelligent routing | Trigger payment/inventory (event-driven) |

This combination provides: reliable queuing + multi-channel notifications + intelligent routing.

**Why not the others:**
- SQS for all ✗ SNS better for multi-channel notifications
- SNS for queuing ✗ SQS provides guaranteed delivery; SNS is best-effort
- All same ✗ Each service optimized for different use cases

---

### Q29: Cost Comparison Scenario

**Question:**
Baseline: 5 EC2 instances 24/7 + peaks to 10 instances 4 hours/day. Which approach is cheapest annually?

**Options:**
- A) All On-Demand: $49,050/year
- B) 5 Reserved + 5 On-Demand for peaks: $2,400/year
- C) 5 Reserved + 5 Spot for peaks: $1,817/year  
- D) All Spot Instances: $1,200/year

**Answer:** **B) 5 Reserved + 5 On-Demand for peaks: $2,400/year (if reliability needed) OR C) 5 Reserved + 5 Spot: $1,817/year (if interruptions tolerable)**

**Explanation:**
Cost breakdown:
- **Option A (All On-Demand):** $0.09/hr × 4,250 hrs/month × 12 = $49,050
- **Option B (Hybrid reliable):** Reserved $1,752 + On-Demand peaks $648 = $2,400 (95% savings!)
- **Option C (Hybrid aggressive):** Reserved $1,752 + Spot peaks $65 = $1,817 (96% savings!)
- **Option D (All Spot):** Risky; instances can be interrupted anytime

**Recommendation:** Option B for production; Option C for batch/non-critical workloads.

**Why not others:**
- All On-Demand ✗ Wastes $46,650/year on unnecessary capacity
- All Spot ✗ Production system interrupted during peak demand

---

### Q30: Real-World Architecture Challenge

**Question:**
Design an architecture for a SaaS platform expecting 10x traffic growth in 6 months. Which components are ESSENTIAL?

**Options:**
- A) Single large instance with backup; add more when needed
- B) ELB + Auto Scaling Group + Multi-AZ RDS + Messaging (SQS/SNS)
- C) Dedicated Hosts across multiple regions
- D) Multiple independent applications running separately

**Answer:** **B) ELB + Auto Scaling Group + Multi-AZ RDS + Messaging**

**Explanation:**
Architecture for 10x growth:

```
ELB (single entry point)
  └─ Auto Scaling Group (min: 2, desired: 3, max: 15+)
      └─ Mix of Reserved (baseline) + On-Demand (variable)
  └─ Multi-AZ RDS Database (automatic failover)
  └─ Messaging: SQS (async jobs) + SNS (notifications)
```

This provides:
- ✅ High availability (multi-AZ)
- ✅ Automatic scaling (ELB + Auto Scaling)
- ✅ Cost optimization (Reserved + On-Demand mix)
- ✅ Loose coupling (SQS/SNS)
- ✅ Data reliability (Multi-AZ RDS)

**Why not the others:**
- Single large instance ✗ Doesn't scale; single point of failure
- Dedicated Hosts ✗ Expensive; not needed for SaaS
- Multiple independent apps ✗ Defeats architecture; difficult to manage

---

## Study Progress Tracker

Use this to track your review progress:

| #  | Category              | Question | Topic                      | Status | Notes |
|:---|:----------------------|:---------|:---------------------------|:-------|:------|
| 1  | EC2 Basics            | Q1       | EC2 vs On-Premises         | ⏳      |       |
| 2  | EC2 Basics            | Q2       | Multi-Tenancy              | ⏳      |       |
| 3  | EC2 Basics            | Q3       | Billing                    | ⏳      |       |
| 4  | EC2 Basics            | Q4       | Launch Requirements        | ⏳      |       |
| 5  | Instance Types        | Q5       | Memory Optimized           | ⏳      |       |
| 6  | Instance Types        | Q6       | Storage Optimized          | ⏳      |       |
| 7  | Provisioning          | Q7       | AWS CLI                    | ⏳      |       |
| 8  | Shared Responsibility | Q8       | EC2 Responsibilities       | ⏳      |       |
| 9  | AMI                   | Q9       | Launch Configurations      | ⏳      |       |
| 10 | AMI                   | Q10      | AMI Purpose                | ⏳      |       |
| 11 | Pricing               | Q11      | Dedicated Hosts            | ⏳      |       |
| 12 | Pricing               | Q12      | Spot Instances             | ⏳      |       |
| 13 | Pricing               | Q13      | On-Demand                  | ⏳      |       |
| 14 | Scaling               | Q14      | Scalability & Elasticity   | ⏳      |       |
| 15 | Scaling               | Q15      | Multi-AZ Deployment        | ⏳      |       |
| 16 | Scaling               | Q16      | Fluctuating Demand         | ⏳      |       |
| 17 | ELB                   | Q17      | Scalability Improvement    | ⏳      |       |
| 18 | ELB                   | Q18      | Primary Function           | ⏳      |       |
| 19 | Messaging             | Q19      | Tightly vs Loosely Coupled | ⏳      |       |
| 20 | Messaging             | Q20      | SQS Banking Scenario       | ⏳      |       |
| 21 | Advanced              | Q21      | Cost Optimization          | ⏳      |       |
| 22 | Advanced              | Q22      | Architecture Decoupling    | ⏳      |       |
| 23 | Advanced              | Q23      | Auto vs Manual Scaling     | ⏳      |       |
| 24 | Advanced              | Q24      | Instance Type Selection    | ⏳      |       |
| 25 | Advanced              | Q25      | Pricing Decision Matrix    | ⏳      |       |
| 26 | Advanced              | Q26      | Startup Growth Strategy    | ⏳      |       |
| 27 | Advanced              | Q27      | HA vs FT Architecture      | ⏳      |       |
| 28 | Advanced              | Q28      | Messaging Comparison       | ⏳      |       |
| 29 | Advanced              | Q29      | Cost Calculation           | ⏳      |       |
| 30 | Advanced              | Q30      | Real-World Architecture    | ⏳      |       |

**Legend:** ⏳ = Need Review | ✅ = Confident | 📝 = Added Notes

---

## Quick Facts to Remember

**EC2 Fundamentals:**
- **Multi-tenancy** = VMs share physical host; hypervisor provides isolation
- **Vertical scaling** = Make instance bigger; **Horizontal scaling** = Add more instances
- **On-Premises challenges** = High upfront cost, weeks to deploy, capacity guessing
- **EC2 advantages** = Low upfront, minutes to deploy, elastic scaling

**Instance Types:**
- **General Purpose** = Balanced; default choice for most workloads
- **Compute Optimized** = CPU-heavy (gaming, HPC, ML)
- **Memory Optimized** = In-memory databases and analytics
- **Accelerated** = GPU/hardware acceleration
- **Storage Optimized** = High I/O, databases, data warehousing

**Pricing Models:**
- **On-Demand** = No commitment; use for unpredictable workloads
- **Reserved Instances** = 1–3 year commitment; 75% savings for stable workloads
- **Spot Instances** = Bid on spare capacity; 90% savings; interruption risk
- **Savings Plans** = Commit to hourly spend; 72% savings; more flexible than RI
- **Dedicated Hosts** = Exclusive server; for compliance and licensing

**Scaling & HA:**
- **Scalability** = Plan for growth (months)
- **Elasticity** = Auto-scale to demand (minutes)
- **High Availability** = Deploy across 2+ AZs for failover
- **Auto Scaling** = Min/Desired/Max capacity automatically maintained
- **ELB** = Single entry point; distributes traffic; decouples tiers

**Messaging:**
- **SQS** = Queue service; store & process at receiver's pace
- **SNS** = Publish-Subscribe; push notifications to multiple subscribers
- **EventBridge** = Event bus; intelligent routing based on rules
- **Loosely Coupled** = Failures isolated; high resilience
- **Tightly Coupled** = Failures cascade; low resilience

**Cost Optimization:**
- **Mix pricing models** = Reserved for baseline, On-Demand for variable, Spot for batch
- **Right-sizing** = Monitor metrics; adjust instance types
- **Reserved Instances** = Best for stable 24/7 workloads
- **Savings Plans** = Best for mixed workloads and flexibility
- **Spot Instances** = Best for non-critical, batch, and cost-sensitive work

---

## Common Exam Patterns

**Pattern 1: "Which pricing option?"**
→ Look for: Stable workload? → Reserved Instances; New app? → On-Demand; Interruptible? → Spot

**Pattern 2: "How to handle demand spikes?"**
→ Answer: Auto Scaling + ELB for even distribution

**Pattern 3: "Reduce costs for stable workload?"**
→ Answer: Reserved Instances or Savings Plans for baseline, On-Demand for peaks

**Pattern 4: "High availability architecture?"**
→ Answer: Multi-AZ, redundancy, automatic failover with ELB

**Pattern 5: "Decouple application components?"**
→ Answer: SQS for queuing, SNS for notifications, EventBridge for events

---

**Module:** Compute in the Cloud (Module 2)  
**Total Q&As:** 30 (20 course + 10 interview/cert prep)
