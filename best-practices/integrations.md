# Интеграции и расширения для Cursor IDE

## Топ-рекомендуемые расширения
1. **GitLens** - расширенная работа с Git
2. **Docker** - управление контейнерами
3. **ESLint/Prettier** - линтинг и форматирование
4. **REST Client** - тестирование API

## Пример конфигурации для Python-разработки
```json
{
  "recommendations": [
    "ms-python.python",
    "charliermarsh.ruff",
    "ms-toolsai.jupyter"
  ],
  "python.analysis.extraPaths": ["./lib"]
}
```

## Полезные интеграции
1. **Jira/Linear** через официальные плагины
2. **Postman** для коллекций API
3. **Fig** для автодополнения в терминале

## Настройка SSH-подключения
```bash
# @terminal Настройка удалённой разработки
ssh-keygen -t ed25519 -C "cursor-ide"
cat ~/.ssh/id_ed25519.pub | clip
```