# Python

_Fonte "Tutorial di Python" Versione 2.3.4_

### Avviare python

#### Inteprete interattivo
Dalla riga di comando digitare python3
```BASH
python3
```
L'ambiente intreattivo termina con quit()

#### Script in una riga
Dalla riga di comando digitare python3 con opzione -c
```BASH
python3 -c "a, b = 3, 5; print(a * b)"
```
Le righe sono separate dal __;__

#### Lo script è contenuto in un file
```BASH
python3 mioscript.py
```
Gli argomenti allo script sono passati tramite la lista di stringhe `sys.argv`

#### Creare un file eseguibile in ambiente linux

La prima riga del file di testo che contiene lo script è
`#!/usr/bin/env python3`
Si rende eseguibile il file
`chmod +x mioscript.py`

### Codifica dei sorgenti in formato non ASCII

Quando sono usati caratteri non ASCII 
`SyntaxError: Non-ASCII character "\xc3" in file secondo.py`

inserire sotto la riga che contiene `#!`
```
# _*_ coding: iso-8859-1 _*_
```
In python3 non è necessario

### Commenti

`# Commento su singola riga `

```
"""Commento su più linee
"""
```

### Stringhe

stringa1 = 'Questa è una stringa racchiusa con apici singoli'
stringa2 = "Questa è una stringa racchiusa con apici doppi"

Stringa3 = "Questa è una stringa\
su più righe"

stringaDivina = "La bocca sollevò dal fiero pasto\n\
quel peccator, forbendola ai capelli\n\
del capo che elli aveva di retro guasto\n"










