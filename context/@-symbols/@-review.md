# Символ @review - Проверка кода

## Синтаксис
```
@review:<файл> <запрос>
@review:<путь> <запрос>
```

## Основные возможности
1. **Статический анализ**:
   ```cursor
   @review:static Проверь код на ошибки
   ```

2. **Стиль кода**:
   ```cursor
   @review:style Проверь соответствие гайдлайну
   ```

3. **Архитектура**:
   ```cursor
   @review:arch Оцени архитектурные решения
   ```

## Поддерживаемые проверки
1. **Автоматизированные**:
   - Линтеры
   - Проверка типов
   - Мержи-конфликты

2. **Ручной анализ**:
   - Читаемость
   - Оптимальность
   - Безопасность

3. **Командные**:
   ```cursor
   @review:team Запроси ревью у коллег
   ```

## Примеры использования
1. Полная проверка:
   ```cursor
   @review:full Проанализируй весь проект
   ```

2. Конкретный файл:
   ```cursor
   @review:service.js Проверь этот модуль
   ```

3. Сравнение:
   ```cursor
   @review:diff Сравни с предыдущей версией
   ```

## Настройки
```json
{
  "@review": {
    "tools": {
      "linters": ["eslint", "stylelint"],
      "security": ["snyk", "semgrep"]
    },
    "rules": {
      "strict": true,
      "ignorePatterns": ["*.test.js"]
    },
    "notifications": {
      "teamChannel": "#code-reviews",
      "priority": "high"
    }
  }
}
```

## Советы
1. Настройте автоматические проверки
2. Комбинируйте с @analyze для глубокого анализа
3. Используйте @team для коллективного ревью
4. Документируйте замечания через @doc
5. Интегрируйте с @git для проверки изменений