# Classi
| [Indice](readme.md) | [Controllo flusso](flusso.md) | [Funzioni](funzioni.md) | [Strutture dati](strutture.md) | [Moduli](moduli.md) | [I/O](io.md) | [Errori e eccezioni](errori.md) | [Classi](classi.md) | [Libreria STD](libreria.md)


## Tutto in python è un oggetto

* Il termine oggetto in python non significa necessariamente istanza di una classe.
Tutti i tipi in python condividono una parte della semantica che trova la
sua migliore descrizone nell'uso della parola oggetto --> tutto in python è un oggetto.

## Ambiti di visibilità e spazio dei nomi

La definzioni di classi modifica la visibilità degli oggetti e permette 
di ampliare lo spazio dei nomi. 

#### Lo spazio dei nomi
Lo spazio dei nomi è una mappa che collega i nomi agli oggetti a cui si riferiscono. 
Esempio di spazio dei nomi sono l'insieme dei nomi built-in ed i nomi delle eccezioni
built-in, i nomi globali dei moduli e il nome delle funzioni definite localmente dall'utente.
E' uno spazio dei nomi anche l'insieme degli attributi che definiscono un oggetto.

* Non c'è nessuna relazione tra nomi uguali di spazi di nomi diversi.

Gli utenti premettono al nome dell'oggetto il nome del modulo.

* `Attributo` qualsiasi nome che segue un punto. `z.real` real è attributo

Gli attributi possono essere a sola lettura o scribili.

#### Creazione e sopravvivenza dello spazio dei nomi
Lo spazio dei nomi che contiene i nomi built-in viene creato all'avvio
dell'interprete python e non viene mai cancellato. Anche lo spazio dei nomi globali
si comporta come i nomi built-in. Le istruzioni eseguite vengono considerate
parte del modulo `__main__` i nomi built-in sono anche parte di un moduolo `__builtin__`

* Funzioni locali. Lo spazio dei nomi di una funzione è creato al momento della
sua invocazione ed eliminato al termine della esecuzione della stessa.

#### Scope

Lo scope `è una regione del codice` di un programma python dove uno spazio dei
nomi è accessibile direttamente: un riferimento non completamente qualificato ad un nome
cerca di trovare tale corrispondenza nello spazio dei nomi.

###### Tre scope annidati

Sebbene gli scope siano determinati staticamente, sono usati dinamicamente.

* Scope interno contiene i nomi locali
* Scope mediano contiene le variabili globali. Se un nome non è presento nello scope
interno la ricerca prosegue sullo scope mediano.
* Scope esterno, in questo scope continua la ricerca, in esso sono contenuti i nomi
built-in

Lo scope locale o più interno si riferisce ai nomi locali della funzione corrente.
All'esterno della funzione, nel resto del codice, lo scope locale della funzione è riferito come scope globale: lo spazio dei nomi del modulo. 

* Lo scope globale di una funzione è lo spazione dei nomi del modulo che la contiene,
non importa da dove o con quale alias la funzione è chiamata. 

La definizione di una classe colloca ancora uno spazio di nomi nello scope locale.

* GLi assegnamenti non copiano dati, ma associano un nome collocato nello scope locale
con un oggetto. ` del 'x' ` rimuove l'associazione di x nello spazio dei nomi locale.


### Sintassi della definizione di una classe

Una classe si definisce cosi:
```PYTHON
class Complex:                          # nome della classe in maiuscolo
    """Una semplice classe """          # Commento 
    
    real = 0                            # due attributi
    imm = 0
    
    def stampa(self):                   # un metodo
        print("r = ", self.real, "; i = ", self.imm)
        
z = Complex()                           # istanziato un oggetto di nome z
z.stampa()                              # uso il metodo su un'istanza
```
* il metodo `__init__` inizializza l'oggetto instanziato a valori noti

```PYTHON
    def __init__(self, r, i):
        self.real = r
        self.imm = i
```

#### Oggetti istanza
In una semplice classe consederiamo la varibile istanza

```PYTHON
class MiaClasse:
    """ Una semplice classe """
    i = 10000
    def f(self):
        return "Ciao Mondo"
```
Il seguente codice usa la varibile x.count senza lasciare traccia
```PYTHON
x = MiaClasse()
x.count = 0
while x.count < 10:
    print(x.count)
    x.count += 2
del x.count
```
#### Oggetti metodo

Un metodo è una funzione che appartiene ad un oggetto. 
Nella classe `MiaClasse` istanziata in x, ` x.f() ` 

```PYTHON
print(x.f())        # stampa Ciao mondo
saluto = x.f()
print(saluto)       # stampa Ciao mondo
```
Il metodo ` x.f() ` è stato chiamato senza argomenti, anche se nella sua definizone
è presente: `self`. In realtà `self` è l'oggetto stesso del metodo che viene sempre
ad essere passato come primo argomento della funzione. In questo caso viene passato
con la notazione puntata.
* Questa è una notazione diversa
```PYTHON
MiaClasse.f(x)
```
In questa seconda notazione è evidente la creazione di un ` oggetto metodo `.
Un oggetto funzione ` f() ` viene ricercata all'interno della classe `MiaClasse` 
e impacchettata insieme all'oggetto parametro ` x ` creando l'oggetto metodo.

#### Note sparse

Gli attributi dato prevalgono sugli attributi metodo quando hanno lo stesso nome
```PYTHON
>>> x = MiaClasse()
>>> x.f = 434
>>> print(x.f)
434
```
Conviene utilizzare qualche convenzione per minimizzare i conflitti
* lettere maiuscole per i metodi
* un trattino basso per gli attributi
* verbi per i metodi, sostantivi per gli attributi


##### Una funzione può essere definita all'esterno di una classe

```PYTHON
def f(self, x, y)
    return x + y + self.i

>>> f(x, 4, 5)
1009
```

## Erediatrietà
La classe base rettangolo è ereditata dalla classe parallelepipedo con i suoi
attributi e i suoi metodi.
```PYTHON
class rettangolo:                       # Classe base
    base = 0
    altezza = 0
    def __init__(self, b, h):
        self.base = b
        self.altezza = h
    
    def area(self):
        return self.base * self.altezza

class parallelepipedo(rettangolo):      # classe derivata
    profondita = 0
    def __init__(self, b, h, p):
        self.base = b
        self.altezza = h
        self.profondita = p
        
    def volume(self):
        return self.base * self.altezza * self.profondita
 
rett_1 = rettangolo(3,4)
print("Area:", rett_1.area())

parall_1 = parallelepipedo(2,3,4)
print("Volume:", parall_1.volume())
print("Area parall:", parall_1.area())  # la classe derivata accede anche ai  
                                        # metodi della classe base
```
Output
```PYTHON
Area: 12
Volume: 24
Area parall: 6
```
Un metodo della classe può essere sovrascritto

### Erediatrietà multipla
```PYTHON
class NomeClasseDerivata(Base1, Base2, Base3):
    ....
    ....
    ....
```
La regola per la risoluzione dei nomi è: `prima in profondità` e poi `da sinistra a destra`
 se un attributo non è trovato nella classe derivata si controlla in Base1 e 
 in tutte le due classi basi, se non è trovato si procede ricorsivamente nelle classi
 base2 e base3 ...
 
 La regola `prima in larghezza` andrebbe a ricercare nella Base1, nella Base2, nella Base3
 e poi nelle classi basi delle classi corrispondenti. In tal modo dovrebbe esserci 
 una differenza tra gli attributi definiti e quelli derivati, cosa che non succede 
 con la regola  `in profondità`

Qui la `classe materia` ha come classi basi `peso` e `parallelepipedo`
a sua volta parallelepipedo a come classe base `rettangolo`

```PYTHON
class peso():
    densita = 0
    
    def pesare(self, volume):
        return volume * self.densita

class materia(peso, parallelepipedo):
    nome = ''
   
    def __init__(self, nome, densita, b, h, p):
        self.nome = nome
        self.densita = densita
        self.base = b
        self.altezza = h
        self.profondita = p
```






















