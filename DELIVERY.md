# Folio 1.1.1 delivery receipt

Folio 1.1.1 adds role-neutral workspace copy and tasteful About credits with the version, QubicsData website, and exact local Apache-2.0 LICENSE and NOTICE text. The license remains Apache-2.0; the informational attribution adds no new restrictions.

The immutable application source is `10bc00d2ba92e6bb715fc371fe8df04f41da78b2` in the private `qubicsdata/folio-distribution` repository. All eight binary assets were built locally from that clean source. The installation channel is the private [Folio release repository](https://github.com/qubicsdata/folio-releases/releases/tag/v1.1.1) and `qubicsdata/homebrew-tap`. GitHub Actions is disabled. Wheels, source distributions and source exports are not installation assets.

Validation completed:

- Python 3.9.6 suite: 379 tests, 372 passed, 7 optional daemon tests skipped.
- Both installed paired modes: 7 scenarios each, 14 passed with zero skips, against Switchboard 2.0.1 source `c3fa728f6f6e44bfd4a16adc8ece7d1cf2d60019`, using production encrypted-file vault settings.
- All four standalone packages: 16 checks each, including genuine released 1.1.0 upgrade and retained-data uninstall/reinstall.
- Installed native macOS browser: 14 workflows, About legal links, both themes and mobile About layout passed.
- All four Homebrew targets:normal bottle pours, complete payload verification, actual embedded formula loaders, effective service PATH, CLI versions and coexistence with final Switchboard passed. Both Linux targets passed stock `brew test`. On macOS, the original formula test blocks passed through Homebrew’s API; stock `brew test` stops before the product test because host CLT 14.3.1 is older than the required 27.0.

ARM64 checks were native. macOS x64 used Rosetta; Linux x64 used full-system QEMU 11.0.3 TCG. These are translated acceptance results, not native Intel results. macOS packages are unsigned and unnotarized as selected for private distribution. No live user home, app, service or account was modified. Live model-provider calls and native destination desktop dialogs were not exercised.

The accompanying JSON lists exact binary hashes. Release evidence contains sanitized receipts, screenshots, runtime provenance, retained upstream notices and a schema-validated scoped CycloneDX SBOM. After publication, authenticated Homebrew installation from an empty cache passed on native macOS ARM64 for Folio 1.1.1 and Switchboard 2.0.1. A fresh HTTPS clone of tap `ffef6ae03418658917e1c5f4efc5cd777693d196` fetched both exact private GitHub release bottles. Normal pours, unchanged formula test blocks, full payload verification, embedded formula loaders and same-prefix coexistence passed. The downloaded Folio bottle SHA-256 was `240b73e607353e7d090b15e262977069f60169c1a46b2dca0cbaec58b953717d`. No live apps or homes were modified.
