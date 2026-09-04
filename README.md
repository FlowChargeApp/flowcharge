```
   ███████╗██╗      ██████╗ ██╗    ██╗ ██████╗██╗  ██╗ █████╗ ██████╗  ██████╗ ███████╗
   ██╔════╝██║     ██╔═══██╗██║    ██║██╔════╝██║  ██║██╔══██╗██╔══██╗██╔════╝ ██╔════╝
   █████╗  ██║     ██║   ██║██║ █╗ ██║██║     ███████║███████║██████╔╝██║  ███╗█████╗  
   ██╔══╝  ██║     ██║   ██║██║███╗██║██║     ██╔══██║██╔══██║██╔══██╗██║   ██║██╔══╝  
   ██║     ███████╗╚██████╔╝╚███╔███╔╝╚██████╗██║  ██║██║  ██║██║  ██║╚██████╔╝███████╗
   ╚═╝     ╚══════╝ ╚═════╝  ╚══╝╚══╝  ╚═════╝╚═╝  ╚═╝╚═╝  ╚═╝╚═╝  ╚═╝ ╚═════╝ ╚══════╝
```

**FlowCharge is the application, and it is the primary product.** Version 1 ships as a
Bun-compiled native binary for macOS, Linux and Windows. The binary starts a local
server, and you open the board in a browser. It reads a project's `flowcharge/` folder
and renders every workstream as a card. It also installs the FlowCharge Core skill
files, tracks their versions, and updates them in one click. The board is read-only
today.

---

## What this repository holds

This repository carries release binaries and documentation only. There is no source code
here to read.

FlowCharge Core, the skill suite, is open source under the MIT licence. FlowCharge is free to use, and its source is not published.

---

## Download

No release is published yet.

When one is published, take the binary for macOS, Linux or Windows from this
repository's Releases page.

On macOS and Linux, make the downloaded file executable:

```sh
chmod +x <the-downloaded-file>
```

Run it, then open the board in your browser at <http://localhost:4173>.

---

## FlowCharge Core

FlowCharge installs and orchestrates FlowCharge Core, the companion open-source skill
suite: <https://github.com/FlowChargeApp/flowcharge-core>. Core is free, complete, and
fully functional on its own.

---

## Security

To report a vulnerability, read the policy in [SECURITY.md](SECURITY.md).

---

Copyright © 2026 Anthony Koukoullis. All rights reserved.
