# Module 1: Q&A Review

**Purpose:** Quick reference guide for reviewing all Q&A from Module 1 Introduction to the Cloud. Use this for self-testing and exam prep.

**How to Use:**
1. Read each question and try to answer without looking
2. Check your answer against the provided explanation
3. Mark ✅ if correct, ⏳ if need more review
4. Focus on ⏳ questions for final study

---

## Foundations 1: Client-Server Model & Pay-as-You-Go

### Q1: Client-Server Model

**Question:**
In our coffee shop example, a barista and customer were used to represent the client-server model. The barista represents the server and a customer represents the client.

Which scenario BEST describes how the client-server model works in this analogy?

**Options:**
- A) The customer takes a cup of coffee from a self-serve station without informing the barista. This describes how a client and server do not interact.
- B) The barista proactively prepares a coffee and brings it to the customer without being asked. This describes how the client does not need to submit a request to the server.
- C) The customer makes their own coffee using the coffee shop equipment without interacting with the barista. This describes how the client does not require the server.
- D) The customer goes to the barista and places an order for a coffee. The barista prepares the coffee and hands it back to the customer. This describes how the client places the request, and the server responds.

**Answer:** **D**

**Explanation:**
The correct answer describes the fundamental client-server interaction: the client (customer) initiates a request, the server (barista) processes it, and returns a response. The other options represent breakdowns in this model where either the client doesn't request, the server doesn't respond appropriately, or the client acts independently without server involvement.

---

### Q2: Pay-as-You-Go Pricing

**Question:**
Which aspect of AWS cloud computing best demonstrates the principle of paying only for what you use?

**Answer:**
AWS billing is fundamentally different from traditional on-premises models in that your bill is variable month-to-month based on actual consumption. There is no need for large upfront investment or fixed costs. You can start small, scale as needed, and only pay for the resources you actually consume during each billing period.

---

## Foundations 2: Cloud Deployment Types

### Q3: Deployment Model Selection

**Question:**
You work for a local charity organization. Your organization has sensitive data that must remain within your country for compliance reasons. However, you also need a solution that can scale quickly to handle seasonal spikes in demand. You decide to keep on-premises resources for compliance and use cloud-based resources for dynamic scaling.

Which type of cloud deployment does this situation describe?

**Options:**
- A) On-premises deployment
- B) Public cloud deployment
- C) Hybrid deployment
- D) Data-compliance deployment

**Answer:** **C) Hybrid deployment**

**Explanation:**
This scenario describes a hybrid deployment because the organization combines both on-premises infrastructure (for compliance-sensitive data) and cloud-based resources (for scalability). The organization is not purely cloud-based and not purely on-premises, but rather using both approaches for different needs.

---

## Foundations 3: Six Key Benefits

### Q4: Capacity Planning

**Question:**
A retail business plans to launch a new line of clothing, but they are struggling with accurately predicting how much server capacity they will need to support the launch.

Which benefit of the AWS Cloud is most relevant to this situation?

**Options:**
- A) Stop spending money to run and maintain data centers.
- B) Stop guessing capacity.
- C) Trade upfront expense for variable expense.
- D) Go global in minutes.

**Answer:** **B) Stop guessing capacity**

**Explanation:**
The retail business's challenge is specifically about capacity prediction. AWS addresses this through the ability to dynamically scale resources up or down based on demand, eliminating the need to guess or pre-provision infrastructure. This is the benefit most directly relevant to their situation.

---

## Foundations 4: AWS Global Infrastructure

### Q5: High Availability

**Question:**
You just joined a tech start-up, and the business is growing rapidly. Your new company decides that they need to design a resilient and scalable infrastructure on AWS to handle increased traffic and help ensure high availability.

Which statement BEST describes the AWS Global Infrastructure benefit of high availability?

**Options:**
- A) AWS stores all of your website's data in a single AWS storage bucket to centralize data management.
- B) AWS has many customer support options to make sure the answers to your questions are highly available on its website.
- C) AWS provides multiple data centers across different geographic regions so your website can remain operational even if one location faces issues.
- D) AWS offers a single, highly secure data center that can handle all your traffic, which makes sure that your website is available.

**Answer:** **C) AWS provides multiple data centers across different geographic regions so your website can remain operational even if one location faces issues**

**Explanation:**
High availability is achieved through geographic distribution and redundancy. By having multiple data centers across different regions, AWS ensures that if one location experiences issues, your website or application can continue to operate from other locations. Single points of failure (whether centralized storage or a single data center) do not provide high availability.

---

## Foundations 5: AWS Shared Responsibility Model

### Q6: OS Patching Responsibility

**Question:**
You work for a startup company that is developing an application in the cloud. A new security update is available for your operating system (OS), and you are tasked with verifying that the OS is patched accordingly.

Which statement BEST describes which party is responsible for applying security patches to the OS that is running in the cloud?

**Options:**
- A) AWS is responsible for applying security patches to the OS.
- B) Your company is responsible applying security patches to the OS.
- C) Both AWS and the customer apply separate patches.
- D) The OS vendor applies the patches.

**Answer:** **B) Your company is responsible for applying security patches to the OS**

**Explanation:**
Under the AWS Shared Responsibility Model, customers are fully responsible for patching the operating system. AWS does not have access to customer instances and cannot apply patches on their behalf. AWS can notify customers of available patches, but the deployment responsibility lies entirely with the customer organization.

---

## Foundations 6: Real-World Application & Additional Certification/Interview Questions

### Q7: Cloud Computing Definition Components

**Question:**
Cloud computing is defined as "the on-demand delivery of IT resources over the internet with pay-as-you-go pricing." Which component of this definition allows businesses to avoid large upfront infrastructure investments?

**Answer:**
The **"pay-as-you-go pricing"** component allows businesses to avoid large upfront investments. This model means customers only pay for the resources they actually consume, without pre-paying for capacity or committing to long-term contracts. This contrasts with traditional on-premises infrastructure that requires significant capital expenditure upfront.

---

### Q8: AWS History & Timeline

**Question:**
When was AWS first publicly launched with its initial service, and what was that first service?

**Options:**
- A) 2000 - Amazon Web Services (general cloud platform)
- B) 2003 - AWS was founded but not yet public
- C) 2004 - Amazon Simple Queue Service (SQS)
- D) 2006 - Amazon EC2 and S3

**Answer:** **C) 2004 - Amazon Simple Queue Service (SQS)**

**Explanation:**
AWS launched its first public infrastructure service in November 2004 with Amazon Simple Queue Service (SQS). While the company was founded in 2003 with plans for cloud services, SQS was the first publicly available service. Amazon EC2 and S3 came two years later in 2006, which accelerated AWS adoption.

---

### Q9: Benefit - Trade Fixed Expense for Variable Expense

**Question:**
Your company traditionally runs two data centers and spends $500,000 annually on infrastructure regardless of actual usage. You're considering migrating to AWS. Which statement best describes how AWS's "Trade fixed expense for variable expense" benefit would impact your business?

**Answer:**
With AWS, your infrastructure costs would become variable and directly tied to consumption. Instead of paying a fixed $500,000 annually, you'd pay only for the computing resources you actually use each month. During low-usage months you pay less; during high-usage months you pay more. This allows better alignment between costs and business needs, and eliminates paying for unused capacity.

---

### Q10: Benefit - Economies of Scale

**Question:**
Why can AWS pass cost savings to customers through "Benefit from Massive Economies of Scale"?

**Answer:**
AWS operates massive global data centers and purchases hardware in huge volumes. This bulk purchasing power results in lower per-unit costs for servers, storage, and networking equipment. Because AWS serves millions of customers sharing this infrastructure, the company can pass these volume discounts to all customers—from small startups to large enterprises—allowing even small companies to benefit from enterprise-grade infrastructure at lower costs.

---

### Q11: Benefit - Stop Spending Money on Data Centers

**Question:**
A manufacturing company currently spends $2 million annually operating its on-premises data center, including facility costs, utilities, cooling, security staff, and hardware maintenance. They want to migrate to AWS. Which AWS benefit would be most relevant to reducing these operational costs?

**Answer:**
**"Stop spending money to run and maintain data centers"** would be most relevant. When migrating to AWS, the company eliminates all operational expenses associated with maintaining physical data center infrastructure: facility costs, electricity, cooling systems, security staff, and routine hardware maintenance. AWS takes responsibility for all physical infrastructure, allowing the company to redirect those resources toward innovation and business growth.

---

### Q12: Benefit - Go Global in Minutes

**Question:**
You are launching a new startup offering a SaaS product. You have customers in the US, Europe, and Asia. To provide low-latency service to all customers, you need infrastructure in multiple geographic locations. Traditionally this would require months and millions of dollars. How does AWS's "Go global in minutes" benefit apply?

**Answer:**
AWS provides Regions across the world (e.g., us-east, eu-west-1, ap-southeast-1). Instead of building and operating your own data centers in each region (which takes months or years and requires large CAPEX), you can deploy your application to AWS Regions in minutes. This allows a startup to reach global customers with low latency without the traditional infrastructure costs and timeline, democratizing global-scale operations.

---

### Q13: Regions and Availability Zones - Definition

**Question:**
What is the relationship between AWS Regions and Availability Zones?

**Answer:**
An **AWS Region** is a geographic area containing multiple isolated locations called **Availability Zones (AZs)**. Each Region contains **3 or more AZs**. Within each AZ are one or more data centers with independent power, networking, and connectivity. Regions are completely separate from each other, while AZs within a Region are connected by low-latency links. This structure allows customers to distribute applications across AZs or Regions for high availability and disaster recovery.

---

### Q14: Regions and AZs - Number of AZs

**Question:**
You are designing a resilient application on AWS. You want to ensure your application remains available if one data center fails. According to AWS infrastructure design, how many Availability Zones should you distribute your application across at minimum?

**Answer:**
AWS recommends distributing applications across **at least 2 Availability Zones** minimum, though **3 or more AZs** is preferred for higher resilience. Each Region contains 3 or more AZs, so this is always possible. By distributing across multiple AZs within a Region, you ensure that if one AZ experiences an outage (due to hardware failure, power issues, or natural disaster), your application continues running in other AZs.

---

### Q15: High Availability vs Fault Tolerance

**Question:**
Compare and contrast high availability and fault tolerance in the context of AWS infrastructure.

**Answer:**

| **Aspect** | **High Availability** | **Fault Tolerance** |
|:-----------|:----------------------|:-------------------|
| **Definition** | System remains operational with minimal downtime when failures occur | System continues operating even when multiple components fail |
| **Goal** | Quick recovery from failures | Continued operation through failures |
| **Implementation Example** | Deploy across 2 AZs; if one fails, failover to other | Deploy across 3+ AZs with full redundancy; system works even with 1-2 AZ failures |
| **Scope** | Component or service level | System-wide, multi-layer resilience |
| **User Experience** | Brief downtime during failover | No downtime or interruption |

**Key Difference:** HA accepts brief downtime and recovers quickly. FT prevents downtime entirely by continuing operation through failures.

---

### Q16: Shared Responsibility - Responsibility Division Examples

**Question:**
For each scenario, identify whether it's an AWS responsibility, customer responsibility, or shared responsibility:

A) Securing the encryption keys to your database
B) Maintaining the physical security of AWS data centers
C) Patching the hypervisor software running your virtual servers
D) Encrypting your customer's personal data
E) Monitoring and alerting on network traffic anomalies

**Answer:**
- A) **Customer responsibility** - Customers control their encryption keys; AWS provides the tools but not the keys themselves
- B) **AWS responsibility** - Physical security of facilities is AWS's responsibility under "security of the cloud"
- C) **AWS responsibility** - Hypervisor patching is AWS infrastructure; customer handles OS and application patching
- D) **Customer responsibility** - Deciding what data to encrypt and how is a customer decision
- E) **Shared responsibility** - Depends on the service; some services provide built-in monitoring (AWS), but customers configure alerts (customer)

---

### Q17: Shared Responsibility - Real Scenario

**Question:**
You launch an e-commerce website on AWS EC2. A hacker attempts to access your database. Which party is primarily responsible for preventing this breach?

**Options:**
- A) AWS - they should prevent all hackers from accessing anything on their platform
- B) Your company - you need to configure security groups, firewalls, passwords, and encryption
- C) Equally split between AWS and your company
- D) The database vendor

**Answer:** **B) Your company**

**Explanation:**
While AWS secures the physical infrastructure and hypervisor, **your company is responsible for security "in the cloud,"** which includes:
- Configuring security groups and network access controls
- Setting strong database passwords and access controls
- Encrypting sensitive data
- Monitoring for suspicious activity
- Updating your application and OS

AWS cannot do these tasks for you—they are customer responsibilities under the Shared Responsibility Model.

---

### Q18: Cloud Deployment - Choosing the Right Model

**Question:**
A financial services company needs to meet regulatory requirements that mandate data must be stored within the country. However, they want to use AWS's advanced analytics and machine learning services for competitive advantage. Which deployment model best fits their needs?

**Answer:**
**Hybrid Deployment** is the best fit. The company can:
- Keep sensitive regulated data on-premises in compliance with local regulations
- Use AWS cloud services for analytics, ML, and other non-regulated workloads
- Connect the two environments securely
This approach balances regulatory compliance with the benefits of cloud innovation.

---

### Q19: AWS Global Infrastructure - Multi-Region Deployment

**Question:**
Why would a business deploy their application across multiple AWS Regions rather than just multiple Availability Zones?

**Answer:**
While multiple AZs provide high availability within a region, deploying across **multiple Regions** provides:
1. **Disaster recovery** - If an entire Region fails, applications continue in other Regions
2. **Geographic redundancy** - Protection against region-wide disasters (natural disasters, regional power outages)
3. **Lower latency** - Serve users from a Region closest to them
4. **Compliance** - Meet data residency requirements in specific countries
5. **Business continuity** - True geographic distribution ensures operations continue under any circumstances

**Note:** Multi-Region deployment is more complex and costly than multi-AZ, so it's used when disaster recovery across regions is critical.

---

### Q20: Cost Model Comparison

**Question:**
Compare the cost implications of on-premises vs AWS infrastructure for a startup:

**Scenario:** A startup needs 10 servers for their first year, expecting to grow to 50 servers by year 3.

**Answer:**

| **Aspect** | **On-Premises** | **AWS** |
|:-----------|:---|:---|
| **Year 1 Cost** | $150,000 (buy 50 servers upfront to plan for growth) | $2,000/month = $24,000 (pay for 10 servers) |
| **Year 2 Cost** | $150,000 (same fixed cost) + maintenance | Scales to $8,000/month = $96,000 (30 servers) |
| **Year 3 Cost** | $150,000 (same fixed cost) + maintenance | Scales to $12,000/month = $144,000 (50 servers) |
| **Total 3-Year Cost** | ~$450,000 + maintenance & staff | ~$264,000 (scales with growth) |
| **Key Benefit** | Predictable costs | Costs align with growth; no idle capacity |

AWS's variable expense model is ideal for startups: you pay for growth, not predicted growth.

---

### Q21: Cloud vs On-Premises - Agility

**Question:**
Your company wants to test a new application architecture. On-premises, this would require:
- 4 weeks to procure hardware
- 2 weeks for installation and configuration
- Testing and teardown if the approach doesn't work

How does AWS improve this scenario?

**Answer:**
On AWS, you can:
- **Launch test infrastructure in minutes** (not weeks)
- **Run experiments and tests** without long procurement cycles
- **Delete resources immediately** when done, stopping charges immediately
- **Fail fast and iterate** - try multiple approaches rapidly

This dramatically increases agility and innovation speed. Companies can experiment with new architectures, services, and configurations without the upfront capital investment and months-long procurement cycles of on-premises.

---

### Q22: Shared Responsibility - Service Type Impact

**Question:**
How does the Shared Responsibility Model change depending on the type of AWS service used?

**Answer:**
The division of responsibilities varies significantly by service type:

**Infrastructure Services (e.g., EC2):**
- AWS: Physical infrastructure, hypervisor
- Customer: OS, applications, security groups, firewalls, data encryption

**Managed Services (e.g., RDS):**
- AWS: Infrastructure, OS patching, database patches, backups
- Customer: Data encryption, access control, user management

**Fully Managed Services (e.g., DynamoDB):**
- AWS: Everything including OS, patching, scaling
- Customer: Data encryption, access control

As you move from infrastructure to managed to fully managed services, AWS takes on more responsibility, but **customers always maintain data and access control responsibility.**

---

### Q23: Definition - What Cloud Computing Actually Enables

**Question:**
Beyond just "accessing IT resources over the internet," what fundamental business capability does cloud computing enable?

**Answer:**
Cloud computing enables **organizations to scale infrastructure rapidly without upfront capital investment.** This transforms how businesses operate:
- **Startups** can compete globally without massive CAPEX
- **Enterprises** can experiment and innovate faster
- **All companies** can align infrastructure costs with actual usage (variable vs fixed)
- **Everyone** can deploy applications worldwide in minutes instead of months

This democratization of enterprise-grade infrastructure is the true power of cloud computing.

---

## Study Progress Tracker

Use this to track your review progress:

| # | Category | Question | Topic | Status | Notes |
|:--|:------|:---------|:------|:-------|:------|
| 1 | Foundations 1 | Q1 | Client-Server Model | ⏳ | |
| 2 | Foundations 1 | Q2 | Pay-as-You-Go | ⏳ | |
| 3 | Foundations 2 | Q3 | Deployment Types | ⏳ | |
| 4 | Foundations 3 | Q4 | Capacity Planning | ⏳ | |
| 5 | Foundations 4 | Q5 | Global Infrastructure | ⏳ | |
| 6 | Foundations 5 | Q6 | Shared Responsibility | ⏳ | |
| 7 | Foundations 6 | Q7 | Cloud Definition | ⏳ | |
| 8 | Foundations 1 | Q8 | AWS History | ⏳ | |
| 9 | Foundations 3 | Q9 | Fixed to Variable Expense | ⏳ | |
| 10 | Foundations 3 | Q10 | Economies of Scale | ⏳ | |
| 11 | Foundations 3 | Q11 | Data Center Costs | ⏳ | |
| 12 | Foundations 3 | Q12 | Go Global in Minutes | ⏳ | |
| 13 | Foundations 4 | Q13 | Regions & AZs Definition | ⏳ | |
| 14 | Foundations 4 | Q14 | AZs for Resilience | ⏳ | |
| 15 | Foundations 4 | Q15 | HA vs Fault Tolerance | ⏳ | |
| 16 | Foundations 5 | Q16 | Responsibility Division | ⏳ | |
| 17 | Foundations 5 | Q17 | Real Scenario | ⏳ | |
| 18 | Foundations 2 | Q18 | Deployment Selection | ⏳ | |
| 19 | Foundations 4 | Q19 | Multi-Region Why | ⏳ | |
| 20 | Foundations 1 | Q20 | Cost Comparison | ⏳ | |
| 21 | Foundations 6 | Q21 | Agility Benefit | ⏳ | |
| 22 | Foundations 5 | Q22 | Service Type Impact | ⏳ | |
| 23 | Foundations 6 | Q23 | Cloud Enables | ⏳ | |

**Legend:** ⏳ = Need Review | ✅ = Confident | 📝 = Added Notes

---

## Quick Facts to Remember

- **Client-Server:** Client requests → Server responds
- **Pay-as-you-go:** No upfront cost; pay only for consumption
- **Deployment types:** Cloud (agile), On-Premises (control), Hybrid (both)
- **Six benefits:** Variable expense, Economies of scale, No capacity guessing, Speed/agility, No data center maintenance, Go global in minutes
- **Global Infrastructure:** Regions contain AZs; AZs contain data centers
- **High Availability:** Distribute across AZs to stay operational if one fails
- **Fault Tolerance:** System continues operating through multiple simultaneous failures
- **Shared Responsibility:** AWS = "of the cloud"; Customer = "in the cloud"
- **AWS History:** SQS (2004), S3 & EC2 (2006)
- **Cost Model:** AWS variable aligns with startup growth; on-prem fixed doesn't
- **Service Responsibility:** Varies by service type (IaaS → less managed → more AWS responsibility)

---

**Last Updated:** March 19, 2026  
**Module:** Introduction to the Cloud (Module 1)
