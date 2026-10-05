# Changelog

All notable changes to the JazzCash toolkit by ICODEDIGITA. All packages share one version number (fixed versioning), so `@icodedigita/jazzcash-next@0.1.x` always works with `@icodedigita/jazzcash@0.1.x`.

Format: [Semantic Versioning](https://semver.org). Generated per release with [Changesets](https://github.com/changesets/changesets).

## 0.1.0 (first public beta)

- Core: secure hash (ISO-8859-1, per the swagger), hosted checkout, MWallet v2 (CNIC), vouchers, wallet linking and pay-by-token, Apple Pay and Google Pay server endpoints, status inquiry, refunds, IPN, response-code map with developer hints.
- Route handler for Next.js (App Router) and Express; checkout components for React; WebView for React Native.
- Setup wizard (browser GUI) with Test Lab, hash calculator, simulator and onboarding guide.
- Local simulator driven by the public sandbox test data.
- n8n community node and IPN/Return URL trigger.
- Spec followed: JazzCash swagger `v1` (see the `SPEC` export for the exact fingerprint).
