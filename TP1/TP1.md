# Databases
TPs de SQL pour le module de base de données

#### 1
```sql
select 
	f.title as titre,
	f.rating as classe,
	f.length as duree
from 
	film as f
where
	(f.length>120 and (f.rating = 'NC-17' or f.rating = 'R'))
	 or (f.length<60 and f.rating = 'G')
```

#### 2
```sql
select 
	a.first_name as prenom,
	a.last_name as nom
from 
	actor as a
where
	a.first_name = 'Cameron' or a.first_name = 'Fay' or a.first_name = 'Penelope'
```

#### 3
```sql
select 
	concat(a.first_name,' ',a.last_name) as prenom_nom
from 
	actor as a
order by
	a.first_name asc
```

#### 4
```sql
select 
	a.first_name as prenom
from 
	actor as a
order by
	a.last_name asc
```

#### 5
```sql
select 
	f.title as titre
from 
	film as f
where
	f.description
like
	'%Chef%'
```

#### 6
```sql
select 
	count(1), ad.city_id as ville
from 
	address as ad
group by
	ad.city_id
```

#### 7
```sql
select 
	sum(pay.amount) as argent_total
from 
	payment as pay
```

#### 8
```sql
select 
	sum(pay.amount) as paiements,
	extract (year from pay.payment_date) as annee,
	extract (month from pay.payment_date) as mois
from 
	payment as pay
group by
	annee,
	mois
order by
	mois asc
```

#### 9
```sql
select 
	f.title as titre,
	f.rating as classe,
	case
		when f.rating='G' then 'Tous âges'
		when f.rating='PG' then 'Tous âges, mais accompagnement parental conseillé'
		when f.rating='PG-13' then '+13 et accompagnement parental fortement conseillé'
		when f.rating='R' then '-17 accompagnés '
		when f.rating='NC-17' then 'Adultes seulement'
	end
from 
	film as f
order by
	classe
```

#### 10
```sql
select 
	f.title as titre,
	f.length as duree
from
	film as f
where
	f.description
like
	'%Japan%'
order by
	f.length
limit 1;
```

#### 11
```sql
select 
	count(1)
from
	film as f
where
	f.description like '%Japan%' or
	f.description like '%Space%' 
```

#### 12
```sql
 select 
	f.title as titre,
	f.rental_duration as duree_location
from
	film as f
```

#### 13
```sql
select 
	distinct ad.district
from
	address as ad
```

#### 14
```sql

```