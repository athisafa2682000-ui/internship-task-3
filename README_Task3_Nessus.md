# 🛡️ Task 3 — Vulnerability Scan using Nessus Essentials

**Author:** Atheeka Bi Safa  
**Date:** October 2025  
**Tool Used:** Nessus Essentials (by Tenable)  
**Target System:** 19.100.0.10 (Localhost)  
**Operating System:** Windows 11  

---

## 📘 Overview

This task involves performing a **vulnerability assessment** on the local Windows system using **Nessus Essentials**.  
The objective was to identify potential weaknesses, analyze their severity, and generate a detailed report for remediation.

---

## ⚙️ Steps Performed

1. **Installed Nessus Essentials**
   - Downloaded from [https://www.tenable.com/products/nessus/nessus-essentials](https://www.tenable.com/products/nessus/nessus-essentials)
   - Activated using the free license key received via email.
   - Waited for **plugin initialization** to complete (~30–45 minutes).

2. **Configured the Scan**
   - Opened Nessus in a browser: `https://localhost:8834`
   - Selected **New Scan → Basic Network Scan**
   - Entered Target IP: `19.100.0.10`
   - Saved and named the scan as `Local Vulnerability Scan`

3. **Executed the Scan**
   - Clicked **Launch** to start scanning.
   - Nessus analyzed the system for open ports, SSL configurations, and SMB services.
   - Scan Duration: Approximately 35 minutes.

4. **Analyzed the Results**
   - Scan completed successfully.
   - Found **2 Medium vulnerabilities** on the system:
     - **SSL Certificate Cannot Be Trusted**
     - **SMB Signing Not Required**

5. **Exported Report**
   - Exported detailed results in PDF format.
   - Report saved as `vulnerability-report-19.100.0.10.pdf`

---

## 📊 Summary of Findings

| Severity | Vulnerability Name | Description | Risk | Solution |
|-----------|--------------------|--------------|------|-----------|
| Medium | **SSL Certificate Cannot Be Trusted** | The SSL certificate used by the server is self-signed or issued by an untrusted authority. This could allow attackers to perform man-in-the-middle attacks. | Medium | Use a valid SSL/TLS certificate from a trusted Certificate Authority (CA). |
| Medium | **SMB Signing Not Required** | The server allows SMB communication without signing, enabling attackers to modify network packets during transmission. | Medium | Enable SMB signing on both client and server to ensure integrity and authenticity of SMB sessions. |

---

## 🧠 Key Learnings

- **Nessus Essentials** provides a user-friendly platform for automated vulnerability scanning.  
- Understanding the meaning and impact of each vulnerability helps in prioritizing remediation.  
- **SSL** and **SMB** configurations are critical components in securing Windows systems.  
- Regular scans improve overall system security and compliance.

---

## 🧩 Recommendations

- Replace self-signed or expired SSL certificates with certificates from a **trusted CA**.  
- Enforce **SMB signing** to prevent packet tampering in local networks.  
- Keep Windows and third-party software **fully updated**.  
- Perform **scheduled monthly scans** to ensure no new vulnerabilities appear.  
- Educate users on safe browsing and network usage practices.

---

## 📁 Repository Structure

```
task3-vulnerability-scan/
├── README.md
├── report/
│   ├── vulnerability-report-19.100.0.10.pdf
│   ├── screenshot-results.png
│   ├── screenshot-dashboard.png
```

---

## 📚 References

- [Tenable Nessus Essentials Documentation](https://docs.tenable.com/nessus/)
- [Microsoft SMB Security Guidance](https://learn.microsoft.com/en-us/windows-server/storage/file-server/smb-security)
- [OWASP SSL/TLS Best Practices](https://owasp.org/www-project-cheat-sheets/cheatsheets/Transport_Layer_Protection_Cheat_Sheet.html)

---

## ✅ Conclusion

The vulnerability scan for **IP 19.100.0.10** identified two medium-risk issues related to **SSL certificate trust** and **SMB signing**.  
By applying the recommended solutions — using a trusted SSL certificate and enabling SMB signing — system security can be significantly improved.  
This exercise enhanced practical knowledge of vulnerability detection and mitigation using Nessus Essentials.

---

**Submitted as part of Task 3 — Vulnerability Scanning and Reporting**
