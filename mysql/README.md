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













