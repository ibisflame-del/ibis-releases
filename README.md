<p align="center"><img src="banner.png" alt="Ibis Tech: AI apps that run on your own PC. Private, free to try, proof on screen." width="760"></p>

# Ibis Tech — releases

**Most AI apps want your files on their servers. I wanted the opposite.** Every Ibis app runs on your own PC, works with
the AI model you pick, and shows its proof on screen. Meet the apps and watch the videos on the
**[Ibis Tech page](https://github.com/ibisflame-del)**, then try them free on itch.io.

This repository holds only the finished installers and the small signed files the apps' built-in updaters read.
**There is no source code here.**

## Get the apps on itch.io

Each app has its own page with screenshots, videos, install steps and the devlog. Start there:

- **Ibis Spider**: a free AI that reads your own books and answers with the page number.
  → **https://ibisflame.itch.io/ibis-spider**
- **Ibis Quantized Containers (IQC)**: run AI models and apps in locked boxes on Windows. Shrink them, race them, and keep your keys safe. Free.
  → **https://ibisflame.itch.io/ibis-quantized-containers**
- **MEDUSA**: a free creative suite that runs on your own PC: video, sound, photos, lettering, and AI pictures, video and
  voices with the models you choose.
  → **https://ibisflame.itch.io/medusa**
- **IBIS-CODER**: a free AI coder you can watch: a real code editor and an AI coder on the model you pick.
  → **https://ibisflame.itch.io/ibiscoder**
- **Dr. Frankenstein's Reanimation Labs**: train an AI model on your own material, on your own PC. Free.
  → **https://ibisflame.itch.io/dr-frankensteins-reanimation-labs**

Follow the pages on itch.io to hear about new versions and new apps.

## What's in this repository

- **One release file per app** (for example `IbisSpider.json`). It names the newest version, where its installer is, the
  installer's SHA-256 fingerprint and a signature. These appear with the first release that has the updater built in.
- **The installers**, attached to each release on the [Releases](../../releases) page. They are the same files as on itch.io.

## How the updater uses it

- An app checks here **only if you said yes** when it asked, or when you press *Check for update*. It asks for that one
  release file and sends nothing about you or your work.
- It trusts a release only if it carries the Ibis Tech signature built into the app, names that app, and is newer than
  what you have.
- It runs an installer only if the installer's size and fingerprint match the signed release.
- If the new version doesn't start properly, the version you had is put back.
- Your own files and data are never touched.

The two public signing keys built into the apps:

| key id | public key (Ed25519) |
|---|---|
| `e560bbc08a5a` | `5a0da08c4ef4191a05170cf7dab34b5b194971d42098e50aef3b90a5b8a1a9fd` |
| `b5a75226bdf2` | `df6f8d341e299b5052edd602112d6125b59884557039dcbc7f7f77fecd893573` |

## Check a download yourself

In PowerShell, in the folder where the installer is:

```powershell
Get-FileHash .\IbisSpider-Setup-1.0.5.exe -Algorithm SHA256
```

The hash must match the `sha256` in that app's release file and the fingerprint on its itch.io page.

---

© 2026 Joseph Carl Thomas — Ibis Tech. All rights reserved. Each app's licence is shown in its installer.
