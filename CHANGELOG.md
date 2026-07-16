# Changelog

All notable changes to this project are documented here. This mirrors the changelog shown in-app under **App Info > Changelog**.

## [0.7.0-alpha] - 2026-07-15

### Added
- 2POP sync: listens for a 1kHz reference tone via the mic, starts the clock 2 seconds before session start TC on detection, then requires confirmation before notes can be taken
- "Not this — keep listening" option if the detection was a false alarm
- Graceful fallback if microphone access is denied or unavailable, with a one-tap "start without 2POP" option

### Fixed
- "Not this — keep listening" sometimes needing multiple presses — the confirm buttons were being destroyed and recreated on every detection cycle, which could eat a click mid-rebuild; they're now static
- Cancel button made visually prominent instead of a small text link
- Detected message simplified to "2POP DETECTED — Picture Synced"
- The Cancel button's hover-contrast fix wasn't actually taking effect — a pre-existing, more specific CSS rule was silently overriding it
- Resuming listening after a false alarm or "Try again" could immediately re-trigger on the same lingering sound; re-arming now requires a brief run of genuinely quiet readings instead of a blind fixed delay, so it doesn't cost a window to catch a real tone the way a fixed wait would

## [0.6.7-alpha] - 2026-07-15

### Added
- `.rtf` export for sending notes to reviewers
- Replaced the Premiere XML export with a Markerbox-compatible CSV

### Fixed
- Duplicated "fps fps" label in the `.rtf` export

## [0.6.6-alpha] - 2026-07-14

### Added
- DaVinci Resolve EDL export
- Premiere XML export: added a placeholder video track (attempt 2)

## [0.6.5-alpha] - 2026-07-14

### Added
- Rebuilt the NLE marker exports
- Premiere Pro XML export
- DaVinci Resolve EDL export
- Renamed "Standard EDL" to "Generic EDL"

### Removed
- Premiere CSV and Resolve CSV exports

## [0.6.4-alpha] - 2026-07-14

### Added
- Active session: tag hover-to-remove matches review; tag clicks no longer steal focus from the note field
- Add-tag and filter-tag dropdown items are full-width with a hover fill
- Notes can go negative on Timecode Adjust, shown in red
- One-time welcome message on first launch
- Clearer backup warning in Preferences
- iPhone safe-area padding
- Internal: `normalizeLibrary()` helper and section comments

### Fixed
- Importing an older backup could break the app afterward
- Re-importing a theme created a duplicate instead of updating

## [0.6.3-alpha] - 2026-07-14

### Added
- Library session action buttons moved to their own bar at the bottom
- Restored review metadata field styling
- Add-tag dropdowns are vertical lists everywhere
- Filter tags button shows a count when active
- Unicorn Party uses a background image

### Fixed
- Session library rows resizing on selection
- Hover-X color didn't match the tag's color
- Unicorn background image not rendering
- Session Edit's metadata list wasn't scrollable
- Selected session card hover border mismatch

## [0.6.2-alpha] - 2026-07-13

### Added
- FPS now sits inline with the session start date on review
- Session metadata is editable again, right on the review screen
- Folder export, from both the project edit window and each folder row
- Library rows now show populated metadata at a glance

### Fixed
- Dark themes briefly showing the light-theme timecode block style
- Duplicated "fps fps" label on review
- Hovering an applied tag shrinking it and hiding its ✕ instead of revealing it
- Tag filter's Clear button sitting outside the list instead of at its top
- Long notes reverted to the simple stacked In/Out box (dashed-bracket style removed)
- Session Edit's Export button only offering the .json format instead of the full menu
- Tag clearing in Session Edit not matching review's hover-to-remove behavior

## [0.6.1-alpha] - 2026-07-13

### Added
- Date format preference now applies throughout the app, not just session names
- Filter tags: dotted style, only shows tags actually in use, no more duplicate button
- Long notes: In/Out bracket the note with a dashed connector; overlapping notes visually link to the long note above
- Session Edit: collapsible Metadata/Move sections, an Export button, tag menu fixed to stay on-screen
- Folder export/import (nested subfolders and sessions), with new tags merged in automatically on import
- Standard upload/download icons across every import/export button

### Fixed
- Timecode Adjust arrows now step from zero (±1 second), not from the session start time
- Tag-add menu escaping its modal instead of being clipped or mispositioned
- Tag editor growing taller than its fixed header with many tags
- Clicking anywhere on an applied tag removed it — now only the hover ✕ does
- Nested subfolders no longer keep shrinking indefinitely past a few levels
- Unicorn emoji lingering on the Start button after switching themes

## [0.6.0-alpha] - 2026-07-13

### Added
- Long notes (in/out points) via ⌘/Ctrl+Enter or Tab
- Single Export button with .txt, .json, Premiere CSV, Resolve CSV, EDL, and best-effort FCPXML
- Session Edit menu in the library
- Project metadata, shown on review
- Mauve and Sky themes; custom theme import/export; date-format preference

### Fixed
- Enter in a library field accidentally starting a session
- Multi-selected sessions only dragging one at a time
- Import-backup confirmation hidden behind Preferences

## [0.5.0-alpha] - 2026-07-12

### Added
- Timecode Adjust and tag filtering on review
- Inline draft note row, session end-of-recording marker
- Multi-select sessions (shift-click), folder drag-and-drop
- Standard/Minimal and Tag Enter as toggle switches

### Fixed
- Tag-add menu failing to open
- A typed session title lost after changing folders

## [0.4.0-alpha] - 2026-07-11

### Added
- Minimal mode
- Add notes directly on review
- Collapsible Settings, drag-and-drop into folders

### Fixed
- Loading a saved session from the library

## [0.3.0-alpha] - 2026-07-10

### Added
- Projects & folders library
- Tags with colors
- Seven themes, start-time offset

## [0.2.0-alpha] - 2026-07-09

### Added
- Session titles, folders, basic library
- First tagging system

## [0.1.0-alpha] - 2026-07-08

### Added
- Running timecode, auto-stamped notes
- .txt and NLE marker .csv export
