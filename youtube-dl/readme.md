# yt-dlp

[yt-dlp guida ufficiale](https://github.com/ytdl-org/yt-dlp/blob/master/README.md)

### istallazione

```BASH 
sudo wget https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp -O /usr/local/bin/yt-dlp
sudo chmod a+rx /usr/local/bin/yt-dlp 
```
Aggiorna
+ sudo yt-dlp -U

### Richiesta formati disponibili
```BASH
yt-dlp -F <video URL>
```
#### Youtube scarica video in diversi formati
Diversi formati di youtube.com

+ 18  mp4 640x360    360p
+ 22  mp4 1280x720   720p 

__Video formato 720p__
```BASH
yt-dlp -f 22 <video URL>
```
__Video e sottotitoli automatici__
```BASH
yt-dlp -f 22  --write-auto-sub <video URL>
```
#### Solo sottotitoli automatic language
```BASH
yt-dlp --write-auto-sub --skip-download <video URL>
```
#### Solo sottotitoli in inglese en o italiano it
```BASH
yt-dlp --write-auto-sub --sub-lang it --skip-download <video URL>
```
### Estrazione mp3
```BASH
yt-dlp --extract-audio --audio-format mp3 <video URL>
```
### Uno script utile
Usare un file con tutti i link da scaricare
```BASH
#!/bin/bash
#       Esempio di uso 
#       ./yt miofile -f 22
#       ./yt miofile --extract-audio --audio-format mp3

if [[ -z $1 ]]; then 
    echo "Manca il file dei link"
    exit -1
else 
    yt="yt-dlp "
    opt=$(echo "$2 $3 $4 $5 $6 $7 $8 $9")
fi
while read -r line; do
    echo "$yt $opt $line " >> tmpY
done < $1
date
bash tmpY
rm tmpY
date
```

## Playlist

```BASH
yt-dlp -i -f 22 --write-auto-sub --yes-playlist --playlist-end 5 /
'https://www.youtube.com/playlist?list=PLjUC8HjyxGTS_kWuWJLanHLAkkg6Lombb'
```

+ -i continue on download errors
 
+ --playlist-start NUMBER              
Playlist video to start at (default is1)

+ --playlist-end NUMBER                
Playlist video to end at (default is last)

+ --playlist-items ITEM_SPEC           
Playlist video items to download. Specify indices of the videos in the
playlist separated by commas like: "--playlist-items 1,2,5,8" 
if you want to download videos indexed 1, 2, 5, 8 in the playlist.
                                      
+ --playlist-items 1-3,7,10-13" 
it will download the videos at index 1, 2, 3,7, 10, 11, 12 and 13.

+ --no-playlist
Download only the video, if the URL refers to a video and a playlist.

+ --yes-playlist 
Download the playlist, if the URL refers to a video and a playlist.

#### Esempi utili con template
+ Download YouTube playlist videos in separate directory indexed by video order in a playlist
```BASH
$ yt-dlp -o '%(playlist)s/%(playlist_index)s - %(title)s.%(ext)s' /
https://www.youtube.com/playlist?list=PLwiyx1dc3P2JR9N8gQaQN_BCvlSlap7re
```
+ Download all playlists of YouTube channel/user keeping each playlist in separate directory:
```BASH
$ yt-dlp -o '%(uploader)s/%(playlist)s/%(playlist_index)s - %(title)s.%(ext)s' /
https://www.youtube.com/user/TheLinuxFoundation/playlists
```



