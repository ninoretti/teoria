# Funzioni

[ [Indice](readme.md) ][ [Controllo flusso](flusso.md) ][ [Funzioni](funzioni.md) ][

```PYTHON
def fib(n):     # Definisce una funzione
    "Stampa una serie di Fibonacci fino a n"  # docstring
    a, b = 0, 1
    while b < n:
        print(b, end = " ")  # non c'è newline
        a, b = b, a + b

fib(1000)       # chiama la funzione con parametro 1000

1 1 2 3 5 8 13 21 34 55 89 144 233 377 610 987 
```
Si può obiettare che fib(n) è una procedura e non una funzione, in quanto
non restituisce nessun valore (restituisce un None non normalmente visibile).

##### Ecco la funzione fib2(n)
```PYTHON
def fib2(n):
    "Calcola i numeri di Fibonacci fino a n e ritorna la lista dei valori"
    lista = []               # Crea una lista vuota
    a, b = 0, 1
    while b < n:
        lista.append(b)      # Inserisce il risulato dentro la lista
        a, b = b, a + b
    return lista
f1000 = fib2(1000)           # chiama la funzione
f1000                        # visualizza i risultati
```

## Argomenti delle funzioni

Le funzioni possono avere un numero variabile di argomenti

#### Uso di valori predefiniti per gli argomenti


```PYTHON
def ask_ok(prompt, retries = 4, complaint = "Si o No, grazie!"):
    while True:                                     # Ripete sempre
        ok = raw_input(prompt)
        if ok in ('s', 'si', 'sì'): return True     # Esce dalla funzione
        if ok in ('n', 'no', 'No'): return False    # Esce dalla funzione
        retries = retries -1
        if retries < 0: raise IOError
        print(compilant)
        
ask_ok('Vuoi leggere? ')
```
#### Uso di argomenti con parole chiavi
Qui è stato passato un argomento con un valore predefinito diverso.
E' necessario dichiare la parola chiave, diversamente si genera un errore.
```
ask_ok('Esci? ', complaint = 'Rispondi si o no!')  # inserisco anche il nome
```
#### La funzione range()
La funzione range() si chiama con un numero di argomenti variabili

```PYTHON
>>> range(10)
0 1 2 3 4 5 6 7 8 9
>>> range(5, 10)
5, 6, 7, 8, 9
>>> range(-10, -100, -30)
-10, -40, -70
```
I valori predefiniti sono inizio = 0, e passo = 1
```PYTHON
def range(x, inizio = 0, passo = 1):
    ...
```


##### I valori predefiniti sono valutati solo al momento della definizione della funzione

```PYTHON
def foo(a, L = []):
    L.append(a)
    return L  
print (foo(1))        # la funzione sarà chiamata tre volte
print (foo(2))
print (foo(3))
```
Spampa. L punta a una lista vuota alla prima valutazione, nelle successive chiamate non sarà
riassegnata la lista vuota, soltanto si esegue l'operazione di append su un oggetto lista
che nel frattempo è stato modificato.
```PYTHON
[1]
[1, 2]
[1, 2, 3]
```
#### Qui il comportamento è diverso
```PYTHON
def foo(a, L = None):
    if L is None:
        L = []
    L.append(a)
    return L
print (foo(1))        # la funzione sarà chiamata tre volte
print (foo(2))
print (foo(3))
```
Spampa. Ad ogni chiamata di funzione la lista L è impostata a []
```PYTHON
[1]
[2]
[3]
```




```PYTHON

```
