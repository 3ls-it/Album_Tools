## Album Tools  

August 2025: v0.2.1 with minor fixes. Need to update README.
August 2025: v0.2.0 Release with Beets integration!  

### About  

  `album-tools` is terminal based tool for managing your music collection, and downloading and/or creating music albums. It has been designed to meet my own needs. Your mileage may vary as your own needs and work flow are different than mine. If it's useful to you, Great! If you like it, and have suggestions/changes, let me know.  

  This started as a way for me to create a histogram of all the album dates in my collection, and grew into something else. (As often happens!)  
  
  It was built and is used on Unix-like systems and requires `FFMPEG` to do the reencoding and `yt-dlp` to download. Any site|service that `yt-dlp` supports, is supported by `album-tools`. As such, it is important to keep `yt-dlp` (and the other dependencies) up to date.  
   
  When downloading an album, the album art is downloaded with the tracks. The files are re-encoded (Ogg Opus by default), the filenames are pre-pended with the track number, and the track number is written to the metadata.  


### Installation

1. Download latest release  
   - Download the latest release and unpack the archive. This will create a directory with a name like `Album_Tools-0.1.x`
   - In a terminal change to this directory.

2. Install dependencies
   - If you don't have FFMPEG installed, install your OS's 'ffmpeg' package or build from source: https://ffmpeg.org/  
   - Install the Python dependencies:
   ```bash
   pip install -r requirements.txt
   ```  

3. Configure `album-tools`
   - Before using, you will need to set the correct values for these variables near the top of the `album-tools` script using your favourite text editor:  
   ```python
   ### -------- User settings -------- ###
   # Set 'music_root' to the full path to your music collection directory.
   # Include trailing slash
   music_root = '/full/path/to/your/music/directory/'
   # Set paths to your shell and `ffmpeg`
   SHELL = '/usr/bin/bash'
   FFMPEG = '/usr/bin/ffmpeg'
   # Set preferred supported encoding
   CODEC = 'opus'
   #CODEC = 'vorbis'
   #CODEC = 'mp3'
   ### ---------------- ###
   ```  
   - If you are unsure of the path to your shell (`bash`, `zsh`, `tcsh`, etc.) or the location of `ffmpeg`,  you can enter the following commands to find out:  

   ```bash
   env | grep SHELL
   ```  
   This will print the full path to the shell you are running.  
  
   ```bash
   which ffmpeg
   ```  
   This will print the full path to `ffmpeg`

4. Running `album-tools`
   - In the Album_Tools directory you can run `album-tools` with:  
   ```bash
   python3 album-tools
   ```  
  
  - Or you can also set `album-tools` to be executable:  
  ```bash
  chmod 750 album-tools
  ```  
  Then just run:
  ```bash
  ./album-tools
  ```  
  For convenience, you can copy the `album-tools` script to somewhere in your `$PATH`, e.g., `~/bin` or `~/.local/bin/`. What ever make sense in your environment.

  If needed, be sure to adust the path to `env` in the shebang statement, i.e., the first line of `album-tools`:
  ```python
  #!/usr/bin/env python3
  ```  

### Features

- Interactive terminal menu to manage your music collection
- List files in an album directory, view dates, and apply metadata changes in bulk
- Download audio from any source supported by yt-dlp with FFmpeg post-processing
- Download album covers or other files (with a progress bar!)
- Scrub directory and file names to remove disallowed characters
- Generate album-year histograms saved as PNG using matplotlib
- Escape to an interactive shell at any time from within the app for flexibility
- Tab-completion for filesystem paths while entering commands
- Coloured output for improved readability
- Configurable file format (Opus, Vorbis, MP3) with high-quality variable bitrate output


### Recommended Reading  
  
Media Players (Open Source, Ad Free):  
  - VLC (Multi-platform, My personal choice)  
    https://www.videolan.org/vlc/  
  - Fossify Music Player (Android)  
    https://f-droid.org/en/packages/org.fossify.musicplayer/ 
