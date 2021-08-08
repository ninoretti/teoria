
## Dichiarazione

La dichiarazione di una variabile o funzione rende noto al compilatore il tipo.
Esempio la dichiarazione del prototipo di funzione o anche una semplice dichiarazione di varibile.

## Definizione

La definizione di una variabile provoca anche  da parte del compilatore
 l'allocazione di memoria che possa contenere quella variabile.  


## Scope 

Lo scope è la porzione di programma nella quale è utilizzabile una variabile o una funzione. Lo scope è delimitato all'interno del codice dal blocco che contiene la dichiarazione della variabile. Un blocco di codice è delimitato da due parentesi graffe aperte/chiuse. 
Esempio una variabile definita all'interno di una funzione è accessibile solo all'interno della funzione e non crea conflitti con variabili omonime di altre funzioni.

Lo scope di una variabile esterna o una funzione va dal punto dove stata dichiarata fino al termine del file.

## Variabili extern

La dichiarazione di una variabile extern indica al compilatore che sarà
 utilizzata quella variabile definita (allocata memoria) altrove.

Esempio:
```C
extern int sp;
extern double val[];
```



