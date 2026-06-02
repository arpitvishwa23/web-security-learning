# A06: Insecure Design

## Introduction

Insecure Design refers to security weaknesses that originate during the planning and design phase of an application. Unlike coding mistakes or implementation errors, these issues exist because the necessary security controls were never considered or included in the design.

OWASP introduced this category to emphasize that security should not only focus on writing secure code but also on designing secure systems from the beginning. A perfectly written application can still be vulnerable if the underlying design is insecure.

---

## Understanding Insecure Design

Insecure Design occurs when developers and organizations fail to identify potential threats and security requirements during the development process.

A secure design should consider:

- Business requirements
- Security requirements
- Threats and attack scenarios
- User behavior
- Data protection requirements
- Access control needs

When these factors are ignored, vulnerabilities can become part of the application's architecture and cannot be easily fixed later.

---

## Difference Between Insecure Design and Insecure Implementation

Many people confuse insecure design with insecure implementation.

### Insecure Design

Security controls are missing from the system design itself.

**Example:** A password recovery system relies only on security questions that can be easily guessed.

### Insecure Implementation

The design is secure, but developers make mistakes while implementing it.

**Example:** Passwords are meant to be encrypted, but the developer stores them in plain text due to a coding error.

---

## Common Causes

### Lack of Threat Modeling

Developers fail to identify possible attack scenarios during the planning phase.

### Missing Security Requirements

Security requirements are not included when defining business requirements.

### Weak Business Logic

Applications allow users to perform actions that should be restricted or validated.

### Poor Access Control Design

The application does not properly define roles, permissions, or separation of responsibilities.

### Failure to Consider Abuse Cases

Designers focus only on normal user behavior and ignore how attackers might misuse the system.

---

## Example Attack Scenarios

### Scenario 1: Weak Password Recovery

An application uses simple security questions for account recovery.

An attacker finds personal information about the victim through social media and successfully resets the victim's password.

### Scenario 2: Business Logic Abuse

A movie ticket booking system allows users to reserve unlimited seats without payment.

Attackers reserve hundreds of seats, preventing legitimate customers from making bookings.

### Scenario 3: Scalper Bots

An e-commerce website does not include anti-bot protections.

Automated bots purchase large quantities of high-demand products within seconds, leaving genuine customers unable to buy them.

### Scenario 4: Excessive User Privileges

An application allows standard users to access functions that should only be available to administrators because proper privilege separation was never included in the design.

---

## Impact

Insecure Design can lead to:

- Unauthorized access
- Business logic abuse
- Data breaches
- Financial losses
- Account compromise
- Compliance violations
- Damage to reputation

Because these issues exist at the architectural level, fixing them often requires significant redesign and redevelopment effort.

---

## Prevention and Mitigation

### Perform Threat Modeling

Identify potential threats during the design phase before development begins.

### Define Security Requirements

Include security requirements alongside business requirements.

### Follow Secure Design Principles

Apply principles such as:

- Least Privilege
- Defense in Depth
- Fail Securely
- Separation of Duties

### Use Secure Design Patterns

Reuse proven and tested security architectures whenever possible.

### Review Business Logic

Analyze how attackers might misuse application functionality and design controls to prevent abuse.

### Conduct Security Reviews

Perform design reviews with security professionals before implementation begins.

### Integrate Security into the SDLC

Include security activities throughout the Software Development Life Cycle (SDLC).

### Validate Critical Workflows

Test both expected and unexpected user actions to ensure security controls work correctly.

---

## Key Takeaways

- Insecure Design focuses on flaws introduced during the planning and architecture phase.
- These issues cannot usually be fixed by simply correcting code.
- Threat modeling and secure design principles help reduce design-related vulnerabilities.
- Business logic flaws are often examples of insecure design.
- Security should be considered from the beginning of the software development lifecycle.

---

## References

- OWASP Top 10:2025
- OWASP Secure Design Principles Cheat Sheet
- OWASP SAMM
- The Threat Modeling Manifesto
- NIST Secure Software Development Framework (SSDF)