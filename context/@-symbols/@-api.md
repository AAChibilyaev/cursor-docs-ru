# Символ @api - Работа с API

## Синтаксис
```
@api:<endpoint> <запрос>
@api:<spec> <запрос>
```

## Поддерживаемые форматы
1. **REST API**:
   ```cursor
   @api:GET /users Получи список пользователей
   ```

2. **GraphQL**:
   ```cursor
   @api:query { users { id name } } Оптимизируй запрос
   ```

3. **OpenAPI/Swagger**:
   ```cursor
   @api:openapi.json Проверь спецификацию
   ```

## Основные возможности
1. **Тестирование API**:
   ```cursor
   @api:/auth/login Протестируй с разными credentials
   ```

2. **Генерация кода**:
   ```cursor
   @api:swagger.yaml Сгенерируй клиентский SDK
   ```

3. **Мониторинг**:
   ```cursor
   @api:status Проверь здоровье всех endpoint'ов
   ```

## Примеры использования
1. Документирование:
   ```cursor
   @api:/products Сгенерируй документацию
   ```

2. Оптимизация:
   ```cursor
   @api:POST /search Улучши производительность
   ```

3. Безопасность:
   ```cursor
   @api:/admin Проверь на уязвимости
   ```

## Настройки
```json
{
  "@api": {
    "defaultBaseUrl": "https://api.example.com",
    "auth": {
      "type": "bearer",
      "token": "env:API_TOKEN"
    },
    "testing": {
      "timeout": 5000,
      "retries": 3
    },
    "codegen": {
      "target": "typescript",
      "output": "src/api"
    }
  }
}
```

## Советы
1. Используйте переменные окружения для чувствительных данных
2. Настройте автоматическое тестирование API
3. Комбинируйте с @db для полного цикла
4. Используйте @test для API-тестов
5. Регулярно обновляйте документацию