#### Strutture
Le strutture raggruppano un insieme di dati anche eterogenei.
La dichiarazione della struttura deve essere posta al di __fuori del main__.
Le variabili sono dichiarate come con la regola di scope.
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




