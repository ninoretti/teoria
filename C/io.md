[indice](readme.md)

#### Accesso a file
##### fclose()
Chiude il file aperto in precedenza, svuota il buffer associato.
Soltanto se si effettua la chiusura del file (senza ritorno di errori) si ha la 
certezza che i dati sono stati scritti.

__int fclose(*fp);__ ritorna 0 se la chiusura ha avuto buon fine.
```C
if ( fclose(*fp) != 0 ) {
    fprintf(stderr, "Error closing input file.\n");
    return -2;
}
```
E' buona norma chiudere il file quando non è più necessario.

##### fopen()
La funzione fopen() apre un file con diverse modalità e ritorna un puntatore.
```C
    FILE * fopen(char *, char * mode);
```
```C
FILE * fp;
fp = fopen()
```
```C
    if(fp == NULL) {
        fprintf(stderr,"Errore nella apertura file\n");
        return -1;
    }
```
Il __parametro mode__ può assumere i seguenti valori:

+ "r": il file è aperto in sola lettura. La posizione è impostata all'__inizio del file__. Restituisce un errore se il file non esiste.
+ "r+": il file viene aperto in lettura/scrittura. La posizione è impostata all'inizio del file. Restituisce un errore se il file non esiste.
+ "w": il file viene aperto in scrittura. La posizione è impostata all'__inizio del file__. 
Se il file non esiste, viene creato; 
se invece il file esiste, ne viene cancellato il contenuto.
+ "w+": il file viene aperto in lettura/scrittura. La posizione è impostata all'__inizio del file__. Se il file non esiste, viene creato; se invece il file esiste, ne viene cancellato il contenuto.
+ "a": il file viene aperto in scrittura (modalità append). La posizione è impostata alla __fine del file__. Se il file non esiste, viene creato; se invece il file esiste, il contenuto viene conservato ed i nuovi dati scritti vengono aggiunti.
+ "a+": il file viene aperto in lettura/scrittura (modalità append). La posizione di lettura è impostata all'__inizio del file__, mentre la scrittura è permessa solo alla fine del file. Se il file non esiste, viene creato; se invece il file esiste, il contenuto viene conservato inalterato ed i nuovi dati scritti vengono aggiunti.

##### Stream file di default
stdin, stdout, strerr

##### fprintf()
Funzione che permette di scrivere su un file.
```C
int fprintf(FILE * fp, char *format, ...);
```

##### fscanf()
Funzione che permette di leggere da un file.
```C
int fscanf(FILE * fp, char * format, ...)
```





