# DB-UNIVERSITY

## TRACCIA

Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una università:

- sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
- ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
- ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
- ogni Corso può essere tenuto da diversi Insegnanti;
- ogni Corso prevede più appelli d'Esame;
- ogni Studente è iscritto ad un solo Corso di Laurea;
- ogni Studente può iscriversi a più appelli di Esame;
- per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente.

Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.
Utilizzare https://www.diagrams.net/ per la creazione dello schema.
Esportare quindi il diagramma in jpg e caricarlo nella repo.

# DB-UNIVERSITY PT.2

## TRACCIA

Dopo aver creato un nuovo database nel vostro phpMyAdmin e aver importato lo schema allegato, eseguite le query riportate di seguito

### QUERY 1

- Selezionare tutti gli studenti nati nel 1990

```sql
SELECT *
FROM `students`
WHERE YEAR(`date_of_birth`) = '1990';
```

### QUERY 2

- Selezionare tutti i corsi che valgono più di 10 crediti

```sql
SELECT *
FROM `courses`
WHERE `cfu` > '10';
```

### QUERY 3

- Selezionare tutti gli studenti con più di 30 anni

```sql
SELECT *
FROM `students`
WHERE `date_of_birth` < '1994-03-11';
```

### QUERY 4

- Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di
  laurea

```sql
SELECT *
FROM `courses`
WHERE `period` = 'I semestre' AND `year` = 1;
```

### QUERY 5

- Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del
  20/06/2020

```sql
SELECT *
FROM `exams`
WHERE `date` = '2020-06-20' AND HOUR(`hour`) >= '14';
```

### QUERY 6

- Selezionare tutti i corsi di laurea magistrale

```sql
SELECT *
FROM `degrees`
WHERE `level` = 'magistrale';
```

### QUERY 7

- Da quanti dipartimenti è composta l'università?

```sql
SELECT COUNT(*) AS 'departments_number'
FROM `departments`;
```
