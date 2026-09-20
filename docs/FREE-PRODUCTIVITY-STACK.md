# Free development productivity stack

The repository now uses weekly Dependabot updates and a `develop` quality workflow covering TypeScript, Semgrep, Gitleaks and production dependency auditing.

Account-level services remain opt-in:

1. Create a Sentry React Native project and store its DSN in the build environment. Keep PII and replay disabled and verify one synthetic event.
2. Use PostHog only for allowlisted product events or feature flags. Do not capture customer form values or uploaded content.
3. Configure CodeRabbit to review pull requests into `develop` while the repository qualifies for its public/open-source free plan.
4. Connect Context7 in the coding client for current Expo, React Native and Supabase documentation.
5. Use Appetize only when the account has an adequate free allowance; physical-device and local emulator tests remain the default.

Expo/EAS store builds, application-store accounts and production payment services are not guaranteed to be free and are outside this repository-only activation.
