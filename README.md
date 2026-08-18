# ocis-web-extensions-debian

[![Debian Build Bot](https://github.com/donmor/ocis-debian/actions/workflows/dpkg-buildpackage.yml/badge.svg?event=release)](https://github.com/donmor/ocis-debian/actions/workflows/dpkg-buildpackage.yml)

(Unofficial) Debian packaging scripts for [oCIS Web Extensions](https://github.com/owncloud/web-extensions).

Provided packages: `ocis-web-app-*` (see Web Extensions [Releases](https://github.com/owncloud/web-extensions/releases))

## Quick configuration
Install [`donmor-repos-keyring`](https://donmor-repos.github.io/pub/donmor-repos-keyring_0.0.1_all.deb) and [`ocis-debian-repo`](https://donmor-repos.github.io/pub/ocis-debian-repo_0.0.1_all.deb), then run `apt-get update`.

## Manual configuration
#### Add keyring:
``` bash
curl -sLOJR --output-dir /usr/share/keyrings https://donmor-repos.github.io/pub/donmor-repos-keyring.gpg
```
#### Add `ocis-web-extensions-debian`:
``` bash
# You may use a separate sources file
tee -a /etc/apt/sources.list.d/ocis.sources <<EOF

Types: deb deb-src
URIs: https://github.com/donmor-repos/ocisi-web-extensions-debian/releases/latest/download
Suites: /
Signed-By: /usr/share/keyrings/donmor-repos-keyring.gpg
EOF
apt-get update
```
