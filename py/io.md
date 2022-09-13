# Input Output

| [Indice](readme.md) | [Controllo flusso](flusso.md) | [Funzioni](funzioni.md) | [Strutture dati](strutture.md) | | [Moduli](moduli.md) | | [Strutture dati](strutture.md) | | [Moduli](moduli.md) | | [I/O](io.md)

## Formattazione output

Alcuni metodi
+ str() trasforma in stringa il parametro
+ repr() trasforma in formato comprensibile all'interpete
+ rjust(n) giustifica a destra in un campo di almeno n spazi
+ zfill()  inserisce ad una stringa numerica zeri a sinistra
```python 
>>> n = -3.15
>>> str(n).zfill(7)
'-003.15'
```

## Leggere e scrivere file
Aprire il file
```python 
mio_file = open('./primo.py', 'r')   # aperto in modalità lettura
mio_file.readline()                  # legge la prima linea
''                                   # se restituisce '' il file è finito
mio_file.seek(0)                     # posiziono il cursore sul primo byte                                      
mio_file.readline() 
'#! /usr/bin/env python\n'
```

