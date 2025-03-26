  This command-line based tool is purely designed to meet my own needs. Your mileage may vary.  
  
  It was build and is used on Unix-like systems and requires `FFMPEG` to do the reencoding and `yt-dlp` to download. As such, any site|service that `yt-dlp` supports, is supported by `album_tools`. You will also need `wget` installed for downloading album cover art.    
   
  My personal choice of sound file is Ogg Vorbis. If you'd like to use this tool, but prefer a different file format, adjust this in the `rip_tmp` and `batch_rip` shell scripts by changing the file extension for the output file in the `FFMPEG` arguments.   
     
  At the top of `album_tools` you will need to provide the path to your music collection directory, as well as the path to `bash`, `wget`, and `yt-dlp`.  

  This started as a way for me to created a histogram of all the album dates in my collection, and grew into something else. (As often happens!)
