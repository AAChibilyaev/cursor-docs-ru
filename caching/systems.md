# Системы кэширования (Русский перевод)

## Основные возможности

### 1. Настройка кэш-серверов
```cursor
@cache:setup --type redis --cluster --nodes 3
```
Поддерживаемые системы:
- Redis (кластерный/одиночный)
- Memcached
- Hazelcast
- In-memory кэш

### 2. Управление стратегиями
```cursor
@cache:policy --strategy lfu --ttl 1h
```
Доступные стратегии:
- LRU (Least Recently Used)
- LFU (Least Frequently Used)
- FIFO (First In First Out)
- Random

### 3. Мониторинг и анализ
```cursor
@cache:monitor --metrics hits,misses,latency
```
Метрики:
- Hit/Miss ratio
- Загрузка памяти
- Задержки запросов

## Таблица интеграций

| Система       | Особенности                     | Команды управления       |
|--------------|--------------------------------|-------------------------|
| Redis        | Поддержка кластеров, транзакции | `@redis:*`              |
| Memcached    | Простота, высокая производительность | `@memcached:*`      |
| Local Cache  | Внутрипроцессный кэш           | `@localcache:*`         |

## Пример рабочего процесса
1. Инициализация:
   ```cursor
   @cache:init --type redis --port 6379 --memory 2GB
   ```
2. Настройка:
   ```cursor
   @cache:config --policy volatile-ttl --max-items 10000
   ```
3. Оптимизация:
   ```cursor
   @cache:analyze --recommendations
   ```

## Конфигурация
```json
{
  "caching": {
    "default": "redis",
    "redis": {
      "clusterMode": true,
      "nodes": [
        {"host": "cache1", "port": 6379},
        {"host": "cache2", "port": 6379}
      ],
      "policies": {
        "eviction": "volatile-lru",
        "defaultTtl": 3600
      }
    },
    "monitoring": {
      "enabled": true,
      "dashboardUrl": "http://localhost:3000/d/cache",
      "alertThresholds": {
        "memory": 90,
        "latency": 50
      }
    }
  }
}
```

## Советы
1. Используйте `@cache:warmup` для предварительного заполнения
2. Настройте `@cache:invalidate` для поддержания актуальности данных
3. Применяйте `@cache:cluster health` для проверки состояния кластера