# Продвинутые техники работы с базами данных (Русский перевод)

## Оптимизация производительности

### 1. Анализ запросов
```cursor
@db:explain --visual "SELECT * FROM large_table"
```
Возможности:
- Визуализация плана выполнения
- Рекомендации по индексам
- Статистика выполнения

### 2. Настройка индексов
```cursor
@db:index --create "users_email_idx" --table users --columns email
```
Типы индексов:
- B-tree
- Hash
- GIN/GIST (для PostgreSQL)
- Полнотекстовые

### 3. Партиционирование
```cursor
@db:partition --table logs --by-range created_at
```
Стратегии:
- По диапазону
- По списку
- По хэшу

## Репликация и кластеризация

### Настройка репликации
```cursor
@db:replicate --role master --replicas 3
```
Конфигурации:
- Master-Slave
- Master-Master
- Шардирование

## Работа с транзакциями

### Управление транзакциями
```cursor
@db:transaction --isolation serializable
```
Уровни изоляции:
- Read uncommitted
- Read committed
- Repeatable read
- Serializable

## Пример сложного workflow
1. Настройка кластера:
   ```cursor
   @db:cluster --nodes 3 --shard-by user_id
   ```
2. Оптимизация:
   ```cursor
   @db:analyze --long-queries --threshold 100ms
   ```
3. Мониторинг:
   ```cursor
   @db:monitor --dashboard --metrics qps,latency
   ```

## Конфигурация
```json
{
  "databaseAdvanced": {
    "performance": {
      "queryTimeout": 10000,
      "maxConnections": 50,
      "poolSettings": {
        "min": 5,
        "max": 20
      }
    },
    "replication": {
      "enabled": true,
      "nodes": [
        {"host": "db1", "role": "master"},
        {"host": "db2", "role": "replica"}
      ]
    }
  }
}
```

## Советы экспертов
1. Используйте `@db:benchmark` для нагрузочного тестирования
2. Настройте `@db:alert` для мониторинга аномалий
3. Применяйте `@db:vacuum` для обслуживания БД