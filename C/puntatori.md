[indice](C.md)


#### Puntatori e Array
Un puntatore è una variabile (solitamente 8byte) che contiene l'indirizzo di una cella di memoria di un'altra variabile. 
Il compilatore deve conoscere il tipo del puntatore per delimitare la zona di memoria interessata e la sua codifica:
 1byte per i char, 4 byte per gli int, 8byte per i double ed altro
 
#### puntatore a void
Il puntatore di tipo void contiene un indirizzo di memoria ma non contiene informazioni sulla zona di memoria puntata,
 per questo motivo non può essere dereferenziato. Prima di essere derefernziato bisogna effettuare un cast
```C
 //La funzione malloc ritorna un puntatore void 
 // ad una determinata quantità allocata nello heap
 int * p ;
 p = (int *) malloc(sizeof(int));  // (int *) cast del puntatore
 * p = 20;
```
#### puntatore ad intero
```C
int numero = 10;  // definizione della variabile
int * p;         // dichiarazione di una variabile puntatore ad intero
p = &numero;    // assegnazione di un valore alla variabile puntatore -> 
                // contiene l'indirizzo della variabile numero
printf("%d\n", * p);  // per accedere al contenuto della varibile puntata 
                     // si deve dereferenziare il valore della variabile puntatore
```
#### Puntatore a carattere
```C
char nome[] = "Qui una stringa";  // definizione di una stringa di char
char * punt;                     // definizione di un puntatore a char (non è un puntatore a stringa)
punt = &nome[0]; // Assegna al puntatore il valore dell'indirizzo dell'array nome
printf("%d\n", * punt);   // dereferenziato il puntantore stampa l'intero 81 (Q)
printf("%s\n", punt);    // qui stampa la stringa in quanto è presente la direttiva %s
```
#### Artmetica dei puntatori
Sui valori contenuto nelle variabili puntatore è lecito effettuare sommme e sottrazioni
```C
int dim = 3;
// crea un array di tre interi nello heap
int p = (int *) malloc(dim * sizeof(int)); // alloca 3 * 4 byte di memoria
*p = 0; // assegna il valore 0 alla prima posizione
*(p++) = 1; // p++ incrementa di una unità (4byte) il valore contenuto in p
*(p++) = 2;
```
L'operatore * ha la stessa priorità di ++
```C
++*p; // incrementa di uno l'oggetto puntato da p
*p++; 
*p += 1; // come sopra
```
#### Puntatori e argomenti di funzione
Quando si vogliono modificare il valore degli argomenti di una funzione
si passano i puntatori agli argomenti
```C
swap(&x,&y);
// la funzione swap è cosi implementata
void swap(int * px, int * py) {
    int tmp = *px;
    *px = *py;
    *py = tmp;
}


```
#### Vettori di puntatori
I puntantori essendo varibili possono essere memorizzati in array.
```C
char * stringhe[12]; // array di 12 puntatori a char
// inizializza un array di puntatori a char
char * mesi[12] = {"Gen","Feb","Mar","Apr", "mag",
    "Giu","Lug","Ago","Set","Ott","Nov", "Dic"
}; 
for(int k=0; k<12;k++)
    printf("%s\n", mesi[k]);
```
Crea 10 interi e il vettore di 10 puntatori ad interi nello heap
```C
int n = 10;
// crea array di puntatori ad interi nello heap
int ** numeri = (int **)malloc(n*sizeof(int*));
// crea e inizializza i 10 interi nello heap
for(int k=0; k<n;k++){
    *(numeri +k)= (int *)malloc(sizeof(int));
    **(numeri +k) = k;
}
for(int k=0; k<n;k++)
    printf("%d\n", **(numeri + k));
```
#### Puntatori e vettori multidimensionali
Le due notazioni sono diverse benchè esse possono essere utilizzate
con la notazione a[3][4] e b[3][4]

```C
int a[10][20];
int *b[10];
```
a è un array bidimensionale di interi, b è un array di 10 di puntatori ad interi
Se si vuole che b punti ad un vettore di 20 elementi o si inizializza staticamente
o con il codice sotto scritto
```C
int numElementi = 20;
for(int k=0; k<10; k++){
    b[k] = (int *)malloc(numElementi*sizeof(int));
    for(int j=0; j<numElementi;j++)
        b[k][j] = (j+1)*(k+1);
}
```

#### Puntatori a funzione
Una funzione non è una varibile, tuttavia può essere dereferenziata con un puntatore
allo stesso modo come se fosse un array.
```C
#include<stdio.h>
int somma(int x, int y) 
{
    return x+y;
}
int differenza(int x, int y) 
{
    return x-y;
}

void main(void)
{
    int (* pFunz)(int, int);
    char op = '-';
    if(op == '+')
        pFunz = somma;
    else if (op == '-')
        pFunz = differenza;
    printf("%d\n", pFunz(5,7));
}
```
Il programma è composto da due funzione relativamente complesse: somma e 
sottrazione. 
All'inizio del main è dichiarato un puntatore a funzione __pFunz__.
La funzione puntata da __pFunz__ accetta due interi come argomenti e ritorna 
un intero. La parentesi (* pFunz) è necessaria altrimenti diventa 
la funzione denominata pFunz ritorna un puntatore ad intero.

#### Array di puntatori a funzione

Modificando la dichiarazione in puntatore a puntatori di funzioni 
che ritornano un interno e accettano come parametri due interi.
Anche qui le parentesi sono necessarie per legare l'operatore *
con il token pFunz
```C
#include<stdio.h>
int somma(int x, int y) 
{
    return x+y;
}
int differenza(int x, int y) 
{
    return x-y;
}

void main(void)
{
    int (*(* pFunz))(int, int); // Array di puntantore a funzione
    char op = '-';
    if(op == '+')
        pFunz[0] = somma;
    else if (op == '-')
        pFunz[0] = differenza;
    printf("%d\n", pFunz[0](5,7));
}
```
#### Passaggio di una funzione come parametro ad un funzione

Il programma è composto da tre funzioni somma, sottrazione e operazione.
La funzione operazione riceve tre parametri: due interi e __una funzione__.
La funzione passata come perametro, accetta due interi e ritorna un intero.


La funzione operazione è valida solo per testare il funzionamento
del meccanismo utilizzato; diversamente è superflua.
```C
#include<stdio.h>
int somma(int x, int y) 
{
    return x+y;
}
int differenza(int x, int y) 
{
    return x-y;
}
int operazione(int (*operatore)(int, int), int x, int y)
{
    return operatore(x,y);
}

void main(void)
{
    printf("Somma %d\n", operazione(somma,5,7));
    printf("Differenza %d\n", operazione(differenza,5,7));
}
```
Il meccanismo ha come difficoltà l'utilizzo delle parentesi () per associare
l'operatore * al nome della funzione e non al valore di ritorno.










