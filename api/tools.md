# Инструменты для работы с API (Русский перевод)

## Основные команды

### 1. Интерактивный клиент API
```cursor
@api:client https://api.example.com
```
Возможности:
- Автодополнение эндпоинтов
- История запросов
- Сохранение окружений

### 2. Генерация кода
```cursor
@api:generate --language typescript --framework axios
```
Поддерживаемые комбинации:
- Python + requests/httpx
- TypeScript + axios/fetch
- Java + Retrofit/OkHttp

### 3. Тестирование API
```cursor
@api:test --scenario auth_flow
```
Функционал:
- Параметризованные тесты
- Проверка схем ответов
- Нагрузочное тестирование

## Таблица возможностей

| Категория       | Команды                          |
|-----------------|----------------------------------|
| Разработка      | `@api:mock`, `@api:validate`     |
| Документирование| `@api:docs`, `@api:spec`         |
| Мониторинг      | `@api:health`, `@api:analyze`    |

## Пример рабочего процесса
1. Создание мок-сервера:
   ```cursor
   @api:mock openapi.yaml --port 3000
   ```
2. Тестирование:
   ```cursor
   @api:test --env staging --report
   ```
3. Документирование:
   ```cursor
   @api:docs --format markdown --output API_GUIDE.md
   ```

## Конфигурация
```json
{
  "apiTools": {
    "defaultEnvironment": "development",
    "environments": {
      "development": {
        "baseUrl": "http://localhost:3000",
        "headers": {
          "Authorization": "Bearer dev_token"
        }
      }
    },
    "codegen": {
      "targetLanguage": "typescript",
      "template": "axios"
    }
  }
}
```

## Советы
1. Используйте `@api:capture` для анализа трафика
2. Интегрируйте с CI/CD через `@api:pipeline`
3. Автоматизируйте документацию через `@api:watch`