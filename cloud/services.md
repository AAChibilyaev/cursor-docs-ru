# Интеграция с облачными платформами (Русский перевод)

## Основные возможности

### 1. Управление инфраструктурой
```cursor
@cloud:infra as-code --provider aws
```
Поддерживаемые технологии:
- Terraform
- AWS CloudFormation
- Pulumi

### 2. Развертывание приложений
```cursor
@cloud:deploy --stack production
```
Возможности:
- Blue/Green deployments
- Canary-релизы
- Автомасштабирование

### 3. Мониторинг и логи
```cursor
@cloud:monitor --alerts
```
Интеграции:
- CloudWatch (AWS)
- Stackdriver (GCP)
- Azure Monitor

## Поддерживаемые платформы

| Провайдер | Команды | Особенности |
|-----------|---------|-------------|
| AWS | `@aws:*` | Полная поддержка сервисов |
| Google Cloud | `@gcp:*` | Интеграция с Firebase |
| Azure | `@azure:*` | Поддержка Active Directory |

## Пример рабочего процесса
1. Инициализация:
   ```cursor
   @cloud:init aws-lambda --name image-processor
   ```
2. Конфигурация:
   ```cursor
   @aws:config --memory 1024 --timeout 30
   ```
3. Мониторинг:
   ```cursor
   @cloud:dashboard --latency --errors
   ```

## Конфигурация
```json
{
  "cloudIntegration": {
    "defaultProvider": "aws",
    "aws": {
      "regions": ["eu-west-1", "us-east-1"],
      "defaultRole": "arn:aws:iam::123456789012:role/CloudRole"
    },
    "ciCd": {
      "autoDeploy": true,
      "approvalRequired": false
    }
  }
}
```

## Советы
1. Используйте `@cloud:cost` для контроля расходов
2. Настраивайте политики через `@cloud:policy`
3. Автоматизируйте через `@cloud:workflow`