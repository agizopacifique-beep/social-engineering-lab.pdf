# Social Engineering Attacks with Social Engineering Toolkit

![Kali Linux](https://img.shields.io/badge/Kali-Linux-blue)
![SET](https://img.shields.io/badge/Tool-SET-red)
![Status](https://img.shields.io/badge/Lab-Completed-success)
![Type](https://img.shields.io/badge/Type-Ethical%20Hacking-orange)

---

## Overview

This lab demonstrates how the Social Engineering Toolkit 
works in a controlled environment. The focus was on 
credential harvesting -- specifically how attackers clone 
legitimate login pages and capture credentials when users 
submit them without realizing the page is fake.

Everything in this lab ran in a protected network. No real 
systems or real users were targeted at any point.

---

## What This Lab Covers

- How SET is used to clone websites and host fake login pages
- How credential harvesters capture submitted form data
- How attackers redirect victims after credentials are captured
- Where SET stores harvested credentials and how to read them
- Why users fall for phishing pages that look identical to 
  real ones

---

## Lab Environment

| Component | Details |
|-----------|---------|
| **Platform** | NDG Ethical Hacking v2 |
| **Attacker Machine** | Kali Linux |
| **Attack Tool** | Social Engineering Toolkit (SET) |
| **Attack Type** | Credential Harvester via Website Clone |
| **Target Page** | Cloned Google Login Page |
| **Attacker IP** | 192.168.9.2 |
| **Victim IP** | 192.168.9.1 |

---

## What I Did

### Step 1 -- Launched SET
Opened the Social Engineering Toolkit from the Kali Linux 
terminal. SET has a menu driven interface that walks through 
setting up different attack types.

### Step 2 -- Selected the Attack Type
Chose the credential harvester attack under the website 
attack vectors menu. This attack works by hosting a cloned 
version of a real website on the attacker machine.

### Step 3 -- Configured the Harvester
Set the POST back IP to the attacker machine at 192.168.9.2. 
This tells SET where to send captured credentials once a 
victim submits a form.

### Step 4 -- Cloned Google Login Page
Selected Google as the template. SET pulled down the Google 
login page and hosted it locally. The page looked identical 
to the real Google login from the victim's browser.

### Step 5 -- Captured Credentials
Once the victim machine visited the fake page and submitted 
credentials the terminal on the attacker machine displayed 
everything that was entered including username, password, 
and session cookies.

### Step 6 -- Reviewed SET Reports
Located the harvested credential logs inside SET's report 
directory and confirmed all captured data was stored 
correctly.

---

## Key Findings

The fake Google page loaded with no visible difference from 
the real one. A regular user with no security training would 
have no way to tell the difference just by looking at it.

A few things stood out during the lab:

- Credentials appeared in the terminal almost instantly after 
  the victim hit submit
- SET captured not just the username and password but also 
  session tokens and browser parameters
- The harvester kept running after the first capture meaning 
  it could collect from multiple victims in a row
- The only real indicator something was wrong was the URL 
  in the browser showing an IP address instead of 
  google.com -- something most users never check

---

## Real World Application

Security teams use this type of testing to measure how 
users respond to phishing attempts before attackers do. 
Running controlled phishing simulations helps organizations:

- Find out what percentage of users click fake links
- Identify which departments need more security training
- Test whether email filters catch phishing attempts
- Measure how quickly the security team detects an attack

---

## Defensive Takeaways

| Attack Step | How to Defend Against It |
|-------------|--------------------------|
| Fake login page served | Check the URL before entering credentials |
| Credential capture | Use a password manager that checks domain |
| Session token theft | Enable multi-factor authentication |
| Redirect after capture | Security awareness training for users |
| No visible difference in page | Browser security extensions and warnings |

---

## Tools Used

- **Kali Linux** -- Attacker operating system
- **Social Engineering Toolkit (SET)** -- Main attack framework
- **Apache** -- Web server hosting the cloned page
- **NDG Ethical Hacking Lab** -- Protected lab environment

---

## Important Note

This lab was completed in a controlled environment for 
educational purposes only. Using SET or any credential 
harvesting tool against real systems or real users without 
explicit written permission is illegal. Everything here was 
done on isolated lab machines with no connection to real 
networks or real people.
