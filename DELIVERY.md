# Folio 1.1.2 delivery receipt

Folio 1.1.2 authenticates every API read and write. The CLI reads a private owner credential; browsers exchange a launch fragment for an HttpOnly, SameSite=Strict cookie and an origin-scoped proof. Both browser factors are required. The fragment is cleared before rendering; authenticated downloads, CSRF, Host/Origin checks and repeated-tab access passed. The same OS account remains the trust boundary.

All eight binary assets were built locally from clean private source `07f0b5b5add879e5d849a5b4a1b7206cdf3c011f`. Installation assets and the Homebrew tap are public and need no GitHub credentials. Apache-2.0 and QubicsData attribution remain unchanged. Existing releases/tags are unchanged; Actions is disabled.

Validation completed before publication:

- Python 3.9.6: 391 tests, 384 passed, 7 optional daemon cases skipped. Eleven focused owner-auth tests passed.
- Both installed paired modes: seven scenarios each, zero skips, against Switchboard 2.0.2 source `f4875e043a37d7e1d6f19dc37ef6b21d284a116d`, with production encrypted-file vault settings and no OS credential-store entries.
- Four standalone packages: 17 checks each, including private owner/browser authentication, genuine 1.1.1 upgrade and retained-data uninstall/reinstall.
- Installed native Mac browser: 14 workflows, fragment clearing, proof reload, both themes, About and mobile layout passed.
- Four Homebrew targets: normal pours, unchanged formula tests, complete payload integrity, actual embedded formula loaders, service PATH and same-prefix Switchboard coexistence passed. Both Linux targets passed stock `brew test`; macOS stock test stops before the product test on the host's outdated CLT. The original formula test blocks passed through Homebrew's API.

Native ARM64 tests used macOS and Linux in Lima. Intel tests used Rosetta and full-system QEMU 11.0.3 TCG, not native Intel hardware. macOS packages are unsigned and unnotarized. Live model-provider calls and native destination dialogs were not exercised. No live app, user home, service or account was modified.

A candidate native Linux run correctly refused a synthetic workspace created as 0775 under umask 002. Product Store already creates new roots as 0700. The tracked verifier fixture now explicitly creates a private workspace; tests confirm private creation under umask 002 and refusal of existing group-writable roots. Final packages were rebuilt from the corrected clean source; original failure logs remain local audit evidence.

The release evidence includes sanitized receipts, screenshots, runtime provenance, upstream notices and a schema-validated scoped CycloneDX SBOM. Publication is pending. Anonymous download/pour proof will be recorded in DELIVERY on repository main after immutable publication, without changing the tag or release assets.
