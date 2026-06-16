<!--
SPDX-FileCopyrightText: 2017-2025 Contributors to the OpenSTEF project <openstef@lfenergy.org>

SPDX-License-Identifier: MPL-2.0
-->

# How to Contribute

We'd love to accept contributions to this project in any form.
You do not need to be a forecasting or energy systems expert to make a contribution.
There are just a few small guidelines you need to follow before making a change.

## Ways to Contribute

Contribution does not necessarily mean committing code. We recognize different levels of contribution in increasing order of dedication:

1. Test and use the library — give feedback on the user experience or suggest new features
2. Report bugs
3. Improve documentation — fix typos, clarify docstrings, write examples or tutorials
4. Fix bugs or implement features — see [Pull Request Process](#pull-request-process)
5. Participate in the community — join our four-weekly co-coding meetings or Slack discussions

A good place to start is to look at issues with the [`good first issue`](https://github.com/OpenSTEF/openstef/labels/good%20first%20issue) label.

## Filing Bugs and Change Requests

You can file bugs and change requests via [GitHub Issues](https://github.com/OpenSTEF/openstef/issues). Consult [GitHub Help](https://docs.github.com/en/free-pro-team@latest/github/managing-your-work-on-github/creating-an-issue) for more information on using GitHub issues.

## Community Guidelines

This project follows the [Code of Conduct](https://github.com/OpenSTEF/.github/blob/main/CODE_OF_CONDUCT.md).

## Getting Help

- **Slack**: [LF Energy Slack workspace](https://slack.lfenergy.org/) (#openstef channel)
- **Issues**: [GitHub Issues](https://github.com/OpenSTEF/openstef/issues)
- **Email**: openstef@lfenergy.org
- **Community meetings**: Join our four-weekly co-coding sessions

## Style Guide

OpenSTEF uses [Ruff](https://docs.astral.sh/ruff/) to enforce Python code style and formatting. If the code format is not complying, the pipeline will fail and the pull request will be blocked.

Run `poe all` to automatically check and fix formatting, linting, and type issues before committing. For full details on conventions, see the [style guide](https://openstef.github.io/openstef/contribute/code_style_guide.html).

## Git Branching

This project uses the [GitHub flow](https://guides.github.com/introduction/flow/) branching model. The `main` branch always contains the latest release. Feature branches are created from `main` and merged back via a Pull Request.

In case of a major version release with new features and/or breaking changes, a temporary `release/` branch may be created to hold all the changes until they are merged into `main`.

### Branch naming

Use descriptive names following these patterns:

| Type | Pattern | Example |
|------|---------|---------|
| New feature | `feat/<issue>-<description>` | `feat/123-add-transformer-model` |
| Bug fix | `fix/<issue>-<description>` | `fix/456-handle-missing-weather-data` |
| Documentation | `docs/<issue>-<description>` | `docs/789-improve-installation-guide` |
| Refactoring | `refactor/<description>` | `refactor/cleanup-feature-engineering` |
| Performance | `perf/<description>` | `perf/optimize-forecasting-pipeline` |

Include the GitHub issue number when one is available.

## Commit Message Guidelines

OpenSTEF uses [Conventional Commits](https://www.conventionalcommits.org/) for structured commit messages. This enables automated changelog generation and semantic versioning.

**Format:** `<type>[optional scope]: <description>`

**Types:** `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`

**Examples:**

```bash
git commit -m "feat(models): add transformer-based forecasting model"
git commit -m "fix(validation): handle missing weather data gracefully

Fixes #456"
```

**Guidelines:**

- Use the imperative mood ("Add feature" not "Added feature")
- Keep the first line under 50 characters
- Reference issues with "Closes #123" or "Fixes #456"
- Use `!` after the type to indicate breaking changes (e.g. `feat!:`)

## Signing the Developer Certificate of Origin (DCO)

This project uses a [Developer Certificate of Origin, Version 1.1](http://developercertificate.org/) to ensure that each commit was written by the author or that the author has the appropriate rights to contribute the change.

Each commit must include a sign-off line:

```
Signed-off-by: Joe Smith <joe.smith@email.com>
```

The project requires your real name and real email address. Anonymous contributions and pseudonyms are not accepted.

**How to sign off:**

- Use `git commit -s` or `git commit --signoff` to add the line automatically (requires `user.name` and `user.email` to be set in your git config)
- [GitHub UI integration](https://github.com/scottrigby/dco-gh-ui) for browser-based commits
- Add a `prepare-commit-msg` hook in `.git/hooks/` — see [this example](https://github.com/Samsung/ONE-vscode/wiki/ONE-vscode-Developer's-Certificate-of-Origin)

## Pull Request Process

Contributions should be submitted as GitHub pull requests. See [Creating a pull request](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request) if you're unfamiliar with this concept.

### Steps

1. [Fork the repository](https://docs.github.com/en/get-started/quickstart/fork-a-repo) to your own GitHub account
2. Clone your fork and create a feature branch (see [Git Branching](#git-branching))
3. Make your changes and add or update tests as needed
3. Run `poe all --check` and ensure all checks pass:
   - REUSE license compliance
   - Linting and formatting (ruff)
   - Type checking (pyright)
   - Tests (pytest)
   - Doctests
4. Sign your commits (see [DCO](#signing-the-developer-certificate-of-origin-dco))
5. Push your branch to your fork and open a pull request against `main` in the main repository, following these steps:
   1. Name your PR as `<type>: <title>` — e.g. `feat: add transformer-based forecasting model`
   2. Assign yourself to the PR
   3. Optionally request reviews from specific reviewers
   4. Add a label to the PR
   5. Link the relevant issue using "Closes #123" or "Fixes #456" (or select it in the Development section)
6. A maintainer will review and may request changes; upon approval you may merge (or request a maintainer to merge)

## REUSE Compliance

All files in the repository must be [REUSE compliant](https://reuse.software/). The pipeline automatically checks this; non-compliant files will block the pull request.

Check and fix compliance:

```bash
poe reuse            # check
poe reuse --fix      # auto-add missing headers
```

Alternatively, you can annotate a file manually:

```bash
reuse annotate \
  --copyright "Contributors to the OpenSTEF project <openstef@lfenergy.org>" \
  --license "MPL-2.0" \
  --fallback-dot-license <path_to_file>
```

### PR requirements

- `poe all --check` must pass (REUSE compliance, linting, formatting, type checking, tests, doctests)
- Code coverage must not decrease significantly
- Documentation must be updated for new features or changed behavior
- At least one maintainer approval is required

## Code Reviews

All patches and contributions, including those by project members, require review by one of the maintainers. We use GitHub pull requests for this purpose. Consult the [GitHub Help](https://help.github.com/articles/about-pull-requests/) for more information on pull requests.

## AI‑Assisted Contributions 
AI tools (e.g. LLMs or coding assistants) can be helpful when contributing to OpenSTEF. We welcome their use, as long as contributions remain clear, maintainable, and aligned with the following guidelines.

> **_NOTE:_**  These guidelines on using AI tools are still in development and will likely be extended over time.

### General expectations
- You remain fully responsible for your contribution, regardless of AI usage  
- You should understand and be able to explain the code you submit  
- Treat AI as a support tool, not as an autonomous contributor  

### Transparency
- If AI played a significant role, please disclose this in your pull request or commit message   (e.g. `Assisted-by: <tool name>`)  
- If AI is only used for fixing grammar or formatting, it does not need to be mentioned

### Quality standards
AI-assisted contributions must meet the same standards as any other contribution:

- Include tests where applicable  
- Update documentation if needed  
- Follow coding style and project conventions (`poe all`)  
- Clearly describe the problem and your approach  

Please make sure to review and validate all generated code. AI tools can produce incorrect, outdated, or insecure patterns.

### Scope and collaboration
- Prefer small, well-scoped pull requests that are easy to review  
- Engage with maintainers via issues if your change is substantial  
- Avoid submitting large or bulk-generated changes without prior discussion, as they may be rejected.

### Security and licensing
- Review generated code for potential vulnerabilities  
- Ensure compliance with project licensing and proper attribution of reused content  

### AI agents
Autonomous agents or bots are not typical contributors to this project. 
- If you plan to use an AI agent, discuss this with the maintainers first
- AI agents should identify themselves as AI  
- AI agents that generate low-value or disruptive contributions may be restricted or blocked

## Release Process

New releases are created manually by a maintainer from the `main` branch. There are no automatic releases triggered by merged pull requests.

## Attribution

This Contributing.md is adapted from the OpenSTEF contributing documentation.
