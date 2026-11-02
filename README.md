# madlink themes

The official theme catalog for **[madlink](https://github.com/madLinux7/madlink)**. Built-in themes and community creations, in one place.

- **[builtin.toml](builtin.toml)** — Core themes, maintained by the madlink project.
- **[community.toml](community.toml)** — themes submitted by the community. **Add yours here!**

## Submit your theme

1. Push your theme to a public GitHub or Codeberg repository.
2. Fork this catalog and add your entry to **`community.toml`**. Keep the existing `schema_version = 1`.
3. Open a pull request. **Only change your entry in `community.toml`.**

```toml
[my-theme]
name = "My Theme"
repo_url = "https://github.com/author/my-theme"
versions = [
    { theme_version = 1, commit = "0123456789abcdef0123456789abcdef01234567" },
]
```

- **`[my-theme]`** — your theme's unique slug.
- **`name`** — the display name.
- **`repo_url`** — the public repository URL on `github.com` or `codeberg.org`, without `.git`, credentials, query strings or fragments. Self-hosted instances are not supported.
- **`versions`** — positive integer versions paired with full **40-character commit hashes**.

Your `theme.toml` must match the entry's slug, `repo_url` (as `repository_url`) and `theme_version`. The manifest also requires `contract_version = 1` and one SemVer `madlink_min_version` such as `0.1.0`; ranges and the removed `version`, `madlink_version` and `short` fields are rejected. The slug determines the CSS/JavaScript prefix.

## Update your theme

Push the new theme commit, then submit another PR adding a higher version number to your entry.

**The highest listed number is current.** Keep older versions listed while they should remain available and eligible for Verified status.

Never assign an existing version number to a different commit or repository — even after removing it!

## Review

CI checks the catalog entry, theme source, licenses and rendered pages. Review artifacts are attached to the workflow run.

**Green checks alone do not approve a theme.** A maintainer reviews the source and rendered results, then merges the PR to accept it.

## Package presentation

Use an English `README.md` to describe the exact package; optional `README.de.md` supplies German text. Put optional `tags` and `screenshots` arrays after `license` and before `theme_version`, with at most six strings in each. Screenshot filenames refer to raster images directly in the repository root. An optional `[summary]` table provides an English short text and optional German text, each at most 160 visible characters. The [core theme contract](https://github.com/madLinux7/madlink/blob/main/docs/theme-contract.md) defines validation and image limits. Repository stars and the repository owner avatar are cached separately; they do not establish Verified status.
