## Album Tools  

### About  

  `album-tools` is terminal based tool for managing your music collection, and downloading and/or creating music albums. It is designed solely to meet my own needs. Your mileage may vary as your own needs and work flow are different than mine. This started as a way for me to create a histogram of all the album dates in my collection, and grew into something else. (As often happens!)  
  
  It was built and is used on Unix-like systems and requires `FFMPEG` to do the reencoding and `yt-dlp` to download. As such, any site|service that `yt-dlp` supports, is supported by `album-tools`.  
   
  When downloading an album, the album art is downloaded with the tracks. The files are re-encoded (Ogg Vorbis by default), and the filenames are pre-pended with the track number.  

### Installation and Usage

1. Download latest release  
   - Download the latest release and unpack the archive. This will create a directory with a name like `Album_Tools-0.1.x`
   - In a terminal change to this directory.

2. Install dependencies
   - If you don't have FFMPEG installed, install your OS's 'ffmpeg' package or build from source: https://ffmpeg.org/  
   - In the Album_Tools directory, install the Python dependencies:
   ```bash
   pip install -r requirements.txt
   ```  

3. Configure `album-tools`
   - Before using, you will need to set the correct values for these variables near the top of the `album-tools` script using your favourite text editor:  
   ```python
   music_root = "/path_to_your_music_collection/"
   # Set paths
   SHELL = '/usr/bin/bash'
   FFMPEG = '/usr/bin/ffmpeg'
   # Set bit-rate and encoding
   BITRATE = '192' # 128, 192, 256, ...
   CODEC = 'vorbis' # 'vorbis' or 'mp3' 
   ```  
   - If you are unsure of the path to your shell (`bash`, `zsh`, `tcsh`, etc.) or the location of `ffmpeg`,  you can enter the following commands:  

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
  
  - You can also set `album-tools` to be executable:  
  ```bash
  chmod 750 album-tools
  ```  
  Then just run:
  ```bash
  ./album-tools
  ```  

  If needed, be sure to adust the path to `env` in the shebang statement; the first line of `album-tools`:
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
- Escape to an interactive shell at any time from within the app
- Tab-completion for filesystem paths while entering commands
- Coloured output for improved readability
- Configurable file format (OGG, MP3) and bitrate settings
