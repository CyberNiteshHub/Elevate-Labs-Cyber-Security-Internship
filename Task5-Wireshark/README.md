# 🌐 Network Traffic Analysis using Wireshark

## 📌 Overview

This project demonstrates how to capture and analyze live network traffic using Wireshark. The objective is to understand how data flows over a network and identify different communication protocols through real-time packet inspection.

This task is part of a Cyber Security Internship and focuses on developing practical skills in packet analysis and network troubleshooting.

---

## 🎯 Objective

* Capture live network packets
* Analyze network traffic
* Identify and understand different protocols
* Gain hands-on experience with Wireshark

---

## 🛠️ Tools Used

* **Wireshark** (Free and Open Source Network Analyzer)
* **Kali Linux** (Operating System)

---

## ⚙️ Steps Performed

### 1. Installed Wireshark

Installed Wireshark on Kali Linux using apt package manager.

### 2. Started Packet Capture

Selected the active network interface (`eth0`) and started capturing live packets.

### 3. Generated Network Traffic

Performed activities like:

* Browsing websites (Google, YouTube)
* Sending ping requests

This generated real-time traffic for analysis.

### 4. Stopped Capture

Stopped the packet capture after sufficient data was collected.

### 5. Applied Filters

Used Wireshark filters to analyze specific protocols:

* `dns`
* `tcp`
* `http`

### 6. Identified Protocols

Observed and analyzed multiple protocols in the captured traffic.

### 7. Exported Capture File

Saved the captured packets as a `.pcap` file.

### 8. Analyzed Packets

Inspected packet details such as:

* Source IP
* Destination IP
* Protocol type
* Packet length

---

## 📡 Protocols Identified

### 🔹 DNS (Domain Name System)

* Used to resolve domain names into IP addresses
* Example: google.com → IP address

### 🔹 TCP (Transmission Control Protocol)

* Provides reliable communication
* Ensures data delivery without loss

### 🔹 HTTP (HyperText Transfer Protocol)

* Used for web browsing
* Transfers web pages between client and server

---

## 📊 Observations

* DNS packets are generated when accessing websites
* TCP ensures stable and ordered communication
* HTTP traffic is visible when browsing non-secure websites
* Network communication involves multiple layered protocols working together

---

## 📸 Screenshots

Screenshots of the following steps are included:

* Packet capturing
* Traffic generation
* Filter usage
* Packet analysis

---

## 📄 Deliverables

* ✔ Packet capture file (`.pcap`)
* ✔ Analysis report (`.pdf`)
* ✔ Screenshots of the process

---

## 🔐 Ethical Considerations

This project was performed in a controlled and legal environment. Only authorized and self-generated traffic was analyzed.

---

## 📚 Key Concepts Learned

* Packet Capture
* Protocol Analysis
* TCP/IP Networking
* DNS Resolution
* Network Troubleshooting

---

## 🚀 Conclusion

This project provided hands-on experience in analyzing real-time network traffic. It helped in understanding how different protocols interact and how tools like Wireshark can be used for network monitoring and security analysis.

---

