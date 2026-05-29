# Port-Scan-CyberSecurity
Network Port Scanning Analysis

**Objective**:
Discover open ports on devices in the local network to understand network exposure and identify potential security risks.

**Tools Used**:
Nmap 7.94SVN

**Network Details**:
Local IP Range Scanned: 10.221.91.0/24
Scan Type: TCP SYN Scan (-sS flag)
Scan Date: 2026-05-30 00:31 IST
Total Scan Duration: 4.98 seconds

**Scan Summary**:
Total IP addresses scanned: 256
Active hosts discovered: 3
Total ports scanned per host: 1000

**Findings**:

**Active Hosts and Open Ports**:

1. **Gateway (10.221.91.117)**
   - Status: UP (latency: 0.0033s)
   - Open Ports: 1
   - Port 53/tcp: OPEN (domain/DNS service)
   - MAC Address: 56:37:CA:55:FC:B8

2. **Host 2 (10.221.91.144)**
   - Status: UP (latency: 0.0070s)
   - Open Ports: 0
   - All 1000 scanned ports are in ignored states
   - MAC Address: E6:B7:55:4A:DD:77

3. **Mine (10.221.91.38)**
   - Status: UP (latency: 0.000031s)
   - Open Ports: 0
   - All 1000 scanned ports are in ignored states

**Port Analysis**:

**Port 53 (DNS Service) on Gateway (10.221.91.117)**

**Service**: Domain Name System (DNS)
**Analysis**: 
The gateway device has port 53 open, which allows DNS queries. This is expected behavior for a network gateway as it typically handles DNS resolution for all devices on the network. However, this does require monitoring.

**Network Observations**:

1. **Low Latency**: All devices show very low latency (under 1ms), indicating they are all on the same local network
2. **Minimal Exposure**: Out of 3 active hosts, only 1 has an open port visible, which shows relatively good network hygiene
3. **Closed Ports**: The other 2 devices (10.221.91.144 and 10.221.91.38) have all scanned ports in ignored/filtered states, suggesting firewall protection

**Key Learnings**:

**Port Scanning**: TCP SYN scan (-sS) is a common reconnaissance technique used to identify open ports without completing full connections
**Network Exposure**: Open ports represent potential attack vectors and should be regularly audited
**Firewall Effectiveness**: The majority of ports being filtered indicates firewall rules are in place
**DNS Services**: Critical services like DNS should be monitored and secured appropriately

**Security Implications**:

This scan demonstrates basic network reconnaissance as a first step in security assessment. Open ports should be regularly monitored and justified. Each open port should have a legitimate business purpose.

**Conclusion**:
The network shows reasonable security posture with minimal open ports exposed. Only the gateway device (10.221.91.117) has an open port (DNS on 53), which is expected and necessary for network functionality. The other devices show good protection with filtered ports, likely due to firewall rules. Regular scanning and monitoring should be performed to detect any unauthorized services or changes in network exposure.
