This document is a work in progress checklist of sorts for if/when I ever enable community uploads to the archive. I want to keep everything consistent in terms of file structure, much easier to keep things tracked and organized.

I'm working on the goal of "1 tape per show", sourcing uploads from various places and users who send them over. After that, I might allow others to upload alt. sources or new tapes when they release.

## Quality
Only FLAC will be accepted as part of the archive unless a tape does not circulate as such. 

## Verification
All files to be uploaded must verify correctly using something like TradersLittleHelper. Save this step for last after renaming, as they won't match with different names.

## Documentation
All submitted files *must* have an info.txt file at the very least. Most bootlegs come with some form of this file. If a tape doesn't have one, you can either find it on SpringsteenLyrics, or create one using the template provided.

## File tagging
All files uploaded *must* be tagged properly. This can be done using software like MP3Tag, or any other tagging software.

Tracks must be tagged with the "proper" song name as listed on Brucebase or my own Database. "Intros/Tuning" can just be labelled as such, if they have a provided name (like EV2 likes to do), then tag like `Intro / "Name"`. If multiple songs are included in a track (and they're supposed to be), then have all names separated by single segue arrows `Not Fade Away > She's the One`. Songs like the "Detroit Medley" should also be named like that.

The artist should be set to `Bruce Springsteen & [BAND]`, unless that band is credited otherwise like Dr. Zoom or The BSB. Then just have that as the artist name. Artists should also be listed in title/capitialized case.

Some examples:
- E Street -> Bruce Springsteen & The E Street Band
- Castiles -> The Castiles

## File naming
This is still not finalized. Up to now I've been doing `DISC-TRACK00 - [SONG]`. This presents some issues with longer track names, especially in regards to some operating systems which can't handle long file paths well. I've been considering switching to the etree naming standard of `bsYYYY-MM-DDdXXtXX.ext`, as all of those names are short. This will only be if the files are properly tagged like above.

## Folder naming
I go into this in the guidelines document I keep meaning to publish. Folders must be named in accordance with those guidelines, the basic form of which is `bsYYYY-MM-DD.type.uploader/label.format`.

## Additional files

### Artwork
Any included images must be names following [this page](https://musichoarders.xyz/reference/naming-scans/). If there is no artwork, check on both SpringsteenLyrics and also Jungleland.it. If none can be found, one could make their own if they're able to. Otherwise, just include none.

### "Housekeeping Files"
These are things like checksum, fingerprint, riplogs, and spectral images. 

The checksum/fingerprint files can be created using a tool called TradersLittleHelper, and saved with the name "fingerprint". These can only be created after file naming is done, as the tool searches by file name. So, make sure that is all set.

Riplogs are usually only included with CD rips. Name them like "Disc XX.log", if the file names don't match that should be okay. They're not used for verification like the fingerprint files, and usually are just a record of how tracks ripped.

Spectral images can be kept as-is. Not as important as those can be generated at any time if needed using tools like Spek.

## Uploading
You can either use the Internet Archive Web Uploader, the python library, or the command line uploader. The web uploader is slow and quite finicky, the command line/python library have a bit of a learning curve, but are much faster. Each has pros and cons, and I might provide my python upload script to help with this. 

### What if files don't verify?
This is a recent issue that came up. If a file doesn't verify in TLH/other tools, you can use a tool called "FFMPEG" to fix it simply by reencoding it at the same bitrate/resolution.

The basic command should be something like `ffmpeg -i INPUT -c copy OUTPUT`, this can't be done in-place, meaning the output name has to be different, but it can be easily renamed afterwards. 

### Scripts to create:
- Python uploader script
- File verify script
- FFMPEG reencode folder script
- Fingerprint/Checksum script
