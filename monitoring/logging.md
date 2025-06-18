# Мониторинг и логирование (Русский перевод)

## Основные возможности

### 1. Настройка мониторинга
```cursor
@monitor:setup --stack prometheus-grafana
```
Поддерживаемые стеки:
- Prometheus + Grafana
- ELK (Elasticsearch + Logstash + Kibana)
- Datadog
- New Relic

### 2. Работа с логами
```cursor
@logs:analyze --time "last 1h" --level ERROR
```
Функционал:
- Фильтрация по времени/уровню
- Агрегация и статистика
- Поиск по паттернам

### 3. Настройка алертов
```cursor
@alert:create "High Load" --condition "cpu > 90% for 5m"
```
Каналы уведомлений:
- Email
- Slack
- SMS
- Webhook

## Таблица интеграций

| Система        | Тип данных       | Команды                  |
|----------------|------------------|--------------------------|
| Prometheus     | Метрики          | `@prometheus:*`          |
| Elasticsearch  | Логи             | `@elastic:*`             |
| Jaeger         | Трассировки      | `@jaeger:*`              |

## Пример рабочего процесса
1. Развертывание стека:
   ```cursor
   @monitor:deploy --stack elk --version 8.5
   ```
2. Настройка дашбордов:
   ```cursor
   @grafana:dashboard import --name "API Monitoring"
   ```
3. Анализ инцидента:
   ```cursor
   @logs:correlate --metrics --traces
   ```

## Конфигурация
```json
{
  "monitoring": {
    "default": {
      "metrics": "prometheus",
      "logs": "elasticsearch",
      "traces": "jaeger"
    },
    "retention": {
      "metrics": "30d",
      "logs": "7d",
      "traces": "2d"
    },
    "alerts": {
      "default": {
        "channels": ["slack", "email"],
        "timeout": "5m"
      }
    }
  }
}
```

## Советы
1. Используйте `@metrics:baseline` для определения нормальных значений
2. Настройте `@logs:archive` для долгосрочного хранения
3. Автоматизируйте отчеты через `@monitor:report`