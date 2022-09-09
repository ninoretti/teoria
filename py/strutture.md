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



