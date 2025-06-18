# Тестирование в Cursor (Русский перевод)

## Основные возможности

### 1. Генерация тестов
```cursor
@test:generate для функции calculate_total()
```
Автоматически создает:
- Unit-тесты
- Моки зависимостей
- Тестовые данные

### 2. Интеллектуальный запуск
```cursor
@test:run --failed --watch
```
Опции:
- `--failed` - только упавшие тесты
- `--watch` - режим отслеживания изменений
- `--coverage` - с анализом покрытия

### 3. Анализ результатов
```cursor
@test:analyze --flaky
```
Выявляет:
- Проблемные тесты
- Узкие места производительности
- Проблемы с изоляцией

## Поддерживаемые фреймворки

| Язык       | Фреймворки                     | Особенности              |
|------------|--------------------------------|--------------------------|
| Python     | pytest, unittest               | Автомокирование fixtures |
| JavaScript | Jest, Mocha                    | Snapshot-тестирование    |
| Java       | JUnit, TestNG                  | Параллельный запуск      |

## Пример конфигурации
```json
{
  "testing": {
    "autoGenerate": {
      "unitTests": true,
      "integrationTests": false
    },
    "coverage": {
      "minimum": 85,
      "exclude": ["generated/", "legacy/"]
    },
    "timeouts": {
      "unit": 5000,
      "integration": 30000
    }
  }
}
```

## Рабочий процесс
1. Создать тест:
   ```cursor
   @test:create для AuthService
   ```
2. Запустить с анализом:
   ```cursor
   @test:run --coverage --threshold 80
   ```
3. Исправить проблемы:
   ```cursor
   @test:fix --all
   ```

## Советы
1. Используйте `@test:data` для генерации тестовых данных
2. Анализируйте flaky-тесты через `@test:flaky`
3. Интегрируйте с CI/CD через `@test:ci`