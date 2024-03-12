# DB-UNIVERSITY PT.3 GROUP BY

## TRACCIA

Dopo aver creato un nuovo database nel vostro phpMyAdmin e aver importato lo schema allegato, eseguite le seguenti queries

### QUERY 1

- Contare quanti iscritti ci sono stati ogni anno

```sql
SELECT DISTINCT YEAR(`enrolment_date`), COUNT(*) as "total_students"
FROM `students`
GROUP BY YEAR(`enrolment_date`);
```

### QUERY 2

- Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```sql
SELECT DISTINCT `office_address`, COUNT(*) as "number_of_teachers"
FROM `teachers`
GROUP BY `office_address`;
```
