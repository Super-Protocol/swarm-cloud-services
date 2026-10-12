# swarm-cloud-services

Public distribution of Super Protocol swarm service plugins (zip archives).

Artifacts are published by CI in the private [`swarm-cloud`](https://github.com/Super-Protocol/swarm-cloud) repository to the `gh-pages` branch of this repository. Do not commit zip archives to `main`.

## URL layout

Base URL: `https://super-protocol.github.io/swarm-cloud-services/`

Each release version is a directory matching `tags.services` in node config (`develop`, `main`, `v1.2.3`, …):

```
https://super-protocol.github.io/swarm-cloud-services/<version>/index.json
https://super-protocol.github.io/swarm-cloud-services/<version>/<service>.zip
```

Example for `develop`:

```
https://super-protocol.github.io/swarm-cloud-services/develop/index.json
https://super-protocol.github.io/swarm-cloud-services/develop/openresty.zip
```

`index.json` lists services with stable file names and SHA-256 checksums:

```json
{
  "version": "develop",
  "services": [
    { "name": "openresty", "file": "openresty.zip", "sha256": "<hex>" }
  ]
}
```

## GitHub Pages setup

After the first CI publish creates the `gh-pages` branch:

1. Repository **Settings → Pages**
2. Source: **Deploy from a branch**
3. Branch: `gh-pages`, folder `/`
