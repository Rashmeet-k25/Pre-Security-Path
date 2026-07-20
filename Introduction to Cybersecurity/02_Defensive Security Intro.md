# Defensive Security Intro | TryHackMe Walkthrough

> **Room:** Defensive Security Intro  
> **Platform:** TryHackMe  
> **Difficulty:** Easy  
> **Learning Path:** Pre Security

---

## Overview

This room introduces the fundamentals of **Defensive Security** by placing us in the role of a **Security Operations Center (SOC) Analyst**. Instead of attacking systems like an ethical hacker, our responsibility is to monitor systems, investigate suspicious activity, and respond to cyber threats before they can cause damage.

Throughout this room, we analyze suspicious network activity, identify an attacker, investigate their actions, and stop the attack using a monitoring dashboard.

---

# What is Defensive Security?

Defensive Security focuses on protecting computer systems, networks, and applications from cyber threats.

Unlike Offensive Security, where ethical hackers actively search for vulnerabilities, Defensive Security is responsible for detecting attacks, investigating incidents, and responding quickly to minimize damage.

Some common responsibilities of defensive security teams include:

- Monitoring security events
- Detecting suspicious activity
- Investigating security alerts
- Blocking malicious users
- Responding to cyber incidents
- Improving security controls

The primary objective is to identify threats as early as possible and protect organizational assets.

---

# Lab Objective

For this room, TryHackMe provides a simulated monitoring dashboard connected to the **FakeBank** web application.

As a SOC analyst, our objectives are to:

- Detect suspicious activity
- Identify the attacker
- Investigate the attack
- Stop the attacker using firewall rules

This exercise introduces the basic workflow followed during a real-world security investigation.

---

# Task 1 - Think Like a Defender

Before starting the investigation, the room explains the role of Defensive Security.

Instead of attacking systems, defenders continuously monitor activity and respond whenever suspicious behaviour is detected.

### Question

**What is the main goal of Defensive Security?**

### Answer

```text
Detect and respond to attacks
```

---

# Task 2 - Detect Suspicious Activity

The monitoring dashboard displays recent activity occurring within the FakeBank environment.

As a SOC analyst, the first step is to review security alerts and identify any abnormal behaviour.

After reviewing the recent alerts, I identified the IP address responsible for generating suspicious traffic.

<img width="2042" height="1476" alt="Screenshot 2026-07-21 013213" src="https://github.com/user-attachments/assets/89bd9898-d483-4101-8627-1cd5c85c3d04" />


### Suspicious Source IP

```text
32.122.195.63
```

Identifying suspicious traffic is often the starting point of an incident investigation.

### Question

**Which source IP address is generating the suspicious traffic?**

### Answer

```text
32.122.195.63
```

---

# Task 3 - Identify the Attack

Knowing who is performing the activity is only part of the investigation.

The next step is understanding **what the attacker is trying to achieve**.

The monitoring dashboard contains a section called **URL Discovery Attempts**, which records every page the attacker attempted to access.

After reviewing the latest entry, I found the following URL.

<img width="2048" height="1384" alt="Screenshot 2026-07-21 014438" src="https://github.com/user-attachments/assets/9124cf4d-870c-43e5-9525-87129d1eac1a" />


```text
https://fakebank.com/admin
```

This indicates that the attacker was attempting to discover hidden administrative pages within the application.

Directory enumeration is a common reconnaissance technique used by attackers to locate hidden resources such as:

- Admin panels
- Login portals
- Backup files
- Configuration pages
- Development directories

### Question

**Copy the latest URL that the attacker has tried to find.**

### Answer

```text
https://fakebank.com/admin
```

---

# Task 4 - Stop the Attack

Once the attacker and their objective have been identified, the next priority is containment.

The monitoring dashboard provides several defensive actions, including:

- Blocking the attacker's IP address
- Applying rate limiting
- Updating security rules

Since the malicious IP address had already been identified, I added the following firewall rule.

```text
IP Address : 32.122.195.63
Action     : BLOCK
```

<img width="1884" height="1492" alt="Screenshot 2026-07-21 014621" src="https://github.com/user-attachments/assets/8fd12758-b35f-40ff-8c6c-c1bc09a4ca4b" />
<img width="1870" height="1478" alt="Screenshot 2026-07-21 014741" src="https://github.com/user-attachments/assets/003444e5-543a-41f1-a961-ed12b8b28ed3" />

After applying the firewall rule, the malicious traffic was successfully blocked and the lab returned the flag.

### Question

**When the success message appears, copy the flag.**

### Answer

```text
THM{FAKEBANK-SECURED}
```

---

# Why Is This Important?

Modern organizations generate thousands of security events every day.

Security analysts use monitoring tools to identify suspicious behaviour, investigate incidents, and respond before attackers can compromise systems.

Even simple attacks, such as attempting to discover hidden administrative pages, can become serious security incidents if they go unnoticed.

This room demonstrates the importance of continuous monitoring and rapid incident response in maintaining a secure environment.

---

# Key Takeaways

After completing this room, I learned:

- The purpose of Defensive Security.
- The role of a Security Operations Center (SOC) analyst.
- How monitoring dashboards help detect suspicious activity.
- How to identify malicious IP addresses.
- How to investigate attacker behaviour using security logs.
- The basics of directory enumeration attacks.
- How firewall rules can be used to contain ongoing attacks.

---

# Conclusion

This room provides a practical introduction to Defensive Security by simulating the responsibilities of a Security Operations Center (SOC) analyst.

Rather than exploiting systems, the focus is on monitoring security events, identifying suspicious activity, understanding attacker behaviour, and responding quickly to prevent further damage.

Although this is an introductory exercise, it demonstrates the same investigation process used by many blue team professionals in real-world environments.

---

## References

- TryHackMe
- SOC (Security Operations Center) Fundamentals
- Incident Response Best Practices
