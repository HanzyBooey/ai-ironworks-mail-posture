# Mail + Web Posture Checklist

- [ ] Confirm outbound path is Microsoft 365 only for `@aiironworks.com`
- [ ] Confirm DKIM signing enabled in M365
- [ ] Publish SPF dual-include soak (Outlook + secureserver) until cutover
- [ ] Run checkdmarc VERIFY — PASS before DMARC reject ramp
- [ ] Keep DMARC policy `quarantine` until VERIFY PASS
- [ ] Ramp DMARC `pct` reject 50 → 100 after PASS
- [ ] Apply HSTS Stage A + baseline headers on host (SSH)
- [ ] Security re-VERIFY with testssl after header change
- [ ] Close Docker TCP 2375 before docker-bench / goss desk runs
