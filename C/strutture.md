#### Strutture
Le strutture raggruppano un insieme di dati anche eterogenei.

Le strutture possono essere copiate, assegnate, indirizzate e manipolate con 
gli operatori punto. Non possono essere confrontate (nella loro totalità). 

La dichiarazione della struttura deve essere dichiarata al di __fuori del main__,
in genere in un file .h

Le variabili sono definite con le normali regole di scope.
```C
struct point {
    int x;
    int y;
};
```
Point è il __tag__ o identificativo della struttura, x,y,z sono variabili.
```C
struct point {
    int x;
    int y;
} x,y,z;
```
Allo stesso modo
```C
struct point p0,p1,p1;
```
Qui il tag point riferisce a quanto scritto precedentemente tra parentesi graffe

##### Inizializzazione
Al momento della dichiarazione
```C
struct point maxPoint = {320, 400};
```
Assegnamento con notazione puntatata
```C
p1.x = 300;
p1.y = 240;
```
#### Strutture nidificate
All'interno di una struttura può essere presente ancora un'altra struttura.
```C
struct rettangolo {
    struct point1;
    struct point2;
}
```
##### Inizializzazione
Al momento della dichiarazione
```C
struct rettangolo2 = {{2,4},{8,12}};
```
Assegamento con notazione puntata
```C
rettangolo.point1.x = 4;
rettangolo.point1.y = 8;
```
#### Puntatori a strutture
Se ad una funzione deve essere passata una struttura troppo grande, allora conviene
passa il puntatore alla struttura.
```C
struct point {
    int x;
    int y;
} * p;
// oppure anche
struct point * pt;
```
Per indirizzare i membri della struttura si usa
```C
(*p).x = 5;
p->x = 5;
```
Le parentesi sono necessarie in quanto __*__ ha priorità minore del __.__

dato il notevole uso si è introdotto l'operatore ->

```C
++p->x; //
```
Incrementa x e non p, -> ha priorità più alta rispetto a ++

#### Vettori di strutture
```C
struct point {
    int x;
    int y;
} triangolo[];
```
#####Inizializzazione
triangolo[] = {
    {0,1},{2,3},{4,5}
};
#####Assegnamento
```C
triangolo[0].x = 7;
triangolo[0].y = 9;
```
####Strutture ricorsive

.......

####Typedef
Typedef si usa per poter creare nuovi tipi
```C
typedef int Lenght;
```
Definisce il tipo Lenght (L maiuscola) come sinonimo di int
```C
typedef *char String;
```
Definisce String (S maiuscola) come sinonimo di * char

Qualche esempio più complesso
```C
typedef struct tnode * TreePtr;

typedef struct tnode {
    int x;
    char * word;
    TreePtr left;
    TreePtr right;
} TreeNode;
```
La prime dichiara tipo TreePtr puntatore a tnode

La seconda dichiara un tipo TreeNode come struttura con tag tnode.

La dichiarazione __typedef non crea un nuovo tipo__, assegna un nome diverso
ad un tipo esistente. Il __vantaggio di typedef__ è permettere di parametrizzare
il programma scritto. In caso di cambiamenti si modificano le istruzioni typedef.
 
####Union
Una union è una variabile che può contenere in diversi momenti variabili 
di tipo diverso. La sua dichiarazione è simile alle __struct__, il compilatore 
alloca alla union memoria che possa contenere la variabile più grande in 
occupazione di memoria
```C
union union_tag {
    int i;
    char * s;
    float f;
} u;
```
Il compito di trattare adeguatamente le variabili contenute spetta al programmatore.

##### Inizializzazione
```C
union union_tag w = {4};
```
#####Assegnamento
L'assegnamento avviene con la notazione puntata
```C
u.f = 123.123;
```
####Campi di bit
Può essere utile definire variabili di lunghezza minore di 8 bit.
```C
struct {
    unsigned int is_keyword : 1;
    unsigned int is_extern  : 1;
    unsigned int is_static  : 1;
} flags;
```
Definisce una variabile flag che contiene tre __field__ di un bit.











