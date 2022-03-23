# Blue Team: Summary of Operations

## Table of Contents
- Network Topology
- Description of Targets
- Monitoring the Targets
- Patterns of Traffic & Behavior
- Suggestions for Going Further

### Network Topology

The following machines were identified on the network:
- ML-REFVM-684427
  - Operating System: Windows 10 Pro
  - Purpose: Host Machine
  - IP Address: 192.168.1.1
- Capstone
  - Operating System: Ubuntu 18.04.1
  - Purpose: Testing Alerts
  - IP Address: 192.168.1.105
- ELK
  - Operating System: Ubuntu 18.04.4
  - Purpose: Log Capture
  - IP Address: 192.168.1.100
- Kali
  - Operating System: Kali Linux
  - Purpose: Attacker
  - IP Address: 192.168.1.90
- Target 1
  - Operating System: Debian GNU/Linux 8
  - Purpose: Vuln WordPress
  - IP Address: 192.168.1.110

### Description of Targets

The target of this attack was: `192.168.1.110`.

Target 1 is an Apache web server and has SSH enabled, so ports 80 and 22 are possible ports of entry for attackers. As such, the following alerts have been implemented:

### Monitoring the Targets

Traffic to these services should be carefully monitored. To this end, we have implemented the alerts below:

#### Alert 1
Excessive HTTP Errors is implemented as follows:
  - **Metric**: Packetbeat
  - **Threshold**: WHEN count() GROUPED OVER top 5 'http.response.status_code' IS ABOVE 400 FOR THE LAST 5 minutes
  - **Vulnerability Mitigated**: Ennumeration/Brute Force
  - **Reliability**: This alert doesn't generates a lots of false positives/false negatives. The rate of the reliability of this alert is medium or high.

#### Alert 2
HTTP Request Size Monitor is implemented as follows:
  - **Metric**: Packetbeat
  - **Threshold**: WHEN sum() of http.request.bytes OVER all documents IS ABOVE 3500 FOR THE LAST 1 minute
  - **Vulnerability Mitigated**: DDOS
  - **Reliability**: This alert doesn't generates a lots of false positives/false negatives. The reliability of this alert is high.

#### Alert 3
CPU Usage Monitor is implemented as follows:
  - **Metric**: Metricbeat
  - **Threshold**: WHEN max() OF system.process.cpu.total.pct OVER all documents IS ABOVE 0.5 FOR THE LAST 5 minutes
  - **Vulnerability Mitigated**: DDOS
  - **Reliability**: This alert doesn't generates a lots of false positives/false negatives. The reliability of this alert is high.
