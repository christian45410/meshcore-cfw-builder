# MeshCore CFW Builder

![alt text](https://github.com/christian45410/meshcore-cfw-builder/blob/main/Screenshot.png)

A web-based firmware builder for [MeshCore](https://github.com/meshcore-dev/MeshCore). Select your board, firmware type, and custom flags — get a compiled `.bin` back.

## What it does

- Clones the latest MeshCore source from GitHub
- Lets you pick a board variant and firmware type (Repeater, Room Server, Companion Radio, etc.)
- Applies custom build flags
- Compiles via PlatformIO and streams logs live
- Serves the merged `.bin` for download

## Stack

- Python / Flask
- PlatformIO
- Docker

## Run with Docker

```bash
docker compose up -d
```

Then open [http://localhost:5000](http://localhost:5000).

PlatformIO packages are cached in a named Docker volume (`pio-cache`) so subsequent builds are fast.

## Run locally (dev)

```bash
pip install -r requirements.txt
python app.py
```

> Requires PlatformIO to be installed and on your PATH.

## Notes

- Max 2 concurrent builds by default (`MAX_CONCURRENT_BUILDS` in `app.py`)
- Build artifacts are stored in a temp directory and cleaned up on restart
