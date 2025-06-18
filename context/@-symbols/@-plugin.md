# Символ @plugin - Управление плагинами

## Синтаксис
```
@plugin:<действие> <запрос>
@plugin:<имя> <запрос>
```

## Поддерживаемые операции
1. **Установка**:
   ```cursor
   @plugin:install Добавь плагин TypeScript
   ```

2. **Настройка**:
   ```cursor
   @plugin:configure Настрой ESLint плагин
   ```

3. **Разработка**:
   ```cursor
   @plugin:create Создай новый плагин
   ```

## Основные возможности
1. **Поиск**:
   ```cursor
   @plugin:search Найди плагины для Python
   ```

2. **Управление**:
   ```cursor
   @plugin:list Покажи установленные плагины
   ```

3. **Отладка**:
   ```cursor
   @plugin:debug Включи режим отладки
   ```

## Примеры использования
1. Активация:
   ```cursor
   @plugin:enable Включи GitLens
   ```

2. Обновление:
   ```cursor
   @plugin:update Обнови все плагины
   ```

3. Интеграция:
   ```cursor
   @plugin:integrate Настрой интеграцию с Jira
   ```

## Настройки
```json
{
  "@plugin": {
    "repositories": {
      "official": true,
      "community": true,
      "private": "https://plugins.internal"
    },
    "permissions": {
      "install": true,
      "configure": true,
      "develop": false
    },
    "isolation": {
      "enabled": true,
      "level": "medium"
    }
  }
}
```

## Советы
1. Проверяйте источники плагинов
2. Используйте @security для проверки
3. Комбинируйте с @experiment для тестирования
4. Документируйте конфигурации через @doc
5. Обновляйте плагины регулярно