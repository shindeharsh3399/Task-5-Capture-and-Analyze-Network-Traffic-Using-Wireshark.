# Task-5-Capture-and-Analyze-Network-Traffic-Using-Wireshark.

🕵️‍♂️ Captured and analyzed live network traffic using Wireshark on Kali Linux 🐱‍💻. Generated traffic via ping and web browsing 🌐. Identified key protocols: HTTP, DNS, and ICMP 📡. Saved results in a .pcap file 📁 and included a short summary report 📝 for protocol analysis 🔍.

---

## 🎯 Objective
  To capture live network traffic using Wireshark on Kali Linux, identify at least three different protocols, and summarize their usage in a short report.

---

## 🛠️ Tools Used
  - Wireshark (Packet Analyzer)

  - Kali Linux (2025.3)

  - Ping Utility

  - Web Browser

---

## 📶 Step-by-Step Process
  **🧰 Step 1: Install Wireshark (if not installed)**
      Open your terminal and run:

        sudo apt update
        sudo apt install wireshark -y

  When prompted “Should non-superusers be able to capture packets?”, choose Yes.

![step_install.png](https://github.com/shindeharsh3399/Task-5-Capture-and-Analyze-Network-Traffic-Using-Wireshark./blob/main/screenshots/step1_install.png)

---

**🚀 Step 2: Start Wireshark**
    
  Launch Wireshark:

    sudo wireshark

Or from the menu: Applications > Internet > Wireshark

![step2_start.png](https://github.com/shindeharsh3399/Task-5-Capture-and-Analyze-Network-Traffic-Using-Wireshark./blob/main/screenshots/step2_start.png)

---

**🌐 Step 3: Select Network Interface**
  
  In the Wireshark GUI:
  
  - You will see a list of interfaces (like eth0, wlan0, etc.)
    
  - Pick the active one (usually wlan0 for Wi-Fi or eth0 for Ethernet)
    
  - Click the interface to start live capture


![step3_interface.png](https://github.com/shindeharsh3399/Task-5-Capture-and-Analyze-Network-Traffic-Using-Wireshark./blob/main/screenshots/step3_interface.png)

---

**🌍 Step 4: Generate Network Traffic**
    While Wireshark is capturing:
  - Open a terminal
  - Run: ```ping google.com```
  - Open a browser
    Visit: ```http://example.com``` or any simple site

Let it run for about 1 minute.

![step4_ping_&_website.png](https://github.com/shindeharsh3399/Task-5-Capture-and-Analyze-Network-Traffic-Using-Wireshark./blob/main/screenshots/step4_ping_%26_website.png)

---

**🛑 Step 5: Stop the Capture**

  In Wireshark:

  Click the **red square button** (Stop) on the toolbar
  
---

***🔎 Step 6: Filter by Protocols***
  Use the Filter bar at the top to search:

- http – for web traffic

- dns – for domain lookups

- tcp – general TCP traffic

- icmp – for ping

- tls or ssl – for encrypted traffic

Example:
Type http and press Enter — only HTTP packets will show.

![step6_filter.png](https://github.com/shindeharsh3399/Task-5-Capture-and-Analyze-Network-Traffic-Using-Wireshark./blob/main/screenshots/step6_filter.png)

---

***📁 Step 7: Save the Capture File (.pcap)***

  Go to:

  - File > Save As

  - Choose location and filename (e.g., ```network-capture.pcap```)

  - Save as ```.pcap/.pcapng```

    [**Exported Report**](https://github.com/shindeharsh3399/Task-5-Capture-and-Analyze-Network-Traffic-Using-Wireshark./blob/main/network-capture.pcapng)

---

# 📘 Protocols Identified

**HTTP**  
  Used when visiting websites.  
  Example: Request to `example.com`.  
  Packet shows **GET** method and HTTP 200 response code.  

**DNS**  
  Used for resolving domain names.  
  Example: Query for `google.com`.  
  Response contains IPv4 and IPv6 addresses.  

**ICMP**  
  Used in ping operations.  
  Shows **echo request** and **echo reply** messages.  

**TCP**  
  Handles reliable connections between hosts.  
  Example: TCP handshake (SYN, SYN-ACK, ACK) before data transfer.  

**ARP**  
  Used for mapping IP addresses to MAC addresses.  
  Example: Request “Who has 192.168.1.1?” with reply from the host.  

---

## 🔍 Interesting Findings
  - Some packets used **TLS**, indicating encrypted HTTPS traffic.  
  - Multiple **TCP handshakes** observed, showing initiation of new connections.  
  - DNS traffic included both **A** and **AAAA** queries, suggesting dual-stack IPv4/IPv6 usage.
--- 

## 📂 Project Structure

    ```
    .  project-folder/
    ├── network-capture.pcapng
    ├── README.md
    └── screenshots/
       ├── step1_interface.png
       ├── step2_capture.png
       ├── step3_traffic.png
       ├── step4_http.png
---

## 📌 Notes
  - Packet capture duration: ~1 minute

  - Capture included TCP handshakes (SYN, SYN-ACK, ACK) as part of HTTP/DNS

  - HTTPS traffic appeared as TLS, but was not analyzed due to encryption.

---
