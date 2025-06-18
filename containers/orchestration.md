# Оркестрация контейнеров (Русский перевод)

## Основные технологии

### 1. Развертывание кластера
```cursor
@container:cluster --type kubernetes --nodes 5
```
Поддерживаемые системы:
- Kubernetes
- Docker Swarm
- Nomad
- OpenShift

### 2. Управление подами
```cursor
@k8s:deploy --image nginx --replicas 3
```
Возможности:
- Автомасштабирование
- Rolling updates
- Canary deployments
- Blue-green deployments

### 3. Мониторинг
```cursor
@container:monitor --metrics cpu,memory,network
```
Ключевые метрики:
- Использование ресурсов
- Health checks
- Логи контейнеров
- Трассировка запросов

## Таблица команд

| Операция       | Kubernetes        | Docker Swarm      |
|---------------|-------------------|-------------------|
| Развертывание | `@k8s:apply`      | `@swarm:deploy`   |
| Масштабирование | `@k8s:scale`    | `@swarm:scale`    |
| Обновление    | `@k8s:rollout`    | `@swarm:update`   |

## Пример рабочего процесса
1. Инициализация:
   ```cursor
   @k8s:init --provider aws --nodes 3
   ```
2. Развертывание:
   ```cursor
   @container:deploy --file deployment.yaml --watch
   ```
3. Оптимизация:
   ```cursor
   @container:autoscale --cpu 80 --min 2 --max 10
   ```

## Конфигурация
```json
{
  "containerization": {
    "default": "kubernetes",
    "kubernetes": {
      "namespaces": ["prod", "stage", "dev"],
      "resourceLimits": {
        "cpu": "2",
        "memory": "4Gi"
      },
      "autoScaling": {
        "enabled": true,
        "metrics": ["cpu", "memory"],
        "scaleDownDelay": "5m"
      }
    },
    "monitoring": {
      "prometheus": true,
      "grafanaDashboards": ["cluster", "services"]
    }
  }
}
```

## Советы
1. Используйте `@container:hpa` для горизонтального масштабирования
2. Настройте `@container:probes` для health checks
3. Применяйте `@container:network` для настройки сетевых политик