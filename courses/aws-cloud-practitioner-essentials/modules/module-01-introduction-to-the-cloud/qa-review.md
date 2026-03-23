# Module 1: Q&A Review

**Purpose:** Quick reference guide for reviewing all Q&A from Module 1 Introduction to the Cloud. Use this for self-testing and exam prep.

**How to Use:**
1. Read each question and try to answer without looking
2. Check your answer against the provided explanation
3. Mark ✅ if correct, ⏳ if it needs more review
4. Focus on ⏳ questions for final study

**Reference Notes:** [notes.md](notes.md)

---

## Topic 1: Client-Server Model & Pay-as-You-Go

### Q1: Client-Server Model

**Question:**
In our coffee shop example, a barista and customer were used to represent the client-server model. The barista represents the server and a customer represents the client.

Which scenario BEST describes how the client-server model works in this analogy?

**Options:**
- A) The customer takes a cup of coffee from a self-serve station without informing the barista. This describes how a client and server do not interact.
- B) The barista proactively prepares a coffee and brings it to the customer without being asked. This describes how the client does not need to submit a request to the server.
- C) The customer makes their own coffee using the coffee shop equipment without interacting with the barista. This describes how the client does not require the server.
- D) The customer goes to the barista and places an order for a coffee. The barista prepares the coffee and hands it back to the customer. This describes how the client places the request, and the server responds.

**Answer:** **D) The customer goes to the barista and places an order for a coffee. The barista prepares the coffee and hands it back to the customer.**

**Explanation:**
The correct answer describes the fundamental client-server interaction: the client (customer) initiates a request, the server (barista) processes it, and returns a response. The other options represent breakdowns in this model where either the client doesn't request, the server doesn't respond appropriately, or the client acts independently without server involvement.
---

**Why not the others:**
- A) Self-serve station ✗ No client-server interaction; the client never makes a request
- B) Barista acts without being asked ✗ Servers respond to requests; they don't push responses unprompted
- C) Customer makes their own coffee ✗ Client operates independently; no server (barista) is involved

---

### Q2: Pay-as-You-Go Pricing

**Question:**
Which aspect of AWS cloud computing best demonstrates the principle of paying only for what you use?

**Options:**
- A) AWS requires annual prepayment for all services before use
- B) Bills are fixed monthly regardless of actual resource consumption
- C) Your bill is variable, tied to actual consumption, with no upfront costs
- D) AWS provides a flat rate regardless of how many resources you use

**Answer:** **C) Your bill is variable, tied to actual consumption**

**Explanation:**
AWS billing is fundamentally different from traditional on-premises models in that your bill is variable month-to-month based on actual consumption. There is no need for large upfront investment or fixed costs. You can start small, scale as needed, and only pay for the resources you actually consume during each billing period.

**Why not the others:**
- A) Annual prepayment ✗ AWS core model is pay-as-you-go; some pricing options (like certain commitments) can include upfront payment, but they are optional
- B) Fixed monthly bills ✗ Costs vary with consumption; low-traffic months cost less
- D) Flat rate ✗ AWS pricing is based on actual usage, not a flat rate

---

## Topic 2: Cloud Deployment Types

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

**Why not the others:**
- A) On-premises ✗ Doesn't provide the cloud-based scaling the organization needs
- B) Public cloud ✗ Can work for some residency requirements, but this scenario explicitly keeps sensitive workloads on premises while using cloud for scale, which is hybrid
- D) Data-compliance deployment ✗ Not a recognised AWS deployment model

---

## Topic 3: Six Key Benefits & Cost Model

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

**Why not the others:**
- A) Stop spending on data centers ✗ Relevant to cost reduction, not the capacity prediction problem described
- C) Trade upfront for variable expense ✗ About payment model, not the ability to scale capacity on demand
- D) Go global in minutes ✗ About geographic reach, not adjusting server capacity

---

## Topic 4: AWS Global Infrastructure

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

**Why not the others:**
- A) Single storage bucket ✗ Centralizing data in one location is a single point of failure, not high availability
- B) Customer support availability ✗ Describes AWS documentation/support, not infrastructure high availability
- D) Single high-security data center ✗ A single data center is a single point of failure regardless of how secure it is

---

## Topic 5: AWS Shared Responsibility Model

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

**Why not the others:**
- A) AWS is responsible ✗ AWS is responsible for the infrastructure (hypervisor, hardware), not the OS inside your instances
- C) Both apply separate patches ✗ AWS has no access to your OS; only the customer can apply OS patches
- D) OS vendor applies patches ✗ OS vendors release patches, but it is the customer's responsibility to apply them

---

## Topic 6: Real-World Application & Certification/Interview Questions

### Q7: Cloud Computing Definition Components

**Question:**
Cloud computing is defined as "the on-demand delivery of IT resources over the internet with pay-as-you-go pricing." Which component of this definition allows businesses to avoid large upfront infrastructure investments?

**Options:**
- A) "On-demand delivery" - provides immediate access to IT resources without procurement delays
- B) "Over the internet" - removes the need for local physical infrastructure
- C) "Pay-as-you-go pricing" - eliminates large upfront capital expenditure
- D) "IT resources" - describes the compute, storage, and database services available

**Answer:** **C) "Pay-as-you-go pricing"**

**Explanation:**
The **"pay-as-you-go pricing"** component allows businesses to avoid large upfront investments. This model means customers only pay for the resources they actually consume, without pre-paying for capacity or committing to long-term contracts. This contrasts with traditional on-premises infrastructure that requires significant capital expenditure upfront.

**Why not the others:**
- A) "On-demand delivery" ✗ Relates to access speed and availability, not cost structure
- B) "Over the internet" ✗ Describes the delivery mechanism, not the pricing model
- D) "IT resources" ✗ Describes what is available, not how it is paid for

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

**Options:**
- A) You continue paying $500,000 annually but receive better hardware performance
- B) AWS charges a one-time migration fee, then eliminates all infrastructure costs
- C) Infrastructure costs become variable, tied to actual monthly consumption
- D) You pay $500,000 upfront to AWS instead of managing your own data centers

**Answer:** **C) Infrastructure costs become variable, tied to actual monthly consumption**

**Explanation:**
With AWS, your infrastructure costs would become variable and directly tied to consumption. Instead of paying a fixed $500,000 annually, you'd pay only for the computing resources you actually use each month. During low-usage months you pay less; during high-usage months you pay more. This allows better alignment between costs and business needs, and eliminates paying for unused capacity.

**Why not the others:**
- A) Same annual cost ✗ Variable pricing means you only pay for actual usage; costs typically drop
- B) One-time migration fee ✗ AWS has no migration fee; ongoing costs are based on consumption
- D) $500K upfront to AWS ✗ AWS has no upfront payment; pay-as-you-go eliminates capital expenditure

---

### Q10: Benefit - Economies of Scale

**Question:**
Why can AWS pass cost savings to customers through "Benefit from Massive Economies of Scale"?

**Options:**
- A) AWS earns profit from large enterprises and uses it to subsidize small customer pricing
- B) AWS bulk-purchases hardware and shares infrastructure across millions of customers, lowering per-unit costs for everyone
- C) Only large AWS customers benefit; small businesses pay standard market rates
- D) AWS buys hardware at market rate but charges customers less to grow market share

**Answer:** **B) AWS bulk-purchases hardware and shares infrastructure across millions of customers**

**Explanation:**
AWS operates massive global data centers and purchases hardware in huge volumes. This bulk purchasing power results in lower per-unit costs for servers, storage, and networking equipment. Because AWS serves millions of customers sharing this infrastructure, the company can pass these volume discounts to all customers—from small startups to large enterprises—allowing even small companies to benefit from enterprise-grade infrastructure at lower costs.

**Why not the others:**
- A) Large enterprises subsidize small customers ✗ Cost reductions come from volume purchasing, not cross-subsidization
- C) Only large customers benefit ✗ All customers benefit equally from the shared infrastructure economics
- D) Below-market pricing for market share ✗ Lower costs come from operational efficiency, not subsidized pricing

---

### Q11: Benefit - Stop Spending Money on Data Centers

**Question:**
A manufacturing company currently spends $2 million annually operating its on-premises data center, including facility costs, utilities, cooling, security staff, and hardware maintenance. They want to migrate to AWS. Which AWS benefit would be most relevant to reducing these operational costs?

**Options:**
- A) Stop guessing capacity - eliminating over-provisioned servers
- B) Go global in minutes - deploying internationally with lower latency
- C) Stop spending money to run and maintain data centers
- D) Trade upfront expense for variable expense - moving to pay-as-you-go

**Answer:** **C) Stop spending money to run and maintain data centers**

**Explanation:**
**"Stop spending money to run and maintain data centers"** would be most relevant. When migrating to AWS, the company eliminates all operational expenses associated with maintaining physical data center infrastructure: facility costs, electricity, cooling systems, security staff, and routine hardware maintenance. AWS takes responsibility for all physical infrastructure, allowing the company to redirect those resources toward innovation and business growth.

**Why not the others:**
- A) Stop guessing capacity ✗ Relevant to rightsizing, not eliminating physical facility costs
- B) Go global in minutes ✗ Addresses geographic expansion, not operational cost reduction
- D) Trade upfront for variable ✗ Overlapping benefit, but the $2M includes recurring operational costs, not just capital

---

### Q12: Benefit - Go Global in Minutes

**Question:**
You are launching a new startup offering a SaaS product. You have customers in the US, Europe, and Asia. To provide low-latency service to all customers, you need infrastructure in multiple geographic locations. Traditionally this would require months and millions of dollars. How does AWS's "Go global in minutes" benefit apply?

**Options:**
- A) AWS ships hardware to your local offices worldwide within minutes of ordering
- B) AWS provides global Regions, enabling deployment near all customers without building your own data centers
- C) AWS's network speeds up international data transfer so one data center feels globally local
- D) AWS partners with local ISPs in each country, reducing your time to establish a local presence

**Answer:** **B) AWS provides global Regions, enabling deployment near all customers**

**Explanation:**
AWS provides Regions across the world (e.g., us-east-1, eu-west-1, ap-southeast-1). Instead of building and operating your own data centers in each region (which takes months or years and requires large CAPEX), you can deploy your application to AWS Regions in minutes. This allows a startup to reach global customers with low latency without the traditional infrastructure costs and timeline, democratizing global-scale operations.

**Why not the others:**
- A) Ships hardware ✗ AWS is cloud-based; no physical hardware is sent to you
- C) Speeds up data transfer ✗ Reduced latency comes from geographic proximity of Regions, not network acceleration
- D) Partners with local ISPs ✗ AWS operates its own global infrastructure; no ISP partnerships required

---

### Q13: Regions and Availability Zones - Definition

**Question:**
What is the relationship between AWS Regions and Availability Zones?

**Options:**
- A) Regions and Availability Zones are the same thing; just different names for data centers
- B) Availability Zones contain multiple Regions, connected by high-speed fiber
- C) A Region is a geographic area containing 3 or more isolated Availability Zones
- D) Each Region contains exactly one Availability Zone for maximum security isolation

**Answer:** **C) A Region is a geographic area containing 3 or more isolated Availability Zones**

**Explanation:**
An **AWS Region** is a geographic area containing multiple isolated locations called **Availability Zones (AZs)**. Each Region contains **3 or more AZs**. Within each AZ are one or more data centers with independent power, networking, and connectivity. Regions are completely separate from each other, while AZs within a Region are connected by low-latency links. This structure allows customers to distribute applications across AZs or Regions for high availability and disaster recovery.

**Why not the others:**
- A) Same thing ✗ Regions and AZs are distinct hierarchical concepts; Regions contain AZs
- B) AZs contain Regions ✗ The hierarchy is inverted; Regions contain AZs, not the reverse
- D) One AZ per Region ✗ Every Region has 3 or more AZs to enable redundancy

---

### Q14: Regions and AZs - Number of AZs

**Question:**
You are designing a resilient application on AWS. You want to ensure your application remains available if one data center fails. According to AWS infrastructure design, how many Availability Zones should you distribute your application across at minimum?

**Options:**
- A) 1 AZ is sufficient; AWS guarantees 100% uptime within a single AZ
- B) At least 2 AZs, with 3 or more preferred for higher resilience
- C) You must use all available AZs in a Region for compliance
- D) At least 5 AZs; fewer AZs cannot provide true high availability

**Answer:** **B) At least 2 AZs, with 3 or more preferred for higher resilience**

**Explanation:**
AWS recommends distributing applications across **at least 2 Availability Zones** minimum, though **3 or more AZs** is preferred for higher resilience. Each Region contains 3 or more AZs, so this is always possible. By distributing across multiple AZs within a Region, you ensure that if one AZ experiences an outage (due to hardware failure, power issues, or natural disaster), your application continues running in other AZs.

**Why not the others:**
- A) 1 AZ ✗ A single AZ is a single point of failure; AWS does not guarantee 100% uptime per AZ
- C) All AZs required ✗ No such compliance rule; 2-3 AZs is the recommended practice
- D) 5 AZs minimum ✗ Most Regions have 3-4 AZs; 2 is the minimum recommended for HA

---

### Q15: High Availability vs Fault Tolerance

**Question:**
Compare and contrast high availability and fault tolerance in the context of AWS infrastructure.

**Options:**
- A) They are interchangeable terms; both mean the system never experiences downtime
- B) High Availability is only for hardware failures; Fault Tolerance is only for software failures
- C) High Availability minimizes downtime through quick recovery; Fault Tolerance keeps systems running despite failures with zero downtime
- D) Fault Tolerance is cheaper because it uses fewer redundant components than High Availability

**Answer:** **C) High Availability minimizes downtime through quick recovery; Fault Tolerance keeps systems running despite failures**

**Explanation:**

| **Aspect**                 | **High Availability**                                                | **Fault Tolerance**                                                               |
|:---------------------------|:---------------------------------------------------------------------|:----------------------------------------------------------------------------------|
| **Definition**             | System remains operational with minimal downtime when failures occur | System continues operating even when multiple components fail                     |
| **Goal**                   | Quick recovery from failures                                         | Continued operation through failures                                              |
| **Implementation Example** | Deploy across 2 AZs; if one fails, failover to other                 | Deploy across 3+ AZs with full redundancy; system works even with 1-2 AZ failures |
| **Scope**                  | Component or service level                                           | System-wide, multi-layer resilience                                               |
| **User Experience**        | Brief downtime during failover                                       | No downtime or interruption                                                       |

**Key Difference:** HA accepts brief downtime and recovers quickly. FT prevents downtime entirely by continuing operation through failures.

**Why not the others:**
- A) Interchangeable ✗ They have distinct definitions; HA allows brief downtime, FT allows none
- B) Hardware vs software ✗ Both apply to any type of failure, not split by failure type
- D) FT is cheaper ✗ Fault Tolerance requires more redundancy and is typically more expensive than HA

---

### Q16: Shared Responsibility - Responsibility Division Examples

**Question:**
Which of the following correctly assigns responsibilities under the AWS Shared Responsibility Model?

**Options:**
- A) AWS: encryption keys and data encryption; Customer: physical data center security
- B) AWS: physical security and hypervisor patching; Customer: encryption keys, data encryption, and application monitoring
- C) AWS: everything including encryption and application security; Customer: nothing in managed services
- D) Customer: physical security of data centers; AWS: all encryption and access management

**Answer:** **B) AWS: physical security and hypervisor patching; Customer: encryption keys, data encryption, and application monitoring**

**Explanation:**
Under the Shared Responsibility Model:
- **Encryption keys** → Customer responsibility (AWS provides tools, not the keys)
- **Physical data center security** → AWS responsibility ("security of the cloud")
- **Hypervisor patching** → AWS responsibility (underlying infrastructure layer)
- **Encrypting customer data** → Customer responsibility (data classification and protection decisions)
- **Network monitoring/alerting** → Shared (AWS provides built-in monitoring; customers configure alerts)

**Why not the others:**
- A) ✗ Inverts responsibilities; physical security is always AWS; encryption keys are always customer
- C) ✗ Even in fully managed services, data and access control remain the customer's responsibility
- D) ✗ Customers never manage physical data centers in the cloud; that is always AWS

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

**Options:**
- A) Cloud deployment - all services should be moved to AWS
- B) On-premises deployment - all systems must stay locally
- C) Hybrid deployment - keep regulated data locally, use AWS for analytics/ML
- D) Multi-region deployment - distribute across different countries

**Answer:** **C) Hybrid deployment**

**Explanation:**
Hybrid deployment allows the company to:
- Keep sensitive regulated data on-premises in compliance with local regulations
- Use AWS cloud services for analytics, ML, and other non-regulated workloads
- Connect the two environments securely
This approach balances regulatory compliance with the benefits of cloud innovation.

**Why not the others:**
- A) Cloud deployment ✗ Violates data residency requirements
- B) On-premises ✗ Loses access to AWS analytics/ML advantages
- D) Multi-region ✗ Doesn't solve local data residency needs; adds complexity

---

### Q19: AWS Global Infrastructure - Multi-Region Deployment

**Question:**
Why would a business deploy their application across multiple AWS Regions rather than just multiple Availability Zones?

**Options:**
- A) Regions are cheaper than Availability Zones
- B) Protection against region-wide disasters and meeting geographic user needs
- C) All Availability Zones are in the same location, so regions are mandatory
- D) Regions provide better performance than AZs

**Answer:** **B) Protection against region-wide disasters and meeting geographic user needs**

**Explanation:**
While multiple AZs provide high availability within a region, deploying across **multiple Regions** provides:
- Disaster recovery from region-wide failures
- Lower latency for geographically distributed users
- Compliance with data residency requirements
- True business continuity across continents

**Why not the others:**
- A) Regions are cheaper ✗ Multi-region deployment is typically more expensive
- C) All AZs in same location ✗ AZs within a region are separate locations
- D) Better performance ✗ AZs have similar performance; regions add latency

---

### Q20: Cost Model Comparison

**Question:**
A startup needs 10 servers for year 1, expecting to grow to 50 servers by year 3. How would costs compare between on-premises and AWS?

**Options:**
- A) On-premises saves ~$200,000; you buy hardware once
- B) AWS costs more; you pay continuously instead of buying hardware
- C) AWS saves ~$200,000; costs scale with growth vs upfront capital
- D) They cost the same over 3 years

**Answer:** **C) AWS saves ~$200,000; costs scale with growth**

**Explanation:**
| **Aspect** | **On-Premises (3-year)** | **AWS (3-year)** |
|:---|:---|:---|
| **Initial** | $150,000 (50 servers) | $0 |
| **Monthly** | $0 (already paid) | Scales from $2K-$12K |
| **Total** | ~$450,000+ | ~$264,000 |

AWS's variable expense model aligns costs with actual usage, making it ideal for growing startups.

**Why not the others:**
- A) On-premises saves money ✗ You pay upfront for unused capacity
- B) AWS costs more ✗ AWS totals $264K vs $450K on-prem
- D) Same cost ✗ AWS significantly cheaper for growing companies

---

### Q21: Cloud vs On-Premises - Agility

**Question:**
Your company wants to test a new application architecture. On-premises would require 4 weeks to procure + 2 weeks to install. How does AWS improve this?

**Options:**
- A) AWS takes the same time but costs less
- B) AWS allows testing in minutes, deleting resources immediately when done
- C) AWS only helps if you commit to 3-year contracts
- D) AWS requires the same infrastructure investment but with monthly payments

**Answer:** **B) AWS allows testing in minutes, deleting resources immediately**

**Explanation:**
On AWS, you can:
- **Launch in minutes** instead of weeks of procurement
- **Run experiments** without capital investment
- **Delete immediately** and stop charges when done
- **Fail fast and iterate** - try multiple approaches rapidly

This dramatically increases agility and innovation speed compared to on-premises procurement cycles.

**Why not the others:**
- A) Same time, costs less ✗ AWS is much faster than procurement cycles
- C) Requires 3-year contracts ✗ AWS offers on-demand pay-as-you-go
- D) Same investment with monthly payments ✗ No upfront investment needed

---

### Q22: Shared Responsibility - Service Type Impact

**Question:**
How does the responsibility division in the Shared Responsibility Model change based on the AWS service type?

**Options:**
- A) AWS responsibilities are identical regardless of service type
- B) Customer responsibilities increase as services become more managed
- C) AWS responsibility increases as services become more managed (IaaS → Managed → Fully Managed)
- D) Private companies are always responsible for everything

**Answer:** **C) AWS responsibility increases as services become more managed**

**Explanation:**
| **Service Type** | **AWS Responsibility** | **Customer Responsibility** |
|:---|:---|:---|
| **Infrastructure (EC2)** | Physical, hypervisor | OS, apps, security groups |
| **Managed (RDS)** | Infrastructure, DB patching | Data encryption, access control |
| **Fully Managed (DynamoDB)** | Everything including scaling | Data encryption, access control |

As you move toward managed services, **AWS handles more, but data and access control remain customer responsibility.**

**Why not the others:**
- A) Same responsibility regardless ✗ Responsibility varies significantly by service
- B) Increases as more managed ✗ Opposite is true
- D) Private companies always responsible ✗ All companies follow same model

---

### Q23: Definition - What Cloud Computing Actually Enables

**Question:**
Beyond just accessing IT resources over the internet, what fundamental business capability does cloud computing enable?

**Options:**
- A) Only large enterprises can use technology
- B) Rapid infrastructure scaling without upfront capital investment
- C) Replacing all IT staff with cloud vendors
- D) Guaranteed 100% uptime on all applications

**Answer:** **B) Rapid infrastructure scaling without upfront capital investment**

**Explanation:**
Cloud computing fundamentally enables:
- **Startups** to compete globally without massive CAPEX
- **Enterprises** to experiment and innovate faster
- **All companies** to align costs with usage (variable vs fixed)
- **Everyone** to deploy worldwide in minutes instead of months

This democratization of enterprise-grade infrastructure is the true power of cloud computing.

**Why not the others:**
- A) Only large enterprises ✗ Cloud enables all sizes to compete
- C) Replaces IT staff ✗ Cloud requires different, not eliminated, IT roles
- D) Guaranteed 100% uptime ✗ Cloud provides high availability, not perfection

---

## Study Progress Tracker

Use this to track your review progress:

| #  | Category              | Question | Topic                     | Status | Notes |
|:---|:----------------------|:---------|:--------------------------|:-------|:------|
| 1  | Cloud Fundamentals    | Q1       | Client-Server Model       | ⏳      |       |
| 2  | Cloud Fundamentals    | Q2       | Pay-as-You-Go             | ⏳      |       |
| 3  | Deployment Models     | Q3       | Deployment Types          | ⏳      |       |
| 4  | Cloud Benefits & Cost | Q4       | Capacity Planning         | ⏳      |       |
| 5  | Global Infrastructure | Q5       | Global Infrastructure     | ⏳      |       |
| 6  | Shared Responsibility | Q6       | Shared Responsibility     | ⏳      |       |
| 7  | Cloud Concepts        | Q7       | Cloud Definition          | ⏳      |       |
| 8  | Cloud Concepts        | Q8       | AWS History               | ⏳      |       |
| 9  | Cloud Benefits & Cost | Q9       | Fixed to Variable Expense | ⏳      |       |
| 10 | Cloud Benefits & Cost | Q10      | Economies of Scale        | ⏳      |       |
| 11 | Cloud Benefits & Cost | Q11      | Data Center Costs         | ⏳      |       |
| 12 | Cloud Benefits & Cost | Q12      | Go Global in Minutes      | ⏳      |       |
| 13 | Global Infrastructure | Q13      | Regions & AZs Definition  | ⏳      |       |
| 14 | Global Infrastructure | Q14      | AZs for Resilience        | ⏳      |       |
| 15 | Global Infrastructure | Q15      | HA vs Fault Tolerance     | ⏳      |       |
| 16 | Shared Responsibility | Q16      | Responsibility Division   | ⏳      |       |
| 17 | Shared Responsibility | Q17      | Real Scenario             | ⏳      |       |
| 18 | Deployment Models     | Q18      | Deployment Selection      | ⏳      |       |
| 19 | Global Infrastructure | Q19      | Multi-Region Why          | ⏳      |       |
| 20 | Cloud Benefits & Cost | Q20      | Cost Comparison           | ⏳      |       |
| 21 | Cloud Concepts        | Q21      | Agility Benefit           | ⏳      |       |
| 22 | Shared Responsibility | Q22      | Service Type Impact       | ⏳      |       |
| 23 | Cloud Concepts        | Q23      | Cloud Enables             | ⏳      |       |

**Legend:** ⏳ = Need Review | ✅ = Confident | 📝 = Added Notes

---

## Quick Facts to Remember

**Cloud Fundamentals:**
- **Client-Server** = Client sends request → Server processes and responds
- **Pay-as-you-go** = No upfront cost; pay only for what you consume
- **AWS History** = SQS (2004), S3 & EC2 (2006); rapid growth led to AWS launch

**Deployment Models:**
- **Cloud** = All resources in the cloud; agile, scalable
- **On-Premises** = Private infrastructure; maximum control, higher cost
- **Hybrid** = Mix of cloud and on-premises; ideal for regulated workloads

**Cloud Benefits & Cost:**
- **Six benefits** = Variable expense, Economies of scale, No capacity guessing, Speed/agility, No data center maintenance, Go global in minutes
- **Cost Model** = AWS variable cost aligns with business growth; on-prem fixed cost doesn't
- **Economies of scale** = AWS bulk purchasing passes savings to all customers

**Global Infrastructure:**
- **Regions** = Physical geographic locations containing multiple AZs
- **Availability Zones** = 3+ isolated data centers per Region with independent power/networking
- **High Availability** = Distribute across AZs; service continues if one AZ fails
- **Fault Tolerance** = System continues operating even through multiple simultaneous failures

**Shared Responsibility:**
- **AWS** = Security *of* the cloud (hardware, networking, facilities, hypervisor)
- **Customer** = Security *in* the cloud (OS, applications, data, access control)
- **Service Responsibility** = Varies by service type; IaaS → more customer responsibility; managed services → more AWS responsibility

---

## Common Exam Patterns

**Pattern 1: "Which deployment model?"**
→ Compliance/data residency + cloud agility? → Hybrid; All in cloud? → Cloud; Full control on-site? → On-Premises

**Pattern 2: "Which AWS benefit applies?"**
→ Capacity guessing problem? → Stop guessing capacity; Slow global expansion? → Go global in minutes; Upfront spend? → Trade fixed for variable

**Pattern 3: "AWS or Customer responsibility?"**
→ Physical hardware / hypervisor / facilities? → AWS; OS / application / data / encryption keys? → Customer

**Pattern 4: "High availability vs fault tolerance?"**
→ Minimise downtime, failover to other AZ? → High Availability; Continue operating through multiple failures? → Fault Tolerance

**Pattern 5: "Which global infrastructure component?"**
→ Geographic location choice? → Region; Isolated data centers within region? → Availability Zone; Content caching closer to users? → Edge Location

---

**Module:** Introduction to the Cloud (Module 1)
**Total Q&As:** 23 (6 course + 17 interview/cert prep)
