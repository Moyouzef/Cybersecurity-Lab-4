# 🔐 Week 4 Penetration Testing Assessment

## Academic Cybersecurity Training Project

**Training Organization:** NETWORKWALKS  
**Cybersecurity Mentor:** Waqas Karim, CCIE  
**Trainee:** Mohamed Yusuf  
**Project:** Week 4 Penetration Testing Assessment  
**Assessment Date:** October 03, 2026  
**Environment:** Kali Linux  
**Assessment Type:** Controlled Academic Security Assessment  
**Classification:** Training / Educational Use

---

## ⚠️ Important Disclaimer

This repository documents a cybersecurity training exercise conducted
as part of an authorized penetration-testing learning program.

The information published here has been sanitized for educational
purposes.

No real patient information, credentials, authentication secrets,
private reports, database contents, or sensitive healthcare information
are included in this repository.

The techniques described are presented at a high level and should only
be applied to systems for which the tester has explicit authorization.

---

# 1. Executive Summary

Week 4 was one of the most challenging penetration-testing projects
completed during my cybersecurity training.

The objective of the assessment was to perform a controlled security
assessment of a web-based patient application and evaluate its
authentication, input handling, exposed services, and overall security
posture.

The assessment involved several stages of testing and investigation.
Multiple tools and techniques were used, including:

- Burp Suite
- SQL injection testing
- Nikto
- Network/service enumeration
- Directory and application enumeration
- Manual HTTP request analysis
- Additional testing utilities available in Kali Linux

The assessment required several attempts because the initial testing
approaches did not immediately produce the expected results.

Rather than relying on a single tool, I compared results from different
tools, manually inspected application behavior, modified testing
strategies, and investigated the application's responses.

The final assessment identified a significant security weakness in the
application's authentication/security controls.

The project provided practical experience in understanding how
penetration testing works in a real-world-style environment.

---

# 2. Project Objectives

The primary objectives were to:

1. Understand the target application's attack surface.
2. Identify exposed services and technologies.
3. Examine the authentication mechanism.
4. Test application input handling.
5. Investigate potential injection vulnerabilities.
6. Analyze HTTP requests and responses.
7. Validate security findings through controlled testing.
8. Assess the potential impact of identified weaknesses.
9. Document findings professionally.
10. Recommend appropriate remediation measures.

---

# 3. Methodology

The assessment followed a structured penetration-testing methodology.

### Phase 1 — Reconnaissance & Scoping

The first stage was focused on understanding the target environment.

Activities included:

- Identifying the target domain.
- Reviewing the externally visible attack surface.
- Identifying technologies and services.
- Examining HTTP responses.
- Looking for publicly exposed application components.
- Establishing the boundaries of the assessment.

The purpose of this stage was to understand the environment before
performing deeper security testing.

---

# 4. Tools Used

## 4.1 Kali Linux

Kali Linux was used as the primary penetration-testing environment.

It provided access to a large collection of security assessment tools
and utilities.

---

## 4.2 Nikto

Nikto was used during the reconnaissance and web-server assessment
stage.

The objective was to identify potentially interesting web-server
configuration issues, exposed files, server technologies, and other
items that required further investigation.

Nikto results were treated as indicators rather than automatic proof
of vulnerabilities.

Each interesting result required manual validation.

---

## 4.3 Burp Suite

Burp Suite was one of the most important tools used during the project.

It was used to understand how the browser communicated with the
application.

Testing activities included:

- Intercepting HTTP/HTTPS requests.
- Reviewing request parameters.
- Reviewing response behavior.
- Replaying requests in a controlled manner.
- Comparing normal and modified requests.
- Investigating authentication-related behavior.
- Observing how the application handled unexpected input.

Burp Suite helped move the assessment from automated scanning toward
manual application-security testing.

---

# 5. SQL Injection Testing

SQL injection testing was performed as part of the assessment.

The objective was to determine whether application input was being
properly validated and safely processed by the backend.

According to OWASP, SQL injection occurs when untrusted input can
influence SQL queries without adequate protection, potentially
affecting confidentiality, integrity, or authentication. 

During the assessment, input points associated with the application
were investigated and their responses were compared.

Testing focused on:

- Authentication-related input.
- Parameter behavior.
- Server responses.
- Error behavior.
- Response differences.
- Whether unexpected input changed application behavior.

No destructive database operations were intentionally performed.

---

# 6. Authentication Testing

Authentication was an important part of the assessment.

The objective was to determine whether the application correctly
enforced authentication before providing access to protected
functionality.

The assessment considered:

- Login behavior.
- Authentication responses.
- Session behavior.
- Request manipulation.
- Direct access to protected functionality.
- Differences between authenticated and unauthenticated requests.

OWASP's Web Security Testing Guide identifies authentication-bypass
testing as a specific web-application testing area. 

The testing revealed behavior indicating that the application's
authentication controls required further security hardening.

---

# 7. Manual Testing

One of the most important lessons from this project was that automated
tools alone were not enough.

Several automated and semi-automated approaches were tested.

Some produced:

- False positives.
- Incomplete results.
- Unexpected responses.
- No useful result.
- Results that required additional manual investigation.

Because of this, the assessment moved toward manual testing.

The process was:

1. Observe application behavior.
2. Capture the relevant request.
3. Analyze the parameters.
4. Modify the request in a controlled manner.
5. Send the request again.
6. Compare the response.
7. Investigate unexpected behavior.
8. Repeat with alternative test conditions.
9. Validate the finding.
10. Document the result.

This iterative process was one of the most valuable parts of Week 4.

---

# 8. Vulnerability Identification

The assessment identified a significant weakness involving the
application's authentication/security controls.

The observed behavior indicated that security controls protecting
sensitive functionality could potentially be bypassed under the tested
conditions.

The issue was investigated using multiple techniques rather than
being accepted from a single automated scanner result.

The finding was therefore documented as requiring urgent remediation
within the controlled training assessment.

---

# 9. Potential Impact

If a vulnerability of this type existed in a production healthcare
application, the potential impact could be significant.

Potential consequences could include:

### Confidentiality

Unauthorized access to sensitive information.

### Integrity

Possibility of unauthorized modification of application or database
information, depending on the vulnerability and backend privileges.

### Authentication

Potential unauthorized access to functionality intended only for
authenticated users.

### Privacy

Exposure of protected healthcare information could create serious
privacy and regulatory consequences.

### Business Impact

A healthcare organization could face:

- Loss of trust.
- Operational disruption.
- Incident-response costs.
- Legal or regulatory consequences.
- Reputational damage.

The actual impact depends on the application's architecture,
database permissions, access controls, and other security mechanisms.

---

# 10. Sensitive Data Handling

Because the assessment involved a healthcare-themed application,
sensitive information was treated carefully.

The public version of this project intentionally does NOT contain:

- Patient names
- Patient IDs
- Medical records
- Laboratory results
- Passwords
- Authentication tokens
- Session cookies
- Database credentials
- Private documents
- Personal information
- Real patient report contents

Any screenshots published publicly should be redacted before upload.

---

# 11. Risk Assessment

| Finding | Category | Potential Impact | Priority |
|---|---|---|---|
| Authentication security weakness | Authentication / Access Control | Unauthorized access | Critical review |
| Input handling weakness | Injection | Potential data exposure | High |
| Exposed web-server information | Security Misconfiguration | Information disclosure | Medium |
| Unnecessary exposed resources | Attack Surface | Additional reconnaissance opportunities | Medium |
| Sensitive information exposure | Data Protection | Privacy impact | High |

> Severity should be confirmed using the actual evidence, affected
> components, exploitability, and business impact rather than relying
> solely on automated scanner output.

OWASP identifies Broken Access Control and Injection among the major
web-application security risks in its Top 10 framework. :contentReference[oaicite:1]{index=1}

---

# 12. Remediation Recommendations

## 12.1 Secure Authentication

The application should enforce authentication on the server side.

Protected resources should not depend solely on client-side controls.

---

## 12.2 Use Parameterized Queries

Database queries should use parameterized statements or other safe
database-access mechanisms.

User-controlled input should never be directly concatenated into SQL
queries.

OWASP recommends separating data from commands/queries through safe
APIs and parameterized interfaces. :contentReference[oaicite:2]{index=2}

---

## 12.3 Server-Side Authorization

Authorization must be enforced by trusted server-side code.

Users should only be able to access information and functions for
which they have explicit permission.

OWASP recommends deny-by-default access control and server-side
enforcement. :contentReference[oaicite:3]{index=3}

---

## 12.4 Protect Sensitive Files

Backups, database exports, configuration files, and other sensitive
resources should not be publicly accessible from the web root.

---

## 12.5 Secure Database Permissions

The application's database account should follow the principle of
least privilege.

The web application should not have unnecessary administrative
database permissions.

---

## 12.6 Improve Logging and Monitoring

Authentication failures, authorization failures, suspicious requests,
and other security events should be logged and monitored.

OWASP recommends sufficient logging and monitoring of access-control
and validation failures. :contentReference[oaicite:4]{index=4}

---

## 12.7 Security Testing During Development

Security testing should be integrated into the development lifecycle.

Recommended activities include:

- Secure code review
- SAST
- DAST
- Dependency scanning
- Authentication testing
- Authorization testing
- SQL injection testing
- Security regression testing

---

# 13. Assessment Challenges

Week 4 was significantly more difficult than the previous projects.

The biggest challenge was that the first testing approaches did not
immediately provide a clear path to the final result.

I had to:

- Test multiple tools.
- Compare different results.
- Investigate unexpected behavior.
- Understand HTTP requests.
- Analyze application responses.
- Re-test findings.
- Change my approach when an attempt failed.
- Avoid relying entirely on automated tools.

This taught me an important lesson:

> A penetration tester needs to understand the application, not just
> know how to run security tools.

---

# 14. Lessons Learned

## Technical Lessons

I gained practical experience with:

- Web reconnaissance.
- HTTP request analysis.
- Burp Suite.
- SQL injection concepts.
- Authentication testing.
- Web-server enumeration.
- Vulnerability validation.
- Security reporting.
- Risk analysis.
- Remediation planning.

---

## Professional Lessons

The project also taught me that penetration testing requires:

- Patience.
- Documentation.
- Critical thinking.
- Persistence.
- Careful validation.
- Understanding of application behavior.
- Responsible handling of sensitive information.

A scanner may identify something interesting, but the penetration tester
must understand what the result actually means.

---

# 15. What Made Week 4 Different?

Previous projects focused heavily on individual tools and techniques.

Week 4 required combining several skills.

Instead of simply running a command and recording the output, I had to
build an investigation process.

The workflow became:

Reconnaissance  
↓  
Enumeration  
↓  
Web application analysis  
↓  
Request interception  
↓  
Input testing  
↓  
Authentication analysis  
↓  
Manual validation  
↓  
Impact assessment  
↓  
Reporting  
↓  
Remediation

This made Week 4 feel much closer to a real penetration-testing
assessment.

---

# 16. Final Result

The Week 4 assessment was successfully completed after multiple testing
attempts.

The project demonstrated how different penetration-testing tools can
be combined with manual analysis to investigate a web application.

The most important achievement was not simply finding a vulnerability.

The most important achievement was learning how to continue an
investigation when the first approach does not work.

---

# 17. Acknowledgment

Special thanks to **Waqas Karim, CCIE**, for his guidance,
encouragement, and technical mentorship throughout this project.

I would also like to thank **NETWORKWALKS** for providing practical
cybersecurity projects that allow trainees to move beyond theory and
experience realistic penetration-testing workflows.

Week 4 was challenging, but it was one of the most valuable learning
experiences of the training so far.

---

# 18. References

- OWASP Top 10
- OWASP Web Security Testing Guide
- OWASP SQL Injection Testing Guidance
- Kali Linux security-testing tools documentation
- Burp Suite documentation

---

## Author

**Mohamed Yusuf**

Cybersecurity Trainee  
NETWORKWALKS — Batch B082  
Week 4 Penetration Testing Project

---

## Educational Notice

This project is published for educational and portfolio purposes.

All penetration-testing activities should only be performed against
systems for which explicit authorization has been provided.
