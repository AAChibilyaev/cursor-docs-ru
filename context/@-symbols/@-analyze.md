# Символ @analyze - Анализ кода

## Синтаксис
```
@analyze:<файл> <запрос>
@analyze:<метрика> <запрос>
```

## Поддерживаемые типы анализа
1. **Статический анализ**:
   ```cursor
   @analyze:static Проверь код на ошибки
   ```

2. **Метрики кода**:
   ```cursor
   @analyze:metrics Рассчитай сложность
   ```

3. **Зависимости**:
   ```cursor
   @analyze:deps Построй граф зависимостей
   ```

## Основные возможности
1. **Качество кода**:
   ```cursor
   @analyze:quality Оцени по шкале 1-10
   ```

2. **Шаблоны**:
   ```cursor
   @analyze:patterns Найди антипаттерны
   ```

3. **Оптимизация**:
   ```cursor
   @analyze:perf Найди узкие места
   ```

## Примеры использования
1. Рефакторинг:
   ```cursor
   @analyze:refactor Предложи улучшения
   ```

2. Безопасность:
   ```cursor
   @analyze:security Проверь на уязвимости
   ```

3. Документирование:
   ```cursor
   @analyze:docs Сгенерируй описание API
   ```

## Настройки
```json
{
  "@analyze": {
    "tools": {
      "linters": ["eslint", "pylint"],
      "complexity": ["cyclomatic", "halstead"]
    },
    "thresholds": {
      "complexity": 15,
      "coverage": 80,
      "duplication": 5
    },
    "reporting": {
      "format": "markdown",
      "detailLevel": "advanced"
    }
  }
}
```

## Советы
1. Настройте приемлемые пороги для метрик
2. Используйте @test для проверки анализа
3. Комбинируйте с @doc для отчетов
4. Интегрируйте с @team для обсуждения
5. Регулярно запускайте анализ