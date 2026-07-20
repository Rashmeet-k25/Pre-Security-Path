# Offensive Security Intro | TryHackMe Walkthrough

> **Room:** Intro to Offensive Security  
> **Platform:** TryHackMe  
> **Difficulty:** Easy  
> **Learning Path:** Pre Security

---

## Overview

This room introduces the fundamentals of **Offensive Security** through a hands-on exercise using a vulnerable banking application called **FakeBank**. Instead of only learning the theory, we get to experience how ethical hackers think and approach a target during a penetration test.

The main objective is to discover a hidden feature within the application and use it to increase the balance of our bank account.

---

# What is Offensive Security?

Offensive Security is the practice of testing systems by simulating the actions of an attacker. The purpose is to identify security weaknesses before malicious hackers can exploit them.

Ethical hackers perform authorized security testing to help organizations strengthen their security posture. Some common activities include:

- Vulnerability Assessment
- Penetration Testing
- Web Application Testing
- Network Security Testing
- Security Research

Unlike Defensive Security, which focuses on protecting systems and monitoring threats, Offensive Security focuses on finding weaknesses by thinking like an attacker.

---

# Lab Objective

In this lab, TryHackMe provides a vulnerable web application called **FakeBank**.

Our goal is to:

- Explore the application
- Discover hidden functionality
- Use that functionality to deposit money into our account

This simple exercise demonstrates how exposed administrative pages can introduce serious security risks.

---

# Task 1 - Identifying the Correct Security Approach

The first question introduces the concept of Offensive Security and asks us to identify which security approach involves simulating the actions of an attacker.

```
Offensive Security
```

---

# Task 2 - Launching the Lab

After starting the virtual machine, the FakeBank application opens inside the browser.
<img width="1185" height="1063" alt="image" src="https://github.com/user-attachments/assets/25d8a671-f9da-4061-8079-d8a5ee47ed9f" />


The application provides a bank account that will be used throughout the lab.

My assigned account number was:

```
8881
```

At first glance, the application appears to be a normal online banking website.

**Answer the questions below**

What is your bank account number in the FakeBank web application?

```
8881 ✅
```
---

# Task 3 - Discovering Hidden Directories

One of the first things penetration testers do during web application testing is perform reconnaissance.

Sometimes developers leave hidden pages that are not accessible through the website's navigation menu.

These pages may include:

- Admin panels
- Backup files
- Testing pages
- Internal tools
- Configuration pages

Although these pages are hidden from normal users, they can often still be accessed if someone knows the correct URL.

To discover these hidden resources, I used **DIRB**.

---

# What is DIRB?

DIRB is a directory brute-forcing tool used during web application reconnaissance.

It works by reading a predefined wordlist containing thousands of common directory names and testing each one against the target website.

If a directory exists, DIRB reports it in the output.

---

# Running DIRB

I executed the following command:

```bash
dirb http://fakebank.thm
```

### Command Breakdown

| Component | Description |
|------------|-------------|
| dirb | Starts the directory brute-force tool |
| http://fakebank.thm | Target website |

---

## DIRB Output

<img width="1400" height="854" alt="image" src="https://github.com/user-attachments/assets/9f06137c-6b9d-4a22-bd6a-774a8800f0fe" />

DIRB discovered two directories:

- `/images`
- `/bank-deposit`

The **/images** directory simply stores website resources.

The second directory looked much more interesting because it appeared to perform banking operations.

```
/bank-deposit
```

This demonstrates why directory enumeration is such an important part of reconnaissance. Hidden pages sometimes expose functionality that regular users should never be able to access.

**Answer the questions below**

Dirb should have found 2 hidden URLs. One of them is http://fakebank.thm/images. What is the other one?

```
http://fakebank.thm/bank-deposit ✅
```
---

# Task 4 - Accessing the Hidden Deposit Page

After opening the **/bank-deposit** page, I found an administrative deposit portal.

<img width="719" height="541" alt="image" src="https://github.com/user-attachments/assets/b03a44b7-48e0-4b00-9b22-98495d4af711" />

The page allowed me to:

- Enter an account number
- Specify the deposit amount
- Submit the transaction

Using my account number:

```
8881
```

I deposited:

```
2000 USD
```

After submitting the request, the transaction completed successfully and my account balance increased.
<img width="1400" height="862" alt="image" src="https://github.com/user-attachments/assets/0569ee38-72c6-408d-81fb-252693834aee" />
<img width="1400" height="941" alt="image" src="https://github.com/user-attachments/assets/74552d64-6a12-4beb-a760-f491577a191f" />

**Answer the questions below**

If your balance is now positive, a pop-up should appear with some green words in it. Input the green words as the answer to this question (all in uppercase).

```
BANK-HACKED
```
---

# Why Is This Vulnerable?

The hidden deposit page performs an administrative action without verifying whether the user has permission to access it.

In a real banking application, only authorized employees should be able to deposit money into customer accounts.

Without proper authentication and authorization, attackers could manipulate financial records or perform unauthorized transactions.

This is an example of **Broken Access Control**, one of the most critical web application security risks.

---

# Key Takeaways

After completing this room, I learned:

- The difference between Offensive Security and Defensive Security.
- How attackers search for hidden website directories.
- How to use DIRB for directory brute forcing.
- Why reconnaissance is an important phase of penetration testing.
- How exposed administrative functionality can become a security vulnerability.
- Why proper authentication and authorization are essential for protecting sensitive endpoints.

---

# Conclusion

Although this is an introductory room, it provides valuable insight into how ethical hackers approach web application testing.

Instead of exploiting complex vulnerabilities, the exercise focuses on reconnaissance and demonstrates how hidden application functionality can expose serious security risks.

Learning techniques such as directory enumeration is an essential first step for anyone beginning their penetration testing journey.

---

## References

- TryHackMe
- DIRB Documentation
