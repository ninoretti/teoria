```
Appunti liberamente tratti, per sostegno alla propria memoria, dal libro:
C programming language - B. Kerningan D. Ritche
```
[indice](c.md)

[Variabili](variabili.md)

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
+ Array di puntatore a funzione
+ Passaggio di una funzione come parametro

[preprocessore](preprocessore.md)


#### Argomenti della linea di comando
Il main accetta come parametri un array di stringhe.
```C
int main(int argc, char *argv[]) 
```
argc contiene il numero dei parametri passati dalla riga di comando.
char * argv[] contiene i puntatori alle stringhe passate dalla linea di comando

argv[0] contiene il nome del programma invocato mentre argv[argc] è NULL


