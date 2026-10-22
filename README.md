# madlink theme catalog

This repository contains data, not executable review tools. No catalog releases or release tags exist. Madlink reads `builtin.toml` and `community.toml` from the same exact protected main-branch commit.

## Submit or update a theme

Fork this repository and change only your entry in `community.toml`. Open a pull request. Do not add scripts, workflows, checksums or review records. Theme repositories contain only theme files, README and license evidence.

```toml
schema_version = 1

[my-theme]
name = "My Theme"
repo_url = "https://github.com/author/my-theme"
versions = [
    { version = 1, commit = "0123456789abcdef0123456789abcdef01234567" },
]
```

`theme.json` must have the same slug, repository_url and positive integer version. The largest listed version is current regardless of array order. Strings, floats, duplicate slugs/versions and abbreviated commits are rejected. Never reassign a version to another commit or repository, including versions removed in the past. CI checks the complete protected catalog history. Removing a version withdraws its offer and Verified status; installed files are never deleted or downgraded automatically. Authors maintain their entries and license evidence; maintainers may remove unsafe or abandoned versions after documented review.

Aviditas, Humilis and Aura are mandatory official builtins with reserved slugs and fixed repositories. Only maintainers edit `builtin.toml`. Local themes remain usable without catalog approval.

## Review and trust

The workflow reads the checker digest and workflow from the trusted PR base, never from candidate code. All parsing, history, package and browser logic lives in the tested Core checker image. Candidate TOML and commit archives are data. Archives must match Git's commit-bound file inventory. PHP/Blade, CSS/JS, license evidence and isolated rendering are checked without network, secrets, write tokens or a host Docker socket in the execution container.

Maintainers document source and browser acceptance directly on the PR for the exact commit and generated artifacts. Human approval is the deliberate maintainer merge, never automatic merge. Branch protection must require PRs and the `theme-package-checks` check, require code-owner approval for protected review configuration, dismiss stale approvals, and prohibit force pushes and deletion. Core checker changes receive separate trusted review before a new image digest is adopted.

## Publication status

The TOML transition is prepared locally. `checker-image.txt` pins the tested TOML checker by its verified public registry digest. The image revision matches Core commit `8c9dfc45f74a042bb979dbb84db34fa97e88ef16`. New theme commits must also be pushed before online checks can pass. Step 15 stays open until real PR, branch-protection and commit-download acceptance is recorded in the Core release checklist.
