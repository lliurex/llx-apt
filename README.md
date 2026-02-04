# llx-apt
LliureX apt wrapper to manage packages from pre and unstable releases.
The shell script sets alternative paths for apt cache and list files, in order to mantain system "as clean as possible".
llx-apt provides a small subset of apt operations like update search, install ..

# Usage

$ llx-apt [pre|unstable][+ubuntu] [--no-update] [--no-pinning] [search|policy|show|update|install|remove] args

* Required repository: This value holds the repository that llx-apt shall use. Possibly values are:
** pre: Pre-Release
** unstable: Development repository

Additionally +ubuntu could be indicated for enabling the corresponding ubuntu repositories.

* --no-update: Don't performn apt update before installing or removing packages
* --no-pinning: Disable pinning. *Potentially dangerous*

* search|policy|et alll..: Apt command
* args: Arguments required for the apt command. A package name and optionally a list of configure options for apt.

Examples

* Policy for package "firefox" in pre-release with ubuntu repositories enabled

$ llx-apt pre+ubuntu policy firefox

* Installing chromium from development repository disabling pinning

$ llx-apt unstable --no-pinning install chromium

* Searching for package k3b without updating the information

$ llx-apt pre search k3b
