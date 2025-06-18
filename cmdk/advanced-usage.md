# Расширенные возможности CMDK (Русский перевод)

## 1. Пользовательские команды
Создание своих команд через `commands.json`:
```json
{
  "commands": [
    {
      "name": "Очистить кэш",
      "command": "rm -rf .cursor/cache",
      "category": "Утилиты"
    }
  ]
}
```

## 2. Комбинированные запросы
Примеры сложных запросов:
```cursor
@file:open app/controllers @symbol:class User*
```

## 3. Плагины CMDK
Подключаемые модули:
```cursor
@plugin:install cmdk-git-integration
```

## Таблица расширенных команд
| Команда | Описание |
|---------|----------|
| `@file:diff` | Сравнение версий файла |
| `@symbol:refactor` | Рефакторинг через поиск |
| `@project:analyze` | Анализ всего проекта |

## Пример рабочего процесса
1. Поиск всех тестов:
```cursor
@file:*test.py @symbol:test_*
```
2. Массовый рефакторинг:
```cursor
@refactor:rename старый_префикс новый_префикс
```

## Конфигурация
```json
{
  "advanced": {
    "fuzzyMatch": true,
    "searchDepth": 3,
    "customPrompts": {
      "api": "Покажи все API endpoints"
    }
  }
}
```

## Советы
1. Используйте `@history` для повторения запросов
2. Сохраняйте сложные запросы через `@save query_name`
3. Комбинируйте с `@ai` для интеллектуального поиска