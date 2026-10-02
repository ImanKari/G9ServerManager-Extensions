# G9ServerManager extensions

The official catalogue of [G9ServerManager](https://dashboard.g9tm.com) extensions: programs that add pages, dashboard
widgets, AI tools and scheduled tasks to the panel, each in a sandbox of its own and able to do only what the owner grants
when installing it.

## Add it to a panel

**Extensions → Catalogue → Feeds**: name it and give this address:

```
https://raw.githubusercontent.com/ImanKari/G9ServerManager-Extensions/main/catalogue.json
```

The panel reads the feed through its *downloads* routing rule (Connectivity → Routing), so a server that cannot reach
GitHub directly can reach it through a proxy.

## What is in it

| Extension | Id | Version | Runs as | Internet | Permissions it asks for |
|---|---|---|---|---|---|
| [AdGuard Home](https://github.com/ImanKari/G9ServerManager-Extensions/releases/download/adguard-1.0.2/adguard-1.0.2.g9x) | `adguard` | 1.0.2 | docker | yes | — |
| [Hello Panel](https://github.com/ImanKari/G9ServerManager-Extensions/releases/download/hello-panel-1.0.0/hello-panel-1.0.0.g9x) | `hello-panel` | 1.0.0 | exec | no | ViewHost |
| [Relay monitor](https://github.com/ImanKari/G9ServerManager-Extensions/releases/download/relay-monitor-1.0.1/relay-monitor-1.0.1.g9x) | `relay-monitor` | 1.0.1 | exec | no | ViewDocker, ViewNetwork |
| [Speedtest](https://github.com/ImanKari/G9ServerManager-Extensions/releases/download/speedtest-1.0.0/speedtest-1.0.0.g9x) | `speedtest` | 1.0.0 | exec | yes | — |
| [Web Automation](https://github.com/ImanKari/G9ServerManager-Extensions/releases/download/web-automation-1.0.4/web-automation-1.0.4.g9x) | `web-automation` | 1.0.4 | exec | yes | — |

Every package is signed with the G9ServerManager release key (fingerprint `0db2422a2a6a09ff`): the panel verifies the
signature and each file's checksum before anything runs, shows the publisher as *Official*, and shows the review — what it
runs, what it can reach, what it asks for — before you install it. The feed also carries each package's SHA-256, which the
panel checks after downloading. A version, once published, is never replaced.

## Files

- `catalogue.json` — the feed (schema 1): each extension's newest version, its download address and SHA-256.
- [Releases](https://github.com/ImanKari/G9ServerManager-Extensions/releases) — one per package version, tagged `<id>-<version>`.

The extensions' source, the SDKs (Python, Node.js, Go) and the guide to writing one are in the G9ServerManager
repository (`extensions/`); this repository is written by its `build/publish-extensions.ps1`.