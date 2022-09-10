# Le struttura

| [Indice](readme.md) | [Controllo flusso](flusso.md) | [Funzioni](funzioni.md) | [Strutture dati](strutture.md) | 

## Le liste

### Metodi degli oggetti lista

+ append(x) Aggiunge un elemento al fondo della lista
+ extend(L) Aggiunge in coda tutti gli elementi della lista L
+ insert(i, x)
+ remove(x) rimove l'occorrenza x se non è presente genera un errore
+ pop(i) estrae i-esimo elemento, se i non è presente estrae l'ultimo
+ index(x)
+ count(x) restituisce il numero di occorrenze di x nella lista
+ sort()
+ revevse()

#### Usare le lista come pile
```PYTHON
>>> stack = [2, 3, 5, 7, 11]
>>> stack.append(13)
>>> stack.append(17)
>>> stack.pop()
    17
>>> stack.pop()
    13
>>> stack
    [2, 3, 5, 7, 11]

```
#### Usare le lista come code
per estrarre il primo della lista si usa pop(0)
```PYTHON
>>> coda = [5, 7, 11]
>>> coda.append(13)
>>> coda.append(17)
>>> coda.pop(0)
    5
>>> coda.pop(0)
    7
>>> coda
    [7, 11, 13, 17]
```
## Strumenti per la programmazione funzionale
#### Filter
`filter(funzione, sequenza)` Restiruisce una sequenza per la quale è vera la funzione
```PYTHON
>>> def primi(x): return x % 2 !0 and x % 3 % 0 # calcola alcuni numeri primi
....
filter(primi, range(2, 25))
[2, 3, 5, 7, 11, 13, 17, 19, 23]
```
#### Map
`map(funzione, sequenza)` restiruisce una sequenza, applicando ad ogni elemento la funzione
```PYTHON
>>> def cube(x): return x * x * x
...
>>> map(cube, renge(1,11))
[1, 8, 27, 64, 125, 216, 343, 512, 729, 1000]

```
Può essere passata più di una sequenza, in questi casi la funzione deve avere
tanti argomenti quanti le sequenze
```PYTHON
>>> def somma(x,y): return x + y
...
map(somma, renge(0,8), range(0,8))
[0, 2, 4, 6, 8, 10, 12, 14]
```
#### Reduce 
`reduce(funzione, sequenza)` Applica la funzione a due argomenti ai primi due elementi della sequenza,
successivamente applica il risultato con il successivo elemento della sequenza.

```PYTHON
>>> def somma(x,y): return x + y
...
>>> reduce(somma, range(1, 11))
55
```

## Costruttori di liste
Per costruire una lista si utilizza la clausola `for` o `if`. 

Supponiamo di avere un vettore e calcolare i cubi degli elementi (senza usare map filter o reduce).
```PYTHON
>>> vettore = [2, 4, 8]
>>> [x*x*x for x in vettore]
[8, 64, 512]
```

Applica l'espressione se è verificata la condizone `if`
```PYTHON
>>> vettore = [2, 4, 8]
>>> [3*x for x in vettore if x > 3]
[12, 24]
```
Con le tuple sono necessarie le parentesi tonde
```PYTHON
>>> vettore = [2, 4, 8]
>>> [(x, 3*x) for x in vettore]
[(2,6), (4,12), (8,24)]
```
Con due for
```PYTHON
>>> pari = [2, 4, 8]
>>> dispari = [1, 3, 5]
>>> [x*y for x in pari for y in dispari]
[2, 12, 40]
# allo stesso modo
>>> [pari[i] * dispari[i] for i in range(len(pari))]
[2, 12, 40]
```
### Istruzione del
Per eliminare un elemento da una lista secondo il proprio indice
```python
>>> dispari = [2, 1, 3, 5]
>>> del dispari[0]
>>> dispari
[1, 3, 5]
# Eliminara una intera variabile
>>> del dispari
```

## Tuple e sequenze

Le stringhe e le liste hanno molte proprietà in comune: slice e indice. Le stringhe non 
sono modificabli le liste si. La tupla è composta da un certo numero di valori separati da una
virgola e non modificabili. 
```python
>>> t = 1, 3, 'ciao', 'sette'
>>> t
(1, 3, 'ciao', 'sette')
>>> t[3]
'sette'

# Tuple annidate
>>> pari = 2, 4, 6, 8
>>> dispari = 1, 3, 5, 7
>>> n = (pari, dispari)
>>> n
((2,4,6,8),(1,3,5,7))
```
#### Creare una tupla con zero o un elemento

```python
>>> tupleNulla = ()
>>> tuplaNulla
()
>>> tuplaUn0 = 3 ,     # la virgola trasforma in tupla e non in un intero
>>> tuplaUn0
(3,)
>>> len(tuplaUno)
1 
```
Il metodo append() non è applicabile alle tuple

#### impacchettamento e spacchettamento di tuple

`pari = 2, 4, 6, 8` Crea un impacchettamento in una tupla

`due, quattro, sei , otto = pari` spacchetta e assegna alle variabili

## Insiemi
Una collezione di dati non ordinata che non contiene dati duplicati
```python
>>> cestino = ['pere', 'mele', 'mele', 'arance', 'pere', 'banane']
>>> frutti = set(cestino)
>>> frutti
{'pere', 'arance', 'banane', 'mele'}    # notare le { } graffe
...
>>> 'pere' in frutti
True
```
Alcune operazione sugli insiemi
```python
>>> a = set('cosacivoletefare')
>>> a
{'r', 'a', 'l', 'e', 't', 'i', 'f', 'c', 'v', 'o', 's'}
>>> b = set('tutto')
>>> b
{'u', 'o', 't'}
>>> a & b
{'o', 't'}
>>> a ^ b
{'u', 'a', 'c', 'r', 'l', 'e', 'f', 'i', 'v', 's'}
```
## Dizionari
E' un insieme non ordinato di coppie `chiave, valore`: memoria associativa. 





















