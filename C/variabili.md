```
Appunti liberamente tratti, per sostegno alla propria memoria, dal libro:
C programming language - B. Kerningan D. Ritche
```

## Le variabili

#### Dichiarazione

La dichiarazione di una variabile o funzione rende noto al compilatore il tipo.
Esempio la dichiarazione del prototipo di funzione o anche una semplice dichiarazione di varibile.

#### Definizione

La definizione di una variabile provoca anche da parte del compilatore
 l'allocazione di memoria che possa contenere quella variabile.  


#### Scope 

Lo scope è la porzione di programma nella quale è utilizzabile una variabile o una funzione. 
Lo scope è delimitato all'interno del codice dal blocco che contiene la dichiarazione della variabile. 
Un blocco di codice è delimitato da due parentesi graffe aperte/chiuse. 
Esempio una variabile definita all'interno di una funzione è accessibile solo all'interno della funzione 
e non crea conflitti con variabili omonime di altre funzioni.

Lo scope di una variabile esterna o una funzione va dal punto dove stata dichiarata fino al termine del file.

#### Variabili extern

La dichiarazione di una variabile extern indica al compilatore che sarà
 utilizzata una variabile che è stata definita (allocata memoria) altrove.

Esempio:
```C
extern int sp;
extern double val[];
```
Le dimensioni devono essere specificate nella definizione e sono opzionali 
nella dichiarazione. 

#### Varibili static

* La dichiarazione static applicata a una varibile esterna (Le variabili interne non possono essere viste da altre funzioni) o a una funzione ne limita l'uso soltanto nel file nel quale si travano. 

```C
static char buffer[BUFFERSIZE]
static int bufp = 0;
```

* La dichiarazione static applicata ad una variabile interna (automatica) consente alla variabile di mantenere il suo valore tra due chiamate successive della funzione che la contiene: non viene deallocata al termine del blocco di codice che la contiene.


#### Inizializzazione variabili

Le variabili esterne e le static sono inizializzate a zero dal compilatore quando sono definite. 
Le varibili automatiche non sono inizializzate dal compilatore e sono "sporche".

```C
int low = 0;
char * day[] = {"Lun", "Mar", "Mer", "Gio", "Ven", "Sab", "Dom"}; // warning in C++
char pattern[] = "ould";
```
Se la dimensione del vettore è omessa, il compilatore calcola la lunghezza in
base al numero di elementi presenti nella istruzione di inizializzazione.
 
***














