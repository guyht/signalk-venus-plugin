# Review: configurable MQTT username and certificate verification

**Owner review only. No pull request or upstream issue has been submitted.**

Upstream: https://github.com/sbender9/signalk-venus-plugin
Base: `67f340caeee8d96942cea8ce89cabb135fd44b05`

## Problem and proposed behavior

Expose a configurable MQTT username, trusted CA file and TLS certificate hostname for local/remote GX connections. This supports paired-token credentials and verified TLS without changing VRM authentication.

## Scope and decisions

Only source options and their use are included. Custom package suffixes, deployment details, certificates, tokens and unrelated lockfile repairs are excluded. The current candidate uses the server-name option only when a CA file is supplied; resolve/document that UX before submission. Recorded local baseline had 13 pre-existing switch-fixture failures, not an all-green suite.

## Validation status

The branch was prepared from current upstream source. Patch applicability and
diff whitespace checks are verified during preparation. These are review drafts,
not a claim of passing CI, deployment readiness or completed hardware validation.

## Before upstream submission

- [ ] Add dedicated connection-option and local TLS tests for username/password, trusted/untrusted CA, hostname mismatch and missing/unreadable CA file.
- [ ] Verify existing MQTT, MQTTS and VRM modes and reconnect behavior.
- [ ] Establish current upstream test baseline; coordinate with CI repair PR #206.

## Related upstream work

- https://github.com/sbender9/signalk-venus-plugin/pull/206

Keep boat identity, credentials, live data, custom release suffixes and deployment
scripts out of an upstream submission. Publish nothing to the parent until approved.
