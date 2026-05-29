<!--
SPDX-FileCopyrightText: 2026 Contributors to the OpenSTEF project <openstef@lfenergy.org>

SPDX-License-Identifier: MPL-2.0
-->

# How to Contribute

We'd love to accept your patches and contributions to this project. There are
just a few small guidelines you need to follow before making a change.


## Filing bugs and change requests

You can file bugs against and change requests for the project via GitHub issues. Consult [GitHub Help](https://docs.github.com/en/free-pro-team@latest/github/managing-your-work-on-github/creating-an-issue) for more
information on using GitHub issues.

For more information on how to get help, report bugs, or suggest features, please refer to [SUPPORT.md](./SUPPORT.md).

## Community Guidelines

This project follows the following [Code of Conduct](https://github.com/OpenSTEF/.github/blob/main/CODE_OF_CONDUCT.md).

## Style guide

This project follows [PEP 8](https://peps.python.org/pep-0008/) as enforced by [Ruff](https://docs.astral.sh/ruff/). For the full style guide, including naming conventions, type hints, documentation standards, and more, please refer to the [OpenSTEF Code Style Guide](https://openstef.github.io/openstef/contribute/code_style_guide.html).

Key formatting rules:

* Maximum line length: 88 characters
* Indentation: 4 spaces (no tabs)
* Double quotes for strings
* Trailing commas required in multi-line constructs
* Import sorting: alphabetical within sections

Most style issues are automatically handled by our development tools. Run `poe all` to fix formatting and catch style violations automatically.

## Git branching

This project uses the [GitHub flow Workflow](https://guides.github.com/introduction/flow/) and branching model. The `main` branch always contains the latest release. New feature branches are branched from `main`. When a feature is finished it is merged back into `main` via a [Pull Request](https://docs.github.com/en/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests#:~:text=Pull%20requests%20let%20you%20tell,merged%20into%20the%20base%20branch.).

The following convention will be used for feature branches: `feature/description`. For example: `feature/unittest-all-schedulers`.

The following convention will be used for bugfix branches: `bugfix/description`. For example: `bugfix/use-training-days`.

## Signing the Developer Certificate of Origin (DCO)
This project utilize a Developer Certificate of Origin (DCO) to ensure that each commit was written by the author or that the author has the appropriate rights necessary to contribute the change. Specifically, we utilize [Developer Certificate of Origin, Version 1.1](http://developercertificate.org/),  which is the same mechanism that the Linux® Kernel and many other communities use to manage code contributions. The DCO is considered one of the simplest tools for sign-offs from contributors as the representations are meant to be easy to read and indicating signoff is done as a part of the commit message.

This means that each commit must include a DCO which looks like this:

`Signed-off-by: Joe Smith <joe.smith@email.com>`

The project requires that the name used is your real name and the e-mail used is your real e-mail. Neither anonymous contributors nor those utilizing pseudonyms will be accepted.

There are other great tools out there to manage DCO signoffs for developers to make it much easier to do signoffs:
* Git makes it easy to add this line to your commit messages. Make sure the `user.name` and `user.email` are set in your git configs. Use `-s` or `--signoff` to add the Signed-off-by line to the end of the commit message.
* [GitHub UI integrations]( https://github.com/scottrigby/dco-gh-ui ) for adding the signoff automatically to commits made with the GitHub browser UI
* Additionally, it is possible to use shell scripting to automatically apply the sign-off. For an example for bash to be put into a `.bashrc` file, see [the documentation provided by LF Energy](https://wiki.lfenergy.org/display/HOME/Contribution+and+Compliance+Guidelines#ContributionandComplianceGuidelines-Contributionsignoff). 
* Alternatively, you can add `prepare-commit-msg hook` in .git/hooks directory. For an example, see [here](https://github.com/Samsung/ONE-vscode/wiki/ONE-vscode-Developer's-Certificate-of-Origin).

## Code reviews

All patches and contributions, including patches and contributions by project members, require review by one of the maintainers of the project. We
use GitHub pull requests for this purpose. Consult the pull request process below and the
[GitHub Help](https://help.github.com/articles/about-pull-requests/) for more
information on using pull requests

## Pull Request Process
Contributions should be submitted as Github pull requests. See [Creating a pull request](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request) if you're unfamiliar with this concept.

The process for a code change and pull request you should follow:

1. Create a topic branch in your local repository, following the naming format
`feature/description` or `bugfix/description`. For more information see the Git branching guideline.
1. Make changes, compile, and test thoroughly. Ensure any install or build dependencies are removed before the end of the layer when doing a build. Code style should match existing style and conventions, and changes should be focused on the topic the pull request will be addressed. For more information see the style guide.
1. Push commits to your fork.
1. Create a Github pull request from your topic branch.
1. Signing the Developer Certificate of Origin (DCO)
1. Pull requests will be reviewed by one of the maintainers who may discuss, offer constructive feedback, request changes, or approve
the work. For more information see the Code review guideline.
1. Upon receiving the sign-off of one of the maintainers you may merge your changes, or if you
   do not have permission to do that, you may request a maintainer to merge it for you.

## Release Process
Every new Pull Request merged to main triggers a new automatic github release with bumped patch version (0.0.**1**) and consequently a new pypi release and new published documentation. If needed, a manual release can be done:
1. Major (**1**.0.0) or minor (0.**1**.0) version need to be bumped besides patch version: do this yourself in the feature branch in the setup.py.
2. Pre-release needs to be made: do this yourself in the feature branch with new pre-release version in setup.py and manual pre-release in github GUI.

## How to report a security vulnerability

Please refer to [SECURITY.md](./SECURITY.md) for details on reporting a security vulnerability.

## Attribution

This Contributing.md is adapted from Google
available at
https://github.com/google/new-project/blob/master/docs/contributing.md
