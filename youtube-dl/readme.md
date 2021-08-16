# Youtube-dl

### Richiesta formati disponibili
```BASH
youtube-dl -F <video URL>
```
#### Youtube scarica video in diversi formati
Diversi formati di youtube.com

18  mp4 640x360    360p
22  mp4 1280x720   720p 

Video formato 720p
```BASH
youtube-dl -f 22 <video URL>
```
Video e sottotitoli automatici 
```BASH
youtube-dl -f 22  --write-auto-sub <video URL>
```
#### Solo sottotitoli automatic language
```BASH
youtube-dl --write-auto-sub --skip-download <video URL>
```
#### Solo sottotitoli in inglese en o italiano it
```BASH
youtube-dl --write-auto-sub --sub-lang it --skip-download <video URL>
```
### Estrazione mp3
```BASH
youtube-dl --extract-audio --audio-format mp3 <video URL>
```
