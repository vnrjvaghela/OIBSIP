# Advanced SQL Injection & Remediation
**Author:** Vanraj Vaghela
**Track:** Cyber Security
**Task:** 9 - Exploit a SQL Injection Vulnerability (Advanced)

## Executive Summary
During a targeted security assessment, a critical SQL Injection vulnerability was identified in the application's data retrieval module. While front-end controls (a dropdown menu) were implemented to restrict input, the backend fails to validate the intercepted POST request data. This flaw allows unauthorized users to manipulate database queries via proxy tools, leading to the complete exposure of sensitive tables, including user credentials. Immediate remediation is required to prevent data exfiltration.

## Vulnerability Exploitation via Proxy
By routing traffic through Burp Suite, the HTTP POST request was intercepted before reaching the server. The `id` parameter was manually modified to include a `UNION SELECT` statement. Because the backend trusted the incoming POST data without sanitization, it executed the appended query, dumping the `information_schema.tables` to the frontend.

## Remediation Strategy: Code Examples
To definitively fix this, the backend must be refactored to use parameterized queries (Prepared Statements). 

**Vulnerable Python Implementation:**
```python
# Unsafe: Concatenating input directly
cursor.execute("SELECT first_name, last_name FROM users WHERE user_id = '" + user_input + "'")