# Security Policy

## Automated Security Scanning

This project has automated security scanning implemented to ensure dependencies remain secure and up-to-date.

### Features

#### 1. Automated Dependency Updates (Dependabot)

We use [GitHub Dependabot](https://docs.github.com/en/code-security/dependabot) to automatically:

- **Daily security scans**: Checks for known vulnerabilities in dependencies
- **Automatic PRs**: Creates pull requests for security updates
- **Grouped updates**: Minor and patch updates are grouped for easier review
- **Multi-package support**: Monitors both server (backend) and client (frontend) dependencies

#### 2. Security Scanning Workflows

Our [Security Scan workflow](.github/workflows/security-scan.yml) runs:

- **On every push** to main, feature, and test branches
- **On every pull request** to main
- **Daily at 6:00 AM UTC** (scheduled)
- **Manual trigger** available via GitHub Actions UI

#### 3. CodeQL Analysis

We use [GitHub CodeQL](https://codeql.github.com/) for advanced code security analysis:

- Detects security vulnerabilities in code
- Identifies potential security issues
- Runs on every push and PR

### Security Reports

#### Where to Find Reports

1. **Workflow Summary**: Each workflow run generates a detailed security report in the Actions tab
2. **Security Tab**: [Security Advisories](../../security/advisories) for vulnerability alerts
3. **Dependabot Alerts**: [Security alerts](../../security/dependabot) for dependency vulnerabilities
4. **Code Scanning**: [Code scanning results](../../security/code-scanning) from CodeQL

#### Report Contents

Each security scan includes:

- ✅ Vulnerability count (npm audit)
- 📦 Outdated packages list
- 🔒 CodeQL security analysis results
- 📊 Summary dashboard

### Automated PRs

Dependabot automatically creates PRs for:

- 🔴 **Critical security vulnerabilities**: Immediate PR creation
- 🟠 **High severity vulnerabilities**: PR within 24 hours
- 🟡 **Medium/low severity**: PR based on schedule
- 📦 **Dependency updates**: Daily checks for newer versions

### Labels

Automated PRs include labels:

- `dependencies` - Dependency updates
- `backend` / `frontend` - Component affected
- `ci/cd` - GitHub Actions updates

### Manual Security Review

To manually trigger a security scan:

1. Go to [Actions](../../actions/workflows/security-scan.yml)
2. Click "Run workflow"
3. Select the branch to scan
4. Click "Run workflow"

### Supported Versions

| Version | Supported          |
| ------- | ------------------ |
| main    | :white_check_mark: |
| feature/* | :white_check_mark: |
| other   | :x: (security scans only) |

### Reporting a Vulnerability

If you discover a security vulnerability, please report it responsibly:

1. **Do NOT** open a public issue
2. Email the maintainers directly or use [GitHub Security Advisories](../../security/advisories/new)
3. Include:
   - Description of the vulnerability
   - Steps to reproduce
   - Potential impact
   - Suggested fix (if available)

We aim to respond within 48 hours and provide a fix within 7 days for critical vulnerabilities.

### Configuration Files

| File | Purpose |
| ---- | ------- |
| `.github/dependabot.yml` | Dependabot configuration |
| `.github/workflows/security-scan.yml` | Security scanning workflow |
| `SECURITY.md` | This security policy |

### Monitoring Dashboard

For a comprehensive view of the project's security posture:

1. **GitHub Security Tab**: [Security Overview](../../security)
2. **Dependabot Alerts**: [Dependency alerts](../../security/dependabot)
3. **Code Scanning**: [CodeQL results](../../security/code-scanning)
4. **Secret Scanning**: [Secret alerts](../../security/secret-scanning)

### Best Practices

- ✅ Review and merge Dependabot PRs promptly
- ✅ Keep dependencies up to date
- ✅ Monitor security alerts regularly
- ✅ Follow security best practices in code
- ❌ Don't ignore security warnings
- ❌ Don't delay critical security updates

---

**Last Updated**: 2026-04-01

**Maintainer**: EDOHWARES

**Related Issues**: [#79](../../issues/79)