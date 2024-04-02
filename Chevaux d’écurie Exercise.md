# Chevaux d’écurie Exercise

This exercise involves querying a database regarding horses and their participation in competitions.

## Questions and SQL Queries

### 1. Combien y a-t-il de Chevaux Noir ?

```sql
SELECT COUNT(*) AS Nombre_de_chevaux_noir
FROM cheval
WHERE colorcheval = 'Noir';```

### 2. Combien y a-t-il de chevaux de la race AngloArabe?

```sql
SELECT COUNT(*) AS Nombre_de_chevaux_AngloArabe
FROM cheval
WHERE nomrace = (SELECT nomrace FROM race WHERE nomrace = 'AngloArabe');```

### 3. Donner le numéro et le nom du cheval dont le Numéro de tatouage est : T0415

```sql
SELECT numcheval, nomcheval
FROM cheval
WHERE numtatouage = 'T0415';```


### 4. Combien y a-t-il d’éditions du concours : « Concours Dubai »?

```sql
SELECT COUNT(*) AS Nombre_d_editions_Concours_Dubai
FROM concours
WHERE nomconcours = 'Concours Dubai';```

### 5. Quel est le nombre total de participants dans toutes les éditions du Concours Dubai?

```sql
SELECT SUM(nombreparticipant) AS Nombre_total_de_participants
FROM concours
WHERE nomconcours = 'Concours Dubai';```

### 6. Dans quels concours /année les chevaux de l’écurie ont eu la première place?

```sql
SELECT nomconcours, anneeconcours
FROM participation
WHERE place = 1;```

### 7. Quels chevaux ont participé à l’édition 2018 du concours de Londres ?

```sql
SELECT nomcheval
FROM cheval
WHERE numcheval IN (SELECT numcheval FROM participation WHERE nomconcours = 'Concours Londres' AND anneeconcours = 2018);```

### 8. Comment s’appelle le directeur de l’établissement ?

```sql
SELECT nomperson, prenomperson
FROM personnes
WHERE fonction = 'Directeur';```

### 9. Combien y a-t-il de propriétaires ?

```sql
SELECT COUNT(DISTINCT id_person) AS Nombre_de_proprietaires
FROM proprietaire;

### 10. Combien de chevaux le propriétaire N6 a acheté en 2020 ?```

```sql
SELECT COUNT(*) AS Nombre_de_chevaux_achetes
FROM proprietaire
WHERE id_person = 6
AND YEAR(date_achat) = 2020;```

### 11. Combien a-t-il payé pour acheter ses chevaux ?

```sql
SELECT SUM(prix) AS Total_paye_pour_acheter_les_chevaux
FROM proprietaire
WHERE id_person = 6;```
