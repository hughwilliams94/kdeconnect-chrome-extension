# KDE Connect Chrome Extension

A Chrome (and compatible) browser extension to send pages and content from your
browser to connected KDE Connect devices, via browser action or context menu.

## Installation

This extension relies on a Native Messaging Host to communicate with KDE Connect
devices.  As a result, installation is a little more involved than stand-alone
extensions.

1. Download the [latest release](https://github.com/pdf/kdeconnect-chrome-extension/releases/latest) of the host application.
2. Close your browser
3. Extract the host application anywhere, open a terminal and run the install
   command:
   ```bash
   ./kdeconnect-chrome-extension -install
   ```
   It will prompt you to select the browser you wish to install for, and deploy
   itself to the appropriate location.

   If you wish to deploy system-wide, rather than for the current user, simply
   run as root:
   ```bash
   sudo ./kdeconnect-chrome-extension -install
   ```
4. Start your browser.
5. Install the extension from the [Chome Web Store](https://chrome.google.com/webstore/detail/kde-connect/ofmplbbfigookafjahpeepbggpofdhbo).

Currently only Linux amd64 builds are produced, however please file an issue if
you would like other operating systems or architectures, as the host should run
anywhere.

### Building the Host from source

1. Install the [Go toolchain](https://golang.org) v1.7+
2. Install [glide](https://github.com/Masterminds/glide):
   ```bash
   go get -u github.com/Masterminds/glide
   ```
3. Obtain the source:
   ```bash
   git clone https://github.com/pdf/kdeconnect-chrome-extension.git
   cd kdeconnect-chrome-extension
   ```
4. Install dependecies:
   ```bash
   glide install
   ```
5. Install the binary:
   ```bash
   go install
   ```

You will find the binary in `${GOPATH}/bin/kdeconnect-chrome-extension` if
`$GOPATH` is set, or `${HOME}/go/bin/kdeconnect-chrome-extension` for Go v1.8+
without `$GOPATH`.
