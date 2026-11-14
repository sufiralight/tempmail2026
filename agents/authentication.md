# Authentication

Use Laravel's guards, hashing, password broker, signed verification URLs, and session controls where applicable. Maintain the [account flows](../docs/authentication.md) with explicit guest, authenticated, verified, or password-confirmed access according to each action.

Assign ordinary privileges server-side at registration. The first Super Admin is created only through the authorized installer. Integrate the named login route with the /setup-complete handoff. The installer session carries no authenticated identity. Enforce administrator abilities on every privileged request through [authorization](../docs/authorization.md). Regenerate session IDs at login, invalidate the session and regenerate the CSRF token at logout, and require recent password confirmation for sensitive actions. Rate-limit login and recovery flows, avoid account enumeration, and test rejected requests as well as successful ones.

Use the shared password strength component for new-password and confirmation fields. Keep its client-side estimate independent of the server policy. Gate privileged routes with verified middleware where needed and keep resend, notice, and logout available to unverified accounts.

The authorized installer records the first Super Admin's initial email as verified during account creation. Public registration and later email changes use signed email verification.
