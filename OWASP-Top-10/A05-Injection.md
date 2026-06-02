# A05: Injection

## Introduction

Injection is one of the most well-known and dangerous web application vulnerabilities. It occurs when an application accepts untrusted user input and sends it to an interpreter such as a database, operating system, or browser without proper validation.

An attacker can manipulate this input to execute unintended commands, access sensitive information, modify data, or even take control of a system.

According to OWASP Top 10:2025, Injection remains a major security risk because it affects a wide range of technologies and applications.

---

## Understanding Injection

Injection vulnerabilities occur when user input is treated as part of a command or query instead of simple data.

Applications often interact with:

- Databases
- Operating systems
- APIs
- Web browsers
- Directory services

If user input is not handled properly, attackers can inject malicious code or commands into these systems.

Common types of injection include:

- SQL Injection
- Cross-Site Scripting (XSS)
- Command Injection
- LDAP Injection
- XPath Injection
- NoSQL Injection

Although the target systems differ, the underlying concept remains the same: untrusted input is executed as a command.

---

## Common Causes

### Lack of Input Validation

Applications fail to verify whether user-supplied data contains malicious characters or commands.

### Dynamic Queries

Developers create queries by directly concatenating user input instead of using parameterized queries.

### Improper Output Encoding

User input is displayed without proper encoding, allowing attackers to inject scripts into web pages.

### Unsafe Command Execution

Applications pass user input directly to operating system commands without validation.

### Weak Security Testing

Lack of code reviews and security testing may allow injection vulnerabilities to remain undetected.

---

## Example Attack Scenarios

### Scenario 1: SQL Injection

An application builds a SQL query using user input:

```sql
SELECT * FROM users WHERE id = 'user_input';
```

An attacker enters:

```sql
' OR '1'='1
```

The query returns all records from the database instead of a single user's data.

### Scenario 2: Cross-Site Scripting (XSS)

A website displays user comments without sanitization.

An attacker submits:

```html
<script>alert('XSS')</script>
```

When other users view the page, the script executes in their browser.

### Scenario 3: Command Injection

An application runs the following command:

```bash
ping user_input
```

An attacker enters:

```bash
example.com && whoami
```

The server executes additional commands that were never intended by the application.

---

## Impact

Injection vulnerabilities can lead to:

- Unauthorized access to data
- Data modification or deletion
- Account compromise
- Remote code execution
- Server takeover
- Information disclosure
- Loss of business reputation

The impact depends on the permissions available to the vulnerable application.

---

## Prevention and Mitigation

### Use Parameterized Queries

Always use prepared statements and parameterized queries instead of building queries through string concatenation.

### Validate User Input

Apply strict server-side validation to ensure only expected data is accepted.

### Sanitize and Encode Output

Encode user-generated content before displaying it in browsers to prevent XSS attacks.

### Avoid Direct Command Execution

Do not pass user input directly into operating system commands.

### Use ORM Frameworks

Object Relational Mapping (ORM) frameworks can reduce the risk of SQL injection when used correctly.

### Perform Security Testing

Use:

- SAST (Static Application Security Testing)
- DAST (Dynamic Application Security Testing)
- IAST (Interactive Application Security Testing)
- Fuzz Testing

to identify injection vulnerabilities before deployment.

### Follow Secure Coding Practices

Developers should follow secure coding standards and regularly review application code.

---

## Key Takeaways

- Injection occurs when untrusted input is executed as commands or queries.
- SQL Injection and Cross-Site Scripting (XSS) are among the most common forms of injection attacks.
- Improper input validation and dynamic query construction are major causes.
- Injection vulnerabilities can lead to data breaches, system compromise, and unauthorized access.
- Parameterized queries, input validation, and secure coding practices are the best defenses.

---

## References

- OWASP Top 10:2025
- OWASP Injection Prevention Cheat Sheet
- OWASP SQL Injection Prevention Cheat Sheet
- OWASP ASVS V5 Input Validation and Encoding
- OWASP Testing Guide
- PortSwigger Web Security Academy