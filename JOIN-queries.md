# DB-UNIVERSITY PT.3 JOIN

## TRACCIA

Dopo aver creato un nuovo database nel vostro phpMyAdmin e aver importato lo schema allegato, eseguite le seguenti queries

### QUERY 1

- Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```sql
SELECT `students`.*
FROM `students`
INNER JOIN `degrees`
ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = "Corso di Laurea in Economia";
```

### QUERY 2

- Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di
  Neuroscienze

```sql
SELECT `degrees`.*
FROM `degrees`
INNER JOIN `departments`
ON `departments`.`id` =`degrees`.`department_id`
WHERE `departments`.`name` = "Dipartimento di Neuroscienze";
```
