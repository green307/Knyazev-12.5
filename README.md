# Домашнее задание к занятию 12.5. «Индексы»

Задание 1
Напишите запрос к учебной базе данных, который вернёт процентное отношение общего размера всех индексов к общему размеру всех таблиц.

![alt text](https://github.com/green307/Knyazev-12.5/blob/d79f3c506e3adefb6e53e3b1f0263452000bc8f2/%D0%97%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5%201.jpg)


Задание 2
Выполните explain analyze следующего запроса:

select distinct concat(c.last_name, ' ', c.first_name), sum(p.amount) over (partition by c.customer_id, f.title)
from payment p, rental r, customer c, inventory i, film f
where date(p.payment_date) = '2005-07-30' and p.payment_date = r.rental_date and r.customer_id = c.customer_id and i.inventory_id = r.inventory_id
перечислите узкие места;
оптимизируйте запрос: внесите корректировки по использованию операторов, при необходимости добавьте индексы.

ИСПРАВЛЕНИЕ

![alt text](https://github.com/green307/Knyazev-12.5/blob/d37e766fe6d0fbc6097e26bcf9441ec5911d06ec/%D0%97%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B52.jpg)
