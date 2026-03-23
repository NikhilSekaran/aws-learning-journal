# Module 3: Exploring Compute Services - Q&A Review

**Purpose:** Quick reference guide for reviewing all Q&A from Module 3 Exploring Compute Services. Use this for self-testing and exam prep.

**How to Use:**
1. Read each question and try to answer without looking
2. Check your answer against the provided explanation
3. Mark ✅ if correct, ⏳ if it needs more review
4. Focus on ⏳ questions for final study

**Reference Notes:** [notes.md](notes.md)

---

## Topic 1: Compute Service Models

### Q1: Matching Responsibilities to Service Models

**Question:**
Match each responsibility to the correct AWS compute service model.

| Responsibility                                                     | Service Model |
|--------------------------------------------------------------------|---------------|
| Configure operating system, security patches, and network settings | ?             |
| Choose deployment options and configure environment settings       | ?             |
| Focus only on writing and deploying code                           | ?             |

**Answer:**

| Responsibility                                               | Service Model                                     |
|--------------------------------------------------------------|---------------------------------------------------|
| Configure OS, security patches, and network settings         | **Unmanaged** (e.g., Amazon EC2)                  |
| Choose deployment options and configure environment settings | **Managed** (e.g., ELB, SNS, SQS)                 |
| Focus only on writing and deploying code                     | **Fully Managed / Serverless** (e.g., AWS Lambda) |

**Explanation:**
- **Unmanaged (EC2):** AWS handles only the physical infrastructure. You manage the OS, security patches, network configurations, and scaling.
- **Managed (ELB/SNS/SQS):** AWS handles infrastructure operations. You configure deployment options and environment settings, but no server management is required.
- **Fully Managed / Serverless (Lambda):** AWS handles all infrastructure — provisioning, scaling, availability, maintenance. You only write, deploy, and secure your application code.

---

## Topic 2: AWS Lambda

### Q2: Lambda Shared Responsibility — Fintech Microservice

**Question:**
A development team at a fintech startup is building a customer-facing microservice using AWS Lambda. AWS manages the infrastructure, but the team must meet strict security and compliance requirements.

Which task is **still the team's responsibility** when using Lambda?

**Options:**
- A) Patching the underlying operating system
- B) Scaling the infrastructure
- C) Managing data access permissions
- D) Managing server availability

**Answer:** **C) Managing data access permissions**

**Explanation:**
With Lambda, AWS manages all infrastructure concerns — OS patching, scaling, and server availability. However, the Shared Responsibility Model still applies: customers remain responsible for application-level security, including IAM policies, data access permissions, and securing application code.

**Why not the others:**
- A) Patching the underlying OS ✗ AWS handles OS patching entirely; customers have no access to the underlying server
- B) Scaling the infrastructure ✗ Lambda auto-scales automatically based on request volume; no customer action required
- D) Managing server availability ✗ AWS manages Lambda's high availability; customers never configure or maintain servers

---

### Q3: Lambda Key Components — Photo Processing Workflow

**Question:**
A photography company uses Lambda to automatically process photos — resizing images, applying filters, and organizing files — every time a client uploads a new image.

Which key components are involved in running this automated workflow with Lambda? **(Select THREE.)**

**Options:**
- A) Lambda function
- B) Triggers
- C) Server provisioning
- D) Runtimes
- E) Manual scaling configuration

**Answer:** **A) Lambda function, B) Triggers, D) Runtimes**

**Explanation:**
Three core components drive every Lambda workflow: (1) The **Lambda function** contains the code to be executed. (2) A **trigger** (e.g., an S3 upload event) initiates execution automatically. (3) A **runtime** provides the language-specific environment (Python, Java, Node.js, etc.) that executes the function code. Server provisioning and manual scaling are not needed — Lambda handles both automatically.

**Why not the others:**
- C) Server provisioning ✗ Lambda is serverless — no servers are ever provisioned by the customer
- E) Manual scaling configuration ✗ Lambda scales automatically; customers never configure scaling manually

---

## Topic 3: Containers and Orchestration on AWS

### Q4: Containers — Solving Deployment Consistency

**Question:**
A developer built an application that runs flawlessly on their laptop, but when the team deploys it to a different environment, it crashes because of missing dependencies and configuration mismatches.

How do containers help solve this problem?

**Options:**
- A) By providing access to multiple operating systems for compatibility testing
- B) By packaging the application and everything it needs to run into one consistent environment
- C) By automatically scaling the application across multiple cloud providers
- D) By eliminating the need to write configuration files

**Answer:** **B) By packaging the application and everything it needs to run into one consistent environment**

**Explanation:**
Containers bundle the application code, runtime, libraries, dependencies, and configuration into a single portable unit. This guarantees the application behaves identically across developer laptops, staging, and production — directly solving the "it works on my machine" problem.

**Why not the others:**
- A) Multiple OS compatibility testing ✗ Containers share the host OS; they don't provide access to multiple operating systems
- C) Auto-scaling across cloud providers ✗ Containers provide portability, not automatic multi-cloud scaling
- D) No configuration files needed ✗ Containers still use configuration files; they just package them consistently

---

### Q5: Matching AWS Container Services

**Question:**
Match each AWS container service to its correct definition.

| Service     | Definition |
|-------------|------------|
| AWS Fargate | ?          |
| Amazon ECS  | ?          |
| Amazon EKS  | ?          |
| Amazon ECR  | ?          |

**Answer:**

| Service         | Definition                                                                    |
|-----------------|-------------------------------------------------------------------------------|
| **AWS Fargate** | Serverless compute engine for containers — removes the need to manage servers |
| **Amazon ECS**  | Scalable container orchestration service for running containers on AWS        |
| **Amazon EKS**  | Fully managed Kubernetes service for deploying and scaling containers         |
| **Amazon ECR**  | Stores, manages, and deploys OCI-compliant container images                   |

**Explanation:**
Amazon ECS and EKS are both **orchestration** services — they manage container lifecycle, scaling, and deployment. The key difference is that EKS uses open-source Kubernetes. Amazon ECR is the **registry** — it stores container images that ECS/EKS pull from. AWS Fargate is the **serverless compute** layer — it runs containers for both ECS and EKS without you managing any servers.

---

## Topic 4: Additional Compute Services

### Q6: Matching Additional Compute Services

**Question:**
Match each AWS service with the correct description.

| AWS Service           | Description |
|-----------------------|-------------|
| AWS Outposts          | ?           |
| AWS Elastic Beanstalk | ?           |
| Amazon Lightsail      | ?           |
| AWS Batch             | ?           |

**Answer:**

| AWS Service               | Description                                                     |
|---------------------------|-----------------------------------------------------------------|
| **AWS Outposts**          | Hybrid cloud service extending AWS to on-premises environments  |
| **AWS Elastic Beanstalk** | Managed service for deploying and scaling web applications      |
| **Amazon Lightsail**      | Simplified service with VPS, storage, databases, and networking |
| **AWS Batch**             | Managed service for large-scale batch computing workloads       |

**Explanation:**
AWS Elastic Beanstalk simplifies web application deployment and scaling. AWS Batch runs and scales large-scale batch jobs. Amazon Lightsail provides simple, predictable VPS-style hosting. AWS Outposts extends AWS services to on-premises infrastructure for hybrid cloud use cases.

---

### Q7: Startup Web App — Simplified Deployment with Auto Scaling

**Question:**
A startup is building a web application and wants a simple way to deploy code without managing infrastructure. They need auto-scaling and monitoring handled for them.

Which AWS service should they use?

**Options:**
- A) AWS Elastic Beanstalk
- B) Amazon EC2
- C) AWS Batch
- D) AWS Outposts

**Answer:** **A) AWS Elastic Beanstalk**

**Explanation:**
Elastic Beanstalk is purpose-built for deploying and managing web applications with minimal operational overhead. It automatically provisions the environment, configures scaling, and monitors application health, allowing teams to focus on development rather than infrastructure operations.

**Why not the others:**
- B) Amazon EC2 ✗ EC2 requires manual provisioning and management of infrastructure
- C) AWS Batch ✗ Batch is for batch/scheduled compute workloads, not interactive web app hosting
- D) AWS Outposts ✗ Outposts is for on-premises hybrid AWS deployments, not simplified app hosting

---

### Q8: Compliance-Driven Hybrid Deployment

**Question:**
A financial company must run workloads on premises due to strict compliance requirements but wants to use AWS services and tools consistently across environments.

Which AWS service meets their needs?

**Options:**
- A) AWS Elastic Beanstalk
- B) Amazon Lightsail
- C) AWS Batch
- D) AWS Outposts

**Answer:** **D) AWS Outposts**

**Explanation:**
AWS Outposts extends AWS infrastructure, services, APIs, and operational tooling to on-premises environments. This enables hybrid cloud architecture while meeting low-latency, data residency, and regulatory compliance requirements.

**Why not the others:**
- A) AWS Elastic Beanstalk ✗ Simplifies web app deployment but does not provide AWS infrastructure on premises
- B) Amazon Lightsail ✗ Simplified cloud VPS service, not a hybrid on-prem AWS extension
- C) AWS Batch ✗ Batch processing service, not designed to provide hybrid on-prem/cloud consistency

---

## Topic 5: Certification / Interview Prep Scenarios

### Q9: Choosing ECS vs EKS

**Question:**
Your team is building containerized workloads and wants a fully AWS-managed orchestration experience without managing Kubernetes complexity.

Which service is the best fit?

**Options:**
- A) Amazon EKS
- B) Amazon ECS
- C) AWS Batch
- D) AWS Outposts

**Answer:** **B) Amazon ECS**

**Explanation:**
Amazon ECS is AWS-native container orchestration designed for teams that want a simpler managed orchestration experience. It removes much of the Kubernetes operational complexity while still supporting scalable container deployments.

**Why not the others:**
- A) Amazon EKS ✗ Great for Kubernetes workloads, but adds Kubernetes control-plane concepts and complexity
- C) AWS Batch ✗ Optimized for batch jobs, not long-running microservices orchestration
- D) AWS Outposts ✗ Hybrid infrastructure extension, not a primary container orchestration service

---

### Q10: ECR Purpose in Container Architecture

**Question:**
What is the primary role of Amazon ECR in a containerized AWS architecture?

**Options:**
- A) Run containers serverlessly
- B) Schedule and scale container tasks
- C) Store and version container images
- D) Provide load balancing for container services

**Answer:** **C) Store and version container images**

**Explanation:**
Amazon ECR is a managed container image registry. Teams push images to ECR, and orchestration services such as ECS or EKS pull those images for deployment.

**Why not the others:**
- A) Run containers serverlessly ✗ That is Fargate's role
- B) Schedule and scale tasks ✗ That is orchestration responsibility (ECS/EKS)
- D) Load balancing ✗ ELB provides load balancing capabilities

---

### Q11: Fargate vs EC2 for Containers

**Question:**
A startup wants to run containers without managing EC2 instances. They use Amazon ECS for orchestration.

Which compute option should they select?

**Options:**
- A) Amazon EC2 launch type
- B) AWS Fargate launch type
- C) AWS Batch
- D) Amazon Lightsail

**Answer:** **B) AWS Fargate launch type**

**Explanation:**
Fargate is the serverless compute engine for containers. With ECS + Fargate, AWS manages the underlying servers, letting teams focus only on container definitions and application behavior.

**Why not the others:**
- A) EC2 launch type ✗ Requires you to manage instance capacity and lifecycle
- C) AWS Batch ✗ Batch workloads, not general microservice hosting
- D) Amazon Lightsail ✗ Simplified VPS service, not ECS container compute backend

---

### Q12: Lambda 15-Minute Limit Implication

**Question:**
Which workload is least appropriate for AWS Lambda based on service limits?

**Options:**
- A) API request processing in under 1 second
- B) S3-triggered image thumbnail generation
- C) Continuous process that runs for 45 minutes per execution
- D) Event-driven ETL step lasting 2 minutes

**Answer:** **C) Continuous process that runs for 45 minutes per execution**

**Explanation:**
Lambda has a maximum execution duration of 15 minutes per invocation. Long-running continuous workloads are better suited for EC2, containers, or other compute services.

**Why not the others:**
- A) API processing ✗ Ideal Lambda use case
- B) S3-triggered image processing ✗ Classic event-driven Lambda pattern
- D) 2-minute ETL step ✗ Well within Lambda execution limits

---

### Q13: Outposts Use Case Identification

**Question:**
Which requirement most strongly indicates AWS Outposts as the right solution?

**Options:**
- A) Need cheapest web hosting for a personal blog
- B) Need AWS services in on-premises data center for latency and data residency
- C) Need managed Kubernetes in AWS Regions only
- D) Need to run ad-hoc batch jobs monthly

**Answer:** **B) Need AWS services in on-premises data center for latency and data residency**

**Explanation:**
Outposts is designed for hybrid cloud scenarios where workloads must run on premises while maintaining a consistent AWS operational model.

**Why not the others:**
- A) Personal blog ✗ Lightsail is typically better suited
- C) Managed Kubernetes only in Region ✗ EKS in AWS Regions covers this
- D) Monthly batch jobs ✗ AWS Batch is better aligned

---

### Q14: Beanstalk Value Proposition

**Question:**
What is a key advantage of AWS Elastic Beanstalk compared with manually deploying on EC2?

**Options:**
- A) No visibility into underlying resources
- B) Automatic provisioning, scaling, and health monitoring for web apps
- C) It replaces the need for application code deployment
- D) It only supports Java applications

**Answer:** **B) Automatic provisioning, scaling, and health monitoring for web apps**

**Explanation:**
Elastic Beanstalk automates operational tasks (environment setup, scaling, monitoring) while still allowing visibility and control over underlying AWS resources.

**Why not the others:**
- A) No visibility ✗ You retain visibility and access to resources
- C) Replaces code deployment ✗ You still deploy your application code
- D) Java only ✗ Supports multiple platforms/languages

---

### Q15: Batch Workload Selection

**Question:**
Which scenario is best aligned with AWS Batch?

**Options:**
- A) Real-time multiplayer game state updates
- B) Periodic rendering of 2 million media files overnight
- C) Hosting a marketing website with low traffic
- D) On-premises low-latency transaction processing

**Answer:** **B) Periodic rendering of 2 million media files overnight**

**Explanation:**
AWS Batch is purpose-built for large-scale, parallel, scheduled or queue-driven compute jobs such as rendering, simulation, and analytics processing.

**Why not the others:**
- A) Real-time game updates ✗ Better fit for low-latency event services, not batch
- C) Marketing website ✗ Beanstalk/Lightsail are more appropriate
- D) On-prem low latency ✗ Outposts is relevant there

---

### Q16: Shared Responsibility in Serverless

**Question:**
In AWS Lambda, which responsibility remains with the customer?

**Options:**
- A) Patching host operating systems
- B) Managing regional infrastructure availability
- C) Securing function code and IAM permissions
- D) Replacing failed physical servers

**Answer:** **C) Securing function code and IAM permissions**

**Explanation:**
Even in fully managed services, customers remain responsible for security in the cloud, including application logic, IAM authorization, and data access controls.

**Why not the others:**
- A) Patching host OS ✗ AWS responsibility
- B) Regional availability ✗ AWS responsibility
- D) Physical server replacement ✗ AWS responsibility

---

### Q17: ECS/EKS/Fargate Relationship

**Question:**
Which statement correctly describes ECS, EKS, and Fargate?

**Options:**
- A) ECS and EKS are compute engines; Fargate is a registry
- B) ECS and EKS are registries; Fargate is an orchestrator
- C) ECS and EKS are orchestrators; Fargate is a serverless compute engine
- D) All three are the same service with different pricing

**Answer:** **C) ECS and EKS are orchestrators; Fargate is a serverless compute engine**

**Explanation:**
ECS and EKS manage container deployment/orchestration, while Fargate provides serverless container runtime infrastructure for tasks/pods launched by those orchestrators.

**Why not the others:**
- A) Compute engines + registry ✗ Incorrect roles
- B) Registries + orchestrator ✗ Incorrect roles
- D) Same service ✗ Distinct services with distinct responsibilities

---

### Q18: Lightsail Best Fit

**Question:**
Which workload is most suitable for Amazon Lightsail?

**Options:**
- A) Complex multi-cluster Kubernetes platform
- B) Simple blog or small business website needing predictable monthly pricing
- C) High-frequency scientific simulation requiring dynamic batch scaling
- D) Hybrid on-premises compliance workload

**Answer:** **B) Simple blog or small business website needing predictable monthly pricing**

**Explanation:**
Lightsail is designed for simple workloads with straightforward deployment and predictable monthly costs, making it a strong fit for small web applications and websites.

**Why not the others:**
- A) Multi-cluster Kubernetes ✗ Better suited for EKS
- C) Scientific simulation ✗ Better suited for AWS Batch
- D) Hybrid compliance workload ✗ Better suited for Outposts

---

## 📊 Study Progress Tracker

| #  | Category            | Question # | Topic                               | Status | Notes |
|----|---------------------|------------|-------------------------------------|--------|-------|
| 1  | Service Models      | Q1         | Unmanaged vs Managed vs Serverless  | ⏳      |       |
| 2  | Lambda              | Q2         | Lambda Shared Responsibility        | ⏳      |       |
| 3  | Lambda              | Q3         | Lambda Key Components               | ⏳      |       |
| 4  | Containers          | Q4         | Containers — Deployment Consistency | ⏳      |       |
| 5  | Containers          | Q5         | AWS Container Services Matching     | ⏳      |       |
| 6  | Additional Services | Q6         | Additional Services Matching        | ⏳      |       |
| 7  | Elastic Beanstalk   | Q7         | Startup Web App Service Choice      | ⏳      |       |
| 8  | Outposts            | Q8         | Compliance-Driven Hybrid Deployment | ⏳      |       |
| 9  | Advanced            | Q9         | Choosing ECS vs EKS                 | ⏳      |       |
| 10 | Advanced            | Q10        | ECR Purpose in Architecture         | ⏳      |       |
| 11 | Advanced            | Q11        | Fargate vs EC2 for Containers       | ⏳      |       |
| 12 | Advanced            | Q12        | Lambda Duration Fit                 | ⏳      |       |
| 13 | Advanced            | Q13        | Outposts Use Case Identification    | ⏳      |       |
| 14 | Advanced            | Q14        | Beanstalk Value Proposition         | ⏳      |       |
| 15 | Advanced            | Q15        | Batch Workload Selection            | ⏳      |       |
| 16 | Advanced            | Q16        | Shared Responsibility in Lambda     | ⏳      |       |
| 17 | Advanced            | Q17        | ECS/EKS/Fargate Relationship        | ⏳      |       |
| 18 | Advanced            | Q18        | Lightsail Best Fit                  | ⏳      |       |

**Legend:** ⏳ = Need Review | ✅ = Confident | 📝 = Added Notes

---

## Quick Facts to Remember

**Compute Service Models:**
- **Unmanaged (EC2):** Full control; you manage OS, patches, network config; AWS manages physical hardware only
- **Managed (ELB/SNS/SQS):** AWS manages infrastructure; you configure deployment options and settings
- **Serverless/Fully Managed (Lambda):** AWS manages all infrastructure; you write & secure application code only
- **Shared Responsibility still applies:** Even in serverless, you own the security of your application code

**Lambda & Serverless:**
- **Event-driven:** code runs only when triggered; no idle server costs
- **Auto-scales:** from 1 to thousands of concurrent executions automatically
- **Max duration:** 15 minutes per invocation
- **Billing:** per millisecond of compute time + memory allocated
- **Key components:** Lambda function (code) + Trigger (event source) + Runtime (language environment)
- **Customer owns:** application code security, IAM/data access permissions
- **AWS owns:** OS patching, scaling, server availability, infrastructure

**Elastic Beanstalk:**
- **Managed deployment platform** for web apps and APIs
- Handles provisioning, autoscaling, load balancing, and health monitoring
- Supports Java, .NET, Python, Node.js, Docker, and more
- Gives control/visibility into underlying AWS resources

**Containers & Orchestration:**
- **Containers** = portable units packaging code + dependencies + config → consistent across all environments
- **Containers vs VMs:** containers share host OS (lighter, faster); VMs run full OS via hypervisor (heavier)
- **Orchestration** automates: deployment, scaling, health monitoring, recovery, updates
- **Amazon ECS** = AWS-native Docker container orchestration; simpler, integrated
- **Amazon EKS** = Managed Kubernetes on AWS; open-source, more flexible for large/hybrid workloads
- **Amazon ECR** = Container image registry; OCI-compliant; integrates with ECS, EKS, Fargate
- **AWS Fargate** = Serverless compute for containers; works with ECS & EKS; no server management
- **Workflow:** Build image → Push to ECR → Choose ECS or EKS → Choose EC2 or Fargate

**Additional Compute Services:**
- **AWS Batch** = managed large-scale batch processing with automatic scheduling and scaling
- **Amazon Lightsail** = simplified VPS + storage + networking with predictable monthly pricing
- **AWS Outposts** = AWS infrastructure/services on premises for hybrid cloud consistency
- **Choose by workload:** Web app simplicity → Beanstalk; Batch jobs → Batch; Simple hosting → Lightsail; Hybrid/compliance → Outposts

**Interview / Certification Focus:**
- **Service-selection questions** dominate this module — map requirement keywords to the right service
- **Serverless boundary:** Lambda/Fargate remove server management but not app-level security responsibility
- **Container stack roles:** ECR stores images; ECS/EKS orchestrate; Fargate/EC2 provide compute runtime
- **Hybrid signal words:** low latency + data residency + on-prem consistency → Outposts
- **Batch signal words:** large-scale parallel offline processing → AWS Batch

---

## Common Exam Patterns

**Pattern 1: "Which compute service should I choose?"**
→ Identify workload style first: Event-driven short tasks → Lambda; Containerized microservices → ECS/EKS; Simple web app deploy → Beanstalk; Batch jobs → AWS Batch; Hybrid/on-prem AWS → Outposts.

**Pattern 2: "Who is responsible for what?"**
→ In managed/serverless services, AWS handles infrastructure operations, but you still own code, IAM policies, and data-access security.

**Pattern 3: "Containers architecture flow"**
→ Think in order: Build image → Store in ECR → Orchestrate with ECS/EKS → Run on EC2 or Fargate.

**Pattern 4: "ECS vs EKS"**
→ ECS for simpler AWS-native orchestration; EKS when Kubernetes ecosystem/control is required.

**Pattern 5: "Fargate vs EC2 launch type"**
→ Need server control/customization → EC2; want serverless operations and less overhead → Fargate.

---

**Module:** Exploring Compute Services (Module 3)  
**Total Q&As:** 18 (8 course + 10 interview/cert prep)
