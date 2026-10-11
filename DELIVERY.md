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

The release evidence includes sanitized receipts, screenshots, runtime provenance, upstream notices and a schema-validated scoped CycloneDX SBOM. Folio 1.1.2 is published as an immutable release with 25 assets, at artifact tag commit `78d570e0ed80a93e552f8a42061621ea6a7b32d0`. GitHub release attestation verification passed and binds that tag to every exact asset hash. All 25 Folio assets and all 66 combined Folio/Switchboard assets were downloaded anonymously; each matched both local and GitHub API SHA-256 digests.

A fresh anonymous HTTPS clone of public tap `d2c1bd3e6107f0d4ad7310e1146f69241c7b0537` and empty Homebrew bottle cache installed both published products on native macOS ARM64 without GitHub credentials. Normal pours, original formula test blocks, complete payload verification, public embedded formula loaders, service PATH and same-prefix coexistence passed. The downloaded Folio bottle was `76bbca090b036428584b83e61d9d07532a1d2ab20b4215f4ac258a92f3361177`. The postpublication receipt is recorded on repository main only. The release tag, asset bytes and source provenance remain unchanged. GitHub attestation does not Apple-sign or notarize the application.
