# Интеграция с системами задач (Русский перевод)

## Поддерживаемые системы
1. **Jira**:
   ```cursor
   @jira:connect https://your-domain.atlassian.net
   ```

2. **GitHub Issues**:
   ```cursor
   @issue:github link
   ```

3. **Linear**:
   ```cursor
   @linear:setup
   ```

## Основные команды
| Команда | Описание |
|---------|----------|
| `@issue:create` | Создать новую задачу |
| `@issue:list` | Показать открытые задачи |
| `@issue:log` | Записать время работы |

## Пример рабочего процесса
1. Создать ветку для задачи:
   ```cursor
   @git:branch fix/ISS-123
   ```
2. Привязать задачу:
   ```cursor
   @issue:bind ISS-123
   ```
3. После завершения:
   ```cursor
   @issue:log 2h Реализация функционала
   @issue:close
   ```

## Конфигурация
```json
{
  "issues": {
    "defaultProvider": "jira",
    "autoTransition": {
      "commit": "In Progress",
      "push": "Code Review"
    },
    "templates": {
      "bug": "Шаги воспроизведения:\n1.\n2.\n3."
    }
  }
}
```

## Полезные советы
1. Используйте `@issue:search` для быстрого поиска задач
2. Автоматизируйте статусы через `@issue:workflow`
3. Связывайте коммиты с задачами через `@issue:ref`