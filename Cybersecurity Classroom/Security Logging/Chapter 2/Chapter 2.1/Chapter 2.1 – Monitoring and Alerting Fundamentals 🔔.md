**🌟 Aisha’s Late Alert**

Aisha implemented [[Security Logging]] and collected all necessary data in her [[Security Information and Event Management (SIEM)]] system. However, the alert for a severe [[SQL Injection]] attempt was only generated and sent to the security team 12 hours after the event occurred, giving the attacker ample time to compromise the database.

Elena: “Logs without timely **Monitoring and Alerting** are useless for **Incident Response**. Detection speed is critical. You must define clear, high-fidelity **Alerting Rules** based on correlated events, not just simple errors. The system needs to tell you _before_ the attacker achieves their objective.”

### 🧠 **The Importance of Near Real-Time Monitoring**

Effective monitoring turns passive logs into an active security defense. The goal is to minimize the **"Dwell Time"**—the period between when a compromise occurs and when it is detected.

- **Detection:** The **[[Security Information and Event Management (SIEM)]]** system continuously analyzes incoming logs for suspicious patterns.
    
- **Correlation:** The **SIEM** doesn't just look at single events; it correlates events across different layers. For example, it might correlate a failed firewall login, followed immediately by a database connection attempt, followed by a large data transfer to identify a **[[Lateral Movement]]** attempt.
    
- **Response Speed:** The security value of a log is inversely proportional to the time it takes to detect and respond to the event. High-severity alerts must trigger instant, automated responses (e.g., locking an account).
    

### 💡 **Designing High-Fidelity Alerting Rules**

Alert rules must be designed to generate **high-fidelity** alerts (low false positives) to prevent alert fatigue, ensuring the security team acts decisively when an alert is received.

|**Attack Pattern**|**Alerting Rule**|**Security Goal**|
|---|---|---|
|**Brute-Force Attack**|10 or more **Failed Login** attempts from the same IP or username within 60 seconds.|Detect **[[Authentication]]** attack attempts.|
|**Data Exfiltration**|A single service account performs over 1,000 unique **`SELECT`** operations on sensitive tables within a 5-minute window.|Detect large-scale **[[Information Leakage]]**.|
|**Logic Probe**|A single user receives 5 or more **Permission Denied** (403) or **Input Validation Failure** logs in 30 seconds.|Detect **[[BOLA]]** or injection attack attempts.|
|**Admin Activity**|Any successful **[[Authentication]]** to a highly privileged account (e.g., DBA) outside of business hours.|Detect misuse or compromise of critical credentials.|

### 🎯 **Standardized Alert Workflow**

Once an alert is generated, a clear workflow is mandatory for **Incident Response**:

1. **Alert Generation:** The **SIEM** flags the correlated event.
    
2. **Notification:** Security team members (via email, PagerDuty, or chat) are notified with the full context (the "Five Ws" from the logs).
    
3. **Containment:** For high-severity alerts (like brute-force), automated actions (e.g., firewall block, account lockout) should be triggered to **Contain** the attack immediately.
    

---

### 🧩 **Mini Quiz – Chapter 2.1**

**Q:** Why is **Event Correlation** in a **[[Security Information and Event Management (SIEM)]]** system more effective for threat detection than simply generating alerts for single error messages?

A) Correlation simplifies the **[[Data Masking]]** process for logs.

B) **It allows the system to identify attack chains (e.g., a firewall probe followed by an application error) that span multiple systems and indicate sophisticated [[Lateral Movement]] or breach.** 

C) It strictly enforces **[[Determinism (Dependency)]]** on all log files.

D) It eliminates the need for logging **[[Verbose Error Message]]**s.

Click here to view the answer : [[ Chapter 2.1 - Answer - Security Logging]]

---

### 🎯 **Learning Objectives – Chapter 2.1**

By the end of this sub-chapter, you should be able to:

- Explain the concept of **Dwell Time** and the need for **near real-time monitoring**.
    
- Define **Event Correlation** and its role in detecting sophisticated attacks.
    
- Design and justify at least two **high-fidelity alerting rules** for common attack patterns.