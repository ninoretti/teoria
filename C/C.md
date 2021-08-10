```
Appunti liberamente tratti, per sostegno alla propria memoria, dal libro:
C programming language - B. Kerningan D. Ritche
```
[indice](c.md)

[Variabili](variabili.md)
+ Dichiarazione
+ Definizione
+ Scope
+ Varibili _extern_
+ Variabili _static_
+ Inizializzazione
+ 

[puntatori](puntatori.md)
+ Puntatori e array
+ Puntantore a void
+ Puntatore ad intero
+ Puntantore a char
+ Aritmetica dei puntatori
+ Puntatori e argomenti di funzioni
+ Vettori di puntantori
+ Puntatori a vettori multidimensionali
+ Puntantori a funzioni
+ Array di puntatori a funzione
+ Passaggio di una funzione come parametro

[preprocessore](preprocessore.md)
+ Include
+ Define
+ IF Define


#### Argomenti della linea di comando
Il main accetta come parametri un array di stringhe.
```C
int main(int argc, char *argv[]) 
```
argc contiene il numero dei parametri passati dalla riga di comando.
char * argv[] contiene i puntatori alle stringhe passate dalla linea di comando

argv[0] contiene il nome del programma invocato mentre argv[argc] è NULL


