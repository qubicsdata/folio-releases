# Folio

A local workspace for planning and coordinating work across projects.

Originally developed by [QubicsData](https://qubicsdata.com). Licensed under [Apache-2.0](LICENSE).

This repository provides ready-to-install Folio packages for macOS and Linux. Application development repositories are maintained separately. All repositories remain private for this delivery.

## Install and open

Your GitHub account needs read access to this repository and `qubicsdata/homebrew-tap`.

```sh
gh auth login
gh auth setup-git
brew tap qubicsdata/tap https://github.com/qubicsdata/homebrew-tap.git
brew trust qubicsdata/tap
brew install qubicsdata/tap/folio-workspace
folio ui
```

`brew trust` is available in Homebrew 7; earlier versions may not need this step. Private asset downloads use your existing GitHub CLI sign-in or `HOMEBREW_GITHUB_API_TOKEN`. Credentials stay out of repository URLs and formula files. Read access to the application development repository is not required for installation.

If an older installation appears first on PATH, use `$(brew --prefix)/bin/folio ui` to open the Homebrew version. Installation does not launch services or move existing workspaces.

## Packages

The [v1.1.1 release](https://github.com/qubicsdata/folio-releases/releases/tag/v1.1.1) contains standalone archives and Homebrew bottles for macOS and glibc Linux, on ARM64 and x64. Runtimes are bundled. SHA-256 checksums, license notices, source/build provenance and validation evidence accompany the packages.

The Homebrew macOS bottles target macOS 27. Other supported macOS versions can use the matching standalone archive, subject to its runtime requirements. macOS ARM64 and Linux ARM64 checks run natively; x64 checks use Rosetta and full-system QEMU TCG. Exact platform and test scopes are recorded in each release's evidence.

Download installers from the release's Assets list. Extract the matching `folio-1.1.1-<platform>-<architecture>.tar.gz`, then follow `README.txt` inside it; the bundled Python runtime runs the installer, so a system Python is not required. GitHub's automatically generated repository archives contain these distribution documents. Development source exports, wheels, source distributions and npm development packages are not installation assets in this channel. Packaged application code can remain readable, including Python and JavaScript; this distribution does not promise obfuscation.

## Update and remove

Back up your workspace and finish active work before upgrading. Stop the running application or its Homebrew service, then run:

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

All packages are built locally. GitHub Actions is disabled. Earlier releases and development histories are preserved in their original repositories.
