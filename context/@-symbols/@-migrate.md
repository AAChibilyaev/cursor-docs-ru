# Символ @migrate - Миграции данных и систем

## Синтаксис
```
@migrate:<тип> <запрос>
@migrate:<направление> <запрос>
```

## Поддерживаемые типы миграций
1. **Базы данных**:
   ```cursor
   @migrate:db Перенеси данные в новую схему
   ```

2. **Системы**:
   ```cursor
   @migrate:system Переведи на новый сервер
   ```

3. **Форматы**:
   ```cursor
   @migrate:format Конвертируй в новый формат
   ```

## Основные возможности
1. **Планирование**:
   ```cursor
   @migrate:plan Создай план миграции
   ```

2. **Тестирование**:
   ```cursor
   @migrate:test Проверь процесс миграции
   ```

3. **Откат**:
   ```cursor
   @migrate:rollback Отмени последнюю миграцию
   ```

## Примеры использования
1. Версии БД:
   ```cursor
   @migrate:pg10to14 Обнови PostgreSQL
   ```

2. Облачные сервисы:
   ```cursor
   @migrate:aws2gcp Перенеси в Google Cloud
   ```

3. Форматы данных:
   ```cursor
   @migrate:csv2json Конвертируй данные
   ```

## Настройки
```json
{
  "@migrate": {
    "batchSize": 1000,
    "validation": {
      "samples": 5,
      "fullCheck": false
    },
    "notifications": {
      "progress": true,
      "errors": true
    },
    "rollback": {
      "enabled": true,
      "strategy": "versioned"
    }
  }
}
```

## Советы
1. Всегда делайте бэкапы (@backup)
2. Тестируйте на копиях данных
3. Используйте @monitor для контроля
4. Документируйте через @doc
5. Планируйте откатные сценарии