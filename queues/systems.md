# Системы очередей сообщений (Русский перевод)

## Основные возможности

### 1. Настройка брокеров
```cursor
@mq:setup --type kafka --brokers 3
```
Поддерживаемые системы:
- Apache Kafka
- RabbitMQ
- AWS SQS
- NATS
- Redis Streams

### 2. Управление топиками/очередями
```cursor
@mq:create --name orders --partitions 5 --replication 2
```
Параметры:
- Retention policy
- Partitioning strategy
- Replication factor
- Message TTL

### 3. Мониторинг и анализ
```cursor
@mq:monitor --lag --throughput
```
Ключевые метрики:
- Consumer lag
- Message throughput
- Error rates
- Queue depth

## Сравнение технологий

| Характеристика | Kafka             | RabbitMQ          | SQS               |
|---------------|-------------------|-------------------|-------------------|
| Гарантии доставки | Exactly-once   | At-least-once     | At-least-once     |
| Производительность | Высокая      | Средняя           | Высокая           |
| Порядок сообщений | По партициям | По очереди        | FIFO/Standard     |

## Пример рабочего процесса
1. Создание топика:
   ```cursor
   @kafka:create --topic payments --partitions 10 --replication 3
   ```
2. Публикация сообщений:
   ```cursor
   @mq:produce --topic payments --key order42 --value '{"amount":100}'
   ```
3. Потребление:
   ```cursor
   @mq:consume --group processors --from-beginning
   ```

## Конфигурация
```json
{
  "messageQueues": {
    "default": "kafka",
    "kafka": {
      "brokers": ["kafka1:9092", "kafka2:9092"],
      "topics": {
        "defaultPartitions": 5,
        "defaultReplication": 2,
        "configs": {
          "retention.ms": "604800000",
          "cleanup.policy": "delete"
        }
      }
    },
    "monitoring": {
      "dashboard": true,
      "alertRules": {
        "lag": 1000,
        "errorRate": 0.01
      }
    }
  }
}
```

## Советы
1. Используйте `@mq:balance` для перераспределения партиций
2. Настройте `@mq:deadletter` для обработки ошибок
3. Применяйте `@mq:mirror` для гео-репликации