# Databases
TP 2 de SQL pour le module de base de données

#### 1
```sql
select
	first_name as prénom,
	last_name as nom,
	city as ville
from
	customer as c
	inner join address as a
		on c.address_id=a.address_id
	inner join city as ci
		on ci.city_id=a.city_id
```

#### 2
```sql
select
	first_name as prénom,
	last_name as nom,
	city as ville,
	country as pays
from
	customer as c
	inner join address as a
		on c.address_id=a.address_id
	inner join city as ci
		on ci.city_id=a.city_id
	inner join country as co
		on co.country_id=ci.country_id
```

#### 3
```sql
select
	f.title as titre,
	f.description as synopsis,
	count(1) as nbr_copies
from 
	film as f
	inner join inventory as i
		on f.film_id=i.film_id
group by
	title,
	description
```

#### 4
```sql
select
	f.title as titre,
	f.description as synopsis,
	i.store_id,
	count(1) as nbr_copies
from 
	film as f
	inner join inventory as i
		on f.film_id=i.film_id
group by
	title,
	description,
	store_id
```

#### 5
```sql
select
	f.title as titre,
	count(1) as nbr_acteurs
from 
	film as f
	inner join film_actor as fa
		on f.film_id=fa.film_id
group by
	title
```

#### 6
```sql
select
	a.first_name as prénom,
	a.last_name as nom,
	ca.name as catégorie
from 
	film_category as fc
	inner join film_actor as fa
		on fc.film_id=fa.film_id
	inner join actor as a
		on a.actor_id=fa.actor_id
	inner join category as ca
		on ca.category_id=fc.category_id
```

#### 7
```sql
select
	f.title
from 
	staff as s
	inner join rental as re
		on s.staff_id=re.staff_id
	inner join inventory as i
		on i.inventory_id=re.inventory_id
	inner join film as f
		on f.film_id=i.film_id
where
	s.first_name='Jon' 
	and extract (month from re.rental_date)=5 
	and extract (year from re.rental_date)=2005
```

#### 8
```sql
select
	re.customer_id as loueur,
	p.customer_id as payeur
from 
	rental as re
	inner join payment as p
		on re.rental_id=p.rental_id		
where
	re.customer_id <> p.customer_id
```

#### 9
```sql
select
	concat('(',f.title,', ',ca.name,', ', a.first_name,' ', a.last_name,')')
from 
	film_category as fc
	inner join film_actor as fa
		on fc.film_id=fa.film_id
	inner join actor as a
		on a.actor_id=fa.actor_id
	inner join category as ca
		on ca.category_id=fc.category_id
	inner join film as f
		on fc.film_id=f.film_id
```

#### 10
```sql
select
	distinct concat('(',f.title,', ',ca.name,', ', a.first_name,' ', a.last_name,')')
from 
	film_category as fc
	inner join film_actor as fa
		on fc.film_id=fa.film_id
	inner join actor as a
		on a.actor_id=fa.actor_id
	inner join category as ca
		on ca.category_id=fc.category_id
	inner join film as f
		on fc.film_id=f.film_id
	inner join inventory as i
		on f.film_id=i.film_id
	inner join staff as st
		on i.store_id=st.store_id
where
	st.first_name='Mike'
```

#### 11
```sql

```

#### 12
```sql

```

#### 13
```sql

```

#### 14
```sql

```

#### 15
```sql

```

#### 16
```sql

```

#### 17
```sql

```

#### 18
```sql

```

#### 19
```sql

```

#### 20
```sql

```

#### 21
```sql

```

#### 22
```sql

```

#### 23
```sql

```