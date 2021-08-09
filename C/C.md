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
## Il preprocessore

Il prepocessore applica la codice alcune funzionalità in una fare separata che precede la compilazione. 
Alcune delle funzionalità utilizzate sono definite dalle direttive *#define* *#include*

#### Include 

```C
#include "buffer.h"
#include <stdio.h>
```
La direttiva di preprocessore include nel file che contiene la direttiva i file specificati tra doppie virgolette e tra <...> . 
Se il nome del file è racchiuso tra le doppie virgolette, il file verrà ricercato partendo dalle directory corrente, 
se il nome è racchiuso tra <...> la ricerca dipende dal sistema utilizzato.

#### Define

Una direttiva define ha la forma:
```C
#define nome testo da sostituire
```
Lo scope di una define va dal punto dove è stato definito fino al termine del file che la contiene.
Le sostituzioni vengono effettuate soltanto sui token e non su testo contenuto in stringhe o sottostringhe.

Qualsiasi nome può essere sostituito da qualsiasi stringa, se la lunghezza di una stringa è maggiore del rigo si usa come fine riga /

Con #define si possono definire le **macro**
```C
#define max(A,B) ((A) > (B) ? (A) : (B))
```
Ogni occorrenza dei parametri A e B vengono sostituiti dai _parametri reali_
```C
x = max(p+q,r+s)
// sostituita con 
((p+q) > (r+s) ? (p+q) : (r+s))
```
In una istruzione cosi fatta i parametri sono valutati due volte (una nella condizione e una nel ramo oppurtuno dell'IF)
Se la macro è chiamata in questa forma max(x++, y++) si ottengono effetti non voluti (l'incremento di uno dei due parametri è effettuato due volte)

Le funzioni contenute in <ctype.h> sono realizzate con macro, si riduce l'overhead della chiamata a funzione.
La definizione di una  funzione può essere annullata con #undef (si assicura che sarà definita come scritto dopo la direttiva)

#### IF Define

La direttiva #if valuta una espressione costante e se non è verificata include la #define. E' utilizzata per includere solo una volta
i file header quando le #define possono essere utilizzate in differenti file. (Le varibili esterne 
e i i prototipi di funzione devo essere definite una sola volta)
```C
#if !define(BUFFER)
#define BUFFER
/* contenuto del di buffer.h*/
#endif
```
Questa direttiva permette di usare #define diverse
```C
#if SYSTEM == MacOs
 #define HDR "macos.h"
#elif SYSTEM = Windows
 #define HRD "windows.h"
#else 
 #define HRD "linux.h"
#endif
#define HRD
```
Invece di #if !define è altrimento usato __#ifndef__ (if not define) oppure __#ifdef__ (if define)



## Puntatori e Array
Un puntatore è una variabile (solitamente 8byte) che contiene l'indirizzo di una cella di memoria di un'altra variabile. 
Il compilatore deve conoscere il tipo del puntatore per delimitare la zona di memoria interessata e la sua codifica:
 1byte per i char, 4 byte per gli int, 8byte per i double ed altro
 #### puntatore a void
 Il puntatore di tipo void contiene un indirizzo di memoria ma non contiene informazioni sulla zona di memoria puntata,
 per questo motivo non può essere dereferenziato. Prima di essere derefernziato bisogna effettuare un cast
 ```C
 //La funzione malloc ritorna un puntatore void 
 // ad una determinata quantità allocata nello heap
 int * p ;
 p = (int *) malloc(sizeof(int));  // (int *) cast del puntatore
 * p = 20;
 ```
#### puntatore ad intero
```C
int numero = 10;  // definizione della variabile
int * p;         // dichiarazione di una variabile puntatore ad intero
p = &numero;    // assegnazione di un valore alla variabile puntatore -> 
                // contiene l'indirizzo della variabile numero
printf("%d\n", * p);  // per accedere al contenuto della varibile puntata 
                     // si deve dereferenziare il valore della variabile puntatore
```
#### Puntatore a carattere
```C
char nome[] = "Qui una stringa";  // definizione di una stringa di char
char * punt;                     // definizione di un puntatore a char (non è un puntatore a stringa)
punt = &nome[0]; // Assegna al puntatore il valore dell'indirizzo dell'array nome
printf("%d\n", * punt);   // dereferenziato il puntantore stampa l'intero 81 (Q)
printf("%s\n", punt);    // qui stampa la stringa in quanto è presente la direttiva %s
```
#### Artmetica dei puntatori
Sui valori contenuto nelle variabili puntatore è lecito effettuare sommme e sottrazioni
```C
int dim = 3;
// crea un array di tre interi nello heap
int p = (int *) malloc(dim * sizeof(int)); // alloca 3 * 4 byte di memoria
*p = 0; // assegna il valore 0 alla prima posizione
*(p++) = 1; // p++ incrementa di una unità (4byte) il valore contenuto in p
*(p++) = 2;
```
L'operatore * ha priorità più alta rispetto ++
```C
++*p; // incrementa di uno l'oggetto puntato da p
*p++; 
*p += 1; // come sopra
```








