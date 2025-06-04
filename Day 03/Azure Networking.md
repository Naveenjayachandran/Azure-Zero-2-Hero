# 🌐 Azure Networking

Azure Networking provides the foundational infrastructure to connect, secure, and manage communication between Azure resources and on-premises systems. At the heart of Azure networking is the **Virtual Network (VNet)**, enabling private, secure communication in the cloud.

---

## 1️⃣ Virtual Network (VNet)

A **Virtual Network** is a logically isolated network within the Azure cloud that allows Azure resources like VMs and services to securely communicate with each other, the internet, and on-premises environments.

### 🔑 Key Features of VNets:

- **🛡️ Isolation:** VNets are isolated from each other for secure and controlled networking.
- **🔀 Subnetting:** Divide VNets into subnets for resource organization and traffic control.
- **📍 Address Space:** Defined using CIDR notation (e.g., `10.0.0.0/16`).

---

## 2️⃣ Subnets and CIDR

### 🧱 Subnets

Subnets are subdivisions within a VNet used to:

- Organize resources by role or tier (e.g., web, app, database).
- Define security and routing boundaries.

### 📐 CIDR (Classless Inter-Domain Routing)

CIDR notation specifies IP ranges.

- **VNet Example:** `10.0.0.0/16`
- **Subnet Example:** `10.0.1.0/24`

---

## 3️⃣ Routes and Route Tables

### 🚦 Routes

Routes define how network traffic moves between Azure resources and external endpoints.

- **Destination Prefix:** Defines the traffic destination.
- **Next Hop:** Specifies the route target (e.g., internet, VPN gateway, virtual appliance).

### 📋 Route Tables

Route tables are collections of user-defined routes applied to subnets to customize traffic flow.

- Override Azure’s default system routes.
- Enforce security and performance policies.

---

## 4️⃣ Network Security Groups (NSGs)

**NSGs** control inbound and outbound traffic at the subnet or network interface (NIC) level.

### 🔒 Key Features:

- **Security Rules:** Define traffic rules based on source, destination, port, and protocol.
- **Default Rules:** Built-in rules permit intra-VNet traffic and restrict public access.
- **Associations:** Apply NSGs to subnets and/or NICs for granular traffic control.

---

## 5️⃣ Application Security Groups (ASGs)

**ASGs** simplify security rule management by grouping VMs logically rather than using IP addresses.

### ⚙️ Key Features:

- **Simplified Management:** Group by function (e.g., web-tier, DB-tier).
- **Dynamic Membership:** Automatically manage VMs using tags.
- **Flexible NSG Integration:** Use ASGs directly in NSG rules.

---

## 📊 Summary

| 🔧 Component       | 📝 Purpose                                                             |
|--------------------|------------------------------------------------------------------------|
| VNet               | Creates isolated network environments in Azure                         |
| Subnet             | Segments the VNet for logical grouping and traffic control             |
| CIDR               | Defines IP address ranges using prefix notation                        |
| Route Table        | Customizes traffic routing between subnets and external destinations   |
| NSG                | Secures network traffic using access control rules                     |
| ASG                | Groups VMs by role to simplify and scale NSG rule management           |
