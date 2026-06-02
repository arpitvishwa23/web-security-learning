# A01: Broken Access Control

## Introduction

Access control is one of the most fundamental security mechanisms in any application. It determines what actions a user is allowed to perform and which resources they can access. When access control mechanisms fail, attackers may gain access to sensitive information, modify data, or perform actions beyond their intended permissions.

In the OWASP Top 10:2025, Broken Access Control remains the number one security risk, highlighting how common and impactful these vulnerabilities continue to be across modern web applications.

---

## Understanding Access Control

Access control is responsible for enforcing security policies that define who can access specific resources and what actions they can perform.

A properly implemented access control system ensures that:

- Users can only access resources they are authorized to use.
- Users can perform only permitted actions.
- Administrative functions remain restricted to privileged users.
- Sensitive data is protected from unauthorized access.

One of the most important principles of access control is the **Principle of Least Privilege**, which states that users should only be granted the minimum permissions necessary to perform their tasks.

---

## What is Broken Access Control?

Broken Access Control occurs when an application fails to properly enforce authorization rules. As a result, users may gain access to resources, data, or functionality that should be restricted.

These vulnerabilities often arise when applications rely on client-side controls, fail to validate permissions on the server side, or expose sensitive resources without proper authorization checks.

---

## Common Types of Broken Access Control

### 1. Insecure Direct Object References (IDOR)

An application exposes internal identifiers such as account numbers, user IDs, or document IDs without verifying ownership.

Example:

```text
https://example.com/account?id=1001
```

An attacker changes the identifier to:

```text
https://example.com/account?id=1002
```

If the application does not verify ownership, the attacker may access another user's account.

### 2. Privilege Escalation

A standard user gains administrative privileges due to missing authorization checks.

Examples include:

- Accessing admin pages directly
- Modifying user roles
- Executing privileged functions

### 3. Forced Browsing

An attacker manually accesses restricted URLs that are not linked in the application interface.

Example:

```text
https://example.com/admin
```

If the server does not verify permissions, unauthorized users may access sensitive functionality.

### 4. API Authorization Failures

Applications expose APIs that lack proper authorization checks for actions such as:

- Creating records
- Updating records
- Deleting records

### 5. Token and Session Manipulation

Attackers modify security tokens, cookies, hidden form fields, or JSON Web Tokens (JWTs) to gain elevated privileges.

---

## Common Attack Scenarios

### Scenario 1: Account Access Manipulation

An application retrieves account information using a user-supplied parameter.

```java
pstmt.setString(1, request.getParameter("acct"));
ResultSet results = pstmt.executeQuery();
```

An attacker changes the account identifier to access another user's information.

### Scenario 2: Unauthorized Administrative Access

An application provides separate URLs for standard users and administrators.

```text
https://example.com/app/getappInfo
https://example.com/app/admin_getappInfo
```

If a non-administrative user can access the administrative endpoint, the application contains an access control flaw.

### Scenario 3: Client-Side Authorization

The application hides administrative features using JavaScript but performs no authorization checks on the server.

An attacker can directly access the endpoint using tools such as:

```bash
curl https://example.com/app/admin_getappInfo
```

Because the server does not verify permissions, the attacker gains unauthorized access.

---

## Impact of Broken Access Control

Successful exploitation can lead to serious consequences, including:

- Unauthorized access to sensitive information
- Modification or deletion of critical data
- Account takeover
- Privilege escalation
- Exposure of confidential business information
- Regulatory and compliance violations
- Financial and reputational damage

---

## Prevention and Mitigation

### Deny Access by Default

Resources should remain inaccessible unless explicit permissions have been granted.

### Enforce Server-Side Authorization

Authorization checks must always be performed on the server side.

### Implement Least Privilege

Users should receive only the permissions required to perform their responsibilities.

### Validate Ownership

Applications should verify that users own or are authorized to access specific records before providing access.

### Protect Administrative Functions

Administrative endpoints should be protected through strong authorization controls and role validation.

### Secure Session Management

- Invalidate sessions after logout.
- Use short-lived access tokens.
- Implement secure token revocation mechanisms.

### Monitor and Log Access Failures

Organizations should log authorization failures and investigate repeated attempts to access restricted resources.

---

## Key Takeaways

- Broken Access Control is the highest-ranked risk in OWASP Top 10:2025.
- It occurs when authorization rules are not properly enforced.
- Common issues include IDOR, privilege escalation, forced browsing, and API authorization failures.
- Strong server-side authorization and least-privilege principles are essential for prevention.

---

## References

- OWASP Top 10:2025
- OWASP Authorization Cheat Sheet
- OWASP Testing Guide
- OWASP ASVS