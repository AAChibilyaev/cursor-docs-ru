# Работа с Docker и контейнерами (Русский перевод)

## Основные команды

### 1. Управление контейнерами
```cursor
@docker:container list --all
```
Функционал:
- Фильтрация по статусу
- Просмотр потребления ресурсов
- Быстрое подключение к shell

### 2. Сборка образов
```cursor
@docker:build --optimize --size
```
Особенности:
- Анализ размера слоев
- Автоматическое кэширование
- Мульти-архитектурные сборки (arm64/amd64)

### 3. Оркестрация
```cursor
@docker:compose up --scale web=3
```
Поддерживаемые технологии:
- Docker Swarm
- Kubernetes
- Nomad

## Сравнение технологий

| Функция         | Docker            | Podman           | containerd       |
|----------------|-------------------|------------------|------------------|
| Изоляция       | namespaces        | rootless         | namespaces       |
| Безопасность   | средняя           | высокая          | высокая          |
| CLI            | полный            | совместимый      | минимальный      |

## Пример рабочего процесса
1. Создание образа:
   ```cursor
   @docker:build --tag backend:v1.2 --build-arg ENV=prod
   ```
2. Тестирование:
   ```cursor
   @docker:test --coverage
   ```
3. Публикация:
   ```cursor
   @docker:push --registry my-registry.com
   ```

## Конфигурация
```json
{
  "docker": {
    "defaultRegistry": "docker.io",
    "build": {
      "cacheTTL": "24h",
      "autoPrune": true,
      "platform": "linux/amd64"
    },
    "compose": {
      "defaultFiles": ["docker-compose.yml", "docker-compose.override.yml"]
    },
    "security": {
      "scanOnBuild": true,
      "vulnerabilityThreshold": "medium"
    }
  }
}
```

## Советы
1. Используйте `@docker:analyze` для оптимизации образов
2. Настраивайте сети через `@docker:network`
3. Мониторьте через `@docker:stats --stream`