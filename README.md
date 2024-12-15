# sql
# 1.Задание: Выберите все кофейни и их местоположения. Решение:

SELECT Name, Location FROM cafes

Описание логики: Запрос извлекает название и местоположение всех кофеен из таблицы cafes.

# 2.Задание: Выберите кофейни с рейтингом выше 4.0. Решение:

SELECT Name, Rating FROM cafes WHERE Rating > 4.0

Описание логики: Запрос выбирает названия и рейтинги кофеен, у которых рейтинг больше 4.0.

# 3.Задание: Отсортируйте кофейни по рейтингу в порядке убывания. Решение:

SELECT Name, Rating FROM cafes ORDER BY Rating DESC

Описание логики: Запрос сортирует кофейни по рейтингу в порядке убывания.

# 4.Задание: Посчитайте общее количество заказов в таблице Orders. Решение:

SELECT COUNT(*) AS TotalOrders FROM orders

Описание логики: Запрос подсчитывает общее количество записей (заказов) в таблице orders.

# 5.Задание: Выберите уникальные местоположения кофеен. Решение:

SELECT DISTINCT Location FROM cafes

Описание логики: Запрос выбирает уникальные местоположения из таблицы cafes.

# 6.Задание: Выберите все напитки, которые стоят менее 4.00. Решение:

SELECT Name, Price FROM drinks WHERE Price < 4.00

Описание логики: Запрос выбирает напитки с ценой ниже 4.00.

# 7.Задание: Выберите кофейни, которые были открыты после 2016 года. Решение:

SELECT Name, OpenYear FROM cafes WHERE OpenYear > 2016

Описание логики: Запрос выбирает кофейни, открытые после 2016 года.

# 8.Задание: Найдите средний рейтинг кофеен в каждом городе. Решение:

SELECT Location, AVG(Rating) AS AverageRating FROM cafes GROUP BY Location

Описание логики: Запрос вычисляет средний рейтинг кофеен для каждого города.

# 9.Задание: Подсчитайте количество кофеен в каждом городе. Решение:

SELECT Location, COUNT(*) AS CafeCount FROM cafes GROUP BY Location

Описание логики: Запрос подсчитывает количество кофеен в каждом городе.

# 10.Задание: Найдите все заказы, которые содержат более 2 единиц любого напитка. Решение:

SELECT * FROM orders WHERE Quantity > 2

Описание логики: Запрос выбирает заказы с количеством напитков больше 2.

# 11.Задание: Выведите список всех напитков и соответствующих им кофеен. Решение:

SELECT d.Name AS DrinkName, c.Name AS CafeName

FROM drinks d

JOIN cafes c ON d.CafeID = c.CafeID

Описание логики: Запрос соединяет таблицы drinks и cafes, чтобы показать названия напитков и соответствующих кофеен.

# 12.Задание: Подсчитайте общее количество проданных напитков для каждой кофейни. Решение:

SELECT o.CafeID, c.Name AS CafeName, SUM(o.Quantity) AS TotalDrinksSold

FROM orders o

JOIN cafes c ON o.CafeID = c.CafeID

GROUP BY o.CafeID, c.Name

Описание логики: Запрос подсчитывает общее количество проданных напитков для каждой кофейни.

# 13.Задание: Найдите среднюю цену напитков для каждой кофейни. Решение:

SELECT d.CafeID, c.Name AS CafeName, AVG(d.Price) AS AveragePrice

FROM drinks d

JOIN cafes c ON d.CafeID = c.CafeID

GROUP BY d.CafeID, c.Name

Описание логики: Запрос вычисляет среднюю цену напитков для каждой кофейни.

# 14.Задание: Выведите все напитки и название кофеен, в которых они подаются. Если напиток не связан с какой-либо кофейней, отобразите NULL для названия кофейни. Решение:

SELECT d.Name AS DrinkName, c.Name AS CafeName

FROM drinks d

LEFT JOIN cafes c ON d.CafeID = c.CafeID

Описание логики: Используется левое соединение для того, чтобы показать напитки и название кофейни или NULL, если связь отсутствует.

# 15.Задание: Выведите список всех заказов и соответствующие названия напитков. Если напиток был удален из базы данных, отобразите NULL для его названия. Решение:

SELECT o.OrderID, d.Name AS DrinkName, o.Quantity, o.OrderDate

FROM orders o

LEFT JOIN drinks d ON o.DrinkID = d.DrinkID;

Описание логики: Левое соединение между таблицами orders и drinks, чтобы показать все заказы и названия напитков или NULL, если напиток отсутствует в базе данных
