# AgentBaseFS client releases

This public repository contains macOS `abfs` binaries and verification assets. The source code is maintained in a separate private repository.

## Install

On a trusted Mac:

```sh
curl -fsSL https://dbay.cloud/install.sh | sh
```

For an Agent machine:

```sh
curl -fsSL https://dbay.cloud/install.sh | sh -s -- --agent
```

The installer supports `--version X.Y.Z`, `--no-onboard`, and `--prefix DIR`. It selects `arm64` or `x86_64`, checks the archive against `SHA256SUMS`, and verifies the Sigstore bundle when `cosign` is installed. Without `cosign`, the checksum only detects download corruption and does not authenticate the release publisher. The installer starts `abfs onboard` when a terminal is attached; otherwise run it yourself afterward.

Each release contains four archives: one trusted and one Agent build for each Mac architecture. The Agent build has no login or local cutover commands.
