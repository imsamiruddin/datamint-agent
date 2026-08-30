# DataMint Agent

The **DataMint Agent** is the local engine that powers the
[DataMint Chrome extension](https://datamint.online). It runs on YOUR computer
and needs **nothing installed**: no Python, no dependencies, no admin rights.
One command installs it. The same command updates it.

<!-- Video placeholder: paste the install-walkthrough embed here later -->

## Requirements

| | |
|---|---|
| **macOS** | Apple Silicon (M1/M2/M3/M4), macOS 12+. *(Intel Macs not supported yet)* |
| **Windows** | Windows 10 or 11, 64-bit |
| **Both** | Google Chrome · internet during install/login · ~500 MB free disk |

## Install (one command)

**macOS: open Terminal, paste, press Enter**

```bash
mkdir -p ~/DataMint && cd ~/DataMint && curl -L -o dm.zip https://github.com/imsamiruddin/datamint-agent/releases/latest/download/DataMint-mac.zip && rm -rf DataMint-Extension && unzip -oq dm.zip && rm dm.zip && chmod +x DataMint && ./DataMint
```

**Windows: open PowerShell, paste (right-click), press Enter**

```powershell
mkdir $HOME\DataMint -Force; cd $HOME\DataMint; curl.exe -L -o dm.zip https://github.com/imsamiruddin/datamint-agent/releases/latest/download/DataMint-windows.zip; Remove-Item DataMint-Extension -Recurse -Force -ErrorAction SilentlyContinue; Expand-Archive -Force dm.zip .; del dm.zip; .\DataMint.exe
```

The first launch can take up to ~30 seconds (the engine unpacks itself).
Wait for `Running at: http://localhost:8000`, then **keep the window open**.

Then load the extension (once): `chrome://extensions` > enable **Developer
mode** > **Load unpacked** > select the `DataMint-Extension` folder inside your
DataMint folder (macOS: `~/DataMint`, Windows: `C:\Users\<you>\DataMint`) >
sign in with your registered email.

## Daily use

- **Start:** `cd ~/DataMint && ./DataMint` (mac), `cd $HOME\DataMint; .\DataMint.exe` (win)
- **Stop:** focus the server window, press **Ctrl+C**

## Update and repair (same command)

Stop the server (Ctrl+C), paste your OS's install command from above **again**
(it always downloads the latest release and safely replaces everything), then
click the reload icon on the DataMint card at `chrome://extensions`.
**Your login and settings are kept**: they live in Chrome, not in these files.
A broken or half-deleted installation is repaired by the same command.
Uninstall = delete the DataMint folder and remove the extension.

## What the Agent does (full transparency)

- Runs a local server at `http://localhost:8000` that the Chrome extension
  talks to. It never exposes your data to us.
- Contacts `auth.datamint.online` ONLY for login, session heartbeat and
  version checks.
- AI calls go to the LLM provider **you configure, with your own API key**.
- Scraping/enrichment happens on your machine. No hidden telemetry.

## What it does NOT do

- No keylogging, no file scanning, no data collection, no ads.
- Does not modify your browser or system settings.

## Downloads

Official binaries live in [Releases](../../releases). Always download from
this repository only.

Support: [datamint.online/contact](https://datamint.online/contact) ·
Docs: [datamint.online/docs](https://datamint.online/docs)

© DataMint. All rights reserved.
