# Module 4: Going Global - Q&A Review

**Purpose:** Quick reference guide for reviewing all Q&A from Module 4 Going Global. Use this for self-testing and exam prep.

**How to Use:**
1. Read each question and try to answer without looking
2. Check your answer against the provided explanation
3. Mark ✅ if correct, ⏳ if it needs more review
4. Focus on ⏳ questions for final study

**Reference Notes:** [notes.md](notes.md)

---

## Topic 1: AWS Regions and Availability Zones

### Q1: Region Selection Factors (Select TWO)

**Question:**
A cloud engineer for a government agency is tasked with selecting an AWS Region to deploy the agency's resources.

Which factors are MOST important to consider when selecting a Region? (Select TWO.)

**Options:**
- A) Any regulatory compliance standards the agency requires
- B) Proximity to users
- C) Number of files stored
- D) Personal preference of the chief information officer
- E) How recently the Region was constructed

**Answer:** **A) Any regulatory compliance standards the agency requires and B) Proximity to users**

**Explanation:**
Compliance requirements are a primary filter when choosing a Region because legal and regulatory obligations can dictate where data is stored and processed. Proximity is also critical because Regions closer to users reduce latency and improve responsiveness.

**Why not the others:**
- C) Number of files stored ✗ File count alone is not a Region-selection driver.
- D) Personal preference of the chief information officer ✗ Region choice should be based on compliance and technical/business needs, not personal preference.
- E) How recently the Region was constructed ✗ Region age is not a key decision criterion for this scenario.

---

## Topic 2: Edge Locations and CloudFront

### Q2: Global Infrastructure Matching (Match Terms)

**Question:**
Match each AWS Global Infrastructure element with its correct definition.

**Items:**
- A) Edge location
- B) AWS Region
- C) Availability Zone

**Definitions:**
- 1) Locations that cache content to deliver data, video, and applications to users with lower latency
- 2) A physical location around the world where AWS operates multiple data centers
- 3) Separate, distinct locations with one or more data centers that are engineered to be isolated from failures in other areas

**Answer:**
- **A – Edge location** → 1) Locations that cache content to deliver data, video, and applications to users with lower latency
- **B – AWS Region** → 2) A physical location around the world where AWS operates multiple data centers
- **C – Availability Zone** → 3) Separate, distinct locations with one or more data centers that are engineered to be isolated from failures in other areas

**Explanation:**
Regions are physical locations around the world that contain multiple data centers. Each Region contains at least three Availability Zones. Each Availability Zone contains one or more data centers. Edge locations are devices in areas outside of Regions that provide user access to frequently accessed data with low latency.

**Why not the others:**
- "A physical location... multiple data centers" → uniquely identifies a Region as the largest geographic grouping.
- "Separate, distinct locations... isolated from failures" → uniquely identifies an AZ due to the fault-isolation design language.
- "Cache content... lower latency" → uniquely identifies an edge location because it emphasizes caching and CDN delivery, not compute hosting.

---

## Topic 3: Global Application Deployment

### Q3: CloudFormation as an IaC Solution

**Question:**
Would AWS CloudFormation be a good solution for managing the company's infrastructure?

**Options:**
- A) CloudFormation would not be useful in this scenario because it only supports simple infrastructure setups.
- B) CloudFormation would be ideal because it supports infrastructure as code (IaC), enabling consistent, repeatable deployments across different environments.
- C) CloudFormation should be used only for setting up static websites, not for complex applications.
- D) CloudFormation is too complicated and would slow down the deployment process.

**Answer:** **B) CloudFormation would be ideal because it supports infrastructure as code (IaC), enabling consistent, repeatable deployments across different environments.**

**Explanation:**
CloudFormation is an AWS infrastructure as code service that uses templates to define and provision resources in a consistent, repeatable, and automated way. This reduces manual configuration drift and supports deployment across multiple environments, Regions, and accounts.

**Why not the others:**
- A) ✗ Incorrect because CloudFormation supports complex and large-scale infrastructure, not only simple setups.
- C) ✗ Incorrect because CloudFormation can provision many AWS resource types for diverse architectures, not just static websites.
- D) ✗ Incorrect because although there is an initial learning curve, IaC typically speeds delivery and reduces errors over time.

---

## Topic 4: Certification / Interview Prep Scenarios

### Q4: Multi-AZ vs Multi-Region Decision

**Question:**
An e-commerce platform needs resilience for AZ-level failures with minimal complexity and lower cost than a full multi-Region setup.

Which architecture is the best first choice?

**Options:**
- A) Single-AZ deployment in one Region
- B) Multi-AZ deployment in one Region
- C) Multi-Region deployment with one AZ in each Region
- D) Edge-location-only deployment with no Region redundancy

**Answer:** **B) Multi-AZ deployment in one Region**

**Explanation:**
Multi-AZ deployment is the recommended first step for high availability within a Region. It provides fault isolation across Availability Zones, automatic failover patterns, and lower operational complexity than immediate multi-Region active deployments.

**Why not the others:**
- A) ✗ Single-AZ leaves a single point of failure.
- C) ✗ Multi-Region can improve resilience further, but is usually more complex/costly than needed for the stated requirement.
- D) ✗ Edge locations accelerate content delivery; they do not replace Region/AZ redundancy for core application workloads.

---

### Q5: Best Access Method by Use Case

**Question:**
Match each use case to the most suitable AWS interaction method.

| Use case                                                              | Best method |
|-----------------------------------------------------------------------|-------------|
| Repeatable infrastructure deployment across multiple Regions/accounts | ?           |
| One-off visual review of billing and dashboards                       | ?           |
| Application code directly invoking AWS service APIs                   | ?           |

**Answer:**

| Use case                                                              | Best method                |
|-----------------------------------------------------------------------|----------------------------|
| Repeatable infrastructure deployment across multiple Regions/accounts | **CloudFormation (IaC)**   |
| One-off visual review of billing and dashboards                       | **AWS Management Console** |
| Application code directly invoking AWS service APIs                   | **AWS SDKs**               |

**Explanation:**
CloudFormation is best for consistent, repeatable infrastructure lifecycle management. The Management Console is ideal for visual administration and dashboards. AWS SDKs are designed for integrating AWS API calls directly inside application code.

**Why not the others:**
- Using Console for repeatable multienvironment infrastructure introduces manual drift and lower reproducibility.
- Using CloudFormation for quick visual cost dashboards is not the intended workflow.
- Using CLI/Console instead of SDKs for in-app service calls is less suitable for application integration.

---

## 📊 Study Progress Tracker

| # | Category           | Question # | Topic                          | Status | Notes                                           |
|---|--------------------|------------|--------------------------------|--------|-------------------------------------------------|
| 1 | Infrastructure     | Q1         | Regions & Availability Zones   | ✅      | Select TWO: compliance + proximity              |
| 2 | CDN                | Q2         | Global Infrastructure Matching | ✅      | Matching: edge location, Region, AZ definitions |
| 3 | Global Deployment  | Q3         | CloudFormation & IaC           | ✅      | IaC for consistent repeatable deployments       |
| 4 | Certification Prep | Q4         | Multi-AZ vs Multi-Region       | ✅      | Prefer Multi-AZ first for AZ-level resilience   |
| 5 | Interview Prep     | Q5         | Access Method Selection        | ✅      | IaC vs Console vs SDK mapping                   |

**Legend:** ⏳ = Need Review | ✅ = Confident | 📝 = Added Notes

---

## Quick Facts to Remember

**Regions & Availability Zones:**
- Region selection factors: compliance, proximity, feature availability, and pricing
- Compliance is often the first filter if regulations constrain geography
- Proximity helps reduce latency for end users

**Edge Locations & CloudFront:**
- Edge locations are separate from Regions and are part of the Amazon Global Edge Network
- Edge locations cache content (images, video, apps, APIs) for low-latency delivery to end users
- Services at edge locations: CloudFront (CDN), AWS Global Accelerator, Amazon Route 53 (DNS)
- Route 53 converts human-readable URLs to machine-readable IP addresses
- Multi-AZ: seamless failover if one AZ fails; benefits include DR, business continuity, lower latency
- Multi-Region: failover at the Region level for maximum resilience

**Global Deployment:**
- CloudFormation is declarative IaC using templates to define AWS resources
- Same template can be deployed across Regions/accounts for consistent environments
- IaC reduces manual setup, improves repeatability, and lowers human error
- Access methods fit different use cases: Console (visual/admin), CLI/SDK (programmatic), CloudFormation (automated infrastructure lifecycle)

---

## Common Exam Patterns

**Pattern 1: "Region selection (Select TWO)"**
→ Prioritize compliance first, then proximity; eliminate distractors unrelated to regulations or latency.

**Pattern 2: "Match infrastructure elements to definitions"**
→ Region = largest geographic grouping (contains AZs); AZ = fault-isolated zone within Region (contains data centers); Edge location = outside Regions, purpose is caching/CDN delivery.

**Pattern 3: "Best tool for consistent multienvironment infrastructure"**
→ Choose CloudFormation/IaC when the requirement emphasizes repeatability, consistency, automation, and reduced manual error.

**Pattern 4: "Resilience with minimal complexity"**
→ Choose Multi-AZ first for high availability within a Region; escalate to Multi-Region for broader disaster tolerance.

---

**Module:** Going Global (Module 4)  
**Total Q&As:** 5 (3 course + 2 interview/cert prep)
