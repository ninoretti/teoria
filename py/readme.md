# Python
_Fonte "Tutorial di Python" Versione 2.3.4_

[ [Indice](readme.md) ][ [Controllo flusso](flusso.md) ][ [Funzioni](funzioni.md) ][

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
```PYTHON
# _*_ coding: iso-8859-1 _*_
```
In python3 non è necessario

### Commenti

`# Commento su singola riga `

```PYTHON
"""Commento su più linee
"""
```

### Stringhe
```PYTHON
stringa1 = 'Questa è una stringa racchiusa con apici singoli'
stringa2 = "Questa è una stringa racchiusa con apici doppi"
```
#### Stringa su più linee
Il carattere `\` indica che la stringa continua alla riga successiva, il carattere
__\n__ indica di andare a capo
```
stringaDivina = "La bocca sollevò dal fiero pasto\n\
quel peccator, forbendola ai capelli\n\
del capo che elli aveva di retro guasto\n"
```
#### Stringa raw
Nella stringa raw non sono necessari \n e \ diversamente saranno resi visibili
come fossero caratteri ordinari. 

```PYTHON
stringaRaw = r"Trasumanar significar per verba
non si poria; però l'esemplio basti
a cui esperienza Grazia serba."
```

#### Stringe con uso delle triple """  o ''' 
```PYTHON
longString = """Trasumanar significar per verba
non si poria; però l'essemplo basti
a cui esperienza grazia serba.
"""
```

### Indicizzazione delle stringhe
```PYTHON
parola = "Commedia" 
>>> parola[4]
'e'
>>> parola[0:2]
'Co'
>>> parola[2:4]
'mmedia'
>>> parola[:2]
'Co'
>>> parola[2:0]
'mmedia'
>>> parola[-1]
'a'
>>> parola[-2]
'ia'
>>> parola[0:-2]
'Commed'
>>> parola[:-2]
'Commed'
```
Le stringhe non possono essere modificate `parola[0] = P` non è consentita.

#### Qualche errore:
```PYTHON
>>> parola[10]  # errore out of range
>>> parola[-100] # errore
```
### Non sono errori
```PYTHON
>>> parola[0:10]
'Commedia'
>>> parola[-100:12] 
'Commedia'
```
### Concatenazione delle stringhe
```PYTHON
"Divina" + commedia
"La Divina " + parola[0:7] + " di Dante"

```
#### Lo schema della indicizzazione 

```
+---+---+---+---+---+---+---+---+
| C | o | m | m | e | d | i | a |
+---+---+---+---+---+---+---+---+
  0   1   2   3   4   5   6   7
 -8  -7  -6  -5  -4  -3  -2  -1
 -0 
```
### Stringhe Unicode
```PYTHON
>>> stringaUnicode = u"Questa\u0020è\u0020una\u0020stringa\u0020Unicode"
u'Questa è una stringa Unicode'
```
#### Stringa Unicode raw
Applica la codifica Unicode nel caso le barre oblique siano dispari
```PYTHON
>>> stringaUnicodeRaw = ur"Ciao\\u0020Mondo"
u'Ciao\\u0020Mondo
```
La modalità raw è utile nelle espressioni regolari

## Liste

Le liste sono raggruppamenti ordinati di valori modificabili composti

```PYTHON
>>> lst = ["Ciao", 123, "753", "Roma"]
>>> lst
["Ciao", 123, "753", "Roma"]
```
Gli elementi della lista sono individuati con gli indici

```PYTHON
>>> lst[0]
'Ciao'
>>> lst[1:-1]
[123, "753"]
```
#### Le liste sono modificabili
Assegnamento di un nuovo valore
```PYTHON
lst[1] = lst[1] + 630
lst[0] = "Salve"
```
Rimpiazza alcuni elementi (Assegnamento multiplo)
```PYTHON
lst[0:2] = ["Ave", -44]
```
Rimuove alcuni elementi 
```PYTHON
lst[1:3] = []
```
Inserisce alcuni elementi
```PYTHON
lst[1:1] = ["Alma", "Mater"]
```
Inserisce una copia di se stessa all'inizio
```PYTHON
lst[:0] = lst
```
### Liste annidate
```PYTHON
uno = ["one", 1]

vero = ["true", 1, "1"]

lst = [uno, vero, due, "Mio"]
>>> lst 
[['one', 1], ['true', 1, '1'], ['two', 2], 'Mio']
```
Uso di len() e append()
```PYTHON
uno.append("1")
>>> lst 
[['one', 1, '1'], ['true', 1, '1'], ['two', 2], 'Mio']
>>> len(lst)
4
```

### Esempio di uso di python
Fibonacci i primi 19 numeri

```PYTHON
a, b = 0, 1
while b < 1000:
    print(b)
    a, b = b, a + b
```








