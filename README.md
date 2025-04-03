# Burp-Suite-Web-Penetration-Testing

## Introduction
**This project documents web penetration testing using Burp Suite, identifying vulnerabilities, and providing remediation recommendations. The results include captured HTTP requests, security flaws, and fixes.**
## 🛠 Tools Used
**Burp Suite Community Edition**

**Kali Linux**

**Firefox/Chrome with Proxy settings**

**DVWA, Acunetix (for testing)**

**✅ Step 1 :Install FoxyProxy Extension in Firefox**
**Open Firefox.**

**Go to Add-ons Manager (about:addons).**

**Search for "FoxyProxy Standard" and install it.**

**Restart Firefox if needed.**

**✅ Step 2: Configure FoxyProxy for Burp Suite**
**Click on the FoxyProxy icon in Firefox (near the address bar).**

**Select "Options" to open the settings.**

**Click "Add New Proxy".**

**Enter the following details:**

**Proxy Type: HTTP**

**Proxy IP Address: 127.0.0.1**

**Port: 8080**

**✅ Check "Use this proxy for all URLs"**

**Click Save.**

**✅ Step 3: Enable Burp Proxy in FoxyProxy**
**Click the FoxyProxy icon in Firefox**

**Select the Burp Proxy profile you just created.**

**The icon should change color, indicating the proxy is active.**

**✅ Step 4: Verify Interception in Burp Suite**
**Open Burp Suite.**

**Go to "Proxy" → "Intercept" and ensure Intercept is ON.**

**In Firefox, visit any HTTPS website (e.g., https://example.com).**

**If Burp captures the request, it’s working!** 

![image](https://github.com/user-attachments/assets/aad048fb-89b2-47c0-a4d7-30d846a9cd14)
![image](https://github.com/user-attachments/assets/6ff64f20-ad7e-401c-b907-b260f2b6797d)
![image](https://github.com/user-attachments/assets/3ed97e56-d730-4241-bc2d-6b6a5a6608c5)
![image](https://github.com/user-attachments/assets/c49923f2-de9a-49eb-8a10-03112fa39408)

## Download Burp Suite CA Certificate from Firefox
**Open Firefox.**

**In the address bar, enter: http://burpsuite**
**and press Enter.**

**Click "CA Certificate" to download the certificate file.**

**Save the file as cacert.der (default name).**
![image](https://github.com/user-attachments/assets/c30edbd4-2bc6-4316-be5e-4292f4c9bf88)
## Import the Certificate into Firefox
**Open Firefox.**

**In the address bar, type:about:preferences**
**and press Enter.**

**Scroll down to "Privacy & Security".**

**Under "Certificates", click "View Certificates".**

**Go to the "Authorities" tab.**

**Click "Import".**

**Select the cacert.der file you just downloaded.**

**A prompt will appear asking if you want to trust the certificate.**

**✅ Check "Trust this CA to identify websites".**

**Click OK.**
![image](https://github.com/user-attachments/assets/8885aa35-ddf3-40b2-8079-bf91c4258031)
![image](https://github.com/user-attachments/assets/1e0d2723-9ede-4a34-9502-f2d1497a5e52)
## Start Your DVWA Application
**Open your Kali Linux / Virtual Machine.**
**Open Firefox and go to: Log in to DVWA (default credentials):**

**Username: admin**

**Password: password**
![image](https://github.com/user-attachments/assets/007a4017-320d-4b19-8e49-7e53ecb2651f)
 ## Add DVWA to Scope in Burp Suite

**In Burp Suite, go to "Target" → "Site map".**

**Right-click on http:// link / → Select "Add to scope".**
![image](https://github.com/user-attachments/assets/3f3ff79d-f307-4f98-933d-58eb18aa0101)
![image](https://github.com/user-attachments/assets/93d7dde2-e302-4419-858a-74088933287c)


## Capture HTTP Requests from DVWA
**In Burp Suite, go to "Proxy" → "Intercept" and click "Intercept is ON".**

**In Firefox, go to DVWA and perform actions like:**

**Logging in**

**Submitting forms**
![image](https://github.com/user-attachments/assets/23528533-7d98-4701-8175-54827aa42d34)
**Analyze HTTP Traffic in Burp Suite**
**Go to "HTTP History" in Burp Suite (under the "Proxy" tab)**

**You’ll see all captured HTTP requests and responses.**
![image](https://github.com/user-attachments/assets/46e284ea-714d-4168-ac7c-56f8b0f0e141)

 ## SQL Injection Testing Using Burp Suite Intruder

**1.Captured the HTTP request in HTTP history while interacting with a vulnerable input field in DVWA.**

**2.Sent the request to Intruder for testing by right-clicking and selecting "Send to Intruder".**
![image](https://github.com/user-attachments/assets/b28f4ec7-5988-4943-9806-ee4877693351)
**3.Identified the parameter where SQL Injection could be tested and marked it as a payload position**
![image](https://github.com/user-attachments/assets/d9177e10-3ff9-42dd-8cb2-e14489972641)
**4.Loaded SQL payloads from GitHub's SecLists (e.g., Payloads/SQLi/Generic-SQLi.txt).**

**5.Used "Sniper" attack type to inject SQL payloads one by one into the vulnerable parameter.**

**6.Started the attack and analyzed responses to detect possible SQL Injection vulnerabilities.**
![image](https://github.com/user-attachments/assets/dad7f1d6-3545-4442-a02f-9148dbd6eeb0)
![image](https://github.com/user-attachments/assets/a34b2995-a799-43ed-9f7e-1716e65707ca)

## Cluster Bomb attack to test multiple payload combinations for identifying vulnerabilities in the login form of Vulnweb.
![image](https://github.com/user-attachments/assets/1f166247-da30-4bec-9178-f8b0e2cbac0d)
![image](https://github.com/user-attachments/assets/961b5a6f-977a-4771-991d-641ed4e3e6ff)
![image](https://github.com/user-attachments/assets/d87b7012-812c-4ea7-b869-195e73837106)
![image](https://github.com/user-attachments/assets/b31627d0-dbf6-4d11-a892-46a592bbc1fb)
![image](https://github.com/user-attachments/assets/f5419574-9d48-4a91-aed9-f0a6f31e7244)
![image](https://github.com/user-attachments/assets/2c67e930-7d99-4736-b4e9-2ad2c09add3d)
![image](https://github.com/user-attachments/assets/e0e9feda-7043-426c-bdf1-c80f6a4a97c4)
## Cross-Site Scripting (XSS)
![image](https://github.com/user-attachments/assets/9325b079-e4a3-42ad-8293-39261655bb2d)
![image](https://github.com/user-attachments/assets/6a179a7c-aaf2-41b2-9f81-cb581f004bcf)
![kali-linux-2024 4-vmware-amd64-2025-04-03-18-10-01](https://github.com/user-attachments/assets/ad7ff403-852a-4b08-a12a-7888759189fd)
![image](https://github.com/user-attachments/assets/bf90a62b-0a89-4e98-ad53-02579a828ff0)
![image](https://github.com/user-attachments/assets/549cbf48-5a75-4836-a4fa-2ec2d20f956a)
![image](https://github.com/user-attachments/assets/2733ff42-4d60-4ad6-850c-193b428d1b90)

## Used Repeater for manual testing.
**Burp Suite's Repeater tool to manually modify and resend HTTP requests, analyzing the server's responses to identify potential security vulnerabilities.**
![image](https://github.com/user-attachments/assets/de81ff8a-f567-410b-ae0b-1dbd0fd4c940)
![image](https://github.com/user-attachments/assets/4f7bdb38-4afe-4142-8cef-2d4dd552d7c5)
![image](https://github.com/user-attachments/assets/49c6ec7d-d44b-4836-9c2a-5376bd2a42d8)
![image](https://github.com/user-attachments/assets/22c3e1f0-3057-49e7-871e-9a9b57fe7373)



