# SQL (PostgreSQL) — Analytics Case Studies

**TL;DR:** набор практических SQL‑кейсов: **CTE**, **JOIN**, **оконные функции (LAG/NTILE)**, **агрегации**, **гео‑анализ PostGIS**.  
**Stack:** PostgreSQL · PostGIS · SQL (CTE / window functions / set operators) · GitHub Issues (как Jira) · Docs (как Confluence)

---

## Что внутри

### 1) PostGIS — Москва (административные округа / районы)
Файл: [`sql/postgis_moscow/tasks_02_10_moscow_admin_areas.sql`](./sql/postgis_moscow/tasks_02_10_moscow_admin_areas.sql)  
Что демонстрирует:
- расчёт площади/периметра/длины границ (**ST_Area, ST_Perimeter, ST_Length**)
- пространственные отношения (**ST_Within, ST_Intersects, ST_Covers**)
- пересечения и доли площадей (**ST_Intersection**)
- работа с округлением и единицами измерения (км²/км)

### 2) PostGIS — “Кремли” (cities/kremlins)
Файл: [`sql/postgis_kremlins/tasks_02_06_kremlins.sql`](./sql/postgis_kremlins/tasks_02_06_kremlins.sql)  
Что демонстрирует:
- подготовка таблиц (**CREATE/INSERT**)
- пространственные метрики и расстояния (**ST_Area, ST_Distance**)  

### 3) Заказы/клиенты — подготовка данных под визуализацию
Файл: [`sql/orders_customers/tasks_01_02_orders_customers_analytics.sql`](./sql/orders_customers/tasks_01_02_orders_customers_analytics.sql)  
Что демонстрирует:
- сегментация по регионам (CASE)
- сравнение показателей по годам (CTE + JOIN)
- подготовка агрегатов для BI/дашбордов

### 4) Chinook (music store) — аналитические задачи
Файлы:  
- [`tasks_22_27_chinook.sql`](./sql/chinook_music_store/tasks_22_27_chinook.sql)  
- [`tasks_28_30_chinook.sql`](./sql/chinook_music_store/tasks_28_30_chinook.sql)  
Что демонстрирует:
- продвинутая аналитика клиентов и продаж
- **оконные функции**: процент изменения по месяцам (**LAG**), сегментация (**NTILE**)
- накопительная выручка, группировки, подзапросы и CTE

---

## Как запускать
> Данные в репозиторий не включены (обычно они объёмные).  
Подразумевается PostgreSQL. Для гео‑части нужен **PostGIS**.

- PostGIS задачи используют таблицы: `admin_areas`, `moscow_districts` и т.п.  
- Chinook задачи используют типичные таблицы: `customer`, `invoice`, `invoice_line`, `track`, `artist`, `album` (набор данных Chinook).

## Структура репозитория
- `sql/` — запросы, разбитые по кейсам  
- `docs/` — допущения/схемы/пояснения  
- `sql/_original_filenames/` — исходные названия файлов (на всякий случай)

