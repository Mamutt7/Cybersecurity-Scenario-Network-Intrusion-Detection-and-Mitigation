# Cybersecurity Scenario: Network Intrusion Detection and Mitigation

This project is part of the Google Cybersecurity Professional Certificate. It focuses on identifying and mitigating network attacks using analysis of packet capture (PCAP) data. The scenario involves diagnosing and responding to a network attack causing a web server to experience downtime.

---

## 📋 Project Overview

### Scenario
A travel agency's web server experienced a connection timeout error, preventing employees and customers from accessing the company's website. After reviewing captured network traffic using a packet sniffer, a large number of TCP SYN requests from an unfamiliar IP address were observed, overwhelming the web server. As a security analyst, I identified the issue, mitigated the immediate attack, and provided recommendations to prevent future occurrences.

---

## 🔍 Key Findings

- **Attack Type:** A **SYN Flood attack**, a subset of a Denial of Service (DoS) attack, was identified based on abnormal TCP SYN traffic patterns in the network logs.
- **Impact:** The attack disrupted the three-way handshake process, overwhelming the web server and causing connection timeouts.
- **Affected Resources:** The travel agency's web server and website functionality were directly impacted, negatively affecting employee productivity and customer access.

---

## 🛠️ Skills Demonstrated

- **Packet Analysis:**
  - Analyzed TCP packet patterns in Wireshark logs to identify SYN Flood attack characteristics.
- **Incident Response:**
  - Took the server offline to recover its functionality and blocked the offending IP address.
- **Reporting and Recommendations:**
  - Documented the findings and suggested solutions for securing the network against future attacks.

---

## 📖 Incident Report Summary

### Part 1: Identifying the Attack
One potential explanation for the website's connection timeout error is a **SYN Flood attack**, a type of Denial of Service (DoS) attack. The logs show an abnormally large number of TCP SYN requests originating from multiple IP addresses, overwhelming the web server and preventing it from completing TCP handshakes. This event could be part of a targeted attack to disrupt the organization's services.

---

### Part 2: Explaining the Attack
When website visitors attempt to connect to the web server, the TCP protocol initiates a three-way handshake:
1. The client sends a SYN packet to the server.
2. The server responds with a SYN-ACK packet.
3. The client replies with an ACK packet to establish the connection.

In a SYN Flood attack, the attacker sends a high volume of SYN packets but never completes the handshake by responding with an ACK. This leaves the server's resources tied up in incomplete connections, preventing legitimate traffic from being processed. The logs indicate that the server was overwhelmed by these SYN requests, leading to connection timeouts.

---

### Part 3: Attack Impact and Recommendations
#### Impact
- **Network Functionality:** The web server became unresponsive to legitimate traffic, disrupting the company's website operations.
- **Organizational Consequences:** Employees were unable to access critical resources, and customers faced poor user experiences, potentially damaging the company's reputation.

#### Recommendations
- Implement a **rate-limiting** mechanism to limit the number of SYN requests accepted by the server.
- Deploy **firewall rules** and intrusion detection systems (IDS) to detect and block suspicious traffic patterns.
- Use a **load balancer** or **Content Delivery Network (CDN)** to distribute traffic and mitigate large-scale attacks.
- Enable SYN cookies, a TCP mechanism to prevent SYN Flood attacks by validating legitimate connections.

---

## 📂 File Contents

- **`wireshark_logs.png`**: Excel file of the packet capture data showing TCP SYN patterns.

---

## 🏆 Key Takeaways

- Understanding packet-level analysis is crucial for identifying network-based attacks like SYN Floods.
- Implementing layered security measures can effectively mitigate DoS and DDoS attacks.
- Clear documentation and reporting are vital for communicating findings and recommendations to stakeholders.

---

### License

This project is shared for educational purposes and is licensed under the MIT License.
