# Символ @experiment - Экспериментальные функции

## Синтаксис
```
@experiment:<функция> <запрос>
@experiment:<тест> <запрос>
```

## Поддерживаемые типы экспериментов
1. **Новые фичи**:
   ```cursor
   @experiment:ai Попробуй новую ИИ-модель
   ```

2. **Прототипы**:
   ```cursor
   @experiment:prototype Создай прототип интерфейса
   ```

3. **Технологии**:
   ```cursor
   @experiment:wasm Протестируй WebAssembly
   ```

## Основные возможности
1. **Безопасное тестирование**:
   ```cursor
   @experiment:safe Протестируй в изолированной среде
   ```

2. **Сравнение**:
   ```cursor
   @experiment:compare Сравни два подхода
   ```

3. **Оценка**:
   ```cursor
   @experiment:evaluate Оцени производительность
   ```

## Примеры использования
1. Тестирование API:
   ```cursor
   @experiment:api Попробуй новую версию
   ```

2. Оптимизация:
   ```cursor
   @experiment:perf Протестируй новый алгоритм
   ```

3. Исследование:
   ```cursor
   @experiment:research Изучи возможность внедрения
   ```

## Настройки
```json
{
  "@experiment": {
    "environment": {
      "isolation": true,
      "rollback": true
    },
    "limits": {
      "duration": "24h",
      "resources": "50%"
    },
    "reporting": {
      "auto": true,
      "level": "detailed"
    }
  }
}
```

## Советы
1. Всегда тестируйте в изоляции
2. Используйте @monitor для отслеживания
3. Комбинируйте с @team для обсуждения
4. Документируйте результаты через @doc
5. Устанавливайте четкие критерии оценки