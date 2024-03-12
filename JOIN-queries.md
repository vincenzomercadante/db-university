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

### QUERY 3

- Selezionare tutti i corsi in cui insegna Fulvio Amato

```sql
SELECT `teachers`.`id` AS "teacher_id", `courses`.*
FROM `courses`

INNER JOIN `course_teacher`
ON `course_teacher`.`course_id` = `courses`.`id`

INNER JOIN `teachers`
ON `course_teacher`.`teacher_id` = `teachers`.`id`

WHERE `teachers`.`id` = 44;
```

### QUERY 4

- Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui
  sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e
  nome

```sql
SELECT DISTINCT `departments`.`name` AS "department_name", `degrees`.`name` AS "degree_name", `students`.*
FROM `students`

INNER JOIN `degrees`
ON `degrees`.`id` = `students`.`degree_id`

INNER JOIN `departments`
ON `departments`.`id` = `degrees`.`department_id`

ORDER BY `students`.`name`, `students`.`surname` ASC;
```

### QUERY 4

- Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui
  sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e
  nome

```sql

```
