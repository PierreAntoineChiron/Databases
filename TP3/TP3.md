# Databases
TP 3 de SQL pour le module de base de données (Modélisation)

## Première BDD: Carnet de notes

### Création des tables
```sql 
create table etudiant
(
	id_etudiant int not null,
	nom varchar(15) not null,
	prenom varchar(15) not null,
	date_naissance timestamp not null,
	
	constraint pk_etudiant primary key (id_etudiant)
)
```

```sql
create table note
(
	id_note serial,
	nom varchar(15) not null,
	coef decimal(2,2) not null,
	id_matiere int not null,
	id_etudiant int not null,
	
	constraint pk_note primary key (id_note),
	constraint pk_matiere foreign key (id_matiere) references matiere(id_matiere),
	constraint pk_etudiant foreign key (id_etudiant) references etudiant(id_etudiant)
)
```

```sql
create table matiere
(
	id_matiere int not null,
	nom varchar(15) not null,
	
	constraint pk_matiere primary key (id_matiere)
)
```

### Remplissage des tables
```sql
insert into etudiant(id_etudiant,nom,prenom,date_naissance)
values
	(1,'Courbin','Michel','2001-10-03'),
	(2,'Guillot','Antony','2000-01-07'),
	(3,'Chiron','Pierre-Antoine','2002-09-13')
```

```sql

```

```sql

```

## Deuxième BDD: Encyclopédie Pokemon

### Création des tables
```sql

```