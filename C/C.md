```
Appunti liberamente tratti, per sostegno alla propria memoria, dal libro:
C programming language - B. Kerningan D. Ritche
```
[indice](c.md)

[Variabili](variabili.md)

[puntatori](puntatori.md)

[preprocessore](preprocessore.md)


#### Argomenti della linea di comando
Il main accetta come parametri un array di stringhe.
```C
int main(int argc, char *argv[]) 
```
argc contiene il numero dei parametri passati dalla riga di comando.
char * argv[] contiene i puntatori alle stringhe passate dalla linea di comando

argv[0] contiene il nome del programma invocato mentre argv[argc] è NULL


