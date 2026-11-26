# Bashir-Abdullahi-week4-medirozahospital-Intern-B084
# Mediroza General Hospital — Penetration Testing Assessment

*Networkwalks | Week 4 Project | Black-box Web Application Pentest*

> *Educational lab only.* This repository documents work performed as part of an instructor-authorised, controlled cybersecurity exercise. Testing must not be repeated against any system without explicit written permission. All sensitive data has been redacted or omitted.

---

## Project Overview

| Item | Details |
|---|---|
| Assessment type | Black-box penetration test and vulnerability assessment |
| Target specified in brief | https://medirozahospital.com |
| Duration specified in brief | Five days |
| Authorisation | The project brief states that written authorisation was granted |
| Scope restriction | Target domain only |
| Explicit exclusions | Social engineering, denial-of-service testing, and testing outside the agreed scope |

---

## Objectives and Milestones

### M1 — Initial Access

- Conducted reconnaissance on the target.
- Identified exposed entry points.
- Analysed authentication behaviour and input handling.
- Assessed the authorised route to the restricted area.
- Recorded evidence relating to the three specified patient PDF laboratory reports.

*Outcome:* [Complete with your verified result. Do not claim success without evidence.]

---

### M2 — Data Extraction

- Examined the protection applied to each of the three retrieved PDF files.
- Selected suitable recovery methods for each file.
- Recorded successful and unsuccessful attempts separately.

*Outcome:* [Complete with your verified result.]

---

### M3 — Critical Data Exposure

- Reviewed retrieved material and relevant file properties.
- Investigated the employee salary information specified in the brief.
- Investigated the hospital shareholder information specified in the brief.
- Documented the source, access path, impact, and supporting evidence.

*Outcome:* [Complete with your verified result.]

---

### M4 — Reporting

- Summarised the engagement and key findings.
- Documented scope, methodology, and limitations.
- Presented findings with proof of exploitation.
- Assigned justified risk ratings.
- Recommended remediation and validation steps.

*Outcome:* [Complete with your verified result.]

---

## Methodology and Tools

Only tools actually used are listed. Accurate versions and commands are retained in private working notes.

| Tool | Intended use in the assessment |
|---|---|
| DNSRecon | DNS reconnaissance |
| Nmap | Network and service discovery within the authorised scope |
| WAFW00F | Web application firewall identification |
| Burp Suite | HTTP request/response inspection and application testing |
| SQLmap | SQL injection testing, if performed |
| networkwalk tools | PDF password recovery testing, if used |

---

## Findings

One entry per *confirmed* finding. Failed tests, generic error messages, technology fingerprints, and unverified suspicions are *not* treated as proof of a vulnerability.

| ID | Finding | Severity 
|---|---|---|---|
| F-01 | [Confirmed finding title] | [Critical/High/Medium/Low/Informational] | [Evidence ID] |
| F-02 | [Confirmed finding title] | [Severity] | [Evidence ID] |
| F-03 | [Confirmed finding title] | [Severity] | [Evidence ID] |


---
  ## Evidence
  

### Finding Write-Up Template

Copy this block for each finding.

markdown
#### F-XX — [Title]

- **Affected component:** [Endpoint / file / feature]
- **Status:** [confirmed / unconfirmed / not reproduced]

**Description**
[What was observed.]

**Validation**
[Concise, authorised reproduction summary.]

**Impact**
- Confidentiality: [impact]
- Integrity: [impact]
- Availability: [impact]

**Severity:** [Critical/High/Medium/Low/Informational]
[Clear justification based on demonstrated impact and evidence.]

**Evidence:** [Screenshot or output reference]

**Remediation**
[Specific corrective action.]

**Retest:** [fixed / partially fixed / not fixed / not retested]


---

## Risk Rating Guide

| Rating | General meaning |
|---|---|
| Critical | Confirmed issue with severe impact, such as broad unauthorised access to highly sensitive information |
| High | Confirmed issue with substantial impact on sensitive information or important functions |
| Medium | Confirmed issue with meaningful but more limited impact or additional exploitation conditions |
| Low | Confirmed issue with limited direct impact |
| Informational | Observation that does not independently demonstrate a vulnerability |
| Unconfirmed | Evidence is insufficient to establish a vulnerability |

Severity is based on demonstrated impact and evidence — not on assumptions or the wording of the project milestone.

---

## Recommendations

Each recommendation maps to a confirmed finding. Depending on what the evidence establishes, remediation may include:

- Enforce server-side authorisation checks for every sensitive record and file request.
- Store confidential reports outside the public web root and provide access only through authenticated, authorised application routes.
- Use parameterised database queries and least-privilege database accounts where SQL injection is confirmed.
- Apply secure authentication and session-management controls.
- Remove unnecessary sensitive metadata and embedded references from downloadable files.
- Restrict employee and shareholder information by role and business need.
- Review access logs, preserve relevant evidence, and conduct a focused retest after remediation.

---
## Responsible Disclosure and Data Handling

This is a public-facing learning portfolio, not a place to publish confidential hospital information. *Do not commit:*

- Patient names, medical reports, diagnoses, patient identifiers, or other health information.
- Employee personal information or unredacted salary records.
- Private shareholder identifiers or confidential financial records.
- Passwords, recovered passwords, session cookies, tokens, API keys, or credentials.
- Unredacted request/response captures that expose personal data or secrets.

Keep original evidence in a secure, access-controlled location for instructor review. Publish only redacted screenshots or summaries approved for public release. If public disclosure of the target or findings is not authorised, anonymise the target and remove identifying details before publishing.

---

## Limitations

[Document what was not tested, what could not be verified, any tool limitations, and any milestones that were only partially completed.]

---

## Conclusion

[Summarise the milestones completed, the most significant confirmed findings, their demonstrated impact, and the highest-priority remediation actions. Do not claim a successful exploit or data retrieval unless supported by evidence.]

---

## Acknowledgement

Prepared as part of the Networkwalks Week 4 Penetration Testing Project. The project brief identifies Mediroza General Hospital as the client and describes the exercise as a controlled, authorised educational assessment.

- *Author:* [BASHIR ABDULLAHI]
- *Date:* [26/11,2024]
-
