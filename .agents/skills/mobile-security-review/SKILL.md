---
name: mobile-security-review
description: Review FrankiFlow Admin authentication, local storage, device permissions and Supabase trust boundaries.
---

# Mobile security review

- Treat the application bundle and device storage as untrusted client environments.
- Keep service-role keys and privileged decisions off the device.
- Verify every protected operation is authorized by RLS, RPC or Edge Function logic.
- Store the minimum session and cached customer data; check logout and account-switch cleanup.
- Request only required device permissions and explain their user-visible purpose.
- Exclude credentials, personal data and uploaded file contents from logs and analytics.
- Test an allowed request and a denied cross-user request when a safe local backend is available.
