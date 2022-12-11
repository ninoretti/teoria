# uso Git

git init 
    \\ inizializza la directory di lavoro

git clone https://github.com/ninoretti/C.git
    \\ scarica in locale il contenuto del repository
    
git remote add origin https://github.com/ninoretti/Arduino.git
    \\ aggiunge un server remoto

git remote -v 
    \\ visualizza il server remoto origin
    \\ origin	https://github.com/ninoretti/C

git add file 
    \\ aggiunge file o directory

git commit -m "Qui il messaggio" 
    \\ aggiunge il file nell'index

git push -u origin main
       \\ trasferisco i file sul repository

BRANCH
git branch <nome-branch>
    // crea un branch locale

git branch -m main
    // rename the current branch in main

git branch -D <local-branch> 
    //-D  forza la cancellazione

git branch -a 
    // visualizza tutti i branch remoti

git push origin --delete <nome-branch>
    // cancella un branch remoto

RIMUOVERE UN FILE DAL REPOSITORY

$ git rm somma.py
$ rm somma.py
Al prossimo commit, prodotto.php sparirà dai file del tuo repository.

RIMUOVERE UN FILE DALLO STAGE

git rm --cached file_da_togliere_.txt

    VARIABILI DI CONFIGURAZIONE
git config --list
    //Elenca tutte le variabili di configurazione.

git config --global -l
    //Elenca solo le variabili di configurazione globali.
    
git config --global user.name "lnx-K5"
git config --global user.email "lnx-K5@gmail.com"

// 11 luglio 2021

         
