# Datasets / Schemas

> Данные в репо не хранятся. Ниже — какие таблицы ожидаются.

## PostGIS — Москва
- `admin_areas` (геометрия округов)
- `moscow_districts` (геометрия районов)
- промежуточные CTE/таблицы создаются в скриптах

## PostGIS — Кремли
- `cities`
- `kremlins`

## Chinook (music store)
- `customer`, `invoice`, `invoice_line`, `track`, `album`, `artist`, …

## Orders/Customers
- `orders`, `customers`, `contacts`, `unique_order_lines` (по названию в скрипте)
