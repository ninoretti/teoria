# Controllo del flusso

| [Indice](readme.md) | [Controllo flusso](flusso.md) | [Funzioni](funzioni.md) | [Strutture dati](strutture.md) | [Moduli](moduli.md) | [Moduli](moduli.md) | [I/O](io.md) | [Errori e eccezioni](errori.md) | [Classi](classi.md) | [Libreria STD](libreria.md)

## If
```PYTHON
x = float(input("Scrivi un numero: "))
if x > 0:
    print("Il numero è maggiore di zero")
elif x == 0:
    print("il numero è nullo")
else:
    print("Il numero è negativo: ")
```

## Loop
#### for
For sugli elementi di una lista
```PYTHON
lst = ["Ciao", 123, "753", "Roma"]
for item in lst:
    print(item, end = " "), print(len(item))  # end = "" non c'è newline
```
Ancora for sugli elementi di una sequenza
```PYTHON
lst = ["Ciao", 123, "753", "Roma"]
for i in range(len(lst)):
    print(lst[i], end = ""), print(len(lst[i]))
```
#### while

```PYTHON
a, b = 0, 1
while b < 1000:
    print(b)
    a, b = b, a + b
```
#### Break, continue, pass, else
+ `break` esce dal ciclo: il ciclo è terminato
+ `continue` esce dalla iterazione corrente del ciclo: non esegue le restanti istruzioni del ciclo e rivaluta la condizione
+ `pass` istruzione nulla
+ `else` è eseguita al termine del ciclo se non c'è stato un `break`
  
Un ciclo while che non fa niente  
```PYTHON
while True:
    pass
```  
    
    
    
    
    
    
