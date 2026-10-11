# Folio 1.1.2

Folio now authenticates every local API read and write. The CLI reads an owner-only server credential from its workspace. `folio ui` opens a private launch fragment, clears it before rendering, and exchanges it for an HttpOnly, SameSite=Strict cookie plus an origin-scoped browser proof. Neither browser factor authorizes API access alone; writes also require CSRF. Reopening the UI preserves authorized tabs. Server restarts rotate credentials.

Backup and project downloads use authenticated requests. `--no-open` and server commands print credential-free addresses; use `folio ui --data-dir /path/to/workspace` to sign in. Host and Origin checks remain active. New workspaces are private independently of the account umask; existing directories writable by other accounts are refused. This protects the local browser interface, not against programs already running as the same OS account. Open only trusted project folders and backups.

Before upgrading, stop the running server using its currently installed `folio server-stop` command and save a planning backup. Upgrade with the same workspace, then run `folio ui` again. The new CLI does not obtain an old server token through an unauthenticated endpoint.

Install through the public GitHub release or `brew tap qubicsdata/tap` and `brew install qubicsdata/tap/folio-workspace`. Downloads require no GitHub account or token. Four standalone archives and four Homebrew bottles include the pinned CPython runtime and preserve workspace data. Apache-2.0 and the QubicsData attribution remain unchanged. macOS packages are unsigned and unnotarized.

The application source is the clean private commit `07f0b5b5add879e5d849a5b4a1b7206cdf3c011f`. Earlier releases and tags remain unchanged. Detailed platform, installed browser, paired Switchboard and Homebrew results accompany the release evidence.
