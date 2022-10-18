# Rsync

E' utiizzato per il trasferimenti incrementale di file
tra due directory anche remote.

#### Sintassi

```BASH
rsync [option] /home/user/ user_remoto@host:/home/user_remoto
```
#### [Option]

+ ` -a ` rsync sincronizza ricorsivamente le directory, mantiene le date, i permessi e quantaltro.
+ ` -e ssh ` utilizza ssh per il trasferimento
+ ` -P ` mostra una progress bar
+ ` -p ` --quiet
+ ` -h ` human readable
+ ` --delete` cancella file estranei nella destinazione
+ ` -v ` verbose
+ `--max-size='100k'`






```BASH

```
