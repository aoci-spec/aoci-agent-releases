# aoci-agent releases

Release archives of aoci-agent, a cognition-first coding agent. The source
repository is not yet public; this repository holds the archives, so that a
benchmark harness or a person can download a version without credentials.

Each [release](https://github.com/aoci-spec/aoci-agent-releases/releases) holds:

| Asset | What it is |
| --- | --- |
| `aoci-agent-<version>-linux-amd64.tar.gz` | The Linux amd64 archive: the `aoci-agent` binary, the bundled AOCI-CODE engine (`bin/aoci`) and its pinned contract documents, `install.sh`, `QUICKSTART.md`, `LICENSE`, `NOTICE`, `THIRD-PARTY-NOTICES`, `MANIFEST.json` and `SHA256SUMS` |
| `aoci-agent-<version>-windows-amd64.zip` | The Windows amd64 archive, with `install.ps1` |
| `*.sha256`, `SHA256SUMS` | The SHA-256 of each archive |

## Install

```sh
curl -fLO https://github.com/aoci-spec/aoci-agent-releases/releases/download/v0.4.0/aoci-agent-v0.4.0-linux-amd64.tar.gz
curl -fLO https://github.com/aoci-spec/aoci-agent-releases/releases/download/v0.4.0/aoci-agent-v0.4.0-linux-amd64.tar.gz.sha256
sha256sum -c aoci-agent-v0.4.0-linux-amd64.tar.gz.sha256
tar -xzf aoci-agent-v0.4.0-linux-amd64.tar.gz
cd aoci-agent-v0.4.0-linux-amd64 && ./install.sh --prefix "$HOME/.local"
aoci-agent version --json
```

`install.sh` checks every file against the archive's `SHA256SUMS` before it
installs, and `aoci-agent version --json` verifies the bundled engine against
the checksum the binary pins. `QUICKSTART.md` in the archive covers models,
sessions, headless runs and hosts.

## License

aoci-agent and the bundled AOCI-CODE engine are released under the
FSL-1.1-MIT license, stated in each archive's `LICENSE` and `NOTICE`. The
`NOTICE` records the date each version was first made publicly available,
from which that version's future MIT license is derived; the same files are
in this repository.
