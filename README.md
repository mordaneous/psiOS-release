# psiOS-release

Firmware updates for the Modern Psion (psiOS). A Psion looks here when you choose
**Settings > Backup & updates > Check for an update**.

- `stable/` is what every Psion installs. `test/` is used only by the board check on the bench.
- Each channel holds `psion.bin` (the firmware) and `manifest.txt` (build number, version, size, SHA-256 and a signature).
- The Psion installs an update only if its build number is higher than the one running, the SHA-256 matches and the
  signature verifies against the public key built into its firmware. The signing key never leaves the developer's Mac,
  so this repository being public is safe: a file changed here, or added by anyone else, is refused.
- An update that fails to start is rolled back to the previous version by the bootloader.

Published by `tools/make_update.py` in psiOS-development. Do not edit these files by hand.
