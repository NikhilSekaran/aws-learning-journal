# AWS Key Terms & Glossary

> Updated progressively as modules are documented. Currently covers **Module 1: Introduction to the Cloud**.

---

## A

**Availability Zone (AZ)**
- A physically distinct, isolated location within an AWS Region
- Each Region has 3 or more AZs
- Separated to protect against localised disasters (floods, power failures, etc.)
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
- Best for new applications and teams wanting to minimise infrastructure management

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
- Best for organisations with legacy systems that cannot fully move to the cloud

## O

**On-Demand**
- Resources available for use at any time without pre-planning or pre-purchasing
- A core characteristic of cloud computing

**On-Premises Deployment**
- Resources deployed in a company's own data centre using virtualisation tools
- Provides full infrastructure control but misses most cloud benefits

## P

**Pay-as-You-Go**
- Cost model where you only pay for resources during actual consumption
- No upfront investment; billing varies month to month based on usage
- Contrasts with traditional fixed-cost data centre spending

## R

**Region**
- A physically separate geographic location where AWS maintains clusters of data centres
- Examples: us-east-1 (N. Virginia), eu-west-1 (Ireland), ap-southeast-1 (Singapore)
- Regions are isolated from each other; businesses can operate across multiple Regions for resilience

## S

**Shared Responsibility Model**
- Security framework dividing responsibilities between AWS and the customer
- **AWS**: Security *of* the cloud — hardware, networking, facilities, hypervisor
- **Customer**: Security *in* the cloud — OS, applications, data, access control
- **Shared**: Server-side encryption, network traffic protection, firewall config (varies by service)

**Note**: This glossary grows as you encounter new terms. Add definitions as you learn.

**Last Updated**: March 19, 2026
