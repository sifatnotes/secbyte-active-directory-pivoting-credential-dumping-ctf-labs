# secbyte-active-directory-pivoting-credential-dumping-ctf-labs
A practical collection of cybersecurity CTF labs covering Active Directory enumeration, internal SSH jump host pivoting, LLMNR/NBT-NS poisoning, Responder NTLM relaying, LSASS memory harvesting, Mimikatz tradecraft, DPAPI secret extraction, and full domain dominance takeover.
# Active Directory Exploitation, Internal Pivoting & Credential Harvesting CTF Labs

Welcome to the **Active Directory Exploitation, Internal Pivoting & Credential Harvesting CTF Lab Collection**. This repository serves as an organized, searchable catalog of practical cybersecurity labs hosted on Learn SecByte.

This collection focuses on internal network compromise, lateral movement, and Active Directory takeover—including **SSH & Jump Host Pivoting**, **Local Network Name Resolution Poisoning (LLMNR/NBT-NS & NTLM Relay)**, **LSASS & Memory Credential Harvesting (Mimikatz, DPAPI)**, and **Active Directory Domain Takeover**.

---

## Lab Collection Index

### 1. Internal Pivoting & Network Redirection
* **Pivoting Basics: The Internal Jump**  
  *Lab Link:* [https://learn.secbyte.org/ctf/pivoting-basics-the-internal-jump](https://learn.secbyte.org/ctf/pivoting-basics-the-internal-jump)  
  *Focus:* Understanding multi-homed network architectures, basic port redirection, and routing traffic across internal network segments.

* **SSH Pivoting: From Jump Host to Internal Admin**  
  *Lab Link:* [https://learn.secbyte.org/ctf/ssh-pivoting-from-jump-host-to-internal-admin](https://learn.secbyte.org/ctf/ssh-pivoting-from-jump-host-to-internal-admin)  
  *Focus:* Setting up SSH local, remote, and dynamic SOCKS proxies (`ssh -D`), tunneling SMB/RDP traffic through jump boxes, and accessing restricted administrative subnets.

<Image src="image_agent_tag_3319151735981724529" alt="Diagram illustrating SSH dynamic port forwarding and pivoting through dual-homed jump host" caption="SSH Dynamic Port Forwarding & Network Pivoting Architecture" />

---

### 2. Local Network Poisoning & Relay Exploitation
* **LLMNR Poisoning: Name Resolution Hijacking**  
  *Lab Link:* [https://learn.secbyte.org/ctf/llmnr-poisoning-name-resolution-hijacking](https://learn.secbyte.org/ctf/llmnr-poisoning-name-resolution-hijacking)  
  *Focus:* Capturing NetNTLMv1/v2 password hashes by poisoning unauthenticated LLMNR and NBT-NS broadcast requests on local subnets.

* **Responder Relay: NTLM Poisoning on LAN**  
  *Lab Link:* [https://learn.secbyte.org/ctf/responder-relay-ntlm-poisoning-lan](https://learn.secbyte.org/ctf/responder-relay-ntlm-poisoning-lan)  
  *Focus:* Operationalizing `Responder` and `ntlmrelayx` to intercept, poison, and relay authentication attempts across internal SMB and HTTP endpoints.

* **NTLM Relay Attack: The Printer That Trusted Too Much**  
  *Lab Link:* [https://learn.secbyte.org/ctf/ntlm-relay-attack-the-printer-that-trusted-too-much](https://learn.secbyte.org/ctf/ntlm-relay-attack-the-printer-that-trusted-too-much)  
  *Focus:* Executing forced authentication techniques (PrinterBug / MS-RPRN RPC abuse) to trigger Domain Controller authentication and relay NTLM credentials to LDAP/S.

### 3. Memory Forensics, LSASS & Credential Extraction
* **LSASS Memory Hunt**  
  *Lab Link:* [https://learn.secbyte.org/ctf/lsass-memory-hunt](https://learn.secbyte.org/ctf/lsass-memory-hunt)  
  *Focus:* Dumping Local Security Authority Subsystem Service (LSASS) memory using native tools (`comsvcs.dll`, `ProcDump`) and analyzing memory dumps for cleartext passwords and NTLM hashes.

* **Mimikatz Essentials**  
  *Lab Link:* [https://learn.secbyte.org/ctf/mimikatz-essentials](https://learn.secbyte.org/ctf/mimikatz-essentials)  
  *Focus:* Leveraging Mimikatz modules (`sekurlsa::logonpasswords`, `lsadump::sam`, `token::elevate`) to harvest credentials, Kerberos tickets, and elevated tokens.

* **Credential Dumping: From Memory to Misuse**  
  *Lab Link:* [https://learn.secbyte.org/ctf/credential-dumping-from-memory-to-misuse](https://learn.secbyte.org/ctf/credential-dumping-from-memory-to-misuse)  
  *Focus:* Extracting NTDS.dit files, parsing SAM/SYSTEM registry hives, offline hash cracking with Hashcat, and utilizing dumped hashes for Pass-the-Hash (PtH) movement.

* **DPAPI Abuse: Vaults & Secrets Recovery Paths**  
  *Lab Link:* [https://learn.secbyte.org/ctf/dpapi-abuse-vaults-secrets-recovery-paths](https://learn.secbyte.org/ctf/dpapi-abuse-vaults-secrets-recovery-paths)  
  *Focus:* Decrypting Data Protection API (DPAPI) master keys, recovering saved browser credentials, Wi-Fi passwords, Chrome/Edge login databases, and Windows Vault secrets.

### 4. Active Directory Reconnaissance & Domain Dominance
* **Active Directory Enumeration: The Domain Desk**  
  *Lab Link:* [https://learn.secbyte.org/ctf/active-directory-enumeration-the-domain-desk](https://learn.secbyte.org/ctf/active-directory-enumeration-the-domain-desk)  
  *Focus:* Enumerating AD environments using PowerView, ActiveDirectory PowerShell modules, and LDAP queries to map domain users, groups, computers, and ACL permissions.

* **Active Directory Intrusion Pathways**  
  *Lab Link:* [https://learn.secbyte.org/ctf/active-directory-intrusion-pathways](https://learn.secbyte.org/ctf/active-directory-intrusion-pathways)  
  *Focus:* Analyzing complex identity relationships to exploit Delegation (Unconstrained, Constrained, Resource-Based Constrained Delegation) and GPO misconfigurations.

* **Domain Dominance: Active Directory Takeover Lab**  
  *Lab Link:* [https://learn.secbyte.org/ctf/domain-dominance-active-directory-takeover-lab](https://learn.secbyte.org/ctf/domain-dominance-active-directory-takeover-lab)  
  *Focus:* Achieving full enterprise forest dominance through DCShadow attacks, Golden/Silver Ticket generation, Skeleton Key injection, and persistent AD backdoors.

<Image src="image_agent_tag_3319151735981724366" alt="Diagram showing Kerberos ticket request flow and ticket generation within Active Directory" caption="Active Directory Kerberos Authentication & Ticket Granting Flow" />

---

## Learning Path

### Path A: Internal Network Pivoting & Relay Operator
1. **Network Movement:** Start with [Pivoting Basics: The Internal Jump](https://learn.secbyte.org/ctf/pivoting-basics-the-internal-jump) and [SSH Pivoting: From Jump Host to Internal Admin](https://learn.secbyte.org/ctf/ssh-pivoting-from-jump-host-to-internal-admin).
2. **Local Poisoning & Relaying:** Master broadcast attacks in [LLMNR Poisoning](https://learn.secbyte.org/ctf/llmnr-poisoning-name-resolution-hijacking), [Responder Relay](https://learn.secbyte.org/ctf/responder-relay-ntlm-poisoning-lan), and [NTLM Relay Attack](https://learn.secbyte.org/ctf/ntlm-relay-attack-the-printer-that-trusted-too-much).

### Path B: Credential Extraction & Active Directory Takeover Specialist
1. **Memory & Secret Extraction:** Extract credentials using [LSASS Memory Hunt](https://learn.secbyte.org/ctf/lsass-memory-hunt), [Mimikatz Essentials](https://learn.secbyte.org/ctf/mimikatz-essentials), [Credential Dumping](https://learn.secbyte.org/ctf/credential-dumping-from-memory-to-misuse), and [DPAPI Abuse](https://learn.secbyte.org/ctf/dpapi-abuse-vaults-secrets-recovery-paths).
2. **AD Recon & Dominance:** Take over domain infrastructure in [Active Directory Enumeration](https://learn.secbyte.org/ctf/active-directory-enumeration-the-domain-desk), [Active Directory Intrusion Pathways](https://learn.secbyte.org/ctf/active-directory-intrusion-pathways), and [Domain Dominance: Active Directory Takeover Lab](https://learn.secbyte.org/ctf/domain-dominance-active-directory-takeover-lab).

---

## How to Use the Labs

1. Select a practice scenario from the **Lab Collection Index**.
2. Click the direct link to launch the exercise environment on Learn SecByte.
3. Review scenario directives, domain target parameters, and target IPs.
4. Set up SSH pivots, poison LLMNR name resolution, dump memory credentials with Mimikatz, or forge Kerberos tickets to achieve domain takeover and capture flags.

---

## Target Audience

* **Red Team Operators & Penetration Testers:** Tunnel through jump hosts, dump LSASS memory credentials, execute NTLM relays, and escalate domain privileges.
* **Active Directory Security Analysts:** Understand internal attack paths, Delegation abuses, and ticket forgery mechanics to secure AD forests.
* **SOC Analysts & Incident Responders:** Detect credential harvesting tools (Mimikatz, ProcDump), identify LLMNR poisoning traffic, and monitor ticket anomalies.
* **Cybersecurity Students:** Acquire practical experience in internal network pivoting, Windows secret recovery, and domain compromise.

---

## Disclaimer

All lab links in this repository direct to official training environments hosted on Learn SecByte. All materials and exercises are provided strictly for educational purposes, defensive skill building, and authorized security research. Unauthorized testing against external systems or enterprise networks is strictly prohibited.
