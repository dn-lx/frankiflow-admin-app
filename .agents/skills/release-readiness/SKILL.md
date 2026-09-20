---
name: release-readiness
description: Review the FrankiFlow Admin mobile release candidate for validation, permissions, configuration, observability and rollback readiness.
---

# Mobile release readiness

1. Confirm the release PR is `develop` to `main` and contains only intended changes.
2. Confirm TypeScript, Expo compatibility, dependency, Semgrep and Gitleaks checks passed.
3. Review application permissions, environment variables and Supabase configuration.
4. Build an Android release candidate and retain the APK briefly for review.
5. Verify core sign-in and administrative flows on the target form factors.
6. Confirm error reporting excludes credentials and customer data when Sentry is connected.
7. Record rollback steps and unresolved risks.
