# Azure_Projects

This repository showcases hands-on Azure projects focused on cloud infrastructure, automation, and optimization. Explore solutions for:

- **Data center migration** using Azure Migrate  
- **Infrastructure as Code (IaC)** with Terraform  
- **Networking configurations**, including VNets, firewalls, and load balancers  
- **Disaster recovery setups** with Azure Site Recovery  
- **Integration with Azure Active Directory** and Entra ID  
- **Automation** with Azure Automation Accounts  

Each project demonstrates real-world scenarios, detailed steps, and best practices for Azure cloud implementations.  

Basic : OSI Layer

![alt text](image.png)

## Virtual Networking (VNet)

Virtual Networking (VNet) is a key component of Azure, enabling you to securely connect Azure resources and extend your on-premises network into the cloud. VNets are similar to traditional networks but provide additional flexibility, scalability, and integration options for cloud-based environments.

## Key Features of Azure VNet

- **Isolation and Segmentation**: VNets provide network isolation for resources, ensuring security and compliance.
- **Subnets**: Divide a VNet into smaller segments (subnets) to organize and manage resources efficiently.
- **IP Addressing**: Use private IP ranges to assign addresses to resources within a VNet.
- **Network Security Groups (NSGs)**: Control inbound and outbound traffic at the subnet or network interface level.
- **DNS Services**: Integrate with Azure-provided DNS or custom DNS servers.
- **Hybrid Connectivity**:
  - Use **VPN Gateways** or **ExpressRoute** to connect on-premises networks to Azure VNets.
  - Enable secure communication between on-premises and Azure resources.

## Common Use Cases

1. **Resource Communication**: Enable secure communication between virtual machines (VMs), databases, and other Azure services.
2. **Hybrid Networking**: Extend on-premises networks to Azure for hybrid cloud scenarios.
3. **Application Isolation**: Use subnets and NSGs to isolate multi-tier applications (e.g., web, app, and database tiers).
4. **Load Balancing**: Distribute traffic across multiple VMs or services using Azure Load Balancer.

## Why Use Virtual Networking?

- **Security**: Enhanced protection with isolated networks and custom routing.
- **Flexibility**: Scalable solutions for diverse workloads.
- **Integration**: Seamless connectivity with Azure resources and ex
