# Интеграция с CI/CD системами (Русский перевод)

## Основные возможности

### 1. Управление пайплайнами
```cursor
@cicd:pipeline manage --provider gitlab
```
Поддерживаемые системы:
- GitHub Actions
- GitLab CI/CD
- Jenkins
- CircleCI
- Azure DevOps

### 2. Шаблоны конфигураций
```cursor
@cicd:template list --language python
```
Доступные шаблоны:
- Node.js (npm/yarn)
- Python (pip/poetry)
- Java (Maven/Gradle)
- Docker

### 3. Оркестрация развертывания
```cursor
@cicd:deploy --strategy blue-green
```
Стратегии:
- Canary-релизы
- Rolling updates
- Feature flags

## Таблица интеграций

| Функция         | GitHub Actions      | GitLab CI/CD       |
|----------------|---------------------|--------------------|
| Кэширование    | `@gha:cache`        | `@gitlab:cache`    |
| Секреты        | `@gha:secrets`      | `@gitlab:variables`|
| Матрица тестов | `@gha:matrix`       | `@gitlab:parallel` |

## Пример рабочего процесса
1. Инициализация:
   ```cursor
   @cicd:init --provider github --template nodejs
   ```
2. Настройка:
   ```cursor
   @cicd:configure --test-command "npm test"
   ```
3. Мониторинг:
   ```cursor
   @cicd:monitor --dashboard
   ```

## Конфигурация
```json
{
  "ciCd": {
    "defaultProvider": "github",
    "providers": {
      "github": {
        "workflowDir": ".github/workflows",
        "defaultBranch": "main"
      },
      "gitlab": {
        "stages": ["build", "test", "deploy"],
        "timeout": 3600
      }
    },
    "notifications": {
      "slack": {
        "channel": "#ci-alerts",
        "events": ["failure", "recovery"]
      }
    }
  }
}
```

## Советы
1. Используйте `@cicd:optimize` для ускорения сборок
2. Настраивайте кэширование через `@cicd:cache`
3. Автоматизируйте rollback через `@cicd:rollback`