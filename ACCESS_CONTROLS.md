

## 🔐 ACCESS CONTROLS – CORE CONCEPTS

### Four Fundamental Functions of Access Control

1. **Identification** – Claims an identity (e.g., username).
2. **Authentication** – Verifies the identity (e.g., password, biometrics).
3. **Authorization** – Grants specific access rights (e.g., read/write).
4. **Accountability** – Logs activity for auditing (e.g., system logs).

### Access Control Models

| Model Type                             | Description                                                                     |
| -------------------------------------- | ------------------------------------------------------------------------------- |
| **MAC (Mandatory Access Control)**     | Central authority assigns classification labels to data and users. Very strict. |
| **DAC (Discretionary Access Control)** | Owners decide who can access their data. Flexible but risky.                    |
| **Non-Discretionary**                  | Central authority assigns access. Includes:                                     |
| - **RBAC (Role-Based)**                | Based on user role (e.g., HR, Finance).                                         |
| - **TBAC (Task-Based)**                | Based on specific tasks or operations.                                          |
| - **LBAC (Lattice-Based)**             | Uses matrix-like access based on clearance levels.                              |
| - **ABAC (Attribute-Based)**           | Access granted based on attributes (e.g., time, location, job title).           |

---

## ✅ AUTHENTICATION FACTORS

| Factor Type            | Example                              |
| ---------------------- | ------------------------------------ |
| **Something you know** | Password, PIN                        |
| **Something you have** | Smart card, token                    |
| **Something you are**  | Fingerprint, retina scan (biometric) |

* Strong authentication = at least two from different types (multi-factor).
* **Biometric Effectiveness Metric**: *Crossover Error Rate (CER)* – Point where false accept and false reject rates intersect.

---

## 🔥 FIREWALLS

### Definition:

Hardware/software that filters traffic between *trusted* and *untrusted* networks.

### Types of Firewalls (Processing Modes):

| Mode                        | Description                                                      |
| --------------------------- | ---------------------------------------------------------------- |
| **Packet Filtering**        | Uses header info like IP, port, protocol.                        |
| **Application Layer Proxy** | Intercepts traffic at app layer; slower but detailed inspection. |
| **MAC Layer Firewall**      | Filters based on MAC addresses.                                  |
| **Hybrid**                  | Combines multiple types; includes NGFW and UTM.                  |

### Stateful Packet Inspection (SPI)

* Tracks active connections via state tables.
* More secure than static filtering.

### Common Architectures:

| Architecture              | Description                                                                         |
| ------------------------- | ----------------------------------------------------------------------------------- |
| **Single Bastion Host**   | Dual NICs; sits at network edge (sacrificial).                                      |
| **Screened Host**         | Router filters first, then proxy.                                                   |
| **Screened Subnet (DMZ)** | Most secure; uses internal and external firewalls to isolate public-facing servers. |

---

## 🛡️ FIREWALL CONFIGURATION – Best Practices

* Deny all unless explicitly allowed (default-deny policy).
* Allow **trusted network traffic out**.
* Deny **ICMP and Telnet** from public.
* Place **SMTP servers** in DMZ.
* Use **rule sets** to define traffic policies:

  * Source/Destination Address
  * Ports (e.g., 80 for HTTP, 443 for HTTPS, 25 for SMTP)
  * Action: Allow or Deny

Example:
`Any → 10.10.10.4 → Port 80 → Allow`

---

## 📶 REMOTE ACCESS CONTROL

### Threats:

* Dial-up connections can be scanned by war dialers.
* Must use strong authentication.

### Key Protocols:

| Protocol     | Description                                                                                         |
| ------------ | --------------------------------------------------------------------------------------------------- |
| **RADIUS**   | Centralized authentication. Uses UDP.                                                               |
| **TACACS**   | Similar to RADIUS but separates authentication and authorization.                                   |
| **Diameter** | More modern version of RADIUS.                                                                      |
| **Kerberos** | Uses tickets and symmetric encryption for mutual authentication. Involves AS, TGS, and KDC servers. |

---

## 🌐 VIRTUAL PRIVATE NETWORKS (VPNs)

### Purpose:

Secure communication over insecure public networks.

### VPN Types:

| Type        | Description                     |
| ----------- | ------------------------------- |
| **Trusted** | Uses leased lines; trust-based. |
| **Secure**  | Encrypts data; software-driven. |
| **Hybrid**  | Combines both.                  |

### VPN Modes:

| Mode          | Description                                                 |
| ------------- | ----------------------------------------------------------- |
| **Transport** | Encrypts data but not headers. Good for host-to-host comms. |
| **Tunnel**    | Encrypts entire packet. Good for network-to-network comms.  |

* Must support **encryption**, **encapsulation**, and **authentication**.
* Used heavily for remote access and remote work (e.g., COVID-19 era).

---

## 🎯 AS A CISO – STRATEGIC GUIDELINES (SCENARIOS)

**Q: What should I recommend to ShopSmart Solutions if they want secure remote access?**

* Use **VPN** (preferably **tunnel mode**).
* Implement **multi-factor authentication**.
* Use **RADIUS** or **Kerberos** for authentication.
* Create a **DMZ** to separate public servers.

**Q: How do I protect internal systems from untrusted networks?**

* Implement a **screened subnet** with DMZ.
* Use **SPI firewalls** with well-defined **rule sets**.
* Deny all unverified traffic; allow only specific services like HTTP, HTTPS, or SMTP through proxy servers.

**Q: How can I audit and track system usage?**

* Use **accountability** via **system logs** and **audit trails**.
* Review **log files** regularly for anomalies.

**Q: How do I select a firewall for ShopSmart Solutions?**

* Choose based on:

  * **Protection vs. cost** balance.
  * **Ease of configuration.**
  * **Scalability** for future growth.
  * **Support** for SPI, hybrid features, and logging.

---

## 🧠 MEMORY CHEAT CODES (Quick Triggers for MCQs)

* **CER = Crossover Error Rate** (biometrics).
* **Stateful firewall = SPI = tracks sessions**.
* **MAC Layer firewall = filters by MAC address**.
* **RBAC = based on job roles**.
* **Kerberos = tickets + symmetric encryption**.
* **Transport mode = encrypts data, not header**.
* **Tunnel mode = encrypts entire packet**.

---

