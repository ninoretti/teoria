# Sed
Sed è un editor di stream, è usato per effettuare delle trasformazioni
al testo 

```
sed 's/morte/torte/' divina.txt
```
```BASH
echo $stringa | sed 's/regxpr/rimpiazzo/'
```


## Sostituzione testo
* E' sostituita sola la prima occorrenza trovata
```BASH
sed 's/regxpr/rimpiazzo/'
```

## Sostituzione globale
* g indica che la sostituzione e' eseguita ' per tutte le righe e non per la prima occorrenza
```BASH
sed 's/regexp/rimpiazzo/g'
```


## Cancella le righe
* Cancella le righe che soddistano una condizione
```BASH
sed '/regexpr/d'
```
__Cancella la riga n__
```BASH
sed 'nd' cancella la n riga
```


```BASH

```
