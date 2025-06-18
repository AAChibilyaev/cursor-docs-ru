# Символ @practice - Практические упражнения

## Синтаксис
```
@practice:<тема> <запрос>
@practice:<уровень> <запрос>
```

## Поддерживаемые типы практики
1. **Кодинг-задачи**:
   ```cursor
   @practice:arrays Реши 5 задач на массивы
   ```

2. **Реальные проекты**:
   ```cursor
   @practice:react Создай todo-приложение
   ```

3. **Алгоритмы**:
   ```cursor
   @practice:sorting Реализуй быструю сортировку
   ```

## Основные возможности
1. **Генерация задач**:
   ```cursor
   @practice:generate Создай задачу по promises
   ```

2. **Проверка решений**:
   ```cursor
   @practice:check Проанализируй мой код
   ```

3. **Персонализация**:
   ```cursor
   @practice:adaptive Подбери задачи по моему уровню
   ```

## Примеры использования
1. Изучение нового:
   ```cursor
   @practice:hooks Практика с React хуками
   ```

2. Подготовка:
   ```cursor
   @practice:interview Задачи для собеседования
   ```

3. Улучшение навыков:
   ```cursor
   @practice:refactoring Улучши этот код
   ```

## Настройки
```json
{
  "@practice": {
    "difficulty": {
      "default": "medium",
      "progression": true
    },
    "feedback": {
      "instant": true,
      "detailed": true
    },
    "sources": {
      "builtin": true,
      "leetcode": true,
      "codewars": false
    },
    "tracking": {
      "streaks": true,
      "weeklyGoal": 10
    }
  }
}
```

## Советы
1. Начинайте с простых задач
2. Используйте @learn для теории
3. Комбинируйте с @debug для анализа ошибок
4. Сохраняйте решения через @code
5. Делитесь прогрессом с @team