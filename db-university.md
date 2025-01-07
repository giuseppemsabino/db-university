## 1. Selezionare tutti gli studenti nati nel 1990 (160)

```sql
SELECT COUNT(id)
FROM university.students
WHERE YEAR(date_of_birth) = 1990;
```

2. Selezionare tutti i corsi che valgono più di 10 crediti (479)

```sql
SELECT COUNT(id) 
FROM university.courses
WHERE `cfu` > 10;
```

3. Selezionare tutti gli studenti che hanno più di 30 anni

```sql
SELECT * 
FROM university.students
WHERE YEAR(date_of_birth) < 1995
```

4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)

```sql
SELECT * 
FROM university.courses
WHERE `year` = 1 AND `period` LIKE "I %"  ;
```



5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)

```sql
SELECT COUNT(id) 
FROM university.exams
WHERE `date` = '2020-06-20' AND `hour` > '14:00:00' ;
```


6. Selezionare tutti i corsi di laurea magistrale (38)

```sql
```

7. Da quanti dipartimenti è composta l'università? (12)

```sql
```

8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

```sql
```

9. Inserire nella tabella degli studenti un nuovo record con i propri dati (per il campo degree_id, inserire un valore casuale)

```sql
```

10. Cambiare il numero dell’ufficio del professor Pietro Rizzo in 126

```sql
```

11. Eliminare dalla tabella studenti il record creato precedentemente al punto 9

```sql
```
