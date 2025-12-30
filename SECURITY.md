# Security Policy

## Supported Versions

We actively support the following versions with security updates:

| Version | Supported          | End of Support |
| ------- | ------------------ | -------------- |
| 2.x.x   | :white_check_mark: | Current        |
| 1.x.x   | :white_check_mark: | December 2025  |
| < 1.0   | :x:                | Unsupported    |

## Reporting a Vulnerability

We take the security of PRSMTECH projects seriously. If you discover a security vulnerability, please follow these steps:

### How to Report

**DO NOT** open a public GitHub issue for security vulnerabilities.

Instead, please report security vulnerabilities via email:

**Email**: [admin@prsmtech.com](mailto:admin@prsmtech.com)

**Subject Line**: `[SECURITY] Brief description of vulnerability`

### What to Include

Please include the following information in your report:

1. **Description**: A clear description of the vulnerability
2. **Impact**: The potential impact of the vulnerability
3. **Affected Versions**: Which versions are affected
4. **Steps to Reproduce**: Detailed steps to reproduce the issue
5. **Proof of Concept**: Code, screenshots, or other evidence (if applicable)
6. **Suggested Fix**: Any recommendations for remediation (optional)

### Response Timeline

| Action | Timeline |
|--------|----------|
| Initial Response | Within 48 hours |
| Preliminary Assessment | Within 5 business days |
| Status Update | Every 7 days until resolved |
| Fix Implementation | Based on severity (see below) |

### Severity Levels

| Severity | Description | Target Resolution |
|----------|-------------|-------------------|
| Critical | Remote code execution, data breach, authentication bypass | 24-72 hours |
| High | Privilege escalation, significant data exposure | 7 days |
| Medium | Limited data exposure, XSS, CSRF | 30 days |
| Low | Minor information disclosure, DoS | 90 days |

## Bug Bounty Program

At this time, PRSMTECH does not operate a formal bug bounty program with monetary rewards.

However, we deeply appreciate security researchers who responsibly disclose vulnerabilities. Researchers who submit valid reports will receive:

- Public acknowledgment (with permission) in our security advisories
- A letter of appreciation for their contribution
- Consideration for early access to new features and beta programs

We are exploring the possibility of a formal bug bounty program in the future. Updates will be posted to this policy.

## Security Best Practices for Contributors

### Code Security

1. **Never commit secrets**: Use environment variables for API keys, tokens, and credentials
2. **Input validation**: Always validate and sanitize user input
3. **Parameterized queries**: Use prepared statements to prevent SQL injection
4. **Dependency management**: Keep dependencies updated and audit regularly
5. **Error handling**: Never expose stack traces or sensitive error details to users

### Authentication & Authorization

1. Use strong password hashing (bcrypt, argon2)
2. Implement proper session management
3. Apply principle of least privilege
4. Use HTTPS for all connections
5. Implement rate limiting on authentication endpoints

### Data Protection

1. Encrypt sensitive data at rest and in transit
2. Minimize data collection and retention
3. Implement proper access controls
4. Log security-relevant events
5. Follow data protection regulations (GDPR, CCPA as applicable)

### Development Environment

1. Use `.gitignore` to exclude sensitive files
2. Never use production data in development
3. Implement pre-commit hooks for secret detection
4. Use separate credentials for each environment
5. Enable two-factor authentication on all accounts

## Security Updates

Security updates and advisories will be communicated through:

- GitHub Security Advisories
- Direct email notification to affected users (when applicable)
- Updates to this SECURITY.md file

## Contact

For security-related inquiries:

- **Email**: admin@prsmtech.com
- **Response Hours**: Monday-Friday, 9 AM - 6 PM EST

For non-security issues, please use the standard GitHub issue templates.

---

**PRSMTECH Security Policy v1.0**

*Last Updated: December 2024*
