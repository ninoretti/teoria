# scp

### Sintassi
```BASH
scp [OPTION] [user@]SRC_HOST:]file1 [user@]DEST_HOST:]file2
```

#### Option

* `-p` preserva gli attributi di modifica e di accesso
* `-q` quiet
* `-r` ricorsivo
* `-l` limita la banda in Kbit/s
* `-v` verbose


```BASH
scp -r /home/lnx/bk lxx@10.1.1.11:/remote/bk
```
