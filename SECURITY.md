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

OpenSTEF is a machine learning framework for short-term energy forecasting. It
provides pipelines for data preprocessing, feature engineering, model training,
and evaluation. The library itself does not handle network connections,
authentication, or user-facing services.

### Dependencies and Supply Chain

The primary security risks for OpenSTEF are **outdated dependencies** and
**supply chain attacks**. OpenSTEF depends on third-party libraries such as
XGBoost, LightGBM, scikit-learn, and pandas. We actively monitor and update
these dependencies to mitigate known vulnerabilities.

### Deployment Responsibility

OpenSTEF is designed to be deployed in a **secured cloud environment**. Securing
the deployment infrastructure (network, authentication, access control, etc.) is
the responsibility of the user. General cloud development security best practices
apply.

### Recommendations

- Always use the **latest version** of OpenSTEF to benefit from the most recent
  security patches.
- Keep your Python environment and all dependencies up to date.
- Follow your organization's security best practices when deploying OpenSTEF in
  production.

## Reporting a Vulnerability

Please report security vulnerabilities privately via GitHub's
[Private Vulnerability Reporting](https://github.com/OpenSTEF/openstef/security/advisories/new)
or by emailing <openstef@lfenergy.org>. Do not open public issues for
security-sensitive reports. The maintainers actively monitor reports and respond
at the earliest opportunity, coordinating a fix before public disclosure.

## Verifying releases

Every OpenSTEF release is cryptographically signed with
[Sigstore](https://www.sigstore.dev/) **keyless** signing. There is no
long-lived private key: each signature uses an ephemeral key bound to the
GitHub Actions release workflow's OIDC identity, with the signing certificate
issued by Fulcio and recorded in the public Rekor transparency log. There is no
public key to download; verification proves the artifact was published by our
release workflow.

Two channels are signed:

- **PyPI**: every distribution carries a [PEP 740](https://peps.python.org/pep-0740/)
  attestation, displayed and verified by PyPI on upload.
- **GitHub Releases**: each artifact ships with a `.sigstore.json` bundle for
  offline verification.

### Verify a PyPI download

`pip` verifies attestations automatically when downloading from PyPI. To check
explicitly:

```bash
pip download openstef --no-deps -d ./dist
uvx pypi-attestations verify pypi --repo OpenSTEF/openstef dist/openstef-*.whl
```

### Verify a GitHub Release artifact

Download the artifact and its `.sigstore.json` bundle from the
[Releases page](https://github.com/OpenSTEF/openstef/releases), then:

```bash
uvx sigstore verify identity \
    --cert-identity-regexp 'release-v4.yaml@refs/tags/v4' \
    --cert-oidc-issuer https://token.actions.githubusercontent.com \
    openstef-*.whl
```

A successful run confirms the artifact was signed by the OpenSTEF release
workflow. The signing private key is ephemeral and never stored, so it is never
present on PyPI, GitHub Releases, or any distribution site.

## Security assurance case

OpenSTEF is a forecasting library. Its security goal is that users can install
and run genuine, unmodified releases, and that known vulnerabilities in its
dependencies are surfaced and fixed promptly. OpenSTEF does not store user
credentials and does not operate a network service; runtime hardening of any
service that embeds OpenSTEF is the responsibility of the deploying application.
The security of the data supplied to OpenSTEF, including protection against data
poisoning and other downstream data-integrity issues, rests with the user; our
responsibility is to keep the package itself as secure as we can, as described
below.

The threats we address and how we address them:

- **Tampered release or supply-chain injection.** Every release is signed with
  keyless Sigstore and carries a PEP 740 attestation on PyPI, verifiable as
  described above. GitHub Actions are pinned to commit SHAs, and workflow tokens
  follow least privilege (`contents: read` by default).
- **Vulnerable dependencies.** Dependabot tracks updates, including a
  security-advisory group exempt from the release cooldown, against a pinned
  lockfile that CI checks with `uv lock --check`.
- **Defects in project code.** Static analysis runs on every change: CodeQL
  code scanning, SonarCloud, ruff (the full rule set), and the `ty` type checker
  with all rules as errors. The test suite runs with an 80% statement-coverage
  gate.
- **Malformed input.** Untrusted inputs (configuration, dataset schemas) are
  validated at the boundary with pydantic models before use.

Vulnerability reports are handled through the process above.
