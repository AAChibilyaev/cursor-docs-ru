# Символ @learn - Обучение и управление знаниями

## Синтаксис
```
@learn:<тема> <запрос>
@learn:<ресурс> <запрос>
```

## Поддерживаемые форматы
1. **Документация**:
   ```cursor
   @learn:react Изучи основы хуков
   ```

2. **Курсы**:
   ```cursor
   @learn:docker Пройди введение в контейнеры
   ```

3. **Практика**:
   ```cursor
   @learn:algorithms Реши задачи на сортировку
   ```

## Основные возможности
1. **Персонализация**:
   ```cursor
   @learn:profile Оптимизируй мой план обучения
   ```

2. **Рекомендации**:
   ```cursor
   @learn:recommend Подбери материалы по TypeScript
   ```

3. **Прогресс**:
   ```cursor
   @learn:progress Покажи мои результаты
   ```

## Примеры использования
1. Изучение технологий:
   ```cursor
   @learn:kubernetes Освой основные концепты
   ```

2. Подготовка к собеседованию:
   ```cursor
   @learn:interview Подготовь вопросы по JavaScript
   ```

3. Решение задач:
   ```cursor
   @learn:leetcode Реши 5 задач за день
   ```

## Настройки
```json
{
  "@learn": {
    "preferences": {
      "language": "ru",
      "difficulty": "intermediate",
      "format": ["video", "text"]
    },
    "sources": {
      "default": ["mdn", "cursor-docs"],
      "external": ["freecodecamp", "leetcode"]
    },
    "tracking": {
      "dailyGoal": 60,
      "reminders": true
    }
  }
}
```

## Советы
1. Ставьте конкретные цели обучения
2. Используйте @doc для заметок
3. Комбинируйте с @practice для закрепления
4. Отслеживайте прогресс
5. Делитесь знаниями через @team