## 1. Selezionare tutti gli studenti nati nel 1990 (160)

```sql
SELECT COUNT(id)
FROM university.students
WHERE YEAR(date_of_birth) = 1990;
```

## 2. Selezionare tutti i corsi che valgono più di 10 crediti (479)

```sql
SELECT COUNT(id) 
FROM university.courses
WHERE `cfu` > 10;
```

## 3. Selezionare tutti gli studenti che hanno più di 30 anni

```sql
SELECT * 
FROM university.students
WHERE YEAR(date_of_birth) < 1995
```

## 4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)

```sql
SELECT * 
FROM university.courses
WHERE `year` = 1 AND `period` LIKE "I %"  ;
```



## 5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)

```sql
SELECT COUNT(id) 
FROM university.exams
WHERE `date` = '2020-06-20' AND `hour` > '14:00:00' ;
```


## 6. Selezionare tutti i corsi di laurea magistrale (38)

```sql
SELECT COUNT(id) 
FROM university.degrees
WHERE `level` LIKE "magistrale";
```

## 7. Da quanti dipartimenti è composta l'università? (12)

```sql
SELECT COUNT(id) 
FROM university.departments;
```

## 8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

```sql
SELECT COUNT(id) AS insegnati_senza_tlf
FROM university.teachers
WHERE `phone` IS NULL;
```

## 9. Inserire nella tabella degli studenti un nuovo record con i propri dati (per il campo degree_id, inserire un valore casuale)

```sql
INSERT INTO `university`.`students` (`id`, `degree_id`, `name`, `surname`, `date_of_birth`, `fiscal_code`, `enrolment_date`, `registration_number`, `email`) 
VALUES ('', '30', 'Giuseppe', 'Mendoza', '2002-05-31', 'DRUATB76D70W116U', '2025-01-07', '621033', 'pepemendoza@test.com');

-- c'è un'errore con l'id iniziale ma dovrebbe essere apposto

```

## 10. Cambiare il numero dell’ufficio del professor Pietro Rizzo in 126

```sql
SELECT * FROM university.teachers WHERE `name` LIKE "Pietro"; --creco al professore 
UPDATE `university`.`teachers` SET `office_number` = '126' WHERE (`id` = '58'); --faccio l'update
```

## 11. Eliminare dalla tabella studenti il record creato precedentemente al punto 9

```sql
DELETE FROM `university`.`students` WHERE (`id` = '#'); --sarebbe cosi solo che non ho poputo creare il mio record 
```



### continuazione 

## 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```sql
SELECT `students`.`id`, `students`.`name`, `students`.`surname`, `students`.`date_of_birth`, `students`.`email`
FROM `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia';
```

## 2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

```sql
SELECT *
FROM `degrees`
INNER JOIN `departments`
ON `degrees`.`department_id` = `departments`. `id`
WHERE `degrees`.`level` = "magistrale" AND `departments`. `name` = "Dipartimento di Neuroscienze";
```

## 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```sql
```

## 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

```sql
```

## 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```sql
```

## 6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

```sql
```

## 7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.

```sql
```