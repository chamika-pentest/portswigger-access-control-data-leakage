# portswigger-access-control-data-leakage
Professional security lab write-up for the PortSwigger Web Security Academy lab “User ID controlled by request parameter with data leakage in redirect”, demonstrating broken access control and sensitive data exposure via HTTP redirects

# User ID Controlled by Request Parameter – Data Leakage in Redirect

**Author:** Chamika Jayasooriya  
**Field:** Cybersecurity / Penetration Testing  
**Platform:** PortSwigger Web Security Academy  
**Lab Level:** Apprentice  
**Category:** Access Control / Information Disclosure  

---

## Overview
This repository contains a professional write-up for the PortSwigger Web Security Academy lab **“User ID controlled by request parameter with data leakage in redirect.”**  
The lab demonstrates how sensitive information, such as API keys, can be exposed in the HTTP response body of a 302 redirect when proper access control is not enforced.

---

## Objectives
- Log in as a normal user.  
- Observe application behavior during redirects.  
- Identify sensitive information leaked in redirect responses.  
- Extract and submit another user’s API key.  

---

## Vulnerability Summary
- **Type:** Broken Access Control, Information Disclosure, Sensitive Data Exposure via Redirect  
- **Description:** The application issues a 302 redirect when an unauthorized request is made. Despite the redirect, sensitive data is included in the response body, allowing attackers to access API keys or other confidential information.  

---

## Tools & Environment
- Web Browser (Chrome / Firefox)  
- Burp Suite (Proxy & HTTP History)  
- PortSwigger Web Security Academy Lab Environment  

---

## Test Accounts
| Username | Password | Role       |  
|----------|---------|------------|  
| wiener   | peter   | Normal User |  
| carlos   | Unknown | Normal User |  

---

## Step-by-Step Exploitation
1. Log in using normal user credentials (`wiener` / `peter`).  
2. Navigate to the account page and observe unexpected redirect behavior.  
3. Intercept the redirect response using Burp Suite.  
4. Examine the response body and identify sensitive data leakage (API key).  
5. Extract and submit the API key as the lab solution.  

---

## Impact
- Exposure of sensitive user information  
- Unauthorized access to API keys  
- Potential abuse of backend APIs  

---

## Mitigation & Recommendations
- Never include sensitive data in redirect responses.  
- Ensure redirect responses contain minimal or empty bodies.  
- Enforce strict server-side access control before generating data.  
- Validate user authorization prior to processing requests.  

---

## References
- [PortSwigger Web Security Academy – Access Control Labs](https://portswigger.net/web-security)  
- [OWASP Top 10 – Broken Access Control](https://owasp.org/Top10/)  
- [OWASP – Sensitive Data Exposure](https://owasp.org/www-project-top-ten/2017/A3_2017-Sensitive_Data_Exposure.html)

---

## Author
**Chamika Jayasooriya**  
Cybersecurity / Penetration Testing

