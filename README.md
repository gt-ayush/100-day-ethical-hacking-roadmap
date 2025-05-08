Here’s a **beginner-friendly 100-day ethical hacking roadmap** tailored for someone with basic Linux command-line knowledge. We’ll start from foundational concepts and slowly ramp up to advanced attacks, ensuring you’re job-ready by the end. Each phase includes hands-on labs and real-world practice. 🚀  

---

### **Phase 1: Days 1–20 – Linux & Networking Basics**  
**Goal**: Master Linux for hacking and understand networks.  

#### **Days 1–5: Linux Deep Dive**  
- **Learn**:  
  - File system navigation (`cd`, `ls`, `pwd`, `mkdir`).  
  - File operations (`cat`, `grep`, `chmod`, `chown`).  
  - Process management (`ps`, `kill`, `top`).  
  - Package management (`apt`, `pip`).  
- **Practice**:  
  - Write a Bash script to automate folder creation and file sorting.  
  - Use `cron` to schedule tasks (e.g., backups).  
- **Lab**: Set up Kali Linux in VirtualBox.  

#### **Days 6–15: Networking Essentials**  
- **Learn**:  
  - TCP/IP model, DNS, HTTP/HTTPS, and ports.  
  - Subnetting basics (IPv4 addressing).  
- **Tools**:  
  - `ping`, `nslookup`, `netstat`, `tcpdump`.  
  - Wireshark: Capture and analyze HTTP traffic.  
- **Lab**:  
  - Use `nmap` to scan your local network:  
    ```bash  
    nmap -sV 192.168.1.0/24  
    ```  
  - Block/allow traffic with `ufw` (Linux firewall).  

#### **Days 16–20: Virtual Labs & Recon**  
- **Lab Setup**:  
  - Install Metasploitable 2/3 (vulnerable VM).  
  - Practice SSH into Metasploitable:  
    ```bash  
    ssh user@metasploitable-ip  
    ```  
- **Reconnaissance**:  
  - Use `whois` and `dig` to gather domain info.  
  - Google Dorking: Find exposed files with `site:example.com filetype:pdf`.  

---

### **Phase 2: Days 21–40 – Scripting & Web Hacking**  
**Goal**: Automate tasks and hack web apps ethically.  

#### **Days 21–30: Python & Bash Scripting**  
- **Learn**:  
  - Python basics: loops, functions, modules.  
  - Script a port scanner:  
    ```python  
    import socket  
    for port in range(1, 100):  
        s = socket.socket()  
        if s.connect_ex(("target-ip", port)) == 0:  
            print(f"Port {port} is open")  
        s.close()  
    ```  
  - Bash: Automate NMAP scans.  
- **Lab**: Write a script to find open ports on Metasploitable.  

#### **Days 31–40: Web App Hacking**  
- **Learn**:  
  - OWASP Top 10 vulnerabilities (SQLi, XSS, CSRF).  
  - How browsers work (cookies, sessions, headers).  
- **Tools**:  
  - Burp Suite: Intercept and modify HTTP requests.  
  - SQLmap: Automate SQL injection attacks.  
- **Labs**:  
  1. Hack [OWASP Juice Shop](https://juice-shop.herokuapp.com/):  
     - Bypass the login page using SQLi: `' OR 1=1 --`.  
     - Steal user credentials via XSS.  
  2. Use `curl` to test HTTP headers:  
     ```bash  
     curl -I http://example.com  
     ```  
- **Reporting**: Draft a mock vulnerability report for Juice Shop flaws.  

---

### **Phase 3: Days 41–60 – Exploitation & Privilege Escalation**  
**Goal**: Hack systems and gain root access.  

#### **Days 41–50: Basic Exploits**  
- **Tools**:  
  - Metasploit Framework: Search and launch exploits.  
  - Example: Exploit vsFTPd on Metasploitable:  
    ```bash  
    msfconsole  
    use exploit/unix/ftp/vsftpd_234_backdoor  
    set RHOSTS [metasploitable-ip]  
    exploit  
    ```  
- **Lab**: Hack a [TryHackMe](https://tryhackme.com/) "Easy" machine (e.g., **Nmap** room).  

#### **Days 51–60: Privilege Escalation**  
- **Learn**:  
  - Linux: SUID binaries, cron jobs, kernel exploits.  
  - Windows: Misconfigured services, registry exploits.  
- **Tools**:  
  - `linpeas.sh` (Linux privilege escalation script).  
  - `Windows-Exploit-Suggester`.  
- **Lab**:  
  - Use `linpeas` on Metasploitable to find misconfigurations.  
  - Escalate to root using a SUID exploit.  

---

### **Phase 4: Days 61–80 – Real-World Attacks & Reporting**  
**Goal**: Practice on live labs and report vulnerabilities professionally.  

#### **Days 61–70: Active Directory & Wireless Hacking**  
- **Active Directory Lab**:  
  - Set up [AttackDefense Lab](https://attackdefense.com/) or **Hack The Box**.  
  - Use `BloodHound` to map AD attack paths.  
- **Wireless Attacks**:  
  - Crack WPA2 passwords with `aircrack-ng`:  
    ```bash  
    airodump-ng wlan0mon  
    aireplay-ng --deauth 10 -a [AP-MAC] wlan0mon  
    aircrack-ng -w rockyou.txt capture.cap  
    ```  

#### **Days 71–80: Bug Bounties & Responsible Disclosure**  
- **Practice**:  
  - Use [PortSwigger’s Web Security Academy](https://portswigger.net/web-security).  
  - Find and report a vulnerability in a test site like [Altoro Mutual](https://demo.testfire.net/).  
- **Reporting**:  
  - Template:  
    ```  
    Title: SQL Injection in Login Page  
    Description: The login page is vulnerable to SQLi via the 'username' parameter.  
    Steps to Reproduce:  
    1. Enter `' OR 1=1 --` in the username field.  
    2. Any password grants access.  
    Impact: Full account takeover.  
    ```  

---

### **Phase 5: Days 81–100 – Job Readiness & Advanced Labs**  
**Goal**: Certifications, resume prep, and specialization.  

#### **Days 81–90: Certifications**  
- **Study For**:  
  - **eJPT** (eLearnSecurity Junior Pentester): Focuses on hands-on skills.  
  - **CEH Practical**: Ethical Hacking labs.  
- **Resources**:  
  - [INE eJPT Course](https://ine.com/).  
  - [Hack The Box Labs](https://www.hackthebox.com/).  

#### **Days 91–100: Build Your Portfolio**  
- **GitHub**:  
  - Upload scripts (e.g., custom scanners, exploit PoCs).  
  - Write CTF walkthroughs (e.g., Hack The Box "Starting Point" machines).  
- **LinkedIn**:  
  - Add skills: Kali Linux, Burp Suite, Vulnerability Assessment.  
  - Connect with cybersecurity recruiters.  
- **Freelance**:  
  - Start with [Bugcrowd](https://www.bugcrowd.com/) or [HackerOne](https://www.hackerone.com/).  

---

### **Daily Routine Example**  
- **Morning (1–2 hours)**: Study theory (e.g., OWASP Top 10).  
- **Afternoon (2–3 hours)**: Hands-on labs (Hack The Box, TryHackMe).  
- **Evening (1 hour)**: Document progress in a blog/Notion page.  

---

### **Key Tools to Learn**  
| **Category**       | **Tools**                                      |  
|---------------------|-----------------------------------------------|  
| Scanning            | Nmap, Nessus, OpenVAS                         |  
| Web Hacking         | Burp Suite, SQLmap, OWASP ZAP                 |  
| Exploitation        | Metasploit, Cobalt Strike (trial), Exploit-DB |  
| OSINT               | Maltego, theHarvester, Shodan                 |  
| Password Cracking   | John the Ripper, Hashcat                       |  

---

### **Final Tips**  
1. **Stay Legal**: Only attack systems you own or have permission to test.  
2. **Join Communities**: Reddit’s r/HowToHack, Discord’s Hack The Box.  
3. **Stay Curious**: Follow blogs like [Krebs on Security](https://krebsonsecurity.com/).  

By day 100, you’ll be ready for roles like **Junior Pentester** or **Security Analyst**. Let’s do this! 💻🔒  

Need help with a specific topic or lab? Ask away!
