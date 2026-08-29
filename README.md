# DataMint Agent

The **DataMint Agent** is the local engine that powers the
[DataMint Chrome extension](https://datamint.online). It runs on YOUR computer
and needs **nothing installed** — no Python, no extra software.

## Install (one command)

**macOS — Terminal:**
mkdir -p ~/DataMint && cd ~/DataMint && curl -L -o dm.zip https://github.com/imsamiruddin/datamint-agent/releases/latest/download/DataMint-mac.zip && unzip -oq dm.zip && rm dm.zip && chmod +x DataMint && ./DataMint

**Windows — PowerShell:**
mkdir $HOME\DataMint -Force; cd $HOME\DataMint; curl.exe -L -o dm.zip https://github.com/imsamiruddin/datamint-agent/releases/latest/download/DataMint-windows.zip; Expand-Archive -Force dm.zip .; del dm.zip; .\DataMint.exe

Updating to any future version = stop the server (Ctrl+C) and run the same
command again. Full guide: see `Guide.md` inside the downloaded zip.

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
