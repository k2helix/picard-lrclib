# LRCLIB Lyrics Plugin for Picard

A MusicBrainz Picard plugin to fetch lyrics from [LRCLIB](https://lrclib.net) and save them to both **audio file metadata** and **.lrc sidecar files** for Jellyfin compatibility.


## Features
- 🎵 Fetches lyrics from LRCLIB's crowdsourced database — either **manually** or **automatically**
- 💾 Saves lyrics to:
  - `lyrics` metadata tag (for players like MusicBee/iTunes)
  - `.lrc` files (for Jellyfin, Plex, Kodi, etc.)
- ⚡ Optionally enable automatic lyric fetching whenever a track is loaded
- 🚫 Receive a confirmation prompt before overwriting existing `.lrc` files or `lyrics` metadata
- 🧹 Remove orphaned `.lrc` files that no longer have matching audio files

## Installation
1. **Download Plugin Files**:
   - Get the latest `.py` files from [**GitHub Releases**](https://raw.githubusercontent.com/izaz4141/picard-lrclib/refs/heads/main/lrcget.py)
   
2. **Install in Picard**:
   - Open Picard → `Options` → `Plugins`
   - Click `Install Plugin` 
   - Select the downloaded `.py` file(s)

## Usage
1. **Fetch Lyrics**  
   - **Automatic Fetching** (on track load):
     - Enable auto-fetch:  
       `Options` → `Plugins` → `LRCLIB Lyrics` → Check "Search for lyrics when loading tracks"

   - **Automatic Fetching**:  
     - Right-click track/album → `Get lyrics automatically with LRCLIB`
     
   - **Manual Fetching**:
     - Right click track/album → `Search lyrics manually with LRCLIB`

2. **Save Lyrics to Files**
   **After fetching**, you **must save the files** to write lyrics to metadata:  
   - Click the 💾 **Save** button in Picard’s toolbar, or press `Ctrl+S`  
   - Lyrics will be:  
     - Embedded into the audio file’s `lyrics` metadata tag  
     - Saved as a `.lrc` file in the same folder as the audio file

3. **Clean Orphaned LRC Files**:
   - Navigate to: `Options` → `Plugins` → `LRCLIB Lyrics`
   - Click the **"Clean Orphaned LRC Files"** button
   - Select your music library root directory
   - The tool recursively scans all subdirectories
   - Identifies `.lrc` files without matching audio files
   - Automatically removes orphaned `.lrc` files

## Compatibility
| Component           | Supported          |
|---------------------|--------------------|
| Picard Versions     | 3.0+ |
| Audio Formats       | All (MP3, FLAC, etc.) |
| Media Servers       | Jellyfin, Plex, Emby |
| Players             | MusicBee, Foobar2000, AIMP |

## Notes
- Lyrics are saved in UTF-8 encoding
- `.lrc` files match your audio filenames automatically
- Fetching on track load **never** overwrites existing lyrics
- Supported audio formats for cleanup: `.mp3`, `.flac`, `.m4a`, `.ogg`, `.opus`, `.wav`, `.wma`, `.aac`, `.ape`, `.mpc`, `.wv`

## Disclaimer
This plugin is unofficial. Always verify lyrics accuracy.
