# ffmpeg

### Converte il formato
* Modifica da mov a mp4
```BASH
ffmpeg -i input.mov  -vcodec h264 output.mp4
```
### modifica il bitrate

* 4Mb/s

```BASH
ffmpeg -i input.mov -b:v 4M  -vcodec h264 output.mp4
```
### Modifica la risoluzione
* Si impostino i valori delle due varibili

```BASH
ffmpeg -i *mov -vf scale=$width:$height -vcodec h264 -b:v 2M due1280_720.mp4 
```
* `scale=$Width:-1` calcola il valore di height mantendo il rapporto originario
* `scale=-1:$height` viceversa

### Trasforma un video in GIF

```BASH
ffmpeg -i vid10.mp4 -r 10 -s 320x320 vid10.gif
```

#### Un ciclo bash utile
* Conserva il tempo di modifica e togli gli spazi nel nome del file
```BASH
bitrate=3M
for input in *.MOV; do
    data_modifica=$(stat -c %y "$input")
    output=$(echo $input | sed -e 's/.MOV//' -e 's/ /_/g')
    ffmpeg -i "$input" -b:v $bitrate -vcodec h264 $output.mp4
    touch -d "$data_modifica" $output.mp4
done
```







