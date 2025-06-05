# 🧠 Azure Networking Interview Q&A

---

## 1️⃣ What is the difference between NSG and ASG?

### 🔹 Network Security Group (NSG)
- Controls inbound and outbound traffic to Azure resources.
- Applied at **subnet** or **NIC** level.
- Rules based on **IP address, port, and protocol**.

### 🔹 Application Security Group (ASG)
- Logical group of VMs based on **application role**.
- Used **in conjunction with NSGs** to simplify rule management.
- Enables defining security rules based on **ASG tags** instead of IPs.

✅ **Use Case:** In a multi-tier app, ASGs can group frontend, backend, and DB VMs, allowing clean NSG rule application.

---

## 2️⃣ How can you block access to a VM from a subnet?

By default, Azure allows traffic between subnets within a VNet due to the built-in NSG rule: `AllowVnetInBound (priority 65000)`.

### 🚫 To block access:
- Create a **Deny NSG rule** with a priority **lower than 65000**.
- Example: A Deny rule with **priority 100** targeting the source subnet IP range.

---

## 3️⃣ Are Azure NSGs stateful or stateless?

✅ **NSGs are stateful.**

- If inbound traffic is allowed, the corresponding **outbound response is automatically allowed**.
- Example: Allowing **inbound port 80** doesn't require a matching outbound rule.

---

## 4️⃣ What is the difference between Azure Firewall and NSG?

| Feature               | Azure Firewall                    | Network Security Group (NSG)      |
|-----------------------|-----------------------------------|-----------------------------------|
| OSI Layer             | Application + Network layers      | Network layer only                |
| Stateful              | ✅ Yes                             | ✅ Yes                             |
| Advanced Filtering    | FQDN, URL, Threat Intelligence    | IP, Port, Protocol                |
| Scope                 | Entire VNet/Subnets               | Subnet or NIC level               |
| Use Case              | Centralized traffic control       | Basic traffic filtering           |

---

## 5️⃣ What are the advantages of Azure Resource Groups?

- 📦 **Logical Organization:** Group related resources (project/environment).
- 🔄 **Lifecycle Management:** Deploy/update/delete as one unit.
- 🏷️ **Tagging:** Use tags for cost tracking and classification.
- 🔐 **RBAC:** Assign permissions per group using Role-Based Access Control.
- 💰 **Cost Management:** View and control expenses per resource group.
- 📜 **ARM Templates:** Enable consistent, repeatable deployments.
- 🛑 **Resource Locks:** Prevent accidental deletion or changes.

---

## 6️⃣ What is the difference between Azure User Data and Custom Data?

| Feature         | User Data                          | Custom Data                          |
|-----------------|------------------------------------|---------------------------------------|
| Persistence     | ✅ Persistent (survives reboots)   | ❌ One-time use (discarded after boot)|
| Access          | Read/update anytime                | Only during provisioning              |
| Use Case        | Boot-time scripts/config updates   | Initial setup scripts during creation |

---

## 7️⃣ Difference between Azure Application Gateway and Azure Load Balancer?

| Feature           | Azure Application Gateway              | Azure Load Balancer                     |
|-------------------|----------------------------------------|------------------------------------------|
| OSI Layer         | Layer 7 (Application)                  | Layer 4 (Transport - TCP/UDP)           |
| Features          | SSL offload, URL routing, WAF          | Basic TCP/UDP load distribution         |
| Use Case          | Web apps with complex routing needs    | General purpose load balancing across VMs|

---

## 8️⃣ Explain the traffic flow to an app in the Web Subnet (Azure VNet).

1. **User Access:**
   - User accesses app via domain name.
   - DNS resolves to public IP.

2. **Traffic Enters Azure:**
   - Public IP mapped to Front Door, App Gateway, or Load Balancer.

3. **Routing to Web Subnet:**
   - Service forwards traffic to backend servers in the Web Subnet.

4. **NSG Enforcement:**
   - NSGs at subnet/NIC level apply traffic rules.

5. **Internal VNet Routing:**
   - Subnets route internally within the VNet.

6. **Application Processing:**
   - Web server processes the request and sends the response back.

---

## 9️⃣ Describe the purpose of Azure Bastion and when to use it.

**Azure Bastion** allows secure RDP/SSH access to VMs via the **Azure Portal**, eliminating public IP exposure.

### ✅ Key Benefits:
- 🔒 **Secure Remote Access:** No open RDP/SSH ports to the internet.
- 🌐 **Private IP Usage:** VMs stay within private network.
- 🛡️ **Reduced Attack Surface:** Minimizes brute-force vulnerabilities.
- 🌍 **Portal-Based Access:** RDP/SSH from browser — no client tools.
- 👥 **RBAC Integration:** Role-based access control.
- 🔐 **MFA Support:** Azure AD-based authentication.
- 📊 **Audit Logs:** Tracks remote access activity for compliance.

