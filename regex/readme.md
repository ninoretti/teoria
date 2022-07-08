# Regular expression

Un espressione regolare è un pattern che descrive un insieme di stringhe

* L'espressione regolare più semplice è composta da un singolo carattere

l'espressione `a` descrive tutte le stringhe {a}

### Metacaratteri Basic regular expression 

* _._ un qualsiasi carattere
* _exp__*___ zero o più occorrenze di exp
* ___^__exp_ stringhe che iniziano con exp
* _exp$_ stringhe che terminano con exp
* ___\<__esp_ inizio di una parola
* _exp__\>___ fine di una parola
* _exp__{N}___ exp compare N volte
* _exp__{N,}___ exp compare almeno N volte
* _exp__{N,M}___ exp compare almeno N volte e meno di M volte
* _[[:CLASS:]]_ un carattere della classe
* _[[:alpha:]]_ tutte le lettere
* _[[:alnum:]]_ lettere e numeri
* _[[:digit:]]_ numeri
* _[[:upper:]]_ maiuscole
* _[[:lower:]]_ minuscole
* _[:xdigit:]_ 
* _[:space:]_
* _[:print:]_
* _[:punt:]_


### Metacaratteri Extended regular expression

Utilizzare l'opzione `-E` 

* _exp__+___ una o più occorrenze di exp
* _exp__?___ zero o una occorrenza di exp
* _exp1 __|__ exp2_
* ___(___ _exp_ ___)___



