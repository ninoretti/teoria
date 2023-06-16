# mysql

* Accesso dalla riga di comando
```
mysql -u utente -p
```
* Visualizza i database presenti
```
mysql> show databases;
```
* Crea un database 
```
mysql> CREATE DATABASE IF NOT EXISTS prova;
mysql> create database if not exists prova \G
```
* Usa il database
```
use prova;
```
* Mostra il database di default
```
mysql> SELECT DATABASE();
```
* Mostra le taballe
```
mysql> show tables;
```
* Crea tabella
```
mysql> CREATE TABLE autori (
    -> id_aut INT UNSIGNED NOT NULL auto_increment,
    -> nome CHAR(20) not null,
    -> cognome CHAR(20) NOT NULL,
    -> categoria CHAR(20),
    -> stato CHAR(20),
    -> PRIMARY KEY (id_aut)
    -> );
```
* Mostra la descrizione della tabella
```
mysql> DESCRIBE autori;
```
* Inserisce valolri all'interno della tabella
```
mysql> INSERT INTO autori VALUES (1, 'Dante', 'Alighieri', 'poeta','Italia');
```
* Cancella una riga
```
mysql> DELETE FROM autori WHERE id_aut = 8;
```
* Uso SELECT
```
mysql> SELECT * FROM autori;
mysql> SELECT 1 + 1 AS Somma;
mysql> select now() AS orario;
```
* uso LIKE
```
a% inzia con a
%a termina con a
a_% a e un carattere
```
* Operatori aritmetici
```
/ - * + % DIV (Divisione intera)
```
* Logical Operators - AND, OR, NOT, XOR

* IN, NOT IN
Accetta valori scalari e liste
* BETWEEN, NOT BETWEEN
* IS NULL, IS NOT NULL
* ORDER BY prezzo LIMIT 2;
* AS - Alias
* concat()
```
mysql> SELECT CONCAT(nome, ' ', cognome) AS Autore, stato FROM autori;
```
* DISTINCT
```
mysql> select distinct stato from autori;
```
* ORDER BY
```
mysql> select nome, stato FROM autori ORDER BY stato ASC;
```
* GROUP BY Clause
```
mysql> SELECT stato, count(*) AS Num FROM autori GROUP BY stato
```
* Update data
```
UPDATE autori SET stato = 'Italiano' WHERE stato = 'Italia';
```

### Modifica tabelle

* ALTER TABLE ADD COUMN
Aggiunge una colonna alla tabella
```
ALTER TABLE opere ADD COLUMN id_aut INT UNSIGNED NOT NULL;
```

* Aggiunge una chiave esterna -  REFERENCE
```
ALTER TABLE opere ADD FOREIGN KEY (id_aut) REFERENCES autori (id_aut);
```

## One-To-Many Relationship




