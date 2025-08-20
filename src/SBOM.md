# Software Bill of Materials (SBOM)

## Core Frameworks & Libraries
- [Qt Quick and QT6 Open Source](https://www.qt.io/)
- [GnuPG Made Easy (GPGME)](https://gnupg.org/software/gpgme/index.html)
- Gpgmepp
- LibGpgError
- [yaml-cpp](https://github.com/jbeder/yaml-cpp/)
- [rnp](https://github.com/rnpgp/rnp)

## Platform-Specific Tools
- pinentry-mac _(Mac only)_
  - On Ubuntu 20.04: already installed and configured for Wayland

## UI & Icons
- Icons by [Icons8](https://icons8.com/icons/)
- Icons by [Google Material Icons](https://developers.google.com/fonts/docs/material_icons)

## Features from KeePassXC
- [TOTP Support](https://github.com/keepassxreboot/keepassxc/tree/develop/src/totp)
- [Allow Screen Capture](https://github.com/keepassxreboot/keepassxc/tree/develop/src/gui/osutils)

## Utilities & Helpers
- [Cog](https://nedbatchelder.com/code/cog)
- [Thread Pool](https://github.com/bshoshany/thread-pool)

---

```Spdx
SPDXVersion: SPDX-2.2
DataLicense: CC0-1.0
DocumentName: BuiltWith-SPDX
DocumentNamespace: http://example.com/spdxdocs/builtwith-001
Creator: Tool: Microsoft Copilot
Created: 2025-08-20T11:41:00Z

##### Packages #####

PackageName: Qt
PackageDownloadLocation: https://www.qt.io/
PackageLicenseDeclared: GPL-3.0-or-later

PackageName: Gpgmepp
PackageDownloadLocation: NOASSERTION
PackageLicenseDeclared: LGPL-2.1-or-later

PackageName: GPGME
PackageDownloadLocation: https://gnupg.org/software/gpgme/index.html
PackageLicenseDeclared: LGPL-2.1-or-later

PackageName: LibGpgError
PackageDownloadLocation: NOASSERTION
PackageLicenseDeclared: LGPL-2.1-or-later

PackageName: pinentry-mac
PackageDownloadLocation: NOASSERTION
PackageLicenseDeclared: GPL-2.0-or-later

PackageName: yaml-cpp
PackageDownloadLocation: https://github.com/jbeder/yaml-cpp/
PackageLicenseDeclared: MIT

PackageName: Icons8
PackageDownloadLocation: https://icons8.com/icons/
PackageLicenseDeclared: NOASSERTION

PackageName: Google Material Icons
PackageDownloadLocation: https://developers.google.com/fonts/docs/material_icons
PackageLicenseDeclared: Apache-2.0

PackageName: KeePassXC TOTP
PackageDownloadLocation: https://github.com/keepassxreboot/keepassxc/tree/develop/src/totp
PackageLicenseDeclared: GPL-2.0-or-later

PackageName: KeePassXC Screen Capture
PackageDownloadLocation: https://github.com/keepassxreboot/keepassxc/tree/develop/src/gui/osutils
PackageLicenseDeclared: GPL-2.0-or-later

PackageName: Cog
PackageDownloadLocation: https://nedbatchelder.com/code/cog
PackageLicenseDeclared: MIT

PackageName: Thread Pool
PackageDownloadLocation: https://github.com/bshoshany/thread-pool
PackageLicenseDeclared: MIT

PackageName: RNP
PackageDownloadLocation: https://github.com/rnpgp/rnp
PackageLicenseDeclared: BSD-2-Clause
```