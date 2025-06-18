# Символ @cloud - Работа с облачными сервисами

## Синтаксис
```
@cloud:<провайдер> <запрос>
@cloud:<сервис> <запрос>
```

## Поддерживаемые платформы
1. **AWS**:
   - EC2, S3, Lambda
   - RDS, DynamoDB
   - CloudFormation

2. **Google Cloud**:
   - Compute Engine
   - Cloud Storage
   - Firebase

3. **Azure**:
   - Virtual Machines
   - Blob Storage
   - Cosmos DB

## Основные возможности
1. **Развертывание**:
   ```cursor
   @cloud:aws Разверни приложение на EC2
   ```

2. **Мониторинг**:
   ```cursor
   @cloud:gcp Покажи метрики за последний час
   ```

3. **Оптимизация**:
   ```cursor
   @cloud:azure Оптимизируй затраты на хранение
   ```

## Примеры использования
1. Инфраструктура:
   ```cursor
   @cloud:terraform Примени изменения
   ```

2. Хранилище:
   ```cursor
   @cloud:s3 Синхронизируй папку assets
   ```

3. Базы данных:
   ```cursor
   @cloud:rds Создай read replica
   ```

## Настройки
```json
{
  "@cloud": {
    "defaultProvider": "aws",
    "credentials": {
      "aws": "env:AWS_CREDS",
      "gcp": "file:gcp-creds.json"
    },
    "regions": {
      "primary": "us-east-1",
      "fallback": "eu-west-1"
    },
    "costAlerts": {
      "threshold": 500,
      "email": "devops@example.com"
    }
  }
}
```

## Советы
1. Используйте переменные окружения для учетных данных
2. Настройте мониторинг затрат
3. Комбинируйте с @db для облачных БД
4. Используйте @api для облачных API
5. Документируйте инфраструктуру через @doc