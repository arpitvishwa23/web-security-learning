# A04: Cryptographic Failures

## Introduction

Cryptography is one of the most important security mechanisms used to protect sensitive information. It helps secure data such as passwords, financial records, personal information, and business data from unauthorized access.

Cryptographic Failures occur when applications fail to properly protect sensitive data through encryption, use weak cryptographic algorithms, implement poor key management practices, or expose sensitive information during transmission or storage.

In OWASP Top 10:2025, Cryptographic Failures remain one of the most significant security risks because they directly impact the confidentiality and integrity of data.

---

## Understanding Cryptographic Failures

Cryptography is commonly used to protect:

- Data in transit
- Data at rest
- User passwords
- Authentication tokens
- Sensitive business information

A cryptographic failure occurs when encryption is missing, weak, outdated, or incorrectly implemented.

Some common examples include:

- Using HTTP instead of HTTPS
- Storing passwords in plain text
- Using weak hashing algorithms
- Hardcoding encryption keys
- Using predictable random values

---

## Common Causes

### Weak Encryption Algorithms

Older algorithms such as MD5 and SHA-1 are considered insecure and should not be used to protect sensitive data.

### Poor Key Management

Encryption keys may be:

- Hardcoded in source code
- Stored insecurely
- Reused across systems
- Never rotated

If attackers gain access to these keys, encrypted data can be easily decrypted.

### Lack of HTTPS

Applications that do not enforce HTTPS expose sensitive information to attackers monitoring network traffic.

### Weak Password Storage

Passwords stored using weak hashing algorithms can be cracked quickly using modern hardware and password-cracking tools.

### Predictable Random Values

Cryptographic operations rely on randomness. Weak random number generation can make encryption and authentication mechanisms vulnerable.

---

## Example Attack Scenarios

### Scenario 1: Insecure Data Transmission

A website allows users to log in over HTTP instead of HTTPS. An attacker connected to the same network captures usernames and passwords transmitted over the network.

### Scenario 2: Weak Password Hashing

An application stores passwords using MD5 without salting. After a database breach, attackers crack the passwords using rainbow tables.

### Scenario 3: Hardcoded Encryption Keys

A developer stores encryption keys directly in the application code. An attacker who gains access to the source code can use the keys to decrypt sensitive information.

### Scenario 4: Predictable Session Tokens

An application uses weak random number generation to create session tokens. Attackers can predict valid tokens and hijack user sessions.

---

## Impact

Cryptographic Failures can result in:

- Exposure of sensitive information
- Account compromise
- Identity theft
- Financial fraud
- Data breaches
- Compliance violations
- Loss of customer trust

Because cryptography is often the final layer of defense protecting sensitive data, failures in this area can have severe consequences.

---

## Prevention and Mitigation

### Encrypt Sensitive Data

Sensitive information should be encrypted both during transmission and while stored.

### Use Strong Cryptographic Algorithms

Use trusted algorithms such as:

- AES
- RSA
- SHA-256
- Argon2
- PBKDF2

Avoid outdated algorithms such as MD5 and SHA-1.

### Enforce HTTPS

All communication should use TLS 1.2 or higher to protect data in transit.

### Secure Key Management

- Store keys securely
- Rotate keys regularly
- Avoid hardcoding keys
- Use secure key management solutions

### Use Strong Password Hashing

Store passwords using:

- Argon2
- bcrypt
- scrypt
- PBKDF2

### Use Secure Random Number Generators

Cryptographic operations should use cryptographically secure random number generators (CSPRNGs).

### Regular Security Reviews

Review encryption implementations regularly to ensure they follow modern security standards and best practices.

---

## Key Takeaways

- Cryptographic Failures occur when sensitive data is not adequately protected.
- Weak encryption, poor key management, and insecure password storage are common causes.
- Sensitive data should always be encrypted both in transit and at rest.
- Modern cryptographic algorithms and secure key management practices should be used.
- Regular security reviews help identify and prevent cryptographic weaknesses.

---

## References

- OWASP Top 10:2025
- OWASP Cryptographic Storage Cheat Sheet
- OWASP Password Storage Cheat Sheet
- OWASP Transport Layer Protection Cheat Sheet
- NIST Cryptographic Standards