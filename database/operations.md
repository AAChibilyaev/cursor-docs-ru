# Работа с базами данных (Русский перевод)

## Основные команды

### 1. Подключение к БД
```cursor
@db:connect {
  "type": "postgresql",
  "host": "localhost",
  "database": "app_db",
  "username": "admin"
}
```
Поддерживаемые СУБД:
- Реляционные: PostgreSQL, MySQL, SQLite
- NoSQL: MongoDB, Redis
- Облачные: Firestore, DynamoDB

### 2. Интерактивный режим
```cursor
@db:shell --live
```
Возможности:
- Автодополнение запросов
- История команд
- Экспорт результатов в CSV/JSON

### 3. Визуализация схемы
```cursor
@db:visualize --format=svg
```
Опции:
- Фильтрация таблиц
- Настройка стилей
- Экспорт в разные форматы

## Таблица команд

| Команда | Описание |
|---------|----------|
| `@db:query` | Выполнить SQL-запрос |
| `@db:explain` | Анализ плана выполнения |
| `@db:mock` | Генерация тестовых данных |

## Пример рабочего процесса
1. Подключение:
   ```cursor
   @db:connect config/db_prod.json
   ```
2. Анализ:
   ```cursor
   @db:analyze --performance --tables users,orders
   ```
3. Оптимизация:
   ```cursor
   @db:optimize --index users_email_idx
   ```

## Конфигурация
```json
{
  "database": {
    "defaultEnvironment": "development",
    "environments": {
      "development": {
        "connectionString": "postgres://localhost/dev",
        "color": "#2ecc71"
      },
      "production": {
        "connectionString": "postgres://prod-db/app",
        "readOnly": true
      }
    },
    "features": {
      "queryHistory": true,
      "autoComplete": true,
      "erdGeneration": true
    }
  }
}
```

## Советы
1. Используйте `@db:diff` для сравнения схем
2. Настраивайте подключения через `@db:config`
3. Экспортируйте данные через `@db:export --format=json`