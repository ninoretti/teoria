# Funzioni

| [Indice](readme.md) | [Controllo flusso](flusso.md) | [Funzioni](funzioni.md) | [Strutture dati](strutture.md) | [Moduli](moduli.md) | [Moduli](moduli.md) | [I/O](io.md) | [Errori e eccezioni](errori.md) | [Classi](classi.md) | [Libreria STD](libreria.md)

### Le funzioni: le stringhe di documentazione
Il primo rigo contiene il sommario inzia con una lettera maiuscola e termina con un punto.
Si lascia una riga vuota e si scrive le convenzione di chiamata della funzione,
gli effetti collaterali ecc.
```PYTHON
>>> def my_function():
        """ Non fa nulla, ma lo documenta.
        
        Davvero non fa nulla.
        """
        pass
>>> print my_function.__doc__
Non fa nulla, ma lo documenta.
        
        Davvero non fa nulla.

```
### Una semplice funzione: Fibonacci 
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
#### Funzioni con argomenti arbitrari
Si usa l'operatore * (Ancora non è stato verificato ...)
```PYTHON
args = [3, 6]
range(* args)
```

### Forme Lambda

Una funzione senza nome ristretta ad una singola istruzione. 
`lambda a, b : a + b` somma i suoi due argomenti. Le forme lambda posso riferirsi
a variabili del proprio __scope che le contiene__
```PYTHON
>>> def make_increment(n):
        return lambda x: x + n
        
f = make_increment(42) # Qui è un assegnamento di referenza
                           # che permette di dare senso alla istruzione f(x)
f(0)                       # il valore che riceve lambda e che incrementa con 42
f(1)
```
```
https://pythontutor.com/render.html#code=def%20make_incrementator%28n%29%3A%0A%20%20%20%20%20%20%20%20return%20lambda%20a,%20b%3A%20a%20%2B%20b%20%20%2B%20n%0A%20%20%20%20%20%20%20%20%0Af%20%3D%20make_incrementator%2822%29%0Ax%20%3D%20f%280,5%29%0Aprint%28x%29%0Ax%20%3D%20f%281,7%29%0Aprint%28x%29&cumulative=false&curInstr=15&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=3&rawInputLstJSON=%5B%5D&textReferences=false
```






