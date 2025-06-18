# Символ @validate - Валидация данных

## Синтаксис
```
@validate:<тип> <запрос>
@validate:<источник> <запрос>
```

## Поддерживаемые типы валидации
1. **Формы**:
   ```cursor
   @validate:form Проверь валидацию регистрации
   ```

2. **API**:
   ```cursor
   @validate:api Валидируй входные параметры
   ```

3. **Схемы**:
   ```cursor
   @validate:schema Проверь соответствие JSON Schema
   ```

## Основные возможности
1. **Проверка**:
   ```cursor
   @validate:check Протестируй все валидаторы
   ```

2. **Генерация**:
   ```cursor
   @validate:generate Создай валидатор для модели
   ```

3. **Оптимизация**:
   ```cursor
   @validate:optimize Ускорь проверки
   ```

## Примеры использования
1. Пользовательский ввод:
   ```cursor
   @validate:input Проверь email и пароль
   ```

2. Конфигурации:
   ```cursor
   @validate:config Убедись в корректности
   ```

3. Данные БД:
   ```cursor
   @validate:db Проверь целостность
   ```

## Настройки
```json
{
  "@validate": {
    "strict": true,
    "languages": {
      "backend": "joi",
      "frontend": "yup"
    },
    "reporting": {
      "detailed": true,
      "format": "markdown"
    }
  }
}
```

## Советы
1. Используйте единые схемы
2. Комбинируйте с @security для проверок
3. Тестируйте граничные случаи
4. Документируйте правила через @doc
5. Оптимизируйте с @performance