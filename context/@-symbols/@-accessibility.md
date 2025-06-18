# Символ @accessibility - Доступность интерфейсов

## Синтаксис
```
@accessibility:<компонент> <запрос>
@accessibility:<стандарт> <запрос>
```

## Поддерживаемые стандарты
1. **WCAG**:
   - 2.1 AA
   - 2.2 AAA

2. **ARIA**:
   - Роли
   - Свойства
   - Состояния

3. **Платформенные**:
   - iOS Accessibility
   - Android Accessibility

## Основные возможности
1. **Проверка**:
   ```cursor
   @accessibility:audit Проведи аудит страницы
   ```

2. **Исправление**:
   ```cursor
   @accessibility:fix Исправь проблемы с контрастом
   ```

3. **Оптимизация**:
   ```cursor
   @accessibility:optimize Улучши семантику
   ```

## Примеры использования
1. Формы:
   ```cursor
   @accessibility:form Добавь aria-атрибуты
   ```

2. Навигация:
   ```cursor
   @accessibility:nav Настрой клавиатурную навигацию
   ```

3. Мультимедиа:
   ```cursor
   @accessibility:media Добавь субтитры и описание
   ```

## Настройки
```json
{
  "@accessibility": {
    "level": "AA",
    "tools": {
      "axe": true,
      "wave": false
    },
    "report": {
      "format": "markdown",
      "include": ["errors", "warnings"]
    }
  }
}
```

## Советы
1. Тестируйте с реальными пользователями
2. Комбинируйте с @ui для реализации
3. Используйте @test для автоматических проверок
4. Документируйте требования через @doc
5. Обучайте команду через @learn