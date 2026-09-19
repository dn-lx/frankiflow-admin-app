# FrankiFlow Admin App agent guidance

## Branch and release policy

Use `develop` as the integration branch. Start implementation work from `develop` on a focused `feature/*`, `fix/*`, or `chore/*` branch.

Before any branch, PR, release, hotfix, deployment, or production operation, read and follow [Release Workflow](.agents/skills/release-workflow/SKILL.md).

The production rule is strict: **only this repository's `develop` branch may merge into `main`**. A `develop → main` production PR requires the `production-approved` label and required checks. Never merge a feature/fix/chore branch directly into `main`, never push directly to `main`, and never force-push `main`.

## Application boundaries

- This is the Expo/React Native administration app for FrankiFlow and FrankiHolz.
- Keep Supabase service-role, Stripe secret, database, signing, and other privileged credentials out of the client.
- Preserve server-side authorization and existing Supabase/RLS boundaries.
- Keep iOS bundle identifier and Android application ID stable unless the user explicitly requests a migration.
- Reuse existing application architecture and pinned dependencies before adding new frameworks or libraries.

## Verification

For application code changes, run at least:

```text
npm run typecheck
npm run doctor
```

Use the existing GitHub Android workflow for APK/build verification and emulator launch smoke tests when Android behavior changes. For iOS-specific behavior, use an iOS simulator or EAS/device testing when available and report any limitation clearly.

For release work, follow the stricter release checks in the Release Workflow skill.

## Testing and security efficiency

Before changing CI, adding tests, reviewing release readiness, or choosing test scope, read and follow [Quality Gates](.agents/skills/quality-gates/SKILL.md). Use fast validation for ordinary PRs and reserve the heavier release matrix for `develop → main`.
