# Интеграция с Git (Русский перевод)

## Основные функции
1. **Визуальное управление репозиторием**
   ```cursor
   @git:ui Открыть Git-панель
   ```

2. **Интеллектуальные коммиты**
   ```cursor
   @git:smartcommit Автоматически сгруппировать изменения
   ```

3. **Разрешение конфликтов**
   ```cursor
   @git:resolve Помощь в merge-конфликтах
   ```

## Рабочие процессы
### Стандартный flow
```mermaid
graph TD
    A[@git:status] --> B[@git:branch]
    B --> C[Редактирование]
    C --> D[@git:commit]
    D --> E[@git:push]
```

### Для Code Review
1. Создать ветку ревью:
   ```cursor
   @git:review ветка-для-ревью
   ```
2. Добавить комментарии:
   ```cursor
   @git:comment Улучшить обработку ошибок
   ```

## Конфигурация
```json
{
  "git": {
    "autoSync": true,
    "commitAnalysis": {
      "detectSecrets": true,
      "validateMessages": true
    },
    "blame": {
      "showAuthors": true,
      "highlightRecent": true
    }
  }
}
```

## Полезные команды
| Команда | Назначение |
|---------|------------|
| `@git:log` | Умная история коммитов |
| `@git:blame` | Показать авторов кода |
| `@git:patch` | Создать патч из изменений |

## Советы
1. Используйте `@git:hook` для настройки хуков
2. Интегрируйте с CI через `@git:ci`
3. Просматривайте статистику через `@git:stats`