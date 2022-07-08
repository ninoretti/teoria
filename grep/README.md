# Grep
Stampa le linee che verificano un pattern

* Quando grep legge direttamente il file `grep 'r' divina.txt`
```
grep [opzioni] pattern [file]
```
* Se il file non è specificato legge il file di input
```BASH
ls -l | grep mp4
```

### Opzioni
```
-E : --extended-regexp
-A num : stampa anche le num righe successive ([A]fter) ad ogni corrispondenza.
-B num : stampa anche le num righe precedenti ([B]efore) ad ogni corrispondenza.
-i : case insensitive
-n : numero di riga del file
-c : numero di occorrenze nel file
-v : inverte la corrispondenza -> Stampa le righe che non corrispondono
-H : print filename per ogni corrispondenza
-h : no print file name for every match
-l : stampa soli i nomi dei file che corrispondono
-L : stampa i nomi dei file che non corrispondono
```





