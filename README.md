# Database Tables

## Table: cheval

| Field            | Type         | Null | Key | Default | Extra |
|------------------|--------------|------|-----|---------|-------|
| numcheval        | int          | NO   | PRI | NULL    |       |
| nomcheval        | varchar(255) | YES  |     | NULL    |       |
| numtatouage      | varchar(50)  | YES  |     | NULL    |       |
| colorcheval      | varchar(50)  | YES  |     | NULL    |       |
| nomrace          | int          | YES  | MUL | NULL    |       |
| numchevalmere    | int          | YES  | MUL | NULL    |       |
| numchevalpere    | int          | YES  | MUL | NULL    |       |
| id_personeleveur | int          | YES  | MUL | NULL    |       |

## Table: concours

| Field             | Type         | Null | Key | Default | Extra |
|-------------------|--------------|------|-----|---------|-------|
| nomconcours       | varchar(255) | NO   | PRI | NULL    |       |
| anneeconcours     | int          | NO   | PRI | NULL    |       |
| nombreparticipant | int          | YES  |     | NULL    |       |

## Table: croissance

| Field        | Type         | Null | Key | Default | Extra |
|--------------|--------------|------|-----|---------|-------|
| idcroissance | int          | NO   | PRI | NULL    |       |
| mois         | int          | YES  |     | NULL    |       |
| taille       | decimal(5,2) | YES  |     | NULL    |       |
| poids        | decimal(5,2) | YES  |     | NULL    |       |
| numcheval    | int          | YES  | MUL | NULL    |       |

## Table: participation

| Field         | Type         | Null | Key | Default | Extra |
|---------------|--------------|------|-----|---------|-------|
| numcheval     | int          | YES  | MUL | NULL    |       |
| anneeconcours | int          | YES  | MUL | NULL    |       |
| nomconcours   | varchar(255) | YES  | MUL | NULL    |       |
| place         | int          | YES  |     | NULL    |       |

## Table: personnes

| Field         | Type         | Null | Key | Default | Extra |
|---------------|--------------|------|-----|---------|-------|
| id_person     | int          | NO   | PRI | NULL    |       |
| nomperson     | varchar(255) | YES  |     | NULL    |       |
| prenomperson  | varchar(255) | YES  |     | NULL    |       |
| teleperson    | varchar(20)  | YES  |     | NULL    |       |
| adresseperson | varchar(255) | YES  |     | NULL    |       |
| fonction      | varchar(100) | YES  |     | NULL    |       |
| id_personsup  | int          | YES  | MUL | NULL    |       |

## Table: proprietaire

| Field      | Type          | Null | Key | Default | Extra |
|------------|---------------|------|-----|---------|-------|
| id_person  | int           | YES  | MUL | NULL    |       |
| num_cheval | int           | YES  | MUL | NULL    |       |
| prix       | decimal(10,2) | YES  |     | NULL    |       |

## Table: race

| Field      | Type         | Null | Key | Default | Extra |
|------------|--------------|------|-----|---------|-------|
| nomrace    | varchar(255) | NO   | PRI | NULL    |       |
| poidstype  | varchar(50)  | YES  |     | NULL    |       |
| tailletyps | varchar(50)  | YES  |     | NULL    |       |
