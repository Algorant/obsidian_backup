
- I did this method to fix [[Robots and Empire]], as it was not really available in a good quality #audiobooks format.
- Update on 04/03/2024: I also did this for the last [[Foundation]] novel, which is Forward the Foundation.


#### Methodology
- Get best quality audio (I found it on Youtube and used [[pytube]] to download it), it got them as #mp4 format
- Convert the audio to m4a format
- Get the breakpoints in 00:00:00 format for where the chapters are. For this book youtube already had them in the description
- Use [[ChatGPT]] to format a metadata.txt file for #ffmpeg to understand. [[ffmpeg]]
- Use #ffmpeg to create those breakpoints and save to #m4b format
- Test that they worked correctly in vlc (it will show chapter breaks in the scroll bar)
- Upload to Plex using rsync
	- ` rsync -av Forward_the_Foundation_P1.m4b Forward_the_Foundation_P2.m4b "incertophile@lyra.usbx.me:/home/incertophile/media/Books/Isaac Asimov/Forward_the_Foundation"`
	- 
- Note: I did this in two parts, but even so Plex was able to concatenate them together into one #audibook 