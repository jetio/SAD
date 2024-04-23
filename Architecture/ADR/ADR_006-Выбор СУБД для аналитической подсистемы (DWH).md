# Выбор СУБД для аналитической подсистемы (DWH)

## Status (Статус)
DONE

## Context (Условия)
Альтернативы:
- Snowflake (https://www.snowflake.com/en/). Well-optimized for executing long-running reports
- Firebolt (https://www.firebolt.io/)
- Clickhouse (https://clickhouse.com/). Real-time data analytics
- Apache Druid (https://druid.apache.org/)
- Apache Pinot (https://pinot.apache.org/)

### Требования
- Производительность: высокая (сравнивать спортивные показатели, персональные и групповые)
- Данные: структурированные
- Тип аналитики: сравнение пользователей и сбор разнообразной статистики (без поиска)


| Критерий / DWH                                     | Snowflake | Druid   | Clickhouse  | Pinot   | Firebolt        |
|:---------------------------------------------------|:----------|:--------|:------------|:--------|:----------------|
| Трудоемкость внедрения и использования             | Низкая    | Средняя | Низкая      | Высокая | Низкая          |
| Партиционирование и горизонтальное масштабирование | Да        | Да      | Да          | Да      | Да              |
| Репликация                                         | Да        | Да      | Да          | Да      | Да              |
| Быстродействие                                     | Высокое   | Высокое | Среднее     | Высокое | Высокое         |
| Cloud-ready                                        | Да        | Да      | Да          | Да      | Да (только AWS) |
| OpenSource                                         | Нет       | Нет     | Да          | Нет     | Нет             |
| Интенсивность развития                             | Высокая   | Высокая | Высокая     | Средняя | Высокая         |
| Доступность у облачных провайдеров SaaS            | Да        | Да      | Да          | Да      | Да              |

## Decision (Решение)
Будем использовать Apache Pinot, как современное Cloud OLAP/BigData решение с возможностями User-Facing Analytics (кастомизация статистики для конечного пользователя).

## Consequences (Последствия)
Будет построен большой кластер или получим в виде SaaS. В качестве источника данных сможем использовать стримминговую систему (Kafka). 
Сможем индексировать произвлольные колонки данных, что позволит быстро обрабатывать множество параллельных запросов статистики от многих пользователей.

## Metainformation (Заметки)
* [Rockset, ClickHouse, Apache Druid или Apache Pinot? Какая база данных лучше всего подходит для клиентской аналитики?](https://embeddable.com/blog/best-databases-for-analytics)
* [Сравнение открытых OLAP-систем Big Data: ClickHouse, Druid и Pinot](https://habr.com/ru/companies/oleg-bunin/articles/351308/)
* [System Properties Comparison ClickHouse vs. Oracle vs. Snowflake](https://db-engines.com/en/system/ClickHouse%3BOracle%3BSnowflake)
* [How to choose the best analytics engine for each type of analytics](https://www.firebolt.io/blog/druid-clickhouse-and-pinot-vs-data-lakes-and-data-warehouses)
* [Comparison Chart](https://sourceforge.net/software/compare/Apache-Druid-vs-ClickHouse-vs-Firebolt-vs-Snowflake/)
* [Comparison Chart](https://sourceforge.net/software/compare/Apache-Pinot-vs-ClickHouse-vs-Firebolt-vs-Snowflake/)
* [Druid vs Pinot: Choosing the best database for Real-Time Analytics](https://imply.io/blog/choosing-a-database-for-real-time-analytics-druid-and-pinot/)
* [Architecture](https://startree.ai/blog/a-tale-of-three-real-time-olap-databases)
* [Apache Pinot Architecture](https://www.decipherzone.com/blog-detail/apache-pinot-architecture)


## Measurements (Измерения)
N/A
