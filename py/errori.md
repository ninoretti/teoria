# Errori e eccezioni
| [Indice](readme.md) | [Controllo flusso](flusso.md) | [Funzioni](funzioni.md) | [Strutture dati](strutture.md) | [Moduli](moduli.md) | [I/O](io.md) | [Errori e eccezioni](errori.md) | [Classi](classi.md) | [Libreria STD](libreria.md) | 

### Errori
+ Errori di sintassi

L'analizzatore sintattico (parser) rileva gli errori di sintassi:
```PYTHON
>>> while true print("Ciao mondo")
File "<stdin>", line 1, in ?
while true print("Ciao mondo")
               ^
SyntaxError: invalid syntax
```
Mancano i (':')

+ Eccezioni
Le eccezioni sono espressioni sintatticamente corrette, che presentano errori
durante l'esecuzione del codice.
```PYTHON
>>> 10 * (1/0)
ZeroDivisionError:

>>> 4 + spam * 3
nomeError: name 'spam' is not defined

>>> '2' + 2
typeError: cannot concatenate 'str' and 'int' object
```
Sono tre eccezioni built-in

### Gestire le eccezioni
Uso della clausola `try` e della clausola `except`
```PYTHON
while True:
    try:
        x = int(input("Scrivi un intero: "))
        break
    except ValueError:
        print("E' stato inserito un valore errato! Ritenta ... ")
print(x) 
```
+ Viene eseguita la clausola `try`, se non avviene nessuna eccezione la clausola 
`except` viene saltata. 
+ Se durante l'esecuzione di `try` è sollevata un'eccezione, se questa eccezione 
collima con quella trattata da `except` e l'esecuzione continua dopo il `try`
+ Se l'eccezione non collima con quella gestita, viene trasmessa a eventuali `try`
di livello superiore.

##### Clausola try con più except


```PYTHON


```
