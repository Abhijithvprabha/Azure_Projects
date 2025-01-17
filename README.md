# Azure_Projects

This repository showcases hands-on Azure projects focused on cloud infrastructure, automation, and optimization. Explore solutions for:

- **Data center migration** using Azure Migrate  
- **Infrastructure as Code (IaC)** with Terraform  
- **Networking configurations**, including VNets, firewalls, and load balancers  
- **Disaster recovery setups** with Azure Site Recovery  
- **Integration with Azure Active Directory** and Entra ID  
- **Automation** with Azure Automation Accounts  

Each project demonstrates real-world scenarios, detailed steps, and best practices for Azure cloud implementations.  

---

## Basic: OSI Layer

images/image.png

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
- **Integration**: Seamless connectivity with Azure resources and external networks.

---

## Azure Network Security Groups (NSGs) Overview

### Definition
Azure Network Security Groups (NSGs) are a key security feature in Microsoft Azure that allow you to control network traffic to and from Azure resources based on rules.

### Levels of NSG Association

#### Subnet Level
- NSGs can be associated with a subnet within a virtual network.
- Rules applied at this level affect all resources (e.g., VMs, NICs) in the subnet.

#### Network Interface Card (NIC) Level
- NSGs can be associated with the NIC of a specific Virtual Machine (VM).
- Rules apply specifically to traffic targeting that NIC.

#### VM Level
- NSGs are not directly applied to VMs but indirectly affect VMs through their NICs.

### Priority of Rules

When NSGs are applied at multiple levels (subnet and NIC), the rules are processed in the following sequence:

1. Traffic is first evaluated against the subnet-level NSG.
2. If allowed by the subnet NSG, it is then evaluated against the NIC-level NSG.
3. Deny rules take precedence over allow rules across all associated NSGs.

### NSG Rules

Rules are defined by:

- **Priority**: Determines the order in which rules are processed (lower number = higher priority).
- **Direction**: Inbound or outbound.
- **Source/Destination**: Can specify IP addresses, ranges, or Azure service tags.
- **Protocol**: TCP, UDP, or Any.
- **Action**: Allow or Deny.

### Best Practices

- Use subnet-level NSGs for general traffic control.
- Use NIC-level NSGs for fine-grained control over individual VMs.
- Avoid conflicts between subnet and NIC NSGs to ensure predictable behavior.
- Regularly audit and optimize NSG rules to reduce complexity and improve security.

### Example Use Case

- A subnet-level NSG allows traffic on port 80 (HTTP) for all VMs in the subnet.
- A NIC-level NSG denies all inbound traffic for a specific VM in the subnet.

**Result**: The specific VM will not receive HTTP traffic, as the NIC-level deny rule overrides the subnet-level allow rule.

### Troubleshooting Tips

- Use Azure Network Watcher to troubleshoot NSG rule application.
- Verify NSG rules and priority to identify conflicting or unexpected behaviors.

---

## Additional Resources

- [Azure Virtual Network Documentation](https://learn.microsoft.com/en-us/azure/virtual-network/)
- [Azure Network Security Groups (NSG) Overview](https://learn.microsoft.com/en-us/azure/virtual-network/network-security-groups-overview)

### What is a Resource Group?

A resource group in Azure is a container for managing related resources in a solution. It allows you to deploy, update, and delete resources together, ensuring coordinated operations. When the solution is no longer needed, deleting the resource group removes all associated resources.

**Key Points:**
- Resources in a group should share the same lifecycle (deploy, update, delete).
- A resource can only belong to one resource group but can connect to resources in others.
- You can add, remove, or move resources between groups anytime.
- Resources can be in different regions than the group, but aligning locations is recommended.
- Resource groups support access control via Azure Policies, roles, or locks.
- Tags can be applied to groups, but resources don’t inherit them.
- Deleting a group removes all its resources.
- Groups can host up to 800 instances of a resource type (exceptions apply).

**Creation Options:** Use the Azure portal, PowerShell, CLI, or ARM templates to create resource groups.
