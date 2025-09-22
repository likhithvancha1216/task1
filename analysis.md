# 🔍 Day 1 Port Scanning – Network Discovery

**Author:** Likhith Bharadwaj Reddy  
**Date:** 2025-09-22  
**Tools:** Nmap, Terminal / Command Prompt  
**Purpose:** Gain practical experience in network scanning to identify hosts and services.

## Objective
This exercise aimed to **perform hands-on network discovery**, discover open ports, identify running services, and record findings. It serves as a practical foundation for basic cybersecurity techniques.

---

## **Step 1: Discover My Network Info**

**Command:**  
`ip addr show`

**What I did:**  
- Listed active network interfaces.  
- Located my IPv4 address, subnet mask, and MAC address.  
- Determined which interface to target for scanning.

**Why it matters:**  
Knowing your network addressing and interface prevents scanning unrelated networks and ensures accurate target selection.

---

## **Step 2: Basic TCP SYN Scan**

**Command:**  
`nmap -sS -oA outputs/tcp_syn 10.91.10.229`

**What I did:**  
- Performed a TCP SYN scan to identify open ports.  
- Saved results in `.nmap`, `.xml`, and `.gnmap` formats.  
- Noted which services replied to probes.

**Why it matters:**  
SYN scans are quick and minimally intrusive, allowing identification of exposed services without completing full TCP handshakes.

---

## **Step 3: Service & Version Detection**

**Command:**  
`nmap -sS -sV -oA outputs/service_version 10.91.10.229`

**What I did:**  
- Queried services on discovered ports to determine the software in use.  
- Collected version information for each detected service.

**Why it matters:**  
Knowing service versions helps in spotting known vulnerabilities and informs further testing or mitigation planning.

---

## **Step 4: OS Detection**

**Command:**  
`nmap -O -oA outputs/os_detection 10.91.10.229`

**What I did:**  
- Attempted to identify the operating system of the scanned host.  
- Recorded probable OS family, device type, and uptime hints.

**Why it matters:**  
OS fingerprinting provides context for potential OS-specific vulnerabilities and helps prioritize follow-up actions.

---

## **Step 5: NSE Script Scan**

**Command:**  
`nmap -sS -sV --script=default -oA outputs/nse_scan 10.91.10.229`

**What I did:**  
- Ran Nmap Script Engine (NSE) using the default script set.  
- Extracted additional details such as HTTP headers, SSL/TLS metadata, and service fingerprints.

**Why it matters:**  
NSE scripts surface deeper configuration issues and weak spots that basic port scans may not reveal.

---

## **Observations & Lessons Learned**
- TCP SYN scans are efficient and less noisy than full-connect scans.  
- Service version detection yields precise software identification.  
- OS detection augments understanding of potential exploitability.  
- NSE scripts provide richer, actionable service-level information.  
- Organizing outputs into structured folders simplifies analysis and reporting.  
- Faced initial setup issues which were resolved and documented for future runs.

---

## **Conclusion**
Day 1 of network discovery offered practical exposure to scanning workflows, interpreting open ports, identifying services, and documenting results.

**Next steps:** delve into advanced NSE scripts, perform vulnerability checks, and analyze traffic with Wireshark for deeper protocol-level insight.
