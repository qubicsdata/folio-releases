# Folio

A local workspace for planning and coordinating work across projects.

Originally developed by [QubicsData](https://qubicsdata.com). Licensed under [Apache-2.0](LICENSE).

This public repository provides ready-to-install Folio packages for macOS and Linux. Application development repositories remain private and are maintained separately.

## Install and open

Download the matching standalone archive and its `.sha256` file from the [latest release](https://github.com/qubicsdata/folio-releases/releases/latest). No GitHub account is required. Verify the archive before extracting it: use `shasum -a 256 -c ARCHIVE.tar.gz.sha256` on macOS or `sha256sum -c ARCHIVE.tar.gz.sha256` on Linux, substituting the downloaded checksum filename. Follow `README.txt` inside the verified archive. The Python runtime is bundled.

### Homebrew

The Homebrew tap is public. Install without GitHub credentials:

```sh
brew tap qubicsdata/tap https://github.com/qubicsdata/homebrew-tap.git
brew trust qubicsdata/tap
brew install qubicsdata/tap/folio-workspace
folio ui
```

`brew trust` is available in Homebrew 7; earlier versions may not need this step. Public downloads use Homebrew’s standard HTTPS downloader with pinned SHA-256 hashes. Read access to the application development repository is not required for installation.

If an older installation appears first on PATH, use `$(brew --prefix)/bin/folio ui` to open the Homebrew version. Installation does not launch services or move existing workspaces.

## Packages

The [v1.1.2 release](https://github.com/qubicsdata/folio-releases/releases/tag/v1.1.2) provides standalone archives and Homebrew bottles for macOS and glibc Linux, on ARM64 and x64. Runtimes are bundled. SHA-256 checksums, license notices, source/build provenance and validation evidence accompany the packages.

The Homebrew macOS bottles target macOS 27. Other supported macOS versions can use the matching standalone archive, subject to its runtime requirements. macOS ARM64 and Linux ARM64 checks run natively; x64 checks use Rosetta and full-system QEMU TCG. Exact platform and test scopes are recorded in each release's evidence.

Download installers from the release's Assets list. Extract the matching `folio-1.1.2-<platform>-<architecture>.tar.gz`, then follow `README.txt` inside it; the bundled Python runtime runs the installer, so a system Python is not required. GitHub's automatically generated repository archives contain these distribution documents. Development source exports, wheels, source distributions and npm development packages are not installation assets in this channel. Packaged application code can remain readable, including Python and JavaScript; this distribution does not promise obfuscation.

## Local browser access

Folio 1.1.2 authenticates every local API read and write. Run `folio ui` to open an authorized browser tab; the private launch fragment is cleared before the workspace renders. The browser uses an HttpOnly, SameSite=Strict cookie together with an origin-scoped session proof. Reloading and opening another authorized tab retain access. CLI commands load an owner-only credential from the workspace rather than an unauthenticated HTTP endpoint. Server restarts require a new `folio ui` launch.

`folio ui --no-open` and server commands print credential-free addresses. Opening that address directly does not grant API access; use `folio ui` to sign in. Keep the server on loopback. This boundary does not isolate programs already running as the same operating-system account. Open only trusted project folders and backups; see [the security policy](SECURITY.md).

## Update and remove

Back up your workspace and finish active work before upgrading. Stop the running application using its currently installed `folio server-stop` command, or stop its Homebrew service, before installing the new version. The new CLI cannot use a legacy server without private owner discovery. Then run:

```sh
brew update
folio server-stop
brew upgrade qubicsdata/tap/folio-workspace
folio ui
```

Optional background service: `brew services start qubicsdata/tap/folio-workspace`. Stop it with `brew services stop qubicsdata/tap/folio-workspace` before upgrading.

`brew uninstall folio-workspace` removes the application and retains workspace/project data. Existing standalone installations remain separate; their transactional installers and data locations are documented inside the downloaded packages.

## Attribution and redistribution

Folio is originally developed by QubicsData. Apache-2.0 permits modification and redistribution, including commercial use, subject to its terms. Redistributed copies must include the license and preserve applicable attribution notices from [NOTICE](NOTICE). Mark modified files as required by the license. Third-party components retain their own licenses and notices.

The About screen identifies QubicsData in our official builds. This is an informational credit; it adds no visible-credit or advertising requirement to Apache-2.0. Product names and logos have separate trademark terms in NOTICE. Prior Apache-licensed releases and their grants remain unchanged.

## Support

Use [this repository's issues](https://github.com/qubicsdata/folio-releases/issues) for installation problems and bug reports. Include the application version, operating system, architecture, and steps to reproduce. Review diagnostics before sharing; omit credentials and private project data.

Report security vulnerabilities through [private vulnerability reporting](https://github.com/qubicsdata/folio-releases/security/advisories/new), rather than a public issue. See the [security policy](SECURITY.md).

All packages are built locally. GitHub Actions is disabled. Folio 1.1.2 will be immutable when published; prior 1.1.1 assets and tags remain unchanged. Earlier releases and development histories are preserved in their original repositories.
