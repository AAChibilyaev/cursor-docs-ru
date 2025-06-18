# Фреймворк для тестирования (Русский перевод)

## Основные возможности

### 1. Создание тестов
```cursor
@test:create --type unit --language python
```
Поддерживаемые типы тестов:
- Unit-тесты
- Интеграционные
- E2E
- Нагрузочные

### 2. Запуск тестов
```cursor
@test:run --coverage --parallel
```
Опции:
- Фильтрация по тегам
- Параллельное выполнение
- Генерация отчетов

### 3. Мокирование
```cursor
@test:mock database --behavior empty
```
Возможности:
- Моки API
- Стабы сервисов
- Фейковые базы данных

## Поддерживаемые фреймворки

| Язык       | Фреймворки                     |
|------------|--------------------------------|
| Python     | pytest, unittest, doctest     |
| JavaScript | Jest, Mocha, Jasmine          |
| Java       | JUnit, TestNG                 |

## Пример рабочего процесса
1. Генерация тестов:
   ```cursor
   @test:generate --source user_service.py
   ```
2. Настройка окружения:
   ```cursor
   @test:env --db mock --cache disabled
   ```
3. Анализ результатов:
   ```cursor
   @test:analyze --flaky --slow
   ```

## Конфигурация
```json
{
  "testing": {
    "defaultFramework": "pytest",
    "python": {
      "pytest": {
        "markers": ["unit", "integration"],
        "timeout": 30
      }
    },
    "coverage": {
      "threshold": 80,
      "exclude": ["migrations/*"]
    },
    "ci": {
      "parallel": true,
      "retryFailed": 1
    }
  }
}
```

## Советы
1. Используйте `@test:watch` для разработки
2. Анализируйте покрытие через `@test:coverage`
3. Интегрируйте с CI через `@test:ci`