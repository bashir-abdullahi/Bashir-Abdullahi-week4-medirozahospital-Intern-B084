# Mediroza General Hospital — Web Application Penetration Testing

> *Academic security assessment | Networkwalks Week 4 project*  
> *Assessment type:* Black-box web application penetration test  
> *Target:* https://medirozahospital.com  
> *Report status:* Redacted portfolio summary — Full unredacted evidence submitted privately.

---

## Repository purpose

This repository documents an authorised, educational black-box security assessment of the Mediroza General Hospital web application, conducted under the project scope supplied by Networkwalks.

The assessment successfully achieved all milestones:
1. *M1 (Initial Access):* Bypassed authentication to retrieve 3 confidential patient PDF lab reports.
2. *M2 (Data Extraction):* Cracked the encryption on all 3 retrieved PDF files.
3. *M3 (Critical Exposure):* Discovered exposed server data containing employee salaries and shareholder details.
4. *M4 (Reporting):* Documented the findings, impact, and remediation strategies.

*No patient records, employee personal information, salary figures, shareholder details, credentials, or raw database exports are published in this repository.* All evidence in the evidence/ folder has been strictly redacted for public portfolio viewing.

---

## Assessment scope and rules

The project brief identified the target domain as https://medirozahospital.com and described a five-day black-box penetration test.

| ID | Objective |
|---|---|
| *M1* | *Initial access:* Assess the application and retrieve 3 confidential patient PDF lab reports. |
| *M2* | *Data extraction:* Crack the encryption on all 3 retrieved files. |
| *M3* | *Critical data exposure:* Find staff salaries and shareholder details of the hospital. |
| *M4* | *Reporting:* Write a professional penetration testing report. |

Testing remained within the written authorisation. Social engineering, denial-of-service, and out-of-scope testing were strictly excluded.

---

## Methodology & Tools

The assessment followed a standard black-box workflow: Reconnaissance → Enumeration → Vulnerability Assessment → Controlled Exploitation → Evidence Collection → Reporting.

### Tools Used

| Tool | Purpose |
|---|---|
| Nmap | Network and service enumeration. |
| DNSRecon | DNS reconnaissance and enumeration. |
| WAFW00F | Web application firewall detection. |
| Burp Suite | Request/response inspection, auth bypass, and input handling. |
| SQLmap | Controlled input-handling validation. |
| Networkwalks (NW) Tool | Project-provided tool used for authorised password/hash auditing (functionally similar to John the Ripper). |

---

## Findings

### Finding 01 — Unauthorised Access to Patient PDF Lab Reports (M1)

*Status:* Successfully Exploited  
*Severity:* High  
*Affected Asset:* Web application authentication/access control mechanisms.

*Description*
During the assessment, access controls were bypassed, allowing unauthorised retrieval of 3 confidential patient PDF lab reports from a restricted area of the site. 

*Evidence*
- Redacted screenshots:
-  [evidence/](evidence)
- Proof of retrieval and access path are documented in the private submission.

*Impact*
An attacker could access highly sensitive medical data, leading to severe privacy violations (e.g., HIPAA/GDPR equivalents), reputational damage, and potential legal liability.

*Recommendations*
1. Enforce strict server-side authentication and authorisation checks for all PDF resources.
2. Move sensitive files outside the public web root.
3. Implement robust access control (e.g., Role-Based Access Control).

---

### Finding 02 — Weak PDF Encryption on Lab Reports (M2)

*Status:* Successfully Exploited  
*Severity:* High  
*Affected Asset:* PDF Document Protection.

*Description*
The 3 retrieved PDF files were encrypted. However, the encryption mechanism was susceptible to cracking using dictionary/brute-force methods via the NW Tool, allowing full extraction of the document contents.

*Evidence*
- Redacted screenshots of the cracking process and recovered contents:
  [evidence/](evidence/shareholder.png)

*Impact*
If an attacker gains access to the files, weak encryption provides minimal protection against data extraction.

*Recommendations*
1. Use strong, modern encryption standards (e.g., AES-256) with complex, high-entropy passwords.
2. Utilize secure key management practices instead of standard password-based encryption.

---

### Finding 03 — Critical Data Exposure: Salaries & Shareholder Details (M3)

*Status:* Successfully Exploited  
*Severity:* Critical  
*Affected Asset:* Exposed server files / Metadata.

*Description*
By analyzing the retrieved data (M1/M2) and examining file properties/metadata, a further critical exposure was identified on the server. This led to the discovery of highly sensitive internal data, specifically employee salary information and hospital shareholder details.

*Evidence*
- Redacted screenshots demonstrating the exposure path and data existence (data itself is masked): [evidence/](evidence/)

*Impact*
This represents a catastrophic confidentiality breach. Exposure of salary structures causes internal friction and reputational damage, while shareholder details can facilitate targeted fraud, financial crime, and corporate espionage.

*Recommendations*
1. *Immediately* restrict public access to directories, backups, and sensitive exports.
2. Review web server configurations, file permissions, and object storage permissions.
3. Remove sensitive files from the public web root and enforce least-privilege access.
4. Scrub metadata from public-facing documents to prevent information leakage.

---

## Risk Rating Guide

| Rating | General meaning |
|---|---|
| *Critical* | Severe compromise with broad or highly sensitive impact (e.g., verified access to extensive sensitive records). |
| *High* | Significant confidentiality, integrity, or access-control impact. |
| *Medium* | Meaningful but limited impact or conditions required for exploitation. |
| *Low* | Limited impact with restricted practical consequences. |

---

## Remediation Priorities

| Priority | Recommended Action |
|---|---|
| *Immediate* | Restrict public access to exposed sensitive data; preserve logs for investigation. |
| *High* | Correct server-side access controls; remove sensitive backups/exports from public paths. |
| *Medium* | Strengthen authentication, secure file handling, and document encryption practices. |
| *Ongoing* | Implement periodic security testing, monitoring, and data-retention controls. |

---

## Evidence Handling

This repository is intended as a professional portfolio summary. The evidence/ folder contains *only non-sensitive, redacted screenshots*. 

### Do not commit:
- Patient reports, patient names, identifiers, or medical information.
- Employee personal data, salary details, or shareholder records.
- Database dumps, backups, private documents, or extracted datasets.
- Passwords, hashes, API keys, session cookies, or authentication tokens.

Original evidence is kept in a private, access-controlled location and submitted only through the instructor's approved channel.

---

## Author

*Tester:* Bashir Abdullahi  
*Programme:* BBIT  
*Project:* Networkwalks Week 4 — Penetration Testing  
*Date:* [Insert Assessment Date, e.g., October 2023
