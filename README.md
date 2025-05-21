# Wazuh-SIEM-Detection-Response-Lab
Real-World SOC Use Cases with Wazuh & MITRE ATT&CK

This lab was designed as a hands-on demonstration of how Wazuh can be used in a Security Operations Center (SOC) setting to detect, analyze, and correlate various attack techniques aligned with the MITRE ATT&CK framework. It simulates realistic attacker behaviors such as brute-force, privilege escalation, session hijacking, and failed login attempts—while also showcasing how vulnerabilities are logged, filtered, and assessed for severity.

The primary goal of this lab was to provide a tangible portfolio-quality project that highlights L1/L2 SOC Analyst capabilities such as triaging alerts, analyzing logs, and understanding attacker behavior.

---

MITRE ATT&CK Mapping & Detection
As part of this lab, I simulated multiple attack scenarios and analyzed how Wazuh detects and classifies them under the MITRE ATT&CK matrix. This included password guessing attempts and the use of sudo (and its caching mechanism).

Through the dashboard, I explored how Wazuh rules are mapped to specific MITRE techniques and how analysts can pivot from an alert to the corresponding tactic and technique.

📸 _Screenshots:_  
<br><img src="https://github.com/Barbarossa01/Wazuh-SIEM-Detection-Response-Lab/blob/main/mitre_attacks/MITRE3.PNG" alt="dashboard1">
<br><img src="https://github.com/Barbarossa01/Wazuh-SIEM-Detection-Response-Lab/blob/main/mitre_attacks/MITRE4.PNG" alt="dashboard1">
<br><img src="https://github.com/Barbarossa01/Wazuh-SIEM-Detection-Response-Lab/blob/main/mitre_attacks/MITRE5.PNG" alt="dashboard1">
<br><img src="https://github.com/Barbarossa01/Wazuh-SIEM-Detection-Response-Lab/blob/main/mitre_attacks/MITRE_1.PNG" alt="Password Guessing">
<br><img src="https://github.com/Barbarossa01/Wazuh-SIEM-Detection-Response-Lab/blob/main/mitre_attacks/MITRE_2.PNG" alt="sudo caching">


---

## Session Logging in Wazuh
I explored how user sessions are captured, including specific commands executed in the terminal. Wazuh logs this data with high fidelity, allowing SOC analysts to review session history and reconstruct attacker actions.

📸 Screenshots:

<br><img src="https://github.com/Barbarossa01/Wazuh-SIEM-Detection-Response-Lab/blob/main/session_logging/OpenedSession1.PNG" alt="dashboard1">
<br><img src="https://github.com/Barbarossa01/Wazuh-SIEM-Detection-Response-Lab/blob/main/session_logging/OpenedSession2.PNG" alt="dashboard1">

---

## Privilege Escalation Scenario (Caesaraugusta → Goya)

This scenario involved a user named caesaraugusta enumerating sudo permissions, exploiting them to escalate privileges, and then accessing another machine (goya) via SSH. Wazuh's monitoring caught each step in the chain, allowing me to document the attack flow fully.


📸 Screenshots:  
<br><img src="https://github.com/Barbarossa01/Wazuh-SIEM-Detection-Response-Lab/blob/main/privilege_escalation/PrivEsc1.PNG" alt="dashboard1">
<br><img src="https://github.com/Barbarossa01/Wazuh-SIEM-Detection-Response-Lab/blob/main/privilege_escalation/PrivEsc2.PNG" alt="dashboard1">
<br><img src="https://github.com/Barbarossa01/Wazuh-SIEM-Detection-Response-Lab/blob/main/privilege_escalation/PrivEsc3.PNG" alt="dashboard1">
<br><img src="https://github.com/Barbarossa01/Wazuh-SIEM-Detection-Response-Lab/blob/main/privilege_escalation/PrivEsc4.PNG" alt="dashboard1">


---

## Failed Login Attempts

I tested failed login scenarios where a user attempts to switch identities (e.g., su - user) and fails. Wazuh precisely captured which user attempted the switch, the command used, and the outcome.

📸 _Screenshots:_  
<br><img src="https://github.com/Barbarossa01/Wazuh-SIEM-Detection-Response-Lab/blob/main/login_failures/UserLoginFailed1.PNG" alt="dashboard1">
<br><img src="https://github.com/Barbarossa01/Wazuh-SIEM-Detection-Response-Lab/blob/main/login_failures/UserLoginFailed2.PNG" alt="dashboard1">
<br><img src="https://github.com/Barbarossa01/Wazuh-SIEM-Detection-Response-Lab/blob/main/login_failures/UserLoginFailed3.PNG" alt="dashboard1">


---

## Vulnerability Inventory & Detection && Dashboard

In this part of the lab, I explored how Wazuh builds an inventory of installed packages and detects known vulnerabilities. I experimented with the filter feature and verified whether flagged packages were actually present.

I reviewed the Wazuh vulnerability dashboard, which lists the most critical vulnerabilities (e.g., severity ≥ 50). The dashboard also highlights the top 5 vulnerable packages. These visualizations help prioritize patching in a SOC environment.

📸 _Screenshots:_  
<br><img src="https://github.com/Barbarossa01/Wazuh-SIEM-Detection-Response-Lab/blob/main/vuln_detection/vulnerability_detection_1.PNG" alt="dashboard1">
<br><img src="https://github.com/Barbarossa01/Wazuh-SIEM-Detection-Response-Lab/blob/main/vuln_detection/vulnerability_detection_2.PNG" alt="dashboard1">
<br><img src="https://github.com/Barbarossa01/Wazuh-SIEM-Detection-Response-Lab/blob/main/vuln_detection/vulnerability_detection_3.PNG" alt="dashboard1">

<br><img src="https://github.com/Barbarossa01/Wazuh-SIEM-Detection-Response-Lab/blob/main/vuln_detection/vulnerability_detection_4.PNG" alt="dashboard1">
<br><img src="https://github.com/Barbarossa01/Wazuh-SIEM-Detection-Response-Lab/blob/main/vuln_detection/vulnerability_detection_5.PNG" alt="dashboard1">

---

Conclusion: SOC Analyst Relevance

This lab reflects practical skills relevant to L1/L2 SOC Analyst :

Detecting and classifying threats using MITRE ATT&CK

Monitoring user behavior and privilege abuse

Analyzing login failures and suspicious session activity

Conducting basic vulnerability management

It demonstrates end-to-end visibility over a simulated attack lifecycle using a fully open-source stack.


