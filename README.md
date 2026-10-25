# @nasustim/skills

Personal collection of reusable AI agent skills managed as a [Microsoft APM (Agent Package Manager)](https://github.com/microsoft/apm) package.

## Installation

### Install all skills

```bash
apm install nasustim/skills
```

Or add to your project's `apm.yml` (optionally pinned to a release tag `vYYYYMMDD(-n)?`):

```yaml
dependencies:
  apm:
    - nasustim/skills#v20261025
```

### Install an individual skill

```bash
apm install nasustim/skills/.apm/skills/lighthouse
```

Or in `apm.yml`:

```yaml
dependencies:
  apm:
    - nasustim/skills/.apm/skills/lighthouse#v20261025
```

## Automated Version Management with Renovate (Consumer Repos)

Releases are published automatically on push to `main` using datetime versioning (`vYYYYMMDD` or `vYYYYMMDD-n`). To automatically update pinned versions in a consuming repository's `apm.yml` with Renovate, add the following `customManagers` configuration:

```json
{
  "customManagers": [
    {
      "customType": "regex",
      "fileMatch": ["(^|/)apm\\.ya?ml$"],
      "matchStrings": [
        "-\\s+(?<depName>nasustim/skills)(?:/[^#\\s]+)?#(?<currentValue>v\\d{8}(?:-\\d+)?)"
      ],
      "datasourceTemplate": "github-releases",
      "versioningTemplate": "regex:^v(?<major>\\d{4})(?<minor>\\d{2})(?<patch>\\d{2})(?:-(?<build>\\d+))?$"
    }
  ]
}
```

## Included Skills

| Skill | Path | Description |
|-------|------|-------------|
| `lighthouse` | [`.apm/skills/lighthouse/SKILL.md`](.apm/skills/lighthouse/SKILL.md) | Run Google Lighthouse audits (Mobile and Desktop) against any URL or local preview server, summarize Core Web Vitals & category scores, and surface non-passing audits. |
