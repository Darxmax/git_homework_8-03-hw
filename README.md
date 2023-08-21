# Домашнее задание к занятию «Работа с данными (DDL/DML)»

### Инструкция по выполнению домашнего задания

1. Сделайте fork [репозитория c шаблоном решения](https://github.com/netology-code/sys-pattern-homework) к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/gitlab-hw или https://github.com/имя-вашего-репозитория/8-03-hw).
2. Выполните клонирование этого репозитория к себе на ПК с помощью команды `git clone`.
3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
   - впишите вверху название занятия и ваши фамилию и имя;
   - в каждом задании добавьте решение в требуемом виде: текст/код/скриншоты/ссылка;
   - для корректного добавления скриншотов воспользуйтесь инструкцией [«Как вставить скриншот в шаблон с решением»](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md);
   - при оформлении используйте возможности языка разметки md. Коротко об этом можно посмотреть в [инструкции по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md).
4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`).
5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
6. Любые вопросы задавайте в чате учебной группы и/или в разделе «Вопросы по заданию» в личном кабинете.

Желаем успехов в выполнении домашнего задания.

---

Задание можно выполнить как в любом IDE, так и в командной строке.

### Задание 1
1.1. Поднимите чистый инстанс MySQL версии 8.0+. Можно использовать локальный сервер или контейнер Docker.

1.2. Создайте учётную запись sys_temp. 

1.3. Выполните запрос на получение списка пользователей в базе данных. (скриншот)

![image](https://github.com/Darxmax/git_homework/assets/54942567/6a364dd9-8eb0-4f71-a036-3a48a0a14a41)


1.4. Дайте все права для пользователя sys_temp. 

1.5. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)

![image](https://github.com/Darxmax/git_homework/assets/54942567/6912faff-a21c-40d7-8015-9616beb35e3a)


1.6. Переподключитесь к базе данных от имени sys_temp.

Для смены типа аутентификации с sha2 используйте запрос: 
```sql
ALTER USER 'sys_test'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```
1.6. По ссылке https://downloads.mysql.com/docs/sakila-db.zip скачайте дамп базы данных.

1.7. Восстановите дамп в базу данных.

1.8. При работе в IDE сформируйте ER-диаграмму получившейся базы данных. При работе в командной строке используйте команду для получения всех таблиц базы данных. (скриншот)

![image](https://github.com/Darxmax/git_homework/assets/54942567/c109426d-1fd8-4995-905c-9bb307215bc4)


*Результатом работы должны быть скриншоты обозначенных заданий, а также простыня со всеми запросами.*


### Задание 2
Составьте таблицу, используя любой текстовый редактор или Excel, в которой должно быть два столбца: в первом должны быть названия таблиц восстановленной базы, во втором названия первичных ключей этих таблиц. Пример: (скриншот/текст)
```
Название таблицы| Название первичного ключа
customer        | customer_id
		| first_name
		| last_name
		| last_update

inventory	| inventory_id
		| film_id
		| store_id
		| last_update

payment         | payment_id
		| customer_id
		| staff_id
		| rental_id
		| amount
		| payment_date
		| last_update

rental          | rental_id
		| rental_date
		| inventory_id
		| customer_id
		| return_date
		| staff_id
		| last_update

store           | store_id
		| manager_staff_id
		| address_id
		| last_update

staff           | staff_id
		| first_name
		| last_name
		|address_id
		| picture
		| email
		| store_id
		| active
		| username
		| password
		| last_update

address         | address_id
		| address
		| address2
		| district
		| city_id
		| postal_code
		| phone
		| location
		| last_update

city            | city_id
		| city
		| country_id
		| last_update

country         | country_id
		| country
		| last_update

film            | film_id
		| title
		| description
		| release_year
		| language_id
		| original_language_id
		| rental_duration
		| rental_rate
		| length
		| replacement_cost
		| rating
		| special_features
		| last_update

language        | language_id
		| name
		| last_update

film_actor      | actor_id\
		| film_id
		| last_update

actor           | actor_id
		| first_name
		| last_name
		| last_update

film_category   | film_id
		| category_id
		| last_update

category        | category_id
		| name
		| last_update
 
film_text       | film_id
		| title
		| description



## Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.

### Задание 3*
3.1. Уберите у пользователя sys_temp права на внесение, изменение и удаление данных из базы sakila.

3.2. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)

*Результатом работы должны быть скриншоты обозначенных заданий, а также простыня со всеми запросами.*
