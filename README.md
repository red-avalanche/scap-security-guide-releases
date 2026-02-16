# SCAP Security Guide Mirror

## What is the SCAP Security Guide?

The **SCAP Security Guide (SSG)** is a dynamic open source project that provides security policies for various platforms and compliance frameworks. It serves as a bridge between generalized policy requirements (like NIST 800-53, DISA STIGs, and CIS Benchmarks) and specific implementation guidelines for operating systems and applications.

These files contain:
- Security benchmarks and configuration profiles
- Machine-readable SCAP content for automated compliance checking
- Human-readable guidance for secure system configuration
- Practical hardening advice linked to government requirements where applicable

## Using with OpenSCAP (oscap)

The `oscap` command-line utility allows you to scan systems for compliance using the SCAP Security Guide content:

```bash
# Scan your system against a specific profile
oscap xccdf eval --profile standard --report report.html scap-security-guide-content.xml

# Generate a human-readable security guide
oscap xccdf generate guide --profile standard scap-security-guide-content.xml > guide.html
```

**Key capabilities**:
- Scan local systems for configuration compliance
- Validate security compliance content
- Generate reports and guides in HTML or plain text formats
- Evaluate DISA STIGs and other security content

> **Important**: The `oscap` tool itself doesn't provide security policies - you must obtain the rule sets from a separate package like the SCAP Security Guide. Performing a configuration compliance scan doesn't guarantee system compliance, but provides actionable guidance toward meeting security requirements.

## Disclaimer

**All content in this repository is not original** and is automatically sourced from the **[ComplianceAsCode/content](https://github.com/ComplianceAsCode/content) GitHub repository**. This repository serves only as a mirror and version tracker for the official SCAP Security Guide release artifacts.

The ComplianceAsCode project is a community-driven effort where "many organizations interested in computer security share their efforts and collaborate on security policies" used across military, healthcare, aviation, telecom, and other industries.

## Purpose of This Repository

This repository exists to:

1. **Provide direct access** to the official SCAP Security Guide release artifacts without having to download the entire .zip file and unpack it

2. **Track changes between versions** directly in Git, allowing users to:
   - See exactly what changed between releases
   - Review historical versions
   - Create diffs between security content versions
   - Maintain a linear history of official releases

3. **Verify integrity** through automatically generated SHA256 checksum files for all repository contents

Each commit corresponds to a single official release version (not pre-releases), with the commit tagged using the exact version number from the ComplianceAsCode project. This structure enables reliable version tracking and content verification for security automation workflows.
