# Интеграция с системами контроля версий (Русский перевод)

## Основные возможности

### 1. Умный контроль версий
```cursor
@vcs:smartcommit
```
Автоматически:
- Группирует связанные изменения
- Генерирует осмысленные сообщения коммитов
- Проверяет код перед фиксацией

### 2. Визуальное управление
```cursor
@vcs:ui
```
Отображает:
- График ветвления
- Изменения файлов
- Историю отдельных строк кода

### 3. Интеграция с задачами
```cursor
@vcs:bind ISSUE-42
```
Связывает:
- Коммиты с задачами
- Ветки с трекером задач
- Pull Request'ы с релизами

## Поддерживаемые системы

| Система       | Уровень поддержки | Ключевые команды         |
|---------------|-------------------|--------------------------|
| Git           | Полная            | `@git`, `@vcs:git`       |
| Mercurial     | Базовая           | `@hg`, `@vcs:hg`         |
| SVN           | Ограниченная      | `@svn`, `@vcs:svn`       |

## Пример рабочего процесса
1. Начало работы:
   ```cursor
   @vcs:clone https://repo.example.com/project.git
   ```
2. Ежедневный workflow:
   ```cursor
   @vcs:sync --prune
   @vcs:commit -m "Рефакторинг модуля авторизации"
   @vcs:push --track
   ```
3. Code Review:
   ```cursor
   @vcs:pr create --reviewers team-lead
   ```

## Конфигурация
```json
{
  "versionControl": {
    "defaultVCS": "git",
    "git": {
      "branch": {
        "autoSetupRemote": true,
        "namingPattern": "{issue}/{user}"
      },
      "commit": {
        "validate": true,
        "template": "[{issue}] {message}"
      }
    },
    "ui": {
      "theme": "dark",
      "graphView": "curved"
    }
  }
}
```

## Советы
1. Используйте `@vcs:stash` для временного сохранения изменений
2. Анализируйте историю через `@vcs:blame`
3. Настраивайте хуки через `@vcs:hooks`