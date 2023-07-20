
<strong>Привет! Меня зовут Вячеслав.</strong>
Я начинающий аналитик данных. В данном репозитории вы можете ознакомиться с моими проектами которые я выполнял во время обучения и практики.

Инструменты для анализа данных SQL/Excel

МОИ ПРОЕКТЫ:
=
Калькулятор юнит-экономики онлайн кинотеатра (Excel)
=
Что требовалось сделать:
Часть 1 «Сводные таблицы»

1. Кол-во подписок в каждый месяц
2. Кол-во просмотров в каждый месяц
3. Кол-во уникальных просматривающих пользователей в каждый месяц
4. Дата первого просмотра для каждого юзера
5. Кол-во первых просмотров для пользователя в каждый месяц
6. Среднее кол-во просмотров на одного юзера в каждом месяце

Часть 2 «Создание калькулятора юнит-экономики»

1. Количество повторных оплат в каждом месяце
2. Retention для каждого месяца
3. Среднее геометрическое Retention
4. Лайфтайм
5. LTR
6. CAC
7. Маржинальность

Часть 3 «Визуализация результатов»

1. Построить график 1: количество пользователей и интенсивность просмотров
2. Построить график 2: пользовательский Retention      
3. Построить график 3: распределение просмотров по суточным часам (0-23) в разрезе будние-выходные      
4. Построить график 4: распределение просмотров по тайтлам

Ссылка для ознакомления с проектом:
https://docs.google.com/spreadsheets/d/1qIltf-s3egnjlFE6oSyC10edBtaJk6tY/edit?usp=sharing&ouid=101742594754056706914&rtpof=true&sd=true


Аналитика онлайн университета (SQL)
=
Что требовалось сделать:
1. Собрал таблицу, в которой для каждого студента хранится его первая дата успешной (со статусом *success*) транзакции (из таблицы `payments`).     
2. Собрал таблицу, которая хранит в себе все дни 2016 года. Для этого выбрал все даты из таблицы `classes`.   
3. Собрал таблицу со списком успешных транзакций из таблицы `payments`. Сделал агрегацию, в которой для каждого клиента на каждую дату ввёл сумму поля `classes` (только для успешных транзакций).   
4. Создал СТЕ для всех запросов из первой части:
    - Первый запрос `first_payments`
    - Второй запрос `all_dates`
    - Третий запрос `payments_by_dates`
5. Создал СТЕ под названием `all_dates_by_user`, в котором объединил `all_dates` и `first_payments`, где хранятся все даты жизни студента после того, как произошла его первая транзакция. 
6.Создал CTE `classes_by_dates`, посчитал в таблице `classes` количество уроков за каждый день для каждого ученика.
7. Нашёл баланс студентов, который сформирован только транзакциями. Для этого я объединил `all_dates_by_user`и `payments_by_dates`так, чтобы совпадали даты и `user_id` . Использовал оконные функции чтобы найти кумулятивную сумму по полю `transaction_balance_change` для всех строк до текущей включительно с разбивкой по `user_id` и сортировкой по `dt`.     
8. По аналогии с уже проделанным шагом для оплат создал CTE `classes_by_dates_dates_cumsum` для хранения кумулятивной суммы количества пройденных уроков. 
Для этого объединл таблицы `all_dates_by_user` и `classes_by_dates` так, чтобы совпадали даты и `user_id`. Использовал оконные выражения, чтобы найти кумулятивную сумму по полю `classes` для всех строк до текущей включительно с разбивкой по `user_id` и сортировкой по `dt`.     
9. Создал CTE `balances` с вычисленными балансами каждого студента. Для этого объединил таблицы `payments_by_dates_cumsum` ****и `classes_by_dates_dates_cumsum` так, чтобы совпадали даты и `user_id`.             
10. Создал визуализацию (линейную диаграмму) итогового результата.
11. 
Ссылка для ознакомления с проектом:
https://docs.google.com/document/d/15F0qg_hDmYk-EctN6SWz6YXHaYrvlYa6/edit?usp=sharing&ouid=101742594754056706914&rtpof=true&sd=true
