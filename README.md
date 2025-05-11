## Album Tools  

### About  

  `album-tools` is terminal based tool for managing your music collection, and downloading and/or creating music albums. It is designed solely to meet my own needs. Your mileage may vary as your own needs and work flow are different than mine. This started as a way for me to created a histogram of all the album dates in my collection, and grew into something else. (As often happens!)  
  
  It was build and is used on Unix-like systems and requires `FFMPEG` to do the reencoding and `yt-dlp` to download. As such, any site|service that `yt-dlp` supports, is supported by `album-tools`.  
   
  When downloading an album, the album art is downloaded with the tracks. The files are re-encoded (Ogg Vorbis by default), and the filenames are pre-pended with the track number.  

  Before using you will need to set the correct values for these variables:  
```python
music_root = "/path_to_your_music_collection/"
# Set paths
SHELL = '/usr/bin/bash'
FFMPEG = '/usr/bin/ffmpeg'
# Set bit-rate and encoding
BITRATE = '192' # 128, 192, 256, ...
CODEC = 'vorbis' # 'vorbis' or 'mp3' 
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
