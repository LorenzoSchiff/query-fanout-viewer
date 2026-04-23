# Security Policy

## Supported scope

This repository handles browser-side parsing of provider conversation payloads.

Security-relevant issues include:
- accidental data leakage
- unsafe remote calls
- unsafe DOM rendering
- parser paths that expose private payload fragments unintentionally

## Reporting

Please do not open a public issue for sensitive security findings.

Instead, contact the maintainer privately first and include:
- a short summary
- impact
- reproduction steps
- affected provider
- sanitized payload or screenshots when possible

## Notes

This project is intended to run client-side only.
Any future feature that introduces server-side collection, upload or relay should be treated as a security-sensitive change.
