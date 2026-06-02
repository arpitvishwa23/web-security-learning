# A03: Software Supply Chain Failures

## Introduction

Modern applications are built using many third-party components such as libraries, frameworks, APIs, packages, and development tools. These components help developers build software faster, but they can also introduce security risks if they are not properly managed.

Software Supply Chain Failures occur when vulnerabilities, misconfigurations, or malicious changes are introduced through software dependencies, development tools, build systems, or deployment pipelines.

In OWASP Top 10:2025, this category highlights the growing risks associated with modern software development and the increasing dependence on external components.

---

## Understanding Software Supply Chain Failures

A software supply chain includes everything involved in creating and delivering software, such as:

- Open-source libraries
- Third-party packages
- Frameworks
- Build tools
- CI/CD pipelines
- Code repositories
- Container images
- Cloud services

If any part of this chain is compromised, attackers may be able to affect the final application.

Unlike traditional vulnerabilities, supply chain attacks often target trusted components that organizations rely on every day.

---

## Common Causes

### Outdated Components

Using old or unsupported software components can expose applications to known vulnerabilities.

### Untracked Dependencies

Many projects use dependencies that themselves depend on other packages. These are known as transitive dependencies. If they are not monitored, vulnerabilities can go unnoticed.

### Untrusted Sources

Downloading packages or tools from unofficial sources increases the risk of installing malicious software.

### Weak Change Management

Poor tracking of changes in repositories, build systems, and development tools can make it difficult to identify security issues.

### Insecure CI/CD Pipelines

If attackers gain access to build pipelines, they may inject malicious code into software before deployment.

### Lack of Regular Updates

Delaying updates and patches leaves applications exposed to publicly known vulnerabilities.

---

## Example Attack Scenarios

### Scenario 1: SolarWinds Attack

In 2019, attackers compromised the SolarWinds software build process and inserted malicious code into trusted updates. Thousands of organizations installed the compromised update, leading to one of the largest supply chain attacks in history.

### Scenario 2: Malicious Software Updates

A trusted software vendor is compromised, and attackers distribute malicious updates to customers. Because the updates come from a trusted source, many organizations install them without suspicion.

### Scenario 3: Compromised Open-Source Package

Attackers publish a malicious version of a popular package. Developers unknowingly install it, allowing attackers to steal sensitive information or gain access to systems.

### Scenario 4: Vulnerable Third-Party Library

An application uses a library with a known security vulnerability. Attackers exploit the weakness to execute malicious code or gain unauthorized access.

Examples include:

- Log4Shell (CVE-2021-44228)
- Apache Struts RCE (CVE-2017-5638)

---

## Impact

Software Supply Chain Failures can lead to:

- Remote code execution
- Data breaches
- Malware infections
- Unauthorized system access
- Supply chain compromise
- Financial losses
- Reputation damage
- Large-scale attacks affecting multiple organizations

Since compromised components are often trusted, these attacks can be difficult to detect.

---

## Prevention and Mitigation

### Maintain an SBOM

A Software Bill of Materials (SBOM) helps track all software components and dependencies used within an application.

### Monitor Dependencies

Regularly monitor both direct and transitive dependencies for security vulnerabilities.

### Use Trusted Sources

Only download packages, libraries, and tools from official and trusted sources.

### Keep Components Updated

Apply security patches and updates as soon as possible based on risk assessment.

### Secure CI/CD Pipelines

Protect build servers and deployment pipelines using:

- Multi-factor authentication (MFA)
- Access controls
- Audit logging
- Separation of duties

### Review Changes

Track modifications to:

- Code repositories
- Build systems
- Developer tools
- Infrastructure configurations

### Remove Unused Components

Unused libraries and packages increase the attack surface and should be removed whenever possible.

### Conduct Regular Security Scans

Use dependency scanning and software composition analysis tools to identify vulnerable components.

---

## Key Takeaways

- Modern applications heavily rely on third-party components and tools.
- A weakness in any part of the software supply chain can affect the final application.
- Outdated, vulnerable, or malicious dependencies are common causes of supply chain failures.
- Regular monitoring, patching, and dependency management are essential for reducing risk.
- Securing development tools and CI/CD pipelines is just as important as securing application code.

---

## References

- OWASP Top 10:2025
- OWASP Dependency-Track
- OWASP Dependency Check
- OWASP CycloneDX
- National Vulnerability Database (NVD)
- MITRE CVE Database