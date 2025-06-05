# ⚡ Azure Networking Advanced

Azure offers advanced networking services to enhance traffic management, security, and connectivity for your cloud applications and infrastructure.

---

## 1️⃣ Azure Application Gateway & Web Application Firewall (WAF)

Azure Application Gateway is a web traffic load balancer designed to manage and route traffic to web applications, with built-in protection via the Web Application Firewall.

### 🔑 Key Features:
- **Load Balancing:** Distributes incoming HTTP/HTTPS traffic across multiple backend servers to prevent overload.
- **SSL Termination:** Offloads SSL decryption/encryption to the gateway, improving backend server efficiency.
- **Web Application Firewall (WAF):** Protects applications from common web vulnerabilities such as SQL injection, cross-site scripting, and other OWASP threats.

---

## 2️⃣ Azure Load Balancer

Azure Load Balancer distributes network traffic to ensure availability and responsiveness of your services.

### 🔑 Key Features:
- **Load Balancing Algorithms:** Supports round-robin, least connections, and more.
- **Integration with Availability Sets:** Ensures high availability of applications.
- **Inbound and Outbound Traffic:** Balances both incoming and outgoing traffic.

---

## 3️⃣ Azure DNS

Azure DNS is a scalable and reliable DNS hosting service leveraging Azure’s global infrastructure.

### 🔑 Key Features:
- **Domain Hosting:** Hosts domain names and resolves DNS queries within Azure.
- **Seamless Integration:** Works smoothly with other Azure services like App Service and Traffic Manager.
- **Global Reach:** Provides low-latency DNS responses worldwide via Microsoft’s global network.

---

## 4️⃣ Azure Firewall

Azure Firewall is a fully managed, stateful firewall service securing your Azure Virtual Network.

### 🔑 Key Features:
- **Stateful Inspection:** Monitors and filters traffic based on connection states and rules.
- **Application FQDN Filtering:** Filters traffic by fully qualified domain names for fine-grained control.
- **Threat Intelligence:** Uses threat intelligence feeds to block traffic from malicious IPs and domains.

---

## 5️⃣ Virtual Network Peering & VNet Gateway

### Virtual Network Peering
Connects two Azure VNets for seamless communication as if on the same network.

- **Global VNet Peering:** Supports peering across Azure regions.
- **Low Latency:** Direct traffic flow without internet routing.
- **No Bandwidth Bottlenecks:** Utilizes Azure backbone network for fast, secure connections.

### VNet Gateway
Enables secure communication between Azure VNets and on-premises networks.

- **Site-to-Site VPN:** Encrypted VPN tunnels for on-premises to Azure connectivity.
- **Point-to-Site VPN:** Allows individual clients to securely connect to Azure resources remotely.

---

## 6️⃣ Azure VPN Gateway

Azure VPN Gateway provides secure, scalable VPN connections between on-premises networks and Azure.

### 🔑 Key Features:
- **IPsec/IKE Protocols:** Ensures encrypted communication over the internet.
- **High Availability:** Supports active-active and active-passive configurations.
- **BGP Routing:** Enables dynamic routing between networks using Border Gateway Protocol.

---

## 📊 Summary Table

| Service                      | Purpose                                 | Key Benefits                               |
|------------------------------|-----------------------------------------|--------------------------------------------|
| Application Gateway & WAF    | Web traffic load balancing + protection | SSL offload, WAF protection                 |
| Azure Load Balancer          | Network traffic load balancing           | High availability, multiple algorithms     |
| Azure DNS                   | Domain hosting and DNS resolution        | Global reach, Azure service integration     |
| Azure Firewall              | Managed network security                  | Stateful filtering, threat intelligence     |
| Virtual Network Peering      | Connects VNets for seamless communication | Low latency, global peering                  |
| VNet Gateway                | Secure connectivity between Azure and on-prem | Site-to-site and point-to-site VPN           |
| Azure VPN Gateway           | VPN connectivity with encryption and routing | Secure IPsec tunnels, BGP support            |
