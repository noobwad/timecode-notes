# Timecode Notes
A lightweight, single-file web app for timecode-stamped note-taking during post-production review sessions. Start the clock when your pass starts, type freely, and every note is stamped with the running timecode the instant you began writing it.
**Current version:** v0.7.0-alpha
## What it does
- Running SMPTE timecode (non-drop-frame), auto-stamped notes, and long notes (in/out spans)
- A project/folder library with tags, metadata, drag-and-drop, and import/export
- Session review: per-note timecode editing, tag filtering, a Timecode Adjust tool (including negative offsets for a session that started a beat early)
- Exports: `.txt`, `.rtf` (for sending notes to reviewers), `.json` (round-trips with this app), a Markerbox-compatible CSV for Premiere, a DaVinci Resolve EDL (confirmed working against a real install), a generic EDL, and a best-effort FCPXML for Final Cut Pro
- 2POP sync: listens for a 1kHz reference tone via the mic and starts the clock precisely 2 seconds before session start TC, with a manual confirm step before note-taking unlocks
- Nine themes, Standard/Minimal interface modes, full data export/import for backup
## Status
This is an active alpha. See the in-app **App Info > Changelog** tab for the full version history, and **App Info > Tips** for known limitations (drop-frame timecode isn't implemented, AAF/frame.io export aren't available yet, Premiere can't import markers on its own — see Tips for the Markerbox workaround).
## Running it locally
This is a single self-contained HTML file — no build step, no dependencies to install. Two ways to open it:
**Just double-click it.** Works for everything except 2POP sync, since microphone access requires a secure context that a local file (`file://`) doesn't satisfy.
**Serve it locally (needed for 2POP testing):**
```
cd path/to/this/repo
python3 -m http.server 8000
```
Then open `http://localhost:8000/timecode-notes.html`. Leave the terminal running; refresh the browser tab after pulling a new version.
## Data & privacy
Everything is stored in your browser's local storage, on your device only. There's no server, no account, and no sync — use **Preferences > Export all data** to back up or move your data to another device.
## Architecture notes
Everything — markup, styles, and logic — lives in the one HTML file by design, so it stays a zero-install, zero-dependency artifact anyone can download and open. The script is organized into commented sections (storage, timecode math, active session, review screen, export writers, library tree, modals); see the header comment at the top of the `<script>` block for the full map.
