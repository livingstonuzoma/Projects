# Skills Learned: Active Directory Home Lab (Server 2019 Domain Controller + Windows 10 Client)

## Project Summary
In this project, I built a small Windows enterprise-style environment using two virtual machines:
- **Windows Server 2019** configured as a **Domain Controller (DC)** with **two virtual NICs**
- **Windows 10 Enterprise** configured as a **domain-joined client**

The goal was to create a functional Windows domain where users can sign in using **unique domain credentials**, while the client machine can access both the private lab network and the internet through the lab network design.

---

## 1. Virtualization & Lab Architecture

### What I learned
- How to create and manage **virtual machines (VMs)** as isolated systems that behave like physical computers.
- How to allocate VM resources (CPU/RAM/storage) to keep the lab stable and responsive.
- How to design a realistic lab architecture that mirrors an enterprise setup (server + workstation).

### Why it matters
Virtualization is foundational in modern IT environments (datacenters and cloud). Knowing how to build and troubleshoot VM-based labs is a practical skill for system administration and cybersecurity.

### Evidence in my lab
- Built two VMs that communicate over a private network.
- Used virtual networking to create separation between internal lab traffic and internet access.

---

## 2. Windows Server Administration Fundamentals

### What I learned
- Installing and configuring **Windows Server 2019** for a domain environment.
- Using **Server Manager** to add and manage server roles and features.
- Basic server configuration habits (naming conventions, admin access, and reliable network settings).

### Why it matters
Most enterprise Windows environments rely on servers to provide centralized services. Admins must be comfortable installing, configuring, and maintaining Windows Server.

### Evidence in my lab
- Configured the server as a stable platform for AD DS and DNS.
- Verified the server could communicate on both internal and external networks using separate adapters.

---

## 3. Active Directory Domain Services (AD DS)

### What I learned
- The purpose of **Active Directory** as a central directory for managing:
  - **Users**
  - **Computers**
  - **Groups**
  - (Optionally) policies and access control
- How to install **Active Directory Domain Services (AD DS)** and promote a server to a **Domain Controller**.
- How the domain becomes the “source of truth” for logins and identity inside the network.

### Why it matters
Active Directory remains one of the most common identity systems in organizations. Understanding AD is a core skill for IT support, system administration, and security roles.

### Evidence in my lab
- Created a domain and promoted Server 2019 to a Domain Controller.
- Confirmed that domain users could authenticate against the DC.

---

## 4. Domain Controller (DC) Responsibilities & Enterprise Concepts

### What I learned
- A **Domain Controller** is responsible for authentication and maintaining the directory database.
- The DC is a critical enterprise asset because it controls identity and access.
- If DC services fail, domain logins and many network services can fail.

### Why it matters
Understanding the DC’s role helps explain why AD environments are tightly controlled and why DC availability and security are major priorities.

### Evidence in my lab
- The Windows 10 client depended on the DC for domain joining and domain logins.
- Successful logins demonstrated that DC services were functioning correctly.

---

## 5. Identity & Access Management (IAM): Users, Groups, and Access Control

### What I learned
- How to create and manage **unique domain user accounts** (centralized credentials).
- How **security groups** simplify access management:
  - Assign permissions to a group instead of individually assigning permissions to each user.
- How identity organization supports a **least-privilege** mindset (standard user vs admin).

### Why it matters
In real organizations, IAM is about controlling who can access what, and being able to manage that access efficiently and securely.

### Evidence in my lab
- Created domain users with unique login credentials.
- Created groups and assigned users appropriately to reflect role-based access patterns.

---

## 6. Organizational Units (OUs) and Directory Organization

### What I learned
- What **Organizational Units (OUs)** are and how they help structure a domain.
- How OUs support scalable management by grouping users/computers into logical containers.
- How OU design becomes important when applying policies (Group Policy) later.

### Why it matters
OUs are essential in real environments because they provide structure and make large domains manageable.

### Evidence in my lab
- Organized users and/or computers into OUs (if implemented).
- Used OU structure to prepare for future policy-based management.

---

## 7. DNS Fundamentals (Critical for Active Directory)

### What I learned
- **DNS is required for Active Directory** to function properly.
- The client must use the DC’s DNS service to locate domain resources (Domain Controller discovery).
- Many “domain join” and authentication issues are actually DNS misconfiguration problems.

### Why it matters
DNS is one of the most common root causes of Active Directory issues in real IT environments. Understanding DNS improves both troubleshooting and system reliability.

### Evidence in my lab
- Configured the client to use the Domain Controller as DNS.
- Successful domain join confirmed that DNS and domain discovery were functioning correctly.

---

## 8. Networking Skills: IP Addressing, Gateways, Dual NIC Design

### What I learned
- Practical networking concepts:
  - IP address configuration
  - Subnets and network separation
  - Default gateway vs DNS roles
- Why a lab may use **two NICs** on a Domain Controller:
  - One NIC for the internal/private domain network
  - One NIC for external connectivity (internet access)

### Why it matters
Even strong AD skills fail without networking fundamentals. In enterprise environments, AD, DNS, and client connectivity are tightly connected.

### Evidence in my lab
- Built a private internal network for domain communication.
- Enabled outbound connectivity while keeping the internal network isolated.

---

## 9. Routing/NAT Concepts (Client Internet Through the Lab Design)

### What I learned
- How a private/internal client can reach the internet through a system that has external access.
- The concept of **routing/NAT** (internet sharing) in a lab setup:
  - Internal clients use a gateway to communicate outside the private network.

### Why it matters
This mirrors how home routers and many enterprise networks function. It also reflects real-world segmentation practices used for security and manageability.

### Evidence in my lab
- The Windows 10 client could access the internet while remaining on the private domain network (through the DC’s network design).

---

## 10. Troubleshooting & Verification Skills

### What I learned
- How to systematically troubleshoot common AD lab issues:
  - Domain join problems
  - DNS misconfiguration
  - Connectivity errors between client and DC
  - Authentication failures
- How to verify that the lab is functioning correctly using practical checks and tools:
  - Domain membership confirmation
  - Domain login tests
  - Basic network and DNS validation

### Why it matters
Troubleshooting is one of the most important job skills in IT and security. Being able to verify and prove systems are working is critical in production environments.

### Evidence in my lab
- Successfully joined Windows 10 to the domain.
- Logged in with domain credentials and confirmed the domain environment was operational.

---

## 11. Security Relevance (Why This Lab Matters for Cybersecurity)

### What I learned
- Active Directory is a core part of enterprise security because it controls identity, authentication, and access.
- Misconfigurations in AD/DNS/networking can cause availability issues and security risk.
- Building a lab environment provides safe, hands-on experience with enterprise identity systems.

### Why it matters
Many real cybersecurity roles (SOC, IAM, blue team, incident response, internal security) interact with AD daily. Understanding AD fundamentals is a major advantage.

### Evidence in my lab
- Demonstrated centralized identity management (domain users).
- Built an environment that can be expanded into security-focused exercises (auditing, policy enforcement, group-based access, etc.).

---

## Conclusion
This Active Directory home lab provided hands-on experience with core enterprise IT topics: **virtualization, Windows Server administration, AD DS, DNS, IAM, and networking**. It also strengthened my troubleshooting workflow and provided a foundation to expand into advanced topics such as **Group Policy**, **file sharing with permissions**, **DHCP**, and security monitoring/auditing.

