# AWS Cloud Security — Reconnaissance and Mitigation

## Objective
This lab demonstrates my ability to identify and mitigate vulnerabilities in a cloud environment using AWS and Kali Linux. I simulated a misconfigured AWS environment, conducted reconnaissance to exploit its vulnerabilities, and applied security measures to secure the system.

---

## 1. AWS Environment Setup

### EC2 Instance Configuration
- **Launched** an EC2 instance (Amazon Linux 2) to simulate a cloud server.
- **Configured** the security group to allow SSH (port 22) and HTTP (port 80) access for testing.
  
**Screenshot:** AWS EC2 dashboard showing the public IP and security group rules.

---

### S3 Bucket Configuration
- **Created** an S3 bucket with Block Public Access **disabled** to simulate a common misconfiguration.
- **Uploaded** a file named `secret.txt` containing sensitive data and allowed public access to this object.

**Screenshot:** S3 bucket settings highlighting the misconfigured Block Public Access and public file permissions.

---

## 2. Kali Linux Reconnaissance

### nmap Scan Results
- **Used `nmap`** from Kali Linux to scan the EC2 instance for open ports and services.
- **Identified** open SSH and HTTP ports.

**Screenshot:** Output of the `nmap` scan showing open ports and services on the EC2 instance.

---

### AWS CLI S3 Enumeration
- **Enumerated** the S3 bucket from Kali Linux using AWS CLI.
- **Listed** the contents of the vulnerable S3 bucket, confirming public access to `secret.txt`.

**Screenshot:** AWS CLI command and output listing the contents of the S3 bucket.

---

### Exfiltration of Sensitive Data
- **Used AWS CLI** to download the `secret.txt` file from the S3 bucket to demonstrate the risk of sensitive data exposure.
- **Displayed** the contents of `secret.txt` after exfiltration.

**Screenshot:** AWS CLI command to download `secret.txt` and the file contents displayed in the terminal.

---

## 3. Mitigation and Security Hardening

### Before Mitigation:
- The S3 bucket was **publicly accessible**, allowing unauthorized users to list and download objects.

**Screenshot:** S3 bucket with Block Public Access turned off, showing public access enabled for `secret.txt`.

---

### After Mitigation:
- **Enabled** Block Public Access for the S3 bucket.
- **Verified** that public access was denied, ensuring no unauthorized access to the bucket or its objects.
- **Tested** access using AWS CLI and browser, both returning `Access Denied`.

**Screenshot:** S3 bucket with Block Public Access turned on and public access denied.

---

## Key Learnings
- **Cloud Misconfigurations:** Identified how misconfigurations like public S3 buckets can expose sensitive data.
- **Reconnaissance Techniques:** Used `nmap` and AWS CLI for effective cloud reconnaissance.
- **Mitigation Strategies:** Secured the environment by enabling Block Public Access and restricting bucket permissions.
- **Practical Security Skills:** Gained hands-on experience in identifying, exploiting, and securing cloud vulnerabilities.

---

## Conclusion
This lab demonstrates my ability to set up, assess, and secure cloud environments. I showcased practical skills in cloud security, from reconnaissance to mitigation.
