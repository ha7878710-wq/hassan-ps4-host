# Hassan PS4 Host — v0.3.0

Arabic PS4 9.00 host. GoldHEN 2.4b18 (pre-release) and pOOBs4 are bundled locally with original credits. This integration has NOT been tested on physical PS4 hardware.

Open the main page, choose the GoldHEN launcher, and follow its Arabic instructions. The launcher requires the PS4 9.00 browser and an exfathax USB prepared separately on a computer. Writing the USB image erases the selected USB. Insert it only when the exploit requests it, wait for the unsupported-format notification, close the dialog, then remove the USB. Keep it unplugged before reboot.

The payload is downloaded locally and SHA256 checked before loading any exploit scripts. Launch is manual, guarded by a 9.00 user-agent check and two readiness checkboxes. Browser detection is advisory, not a hardware guarantee. No TCP payload receiver is started: bridge.js replaces the upstream run_hax payload-loader tail with a local call to the pinned binary. Upstream vendor JS files are unchanged.

Sources, exact revisions, byte counts and SHA256 hashes are in docs/tools/900/sources.json. Upstreams do not include an explicit license file in the downloaded release/revision. We retain upstream readmes and credits and do not claim they are MIT, public domain, or licensed by this project. GoldHEN source is private.

Run `node scripts/build_cache.cjs` then `node scripts/check.cjs`. The original Python cache builder remains usable; Python check.py delegates to the Node integration checks. AppCache and Service Worker include the complete runtime. Hardware exploit success and offline behavior on a PS4 must be tested separately. No firmware update or USB writing is performed by the website. It does not provide official PSN.

Publish by replacing Hassan-PS4-Host.zip in the repository root. Existing GitHub Actions extracts this directory and publishes docs.
