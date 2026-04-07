# Module 5: Networking - Q&A Review

**Purpose:** Quick reference guide for reviewing all Q&A from Module 5 Networking. Use this for self-testing and exam prep.

**How to Use:**
1. Read each question and try to answer without looking
2. Check your answer against the provided explanation
3. Mark ✅ if correct, ⏳ if it needs more review
4. Focus on ⏳ questions for final study

**Reference Notes:** [notes.md](notes.md)

---

## Topic 1: Subnets and Network Gateways

### Q1: Subnet Uses in Amazon VPC (Select THREE)

**Question:**
What are the uses of a subnet in an Amazon VPC? (Select THREE.)

**Options:**
- A) Can be used to share public resources
- B) Can be used to organize your resources
- C) Can provide high availability because they consist of one or more discrete data centers
- D) Can provide a centralized interface for accessing and managing various AWS resources and services
- E) Can be used to isolate resources and keep them private
- F) Can be used as an on-demand and scalable computing capacity in the AWS Cloud

**Answer:** **A) Can be used to share public resources, B) Can be used to organize your resources, and E) Can be used to isolate resources and keep them private**

**Explanation:**
Subnets divide a VPC into smaller segments, enabling three core functions: organizing AWS resources into logical groups, sharing public-facing resources through public subnets (connected to an internet gateway), and isolating private resources through private subnets with no direct internet access. Public subnets are commonly used for customer-facing websites; private subnets are commonly used for databases and back-end resources.

**Why not the others:**
- C) Can provide high availability because they consist of one or more discrete data centers ✗ This describes Availability Zones. AZs consist of one or more discrete data centers with redundant power and connectivity; subnets are simply IP address ranges within a VPC.
- D) Can provide a centralized interface for accessing and managing various AWS resources and services ✗ This describes the AWS Management Console, not subnets.
- F) Can be used as an on-demand and scalable computing capacity in the AWS Cloud ✗ This describes Amazon EC2 compute capacity, not subnets.

---

## Topic 2: VPC (Virtual Private Cloud)

### Q2: VPC Gateway Connection for Corporate Data Center

**Question:**
A company is setting up their Amazon VPC. They need to connect their corporate data center through the internet with a secure connection. They also want to make sure the resources are isolated from the public.

Which solution would BEST meet their needs?

**Options:**
- A) An internet gateway with a public subnet holding the resources in the Amazon VPC
- B) A virtual private gateway with a VPN connection and a private subnet in the Amazon VPC
- C) An internet gateway with an Amazon VPC and no subnets
- D) An internet gateway with an Amazon VPC and a public subnet

**Answer:** **B) A virtual private gateway with a VPN connection and a private subnet in the Amazon VPC**

**Explanation:**
The company needs two things: a secure connection from their corporate data center to AWS, and resources isolated from the public internet. A virtual private gateway establishes an encrypted VPN connection from an approved private network (the corporate data center) into the VPC, allowing only authorized traffic. A private subnet ensures the resources inside are not publicly accessible. Together, these two components satisfy both requirements.

**Why not the others:**
- A) An internet gateway with a public subnet holding the resources in the Amazon VPC ✗ An internet gateway opens the VPC to the public internet, and a public subnet makes resources publicly accessible — the opposite of the isolation requirement.
- C) An internet gateway with an Amazon VPC and no subnets ✗ An internet gateway allows public traffic. Without subnets, there is no way to organize or isolate resources either.
- D) An internet gateway with an Amazon VPC and a public subnet ✗ Same problem as A — this exposes resources to the public internet rather than isolating them.

---

## Topic 3: AWS Connectivity Services

### Q3: AWS Direct Connect for Large-Scale Migration

**Question:**
A company is conducting a large-scale migration of their on-premises data center with their data warehouse and data backup. They need a solution that will meet the large amount of bandwidth requirements during migration. The solution will also be used for their ongoing data transfers after the move because they will retain part of their on-premises data center for a hybrid cloud solution.

Which AWS solution would best meet their needs?

**Options:**
- A) AWS Client VPN
- B) AWS Site-to-Site VPN
- C) AWS Direct Connect link to their on-premises network and the AWS Cloud
- D) AWS Private Link to their on-premises datacenter

**Answer:** **C) AWS Direct Connect link to their on-premises network and the AWS Cloud**

**Explanation:**
Direct Connect provides a dedicated private connection with high, consistent bandwidth — precisely what is needed for large-scale data migration and for ongoing hybrid cloud data transfers. It bypasses the public internet entirely, ensuring reliable throughput without congestion. Because the company retains part of their on-premises data center, they also need a persistent long-term connectivity solution, which Direct Connect supports.

**Why not the others:**
- A) AWS Client VPN ✗ Client VPN is designed for remote worker access to AWS or on-premises resources. It does not provide the high bandwidth required for migrating a data warehouse.
- B) AWS Site-to-Site VPN ✗ Site-to-Site VPN routes through the shared public internet, which cannot guarantee the bandwidth needed for large-scale migration or consistent ongoing hybrid transfers.
- D) AWS Private Link to their on-premises datacenter ✗ PrivateLink provides private connectivity between VPCs and services within AWS; it is not designed for connecting on-premises data centers to AWS.

---

## Topic 4: VPC Gateway Selection

### Q4: Virtual Private Gateway for Corporate Data Center

**Question:**
A company is choosing the type of gateway for their network. They need to connect their corporate data center with their private subnet in their Amazon Virtual Private Cloud. Their gateway needs to allow only protected internet traffic to enter into the Amazon VPC. It should also allow a connection between their Amazon VPC and a private network only if it is coming from an approved network.

Which type of gateway would BEST meet their needs?

**Options:**
- A) Internet gateway
- B) Virtual private gateway
- C) AWS Transit Gateway
- D) Amazon API Gateway

**Answer:** **B) Virtual private gateway**

**Explanation:**
A virtual private gateway is the AWS-side VPN endpoint that allows encrypted, protected traffic from an approved private network (such as a corporate data center) to enter the VPC. It does not allow public internet traffic — only VPN-authenticated connections from approved networks pass through. This matches both requirements: protected traffic entry and approved-network-only access.

**Why not the others:**
- A) Internet gateway ✗ An internet gateway allows any public internet traffic into the VPC. It does not restrict access to approved networks only — the opposite of what is required.
- C) AWS Transit Gateway ✗ Transit Gateway connects multiple VPCs and on-premises networks through a central hub. It is not the dedicated endpoint for approved-only encrypted VPN access from a single corporate data center.
- D) Amazon API Gateway ✗ Amazon API Gateway is used for creating, publishing, and managing APIs. It is not a network gateway for VPC connectivity between a data center and a VPC.

---

## Topic 5: Security Groups and Network ACLs

### Q5: Security Groups for Individual EC2 Instance Control

**Question:**
A retail customer is setting up their application in the AWS Cloud. The application requires a lot of control in defining traffic rules for the individual Amazon EC2 instances in their public subnet.

Which solution would BEST meet the requirements for securing the resources?

**Options:**
- A) Change all the subnets to private subnets to avoid accessing from the public internet.
- B) Set up security groups for the EC2 instances based on the application requirements.
- C) Set up network ACLs for the EC2 instances based on the application requirements.
- D) Set up a public subnet with strong passwords that meet the customer's requirements.

**Answer:** **B) Set up security groups for the EC2 instances based on the application requirements.**

**Explanation:**
Security groups operate at the instance level and provide granular, per-instance control over inbound and outbound traffic. When the requirement is fine-grained traffic rule control for individual EC2 instances, security groups are the correct tool. Network ACLs operate at the subnet level and apply broad rules to all traffic entering or exiting a subnet, not per-instance rules.

**Why not the others:**
- A) Change all the subnets to private subnets to avoid accessing from the public internet ✗ This removes public accessibility entirely and does not address the requirement for fine-grained traffic control on EC2 instances.
- C) Set up network ACLs for the EC2 instances based on the application requirements ✗ Network ACLs apply at the subnet level, not the instance level. They cannot define rules for individual EC2 instances.
- D) Set up a public subnet with strong passwords that meet the customer's requirements ✗ Passwords are an authentication mechanism, not a network traffic control tool. They do not define inbound or outbound traffic rules.

---

## Topic 6: Stateless Packet Filtering

### Q6: Network Component That Performs Stateless Packet Filtering

**Question:**
Which network component performs stateless packet filtering?

**Options:**
- A) Private subnet
- B) Network access control list (network ACL)
- C) Amazon VPC
- D) Security groups

**Answer:** **B) Network access control list (network ACL)**

**Explanation:**
Network ACLs are stateless — they evaluate every packet that crosses a subnet boundary independently, without remembering previous requests or responses. This means return traffic must also be explicitly allowed by the ACL rules. Security groups, by contrast, are stateful and automatically allow return traffic for established connections.

**Why not the others:**
- A) Private subnet ✗ A private subnet is a network segment that restricts public internet access. It is not itself a packet-filtering component; it does not evaluate or enforce traffic rules.
- C) Amazon VPC ✗ A VPC is the isolated network environment in AWS. It is the container for subnets, gateways, and other components, but it does not itself perform packet filtering.
- D) Security groups ✗ Security groups perform stateful packet filtering. They remember prior decisions and automatically permit return traffic for approved connections, unlike the stateless behaviour of network ACLs.

---

## Topic 7: Global Networking

### Q7: CloudFront for Global Content Delivery

**Question:**
An enterprise customer with a worldwide sales force wants to deliver a large library of media-rich sales training content with low latency and reduced costs. Which AWS service would BEST fit the customer's need?

**Options:**
- A) Amazon VPC
- B) Amazon Route 53
- C) Amazon CloudFront
- D) AWS Global Accelerator

**Answer:** **C) Amazon CloudFront**

**Explanation:**
CloudFront is a CDN that caches content at edge locations worldwide, delivering media-rich libraries (videos, images) to users with low latency and reduced origin-server costs. It is purpose-built for distributing large content libraries globally.

**Why not the others:**
- A) Amazon VPC ✗ A VPC provides private network isolation for AWS resources. It does not distribute or cache content globally and has no CDN capability.
- B) Amazon Route 53 ✗ Route 53 is a DNS service that routes user requests to endpoints. It translates domain names to IP addresses but does not store or deliver content.
- D) AWS Global Accelerator ✗ Global Accelerator accelerates network-layer performance using the AWS private network. It does not cache content or function as a CDN.

---

## Topic 8: Route 53 and Domain Management

### Q8: Route 53 for Domain Name Management

**Question:**
After years of working with different domain registration companies, a media company wants to manage all existing domain names and register new ones through a single service. Which AWS service would BEST fit the customer's need?

**Options:**
- A) Amazon VPC
- B) Amazon Route 53
- C) Amazon CloudFront
- D) AWS Global Accelerator

**Answer:** **B) Amazon Route 53**

**Explanation:**
Route 53 allows businesses to register new domain names and transfer DNS records from other registrars, enabling management of all domain names in one location with globally dispersed DNS servers.

**Why not the others:**
- A) Amazon VPC ✗ A VPC creates an isolated virtual network for AWS resources. It has no domain name registration or DNS management capabilities.
- C) Amazon CloudFront ✗ CloudFront is a CDN for delivering content with low latency. It does not manage domain names or DNS records.
- D) AWS Global Accelerator ✗ Global Accelerator optimizes routing through the AWS private network. It does not offer domain registration or DNS record management.

---

## Topic 9: Global Architectures

### Q9: Direct Connect for High Bandwidth and Compliance

**Question:**
A healthcare company wants to create a dedicated network connection to AWS for heavy data transfers. They also have compliance requirements due to the sensitive nature of their patient data. Which connection to AWS would BEST meet their needs?

**Options:**
- A) Standard internet connection from the client to an internet gateway in the VPC in the AWS Cloud
- B) VPN connection from their corporate data center to the AWS Cloud
- C) VPN connection from their corporate data center to a virtual private gateway to their Amazon VPC
- D) AWS Direct Connect connection from their corporate data center to a virtual private gateway in their VPC in the AWS Cloud

**Answer:** **D) AWS Direct Connect connection from their corporate data center to a virtual private gateway in their VPC in the AWS Cloud**

**Explanation:**
Direct Connect is a dedicated private fiber connection that bypasses the public internet entirely. It provides consistent high bandwidth for heavy data transfers and meets compliance requirements by keeping traffic off shared public infrastructure — making it the correct answer when both high bandwidth and compliance are requirements.

**Why not the others:**
- A) Standard internet connection ✗ Provides no encryption, no dedicated bandwidth, and no compliance guarantees. Entirely unsuitable for sensitive patient data.
- B) VPN to the AWS Cloud ✗ A VPN encrypts traffic but shares public internet bandwidth. Heavy payloads cause slowdowns, and it cannot guarantee the compliance posture of a dedicated private connection.
- C) VPN to virtual private gateway ✗ More specific than option B but still relies on shared internet bandwidth. Does not meet the high-bandwidth requirement or provide the compliance guarantees of a dedicated connection.

---

## Topic 10: Certification / Interview Prep Scenarios

### Q10: Security Layer for EC2 — Stateful vs. Stateless

**Question:**
A solutions architect is designing a two-tier web application in an Amazon VPC. The web tier (EC2 instances in a public subnet) needs to accept HTTPS traffic from the internet and communicate with the database tier (EC2 instances in a private subnet). The architect wants to ensure that return traffic for accepted connections is automatically allowed without needing explicit outbound rules, while traffic crossing subnet boundaries is strictly evaluated in both directions. Which combination correctly describes the security components that meet these requirements?

**Options:**
- A) Security groups at the subnet level (stateless) and network ACLs at the instance level (stateful)
- B) Network ACLs at the subnet level (stateless) and security groups at the instance level (stateful)
- C) Security groups at both the subnet and instance level (both stateful)
- D) Network ACLs at both the subnet and instance level (both stateless)

**Answer:** **B) Network ACLs at the subnet level (stateless) and security groups at the instance level (stateful)**

**Explanation:**
AWS uses a two-layer security model in a VPC. Network ACLs operate at the subnet boundary and are stateless — they evaluate every packet crossing the subnet in both directions independently, so explicit rules are needed for both inbound and outbound traffic. Security groups operate at the EC2 instance level and are stateful — when an inbound connection is allowed, the return traffic is automatically permitted regardless of outbound rules. This combination satisfies the stated requirements: stateful automatic return traffic at the instance level (security groups) and strict bidirectional evaluation at the subnet boundary (network ACLs).

**Why not the others:**
- A) Security groups at the subnet level (stateless) and network ACLs at the instance level (stateful) ✗ The scope and stateful/stateless properties are reversed. Security groups are instance-level and stateful; network ACLs are subnet-level and stateless.
- C) Security groups at both the subnet and instance level (both stateful) ✗ Security groups only operate at the instance level, not the subnet level. Network ACLs — not security groups — govern traffic at the subnet boundary.
- D) Network ACLs at both the subnet and instance level (both stateless) ✗ Network ACLs only operate at the subnet boundary. Instance-level traffic filtering is performed by security groups, which are stateful, not stateless.

---

### Q11: CloudFront vs. Global Accelerator

**Question:**
A company runs a globally distributed web application that serves dynamic API requests to users in multiple continents. Response times are slow for users far from the origin server. The team needs a solution to reduce latency for these dynamic, non-cacheable requests by routing them over the AWS private network instead of the public internet. Which service BEST meets this requirement?

**Options:**
- A) Amazon CloudFront
- B) Amazon Route 53 with latency-based routing
- C) AWS Global Accelerator
- D) AWS Direct Connect

**Answer:** **C) AWS Global Accelerator**

**Explanation:**
Global Accelerator routes traffic through the AWS private global network using anycast IP addresses, reducing latency for dynamic, non-cacheable content that cannot be served from a CDN cache. CloudFront is optimised for caching static or semi-static content at edge locations — it cannot accelerate dynamic API responses that must always reach the origin. Global Accelerator is the right choice when the requirement is private-network routing for dynamic traffic rather than edge caching.

**Why not the others:**
- A) Amazon CloudFront ✗ CloudFront caches content at edge locations and is designed for static or cacheable content (images, videos, web pages). It does not accelerate dynamic non-cacheable API requests via the AWS private network.
- B) Amazon Route 53 with latency-based routing ✗ Route 53 directs users to the lowest-latency AWS Region, but traffic still travels over the public internet. It does not route packets through the AWS private global network.
- D) AWS Direct Connect ✗ Direct Connect provides a dedicated private link between an on-premises data center and AWS. It does not improve latency for end-user requests from the public internet to a globally distributed web application.

---

### Q12: Making a Subnet Truly Public

**Question:**
A developer created a new subnet inside an Amazon VPC and launched an EC2 instance with a public IP address. However, the instance cannot communicate with the internet. The VPC has an internet gateway already attached. What is the MOST LIKELY missing configuration?

**Options:**
- A) The EC2 instance does not have a security group attached
- B) The subnet's route table does not have a route sending internet-bound traffic (0.0.0.0/0) to the internet gateway
- C) The VPC does not have a second internet gateway for redundancy
- D) The subnet needs to be in a different Availability Zone

**Answer:** **B) The subnet's route table does not have a route sending internet-bound traffic (0.0.0.0/0) to the internet gateway**

**Explanation:**
Attaching an internet gateway to a VPC is only the first step. For a subnet to be truly public, its associated route table must have a route with destination `0.0.0.0/0` pointing to the internet gateway. Without this route, outbound internet traffic has nowhere to go and the instance cannot reach the internet even if it has a public IP. This is also the step that makes a subnet "public" — a private subnet has no such route.

**Why not the others:**
- A) The EC2 instance does not have a security group attached ✗ Every EC2 instance must have a security group and gets one by default. A missing or restrictive security group would block specific ports, but would not prevent all internet communication as described.
- C) The VPC does not have a second internet gateway for redundancy ✗ A VPC can only have one internet gateway attached. Internet gateways are highly available by design and do not require redundant copies.
- D) The subnet needs to be in a different Availability Zone ✗ The AZ of a subnet has no bearing on whether it can route traffic to an internet gateway. Public routing is determined by the route table association, not the AZ.

---

### Q13: Default Network ACL vs. Custom Network ACL

**Question:**
A security engineer is reviewing network access control lists in a company's AWS account. She notices that the default network ACL behaves differently from a newly created custom network ACL. Which statement CORRECTLY describes this difference?

**Options:**
- A) The default network ACL denies all inbound and outbound traffic; a custom network ACL allows all traffic until rules are added
- B) The default network ACL allows all inbound and outbound traffic; a custom network ACL denies all traffic until explicit allow rules are added
- C) Both the default and custom network ACLs deny all traffic by default
- D) Both the default and custom network ACLs allow all traffic by default

**Answer:** **B) The default network ACL allows all inbound and outbound traffic; a custom network ACL denies all traffic until explicit allow rules are added**

**Explanation:**
AWS creates a default network ACL for every VPC that allows all inbound and outbound traffic by default — it is permissive out of the box. When you create a custom network ACL, all inbound and outbound traffic is denied until you explicitly add allow rules. All network ACLs (default and custom) also have an implicit explicit-deny rule at the end of the list that denies any traffic not matched by a prior rule.

**Why not the others:**
- A) The default network ACL denies all inbound and outbound traffic ✗ This is the opposite of the correct behaviour. It is the custom ACL that starts with a deny-all posture, not the default.
- C) Both the default and custom network ACLs deny all traffic by default ✗ Incorrect for the default ACL, which allows all traffic by default to avoid breaking connectivity in new VPCs.
- D) Both the default and custom network ACLs allow all traffic by default ✗ Incorrect for custom ACLs, which start in a deny-all state requiring explicit allow rules to permit traffic.

---

### Q14: Choosing the Right Private Connectivity Service

**Question:**
A company runs a SaaS application hosted in an Amazon VPC. They want to allow customers (who operate their own AWS accounts and VPCs) to privately access this SaaS application without the traffic traversing the public internet, without requiring VPN connections or Direct Connect links, and without exposing the entire SaaS VPC to the customers. Which AWS service BEST meets this requirement?

**Options:**
- A) AWS Site-to-Site VPN
- B) VPC Peering
- C) AWS PrivateLink
- D) AWS Direct Connect

**Answer:** **C) AWS PrivateLink**

**Explanation:**
AWS PrivateLink enables a VPC to privately access a specific service or endpoint in another VPC (or AWS service) without internet gateways, NAT devices, public IP addresses, VPN connections, or Direct Connect. The SaaS provider exposes their service via a VPC endpoint service, and customers create interface VPC endpoints in their own VPCs to connect. Only the specific service endpoint is accessible — the entire SaaS VPC is never exposed to the customer.

**Why not the others:**
- A) AWS Site-to-Site VPN ✗ Site-to-Site VPN creates an encrypted tunnel between an on-premises network and a VPC over the public internet. It does not provide private AWS-to-AWS service access without internet traversal, and it exposes broader network connectivity rather than a single service endpoint.
- B) VPC Peering ✗ VPC Peering connects two VPCs so their resources can communicate directly, but it exposes the entire CIDR ranges of both VPCs. It does not provide selective single-service access, and it requires non-overlapping CIDR blocks and individual route table entries.
- D) AWS Direct Connect ✗ Direct Connect is a dedicated physical private link between an on-premises data center and AWS. It is not designed for AWS-account-to-AWS-account private service access and requires physical infrastructure setup.

---

## 📊 Study Progress Tracker

| # | Category | Question # | Topic | Status | Notes |
|---|----------|------------|-------|--------|-------|
| 1 | Networking | Q1 | Subnets & Network Gateways | ✅ | Select THREE: share public, organize, isolate private |
| 2 | VPC | Q2 | VPC Gateway Connection | ✅ | Virtual private gateway + VPN + private subnet for secure isolated access |
| 3 | Connectivity | Q3 | AWS Direct Connect | ✅ | Direct Connect for large-scale migration and hybrid cloud |
| 4 | VPC Gateways | Q4 | VPC Gateway Selection | ✅ | Virtual private gateway for approved-network-only protected access |
| 5 | Security Groups & NACLs | Q5 | Security Groups for EC2 Instance Control | ✅ | Instance-level security groups for fine-grained per-EC2 traffic rules |
| 6 | Stateless Filtering | Q6 | Stateless Packet Filtering | ✅ | Network ACLs are stateless; security groups are stateful |
| 7 | Global Networking | Q7 | CloudFront for Global Content Delivery | ✅ | CDN caches content at edge locations; low latency for media-rich libraries |
| 8 | Route 53 & DNS | Q8 | Route 53 for Domain Name Management | ✅ | Route 53 registers domains and transfers DNS records from other registrars |
| 9 | Global Architectures | Q9 | Direct Connect for High Bandwidth and Compliance | ✅ | Direct Connect = dedicated line; high bandwidth + compliance; VPN shares internet bandwidth |
| 10 | Certification Prep | Q10 | Security Groups vs. NACLs — Scope & State | ✅ | NACLs = subnet-level stateless; security groups = instance-level stateful |
| 11 | Certification Prep | Q11 | CloudFront vs. Global Accelerator | ✅ | CloudFront = CDN edge caching for static content; Global Accelerator = private-network routing for dynamic traffic |
| 12 | Certification Prep | Q12 | Making a Subnet Truly Public | ✅ | Internet gateway attached + route table 0.0.0.0/0 → IGW required; just attaching IGW is not enough |
| 13 | Certification Prep | Q13 | Default vs. Custom Network ACL | ✅ | Default ACL allows all traffic; custom ACL denies all until explicit allow rules added |
| 14 | Certification Prep | Q14 | PrivateLink for SaaS Private Access | ✅ | PrivateLink exposes single service endpoint privately; no internet, no VPN, no full-VPC exposure |

**Legend:** ⏳ = Need Review | ✅ = Confident | 📝 = Added Notes

---

## Quick Facts to Remember

**VPC:**
- Amazon VPC provisions a logically isolated section of the AWS Cloud for your resources
- VPC benefits: security (monitor/restrict access), full control (placement, connectivity, security), convenience (less management vs. on-premises)
- Resources in a VPC can be public-facing (internet-accessible) or private (no direct internet access)
- Network nesting order: AWS Cloud → Region → VPC → Availability Zones → Subnets → Resources
- Internet gateway: connects a VPC to the public internet; open to anyone (like the coffee shop front door)
- Virtual private gateway: connects a VPC to an approved private network via encrypted VPN; only authorized traffic enters
- VPN: encrypts internet traffic through a secure tunnel; shares public infrastructure so bandwidth may vary
- AWS Direct Connect: dedicated private fiber connection from data center to AWS; bypasses internet entirely for consistent performance

**Subnets & Gateways:**
- A subnet is a range of IP addresses within a VPC, used to divide the network into manageable sections
- Private subnets: isolate resources (e.g., databases) from the internet; drawn as solid boxes in diagrams
- Public subnets: provide internet access via an internet gateway; drawn as dashed boxes in diagrams
- Three subnet use cases: share public resources, organize resources, isolate private resources
- AWS Client VPN: fully managed elastic VPN for remote workers; no hardware required; uses OpenVPN; auto-scales with demand
- AWS Site-to-Site VPN: encrypted connection between on-premises data center/branch office and AWS VPC
- AWS PrivateLink: private connectivity from VPC to services/other VPCs without internet gateway, NAT, or public IP
- AWS Direct Connect: dedicated private fiber connection to AWS; bypasses internet; consistent bandwidth and low latency
- Direct Connect use cases: latency-sensitive apps (video streaming), large-scale data migration, hybrid cloud architectures
- AWS Transit Gateway: connects multiple VPCs and on-premises networks through a central hub
- NAT Gateway: lets private subnet instances make outbound internet connections; blocks inbound-initiated connections
- Amazon API Gateway: creates, publishes, manages, monitors, and secures APIs at any scale

**Security Groups & NACLs:**
- Network ACL: virtual firewall at subnet level; stateless (checks every packet both ways independently)
- Security group: virtual firewall at instance level; stateful (remembers decisions; return traffic auto-allowed)
- Default network ACL: allows all inbound and outbound traffic
- Custom network ACL: denies all traffic until explicit allow rules are added; has explicit deny at end
- Default security group: denies all inbound; allows all outbound
- Packet flow inbound: internet gateway → network ACL (subnet) → security group (instance)
- Packet flow return: security group auto-allows (stateful); network ACL re-evaluates (stateless)
- Security groups: allow rules only; applies to specific EC2 instances
- Network ACLs: allow AND deny rules; applies broadly to all traffic across a subnet boundary
- Securing subnets and instances with network ACLs and security groups is the customer’s responsibility under the AWS Shared Responsibility Model
**Global Networking:**
- DNS (Domain Name System): phone book of the internet; translates domain names to IP addresses
- Amazon Route 53: cloud DNS service; globally dispersed servers; supports latency-based, geolocation, geoproximity, and weighted round robin routing; can register and transfer domain names
- Amazon CloudFront: CDN service; caches content at edge locations closest to users; reduces latency and origin server load
- AWS Global Accelerator: uses AWS private global network for intelligent traffic routing and fast failover; like express lanes on the internet highway
- Route 53 + CloudFront workflow: Route 53 resolves domain → customer request routed to nearest CloudFront edge location → CloudFront connects to ALB → ALB routes to EC2
- Edge networking: brings storage and compute closer to users and devices to reduce latency

**Global Architectures:**
- VPN: use for secure flexible remote access, small-scale data transfers; shares internet bandwidth → prone to slowdowns under heavy load
- Direct Connect: use for heavy data payloads, compliance requirements, dedicated bandwidth; physical private fiber line; bypasses internet
- VPN as Direct Connect failover: common pattern; VPN backs up Direct Connect when the physical line is disrupted
- Multiple Direct Connect connections: combine for higher aggregate bandwidth and fault tolerance
- Multi-Region architecture: Route 53 (latency-based routing) → CloudFront edge location (nearest Region) → origin server in Region (across multiple AZs)
- Real-world architectures often span multiple AWS accounts, multiple Regions, multiple VPCs, and hybrid cloud deployments
---

## Common Exam Patterns

**Pattern 1: "Subnet use cases (Select TWO/THREE)"**
→ Subnets organize resources, expose public-facing resources (public subnet + internet gateway), and isolate private resources (private subnet). Distractors typically describe AZs (high availability / discrete data centers), the Management Console (centralized management interface), or EC2 (on-demand compute capacity).

**Pattern 2: "Secure connection from on-premises to VPC with resource isolation"**
→ Choose virtual private gateway + VPN + private subnet. Distractors use internet gateways (which allow public access) or public subnets (which expose resources). The key signal words are: corporate data center, secure connection, isolated from public.

**Pattern 3: "Large bandwidth requirement for migration or hybrid cloud"**
→ Choose AWS Direct Connect. Distractors offer Client VPN (remote workers, not migration), Site-to-Site VPN (shared internet, can’t guarantee bandwidth), or PrivateLink (within AWS, not on-premises). Key signals: large-scale migration, data warehouse, hybrid cloud, bandwidth.

**Pattern 4: "Gateway that allows only approved-network protected traffic into VPC"**
→ Choose Virtual private gateway. Key signals: only approved/protected traffic, corporate data center, VPN connection. Distractors: internet gateway (public, no restrictions), Transit Gateway (hub for multiple VPCs/networks), API Gateway (API management, not network connectivity).

**Pattern 5: "Fine-grained traffic control for individual EC2 instances"**
→ Choose Security groups. Key signals: individual instances, instance-level, fine-grained, per-EC2. Distractors: network ACLs (subnet level, not instance level), private subnets (changes access, not traffic rules), passwords (authentication, not network control).

**Pattern 6: "Stateless vs stateful packet filtering"**
→ Network ACLs = stateless (check every packet both ways, no memory). Security groups = stateful (remember prior decisions, auto-allow return traffic). Key exam signal: “remember nothing” or “check every packet” = stateless = network ACL.

**Pattern 7: "Global content delivery with low latency and reduced costs"**
→ Choose Amazon CloudFront. Key signals: worldwide users, media-rich content, low latency, CDN, videos/images, loading times. Distractors: Route 53 (DNS translation, not content delivery), Global Accelerator (network routing, not CDN caching), VPC (private network, no content distribution).

**Pattern 8: "Register domain names and manage DNS records in one place"**
→ Choose Amazon Route 53. Key signals: domain registration, DNS records, single location, transfer from other registrars. Distractors: CloudFront (CDN delivery, not domain management), Global Accelerator (network optimization, not DNS), VPC (network isolation, not domain management).

**Pattern 9: "Heavy data transfers + compliance/regulatory requirements"**
→ Choose AWS Direct Connect. Key signals: heavy payloads, compliance, dedicated, sensitive data, patient data, regulated industry, consistent bandwidth. Distractors: VPN (shared internet bandwidth, not dedicated), standard internet (no encryption or compliance), even VPN-to-virtual-private-gateway (still internet-based, not dedicated).

**Pattern 10: "CloudFront vs. Global Accelerator confusion"**
→ CloudFront = CDN for **static/cacheable** content (images, videos, web pages); caches at edge locations; reduces origin load. Global Accelerator = **dynamic/non-cacheable** traffic routed via AWS private network; uses anycast IPs; ideal for APIs, gaming, real-time apps. Key signal: "cache" or "media" → CloudFront; "dynamic API" or "consistent private routing" → Global Accelerator.

**Pattern 11: "Instance cannot reach the internet despite having public IP"**
→ Missing route in route table: `0.0.0.0/0 → internet gateway`. Attaching an IGW to the VPC is not enough — the subnet's route table must explicitly route internet-bound traffic to the IGW. This is also what makes a subnet "public."

**Pattern 12: "Default ACL vs. Custom ACL behaviour"**
→ Default network ACL: **allows** all inbound and outbound (permissive by default). Custom network ACL: **denies** all inbound and outbound until you add explicit allow rules. Both have an explicit deny rule at the end of the list.

**Pattern 13: "Private service access between VPCs without VPN or internet"**
→ Choose AWS PrivateLink. Key signals: SaaS provider, expose single service (not entire VPC), customer VPC access, no internet gateway, no VPN needed, no public IP. Distractors: VPC Peering (exposes full CIDR of both VPCs), Site-to-Site VPN (on-premises to AWS, uses internet), Direct Connect (physical on-premises link).

---

**Module:** Networking (Module 5)  
**Total Q&As:** 14 (9 course + 5 interview/cert prep)
