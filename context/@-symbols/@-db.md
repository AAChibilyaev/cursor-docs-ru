# Символ @db - Работа с базами данных

## Синтаксис
```
@db:<тип> <запрос>
@db:<конфиг> <запрос>
```

## Поддерживаемые СУБД
1. **Реляционные**:
   - PostgreSQL
   - MySQL
   - SQLite
   - MS SQL

2. **NoSQL**:
   - MongoDB
   - Redis
   - Elasticsearch

3. **Облачные**:
   - Firebase
   - AWS DynamoDB
   - Google Cloud Datastore

## Основные возможности
1. **Запросы**:
   ```cursor
   @db:postgres Оптимизируй этот SQL-запрос
   @db:mongodb Найди дубликаты в коллекции users
   ```

2. **Схемы**:
   ```cursor
   @db:schema Сгенерируй миграцию для новой таблицы
   ```

3. **Анализ**:
   ```cursor
   @db:performance Проверь медленные запросы
   ```

## Примеры использования
1. Оптимизация:
   ```cursor
   @db:mysql EXPLAIN этот запрос
   ```

2. Миграция:
   ```cursor
   @db:psql Создай миграцию для изменения схемы
   ```

3. Тестирование:
   ```cursor
   @db:test Сгенерируй тестовые данные
   ```

## Настройки
```json
{
  "@db": {
    "connections": {
      "main": {
        "type": "postgres",
        "url": "env:DB_URL"
      },
      "cache": {
        "type": "redis",
        "host": "localhost"
      }
    },
    "query": {
      "timeout": 3000,
      "limit": 1000
    },
    "migration": {
      "autoGenerate": true,
      "folder": "migrations"
    }
  }
}
```

## Советы
1. Используйте именованные подключения
2. Настройте лимиты для запросов
3. Включите автоматическое логирование медленных запросов
4. Комбинируйте с @code для анализа запросов в коде
5. Используйте @test для тестирования работы с БД