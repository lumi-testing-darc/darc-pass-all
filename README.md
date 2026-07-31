# darc-pass-all

DARC control fixture. Configured so every GitHub-scanned control resolves to **pass**.

| Control | Expected | Why |
|---|---|---|
| SD-1.01 branch protection | pass | ruleset on `main` requires a PR with 1 approval and blocks force pushes |
| SD-1.02 signed commits | pass | ruleset carries `required_signatures` |
| SD-1.03 secret scanning | pass | secret scanning enabled |
| SD-1.04 local secret hooks | pass | `.pre-commit-config.yaml` at the repo root |
| SD-1.05 no secrets in source | pass | no open secret-scanning alerts |
| SY-1.02 registry-only deps | pass | every `resolved` in `package-lock.json` points at registry.npmjs.org |
| SY-1.03 version pinning | pass | `package.json` ships with `package-lock.json` |
| SY-1.04 dependency scanning | pass | Dependabot alerts on, `.github/dependabot.yml` committed |
| SY-1.05 pinned CI actions | pass | every `uses:` is a 40-character commit SHA |
