# Символ @deploy - Развертывание приложений

## Синтаксис
```
@deploy:<среда> <запрос>
@deploy:<стратегия> <запрос>
```

## Поддерживаемые среды
1. **Локальные**:
   - Docker
   - Kubernetes
   - Virtual Machines

2. **Облачные**:
   - AWS ECS/EKS
   - Google Cloud Run
   - Azure App Service

3. **Гибридные**:
   - On-premise + Cloud
   - Multi-cloud

## Основные возможности
1. **Автоматизация**:
   ```cursor
   @deploy:production Запусти CI/CD pipeline
   ```

2. **Откат**:
   ```cursor
   @deploy:rollback Верни предыдущую версию
   ```

3. **Мониторинг**:
   ```cursor
   @deploy:status Проверь состояние развертывания
   ```

## Примеры использования
1. Канареечное развертывание:
   ```cursor
   @deploy:canary Разверни 10% трафика
   ```

2. Синий-зеленый:
   ```cursor
   @deploy:blue-green Переключи окружение
   ```

3. Миграция:
   ```cursor
   @deploy:migration Примени изменения БД
   ```

## Настройки
```json
{
  "@deploy": {
    "environments": {
      "staging": {
        "url": "https://staging.example.com",
        "approval": true
      },
      "production": {
        "url": "https://example.com",
        "backup": true
      }
    },
    "strategies": {
      "default": "rolling",
      "options": {
        "rolling": {
          "batchSize": 20,
          "pauseBetween": 30
        }
      }
    },
    "notifications": {
      "slack": "#deploys",
      "email": "devops@example.com"
    }
  }
}
```

## Советы
1. Используйте разные стратегии для разных сред
2. Настройте автоматическое тестирование перед деплоем
3. Комбинируйте с @cloud для облачных развертываний
4. Используйте @security для проверки безопасности
5. Документируйте процесс через @doc