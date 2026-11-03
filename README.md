# AI Ironworks — Mail + Web Posture (demo)

Checklist-style demo of how we harden outbound mail and baseline HTTPS for `aiironworks.com`.

## Stack (facts)

| Control | Intent |
| --- | --- |
| **SPF** | Dual-include soak: Outlook 365 + GoDaddy legacy (`secureserver.net`) until cutover |
| **DKIM** | Microsoft 365 signing for `@aiironworks.com` |
| **DMARC** | Stay `quarantine` until VERIFY PASS, then ramp `reject` 50 → 100 |
| **HSTS Stage A** | Host/Caddy path over SSH; Security re-checks with `testssl` |

## Tools we pin (owned)

- [checkdmarc](https://github.com/domainaware/checkdmarc) — VERIFY after DNS changes
- [testssl.sh](https://github.com/drwetter/testssl.sh) — TLS / header re-verify
- Caddy for staged security headers

See [`CHECKLIST.md`](./CHECKLIST.md).

## Status

Public evaluator demo. Live DNS apply stays gated on ops Yes — this repo is process, not credentials.

© AI Ironworks
