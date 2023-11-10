### Задание 1

Одним запросом получите информацию о магазине, в котором обслуживается более 300 покупателей, и выведите в результат следующую информацию: 
- фамилия и имя сотрудника из этого магазина;
- город нахождения магазина;
- количество пользователей, закреплённых в этом магазине.
select  concat(s.first_name, ' ', s.last_name) as ФИО_сотрудника, ci.city  AS город_магазина, count(c.customer_id) as количество_пользователей
from staff s
join store st on s.store_id = st.store_id
join address ad on st.address_id = ad.address_id
join customer c on st.store_id = c.store_id
join city ci on ad.city_id = ci.city_id group by s.first_name, s.last_name, ad.city_id
having count(c.customer_id) > 300;
![image](https://github.com/rulezzz7373/Netology/assets/138396672/25ae95ab-d063-44b6-9c7e-55cc34cce613)

### Задание 2

Получите количество фильмов, продолжительность которых больше средней продолжительности всех фильмов.
select count(*) as количество_фильмов
FROM film
where length > (select avg(length) from film);
![image](https://github.com/rulezzz7373/Netology/assets/138396672/fb0ab06f-15ae-4b50-b130-4baebbf13c73)


### Задание 3

Получите информацию, за какой месяц была получена наибольшая сумма платежей, и добавьте информацию по количеству аренд за этот месяц.
select date_format(payment_date, '%Y-%m') as месяц, SUM(amount) as сумма_платежей, count(rental_id) AS количество_аренд
from payment
group by date_format(payment_date, '%Y-%m')
order by сумма_платежей desc
limit 1
![image](https://github.com/rulezzz7373/Netology/assets/138396672/595a5d5d-acaa-448f-91ac-1dc3367c5af6)
