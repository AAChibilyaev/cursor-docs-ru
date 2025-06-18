# Инструменты безопасности (Русский перевод)

## Основные возможности

### 1. Статический анализ кода (SAST)
```cursor
@security:sast --tool semgrep --rules owasp
```
Поддерживаемые инструменты:
- Semgrep
- SonarQube
- Checkmarx

### 2. Анализ зависимостей (SCA)
```cursor
@security:dependencies --fix --report
```
Интеграции:
- Snyk
- Dependabot
- OWASP Dependency-Check

### 3. Динамический анализ (DAST)
```cursor
@security:dast --target https://app.example.com
```
Возможности:
- Сканирование OWASP Top 10
- Фаззинг API
- Проверка конфигураций

## Таблица утилит

| Категория      | Инструмент         | Пример команды            |
|---------------|--------------------|---------------------------|
| SAST          | Semgrep            | `@sast:scan --deep`       |
| Секреты       | GitLeaks           | `@secrets:detect`         |
| Контейнеры    | Trivy              | `@container:scan`         |

## Пример рабочего процесса
1. Проверка кода:
   ```cursor
   @security:code --critical --html-report
   ```
2. Аудит зависимостей:
   ```cursor
   @security:deps --level high
   ```
3. Харденинг:
   ```cursor
   @security:harden --cis-docker
   ```

## Конфигурация безопасности
```json
{
  "securityConfig": {
    "defaultTools": {
      "sast": "semgrep",
      "sca": "snyk",
      "secrets": "gitleaks"
    },
    "policies": {
      "failThreshold": "high",
      "autoUpdate": true,
      "exclusions": ["test/**", "mocks/**"]
    },
    "notifications": {
      "slackChannel": "#appsec",
      "emailGroup": "security-team@example.com"
    }
  }
}
```

## Советы
1. Используйте `@security:ci` для интеграции в пайплайны
2. Настройте `@security:monitor` для постоянного сканирования
3. Генерируйте отчеты через `@security:report --format pdf`