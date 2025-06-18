# Символ @monitor - Мониторинг и наблюдение

## Синтаксис
```
@monitor:<система> <запрос>
@monitor:<метрика> <запрос>
```

## Поддерживаемые системы
1. **Инфраструктура**:
   - Prometheus
   - Datadog
   - New Relic

2. **Приложения**:
   - Application Insights
   - OpenTelemetry
   - Sentry

3. **Логи**:
   - ELK Stack
   - Splunk
   - Graylog

## Основные возможности
1. **Метрики**:
   ```cursor
   @monitor:metrics Покажи загрузку CPU
   ```

2. **Логи**:
   ```cursor
   @monitor:logs Найди ошибки за последний час
   ```

3. **Трейсинг**:
   ```cursor
   @monitor:trace Анализируй этот запрос
   ```

## Примеры использования
1. Оптимизация:
   ```cursor
   @monitor:performance Найди узкие места
   ```

2. Оповещения:
   ```cursor
   @monitor:alerts Настрой уведомления
   ```

3. Анализ:
   ```cursor
   @monitor:errors Сгруппируй похожие ошибки
   ```

## Настройки
```json
{
  "@monitor": {
    "connections": {
      "prometheus": "http://prometheus:9090",
      "sentry": "env:SENTRY_DSN"
    },
    "dashboards": {
      "default": "overview",
      "refresh": 30
    },
    "alerts": {
      "thresholds": {
        "cpu": 90,
        "memory": 85,
        "errors": 10
      },
      "channels": ["slack", "email"]
    }
  }
}
```

## Советы
1. Настройте базовые уровни для метрик
2. Используйте корреляцию событий
3. Комбинируйте с @debug для устранения проблем
4. Интегрируйте с @deploy для контроля релизов
5. Сохраняйте историю через @doc