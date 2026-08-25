# mythicos-dev-tools

A collection of tools to develop/compile MythicOS projects.
Forked from [Linux Mint's mint-dev-tools](https://github.com/linuxmint/mint-dev-tools).

## ⚠️ Before you build the package

`usr/bin/mythicos-build` and `usr/bin/mythicos-docker-build-from-git` default
to cloning from the `StudioHastag` GitHub org when you pass just a project
name (e.g. `mythicos-build -g mythicos-report`). Edit the `GITHUB_ORG`
constant near the top of `mythicos-build` if your real org/user is different.
Full URLs (`mythicos-build -g https://github.com/you/repo.git`) always work
regardless of this setting.

## Tools

- **mythicos-build** — clone + build a Debian package (installs build-deps
  automatically via `mk-build-deps`, then runs `dpkg-buildpackage`). Supports
  `-g/--git-repository` (URL, or bare name + `#tag`/`#branch`/`%PR`),
  `-t/--temporary`, `-s/--suffix`, `-i/--install`, `-d/--deb-dir`. Also works
  on multi-project folders via a `build-order` file.
- **mythicos-dev-setup** — one-time setup of your local dev sandbox root.
- **mythicos-dev-settings** — GTK settings panel (stats tracker, sandbox path).
- **cinnade-stats-tracker** — memory/CPU tracker for a running Cinnade session.
- **mythicos-check-translations** — GTK tool to validate .po translations
  (checks that format tokens like `%s`, `%d`, dates survive translation).
- **mythicos-compare-potfiles** — diff msgid entries between two .po/.pot
  files (or auto-diff current file vs HEAD).
- **mythicos-compare-manifests / mythicos-search-manifests** — compare/search
  packages across release manifests stored in
  `/usr/share/mythicos-dev-tools/manifests`.
- **mythicos-check-upgrade-versions** — sanity-check package versions across
  an upgrade path.
- **mythicos-compare-isos** — mount two ISOs and diff installed packages.
- **mythicos-check-usrmerge** — check a .deb for usrmerge path compatibility.
- **mythicos-apt-backend-tester** — GTK tool to test PackageKit / aptdaemon /
  aptkit backends side by side.
- **mythicos-docker-build / mythicos-docker-build-from-git /
  mythicos-docker-build-packages** — build packages inside Docker containers
  per release/arch.
- **mythicos-icon-picker / mythicos-test-icon-lookup** — icon picker dialog
  and icon-theme lookup tester.
- **mythicos-show-gvfs-metadata** — view/edit GVFS file metadata.
- **generate-gobject-class** — scaffold a GObject C class (header + template).
- **bakunbak** — rename/copy files to/from a `.bak` suffix.
- **mythicos-add-shadow / mythicos-make-thumbnail** — ImageMagick helpers to
  add a drop shadow / generate a thumbnail for a screenshot.
- **mythicos-perf-record / mythicos-valgrind** — perf and valgrind wrappers.
- **mythicos-get-browser** — fetch/package Chromium/Firefox/Thunderbird
  builds (still points at upstream Mint/Ubuntu build infrastructure — check
  before relying on it).

Note: manifest files, Mint release codenames, and `packages.linuxmint.com`
URLs used for comparison tools were left untouched on purpose — they're
reference data for diffing against upstream Mint/Ubuntu, not MythicOS
branding.
