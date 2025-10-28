# CN_Assignment_2_22110296_22110206
# 🧠 CN331: Computer Networks – Assignment 2  
### **DNS Query Resolution in Mininet**

**Team Members:**  
- 🧑‍💻 **Yash Patkar (2211010296)**  
- 🧑‍💻 **Praveen Rathod (22110206)**  

**Instructor:** Dr. Sameer Kulkarni  
**Course:** CN331 – Computer Networks  
**Institute:** Indian Institute of Technology Gandhinagar  
**Submission Date:** 28 October 2025  

---

## 🗂️ Overview

This repository contains the complete implementation of **Assignment 2: DNS Query Resolution in Mininet**.  
The goal is to simulate a **multi-switch Mininet topology**, analyze **DNS query resolution** using both the default and a **custom DNS resolver**, and compare performance metrics through benchmarking and visualization.

---

## 📁 Repository Structure
CN331-Assignment2/
│
├── topology.py # Part A: Mininet topology simulation
├── dns_topo_custom.py # Part C: Topology with custom resolver
├── custom_resolver.py # Part C/D: Simple forwarding DNS resolver
├── partd_custom_resolver.py # Part D: Resolver with detailed logging
├── Benchmark.py # Part B/D: Benchmark DNS queries from PCAPs
├── plot_logs.py # Part D: Generate latency & DNS server plots
├── PCAP_1_H1.pcap # Sample PCAP for Host 1
├── PCAP_1_H2.pcap
├── PCAP_1_H3.pcap
├── PCAP_1_H4.pcap
├── dns_log1.csv # Logged query details
├── D_latency_plot.png # Per-query latency plot
├── D_servers_visited_plot.png # DNS servers visited per query
├── report.pdf # Full LaTeX report (Tasks A–D)
├── report.tex # Source LaTeX code
├── images/ # Screenshots: pingall, nslookup, benchmarks
└── README.md # This file



---

## ⚙️ Tasks Implemented

| Task | Description | Status |
|------|-------------|--------|
| **Part A** | Simulate topology (H1–H4, S1–S4, DNS, NAT, link delays) | ✅ Complete |
| **Part B** | Benchmark DNS using default system resolver | ✅ Complete |
| **Part C** | Configure hosts to use custom DNS resolver (`10.0.0.5`) | ✅ Complete |
| **Part D** | Implement logging DNS proxy and visualize results | ✅ Complete |

---

## 🌐 Network Topology

      [H1]     [H2]     [H3]     [H4]
       |        |        |        |
    (2ms)    (2ms)    (2ms)    (2ms)
       |        |        |        |
     [S1]----[S2]----[S3]----[S4]
       |       / |       |
    (5ms)   (1ms)|   (10ms)
       |        |        |
    [NAT]    [DNS: 10.0.0.5]
              (8ms)
                |
              [S2]

Bandwidth: 100 Mbps on all links
Connectivity: Verified via pingall → 0% packet loss


---

## 🚀 How to Run

### **1️⃣ Setup Environment**
```bash
sudo apt update
sudo apt install mininet python3-pip
pip3 install scapy matplotlib pandas


  # Part A – Base topology and connectivity check
sudo python3 topology.py

  # Part C – Topology using custom DNS resolver
sudo python3 dns_topo_custom.py

