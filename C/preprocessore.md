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


