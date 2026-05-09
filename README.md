# Ragnarok Effects List

A static catalog of Ragnarok Online visual effects, with preview videos, thumbnails, sound playback, metadata, and GRF file references.

This repository is designed to be published directly with GitHub Pages. The app runs entirely in the browser and does not require a backend.

## Catalog Contents

- 2,441 effect entries
- 2,234 video previews
- 1,954 thumbnails
- 780 MP3 audio files
- 775 effects marked as having sound
- 361 hidden/no-change entries

## Features

- Search by effect ID, description, type, or referenced GRF file name
- Filter by effect type: all, simple, continuous, unknown, sound, skipped, or hidden
- Hover over an effect card to preview its video and sound
- Toggle hidden effects
- Toggle GRF file names loaded by each effect
- Edit effect descriptions locally in the browser
- Export the edited metadata as JSON

Description edits are stored in `localStorage` until exported. They do not automatically modify `effects.json`.

## File Structure

```text
.
├── index.html      # Static catalog UI
├── effects.json    # Effect metadata used by the page
├── audio/          # MP3 audio previews
├── thumbs/         # PNG thumbnails
└── videos/         # WEBM video previews
```

## Running Locally

Open `index.html` in a browser, or serve the folder with any static file server.

Example:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

Using a local server is recommended because browser security rules can restrict `fetch('effects.json')` when opening HTML files directly from disk.

## Audio Format

Audio previews are stored as MP3 files to keep the page lightweight. The original WAV files were converted because they were too large for practical static hosting.

The page loads audio on demand when an effect is previewed. It keeps a small in-browser cache of recently used audio files so repeated previews start faster without loading every sound at once.

## Notes

Some effect entries may not have a thumbnail, video, or audio preview. Hidden entries are omitted by default and can be shown with the `Show hidden` toggle.

The GRF file names shown by the toggle are metadata references for the files used by each effect, including image assets and sound assets when available.

## Future Updates

- All game skill effects capture
- All str files in GRF folder