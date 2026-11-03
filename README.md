# Play 2s Before Next Marker or Region

**English** · [Русский](README_RU.md)


Seeks to 2 seconds before the next marker or region start. If the transport is active (playing, paused, or recording), it seeks without stopping. If the transport is stopped, it moves the edit cursor and starts playback.

No js_ReaScriptAPI required.

## Installation

### ReaPack

Import the [Patch34 ReaPack catalog](https://raw.githubusercontent.com/patch-34/patch34-reapack/main/index.xml) via **Extensions → ReaPack → Import repositories…** and install **Play 2s Before Next Marker or Region** from **Browse packages**.

### Manual installation

1. In REAPER: **Actions → Show action list…**
2. Click **ReaScript: Load…**
3. Select `Play_2s_Before_Next_Marker_Or_Region.lua`
4. Optionally assign a keyboard shortcut

## How it works

- **Transport active** (play / pause / record) — uses the play cursor position, then seeks to `next_pos - 2.0s` without interrupting transport
- **Transport stopped** — uses the edit cursor position, moves it to `next_pos - 2.0s`, and starts playback
- Both markers and region starts are considered; the nearest one to the right wins
- If nothing is found to the right, a message box is shown and nothing happens

## Configuration

The pre-roll duration is defined at the top of the script:

```lua
local PRE_ROLL_SEC = 2.0
```

Change this value to adjust the offset.

## License and credits

Distributed under the [MIT License](LICENSE).

Author: [Aleksei Vorobev / Patch34](https://github.com/patch-34).