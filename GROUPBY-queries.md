# DB-UNIVERSITY PT.3 GROUP BY

## TRACCIA

Dopo aver creato un nuovo database nel vostro phpMyAdmin e aver importato lo schema allegato, eseguite le seguenti queries

### QUERY 1

- Contare quanti iscritti ci sono stati ogni anno

```sql
SELECT DISTINCT YEAR(`enrolment_date`), COUNT(*) AS "total_students"
FROM `students`
GROUP BY YEAR(`enrolment_date`);
```

### QUERY 2

- Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```sql
SELECT DISTINCT `office_address`, COUNT(*) AS "number_of_teachers"
FROM `teachers`
GROUP BY `office_address`;
```

### QUERY 3

- Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```sql
SELECT `exam_id`, CEIL(AVG(`vote`)) AS "avg_vote"
FROM `exam_student`
GROUP BY `exam_id`;
```

### QUERY 4

- Contare quanti corsi di laurea ci sono per ogni dipartimento

```sql
SELECT `departments`.`name`, COUNT(*) AS "degrees_for_department"
FROM `departments`
INNER JOIN `degrees`
ON `departments`.`id` = `degrees`.`department_id`
GROUP BY `departments`.`id`;
```
