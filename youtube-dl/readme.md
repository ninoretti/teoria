# Youtube-dl

### Richiesta formati disponibili
```BASH
youtube-dl -F <video URL>
```
#### Youtube scarica video in diversi formati
Diversi formati di youtube.com

+ 18  mp4 640x360    360p
+ 22  mp4 1280x720   720p 

__Video formato 720p__
```BASH
youtube-dl -f 22 <video URL>
```
__Video e sottotitoli automatici__
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
    yt="youtube-dl "
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



