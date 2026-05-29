<!--
SPDX-FileCopyrightText: 2025 Contributors to the OpenSTEF project <openstef@lfenergy.org>

SPDX-License-Identifier: MPL-2.0
-->

# Security Policy

## Supported Versions

This project uses versioned releases.

**Bug fixes and security patches are only applied to the latest release.
No effort will be spent on backporting fixes to previous versions.**

| Version            | Supported |
| ------------------ | --------- |
| Latest release     | ✅        |
| All other releases | ❌        |

Python libraries in this project are only released for Python 3.12 and above.

## Security Considerations

OpenSTEF is a machine learning framework for short-term energy forecasting. It provides pipelines for data preprocessing, feature engineering, model training, and evaluation. The library itself does not handle network connections, authentication, or user-facing services.

### Dependencies and Supply Chain

The primary security risks for OpenSTEF are **outdated dependencies** and **supply chain attacks**. OpenSTEF depends on third-party libraries such as XGBoost, LightGBM, scikit-learn, and pandas. We actively monitor and update these dependencies to mitigate known vulnerabilities.

### Deployment Responsibility

OpenSTEF is designed to be deployed in a **secured cloud environment**. Securing the deployment infrastructure (network, authentication, access control, etc.) is the responsibility of the user. General cloud development security best practices apply.

### Recommendations

- Always use the **latest version** of OpenSTEF to benefit from the most recent security patches.
- Keep your Python environment and all dependencies up to date.
- Follow your organization's security best practices when deploying OpenSTEF in production.

## Reporting a Vulnerability

If you discover a security vulnerability in OpenSTEF, please report it responsibly.

**Please use GitHub's [Private Vulnerability Reporting](https://github.com/OpenSTEF/openstef/security/advisories) to report vulnerabilities.** This ensures the report is handled confidentially and allows us to coordinate a fix before public disclosure.

The maintainers of the project will actively monitor reports and respond at the earliest opportunity.
