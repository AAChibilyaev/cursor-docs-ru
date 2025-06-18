# Символ @search - Поиск в коде

## Синтаксис
```
@search:<шаблон> <запрос>
@search:<scope> <запрос>
```

## Поддерживаемые типы поиска
1. **Текстовый**:
   ```cursor
   @search:"UserService" Найди все упоминания
   ```

2. **Семантический**:
   ```cursor
   @search:class:User Найди все классы User
   ```

3. **Структурный**:
   ```cursor
   @search:import:react Найди все импорты React
   ```

## Основные возможности
1. **Глобальный поиск**:
   ```cursor
   @search:global Ищи во всех проектах
   ```

2. **Фильтрация**:
   ```cursor
   @search:filter Ищи только в .ts файлах
   ```

3. **История**:
   ```cursor
   @search:history Покажи мои последние запросы
   ```

## Примеры использования
1. Поиск определений:
   ```cursor
   @search:def:calculate Найди все определения
   ```

2. Поиск использования:
   ```cursor
   @search:ref:logger Найди все вызовы
   ```

3. Комплексный поиск:
   ```cursor
   @search:"error" file:*.js Найди ошибки в JS
   ```

## Настройки
```json
{
  "@search": {
    "defaultScope": "project",
    "engines": {
      "text": "ripgrep",
      "semantic": "tree-sitter"
    },
    "preview": {
      "lines": 3,
      "context": true
    },
    "shortcuts": {
      "findAll": "Alt+F",
      "findRefs": "Alt+R"
    }
  }
}
```

## Советы
1. Используйте кавычки для точных совпадений
2. Комбинируйте с @refactor для массовых изменений
3. Сохраняйте частые запросы
4. Используйте @doc для заметок
5. Настройте горячие клавиши