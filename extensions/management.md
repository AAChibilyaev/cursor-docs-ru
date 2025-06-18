# Управление расширениями (Русский перевод)

## Основные команды
### Установка и обновление
```cursor
@ext:install cursor-python-pro  # Установка конкретного расширения
@ext:update --all              # Обновление всех расширений
```

### Поиск и анализ
```cursor
@ext:search typescript  # Поиск расширений
@ext:audit             # Проверка безопасности
```

## Таблица популярных расширений
| Категория       | Рекомендуемые расширения          |
|-----------------|-----------------------------------|
| Python          | Pylance, Python Pro, Django Helper|
| JavaScript      | React Tools, Vue Assistant        |
| Базы данных     | SQL Navigator, MongoDB Explorer  |

## Конфигурация
```json
{
  "extensions": {
    "autoUpdate": {
      "enable": true,
      "time": "daily"
    },
    "allowedSources": [
      "official-store",
      "verified-authors"
    ],
    "blacklist": [
      "outdated-plugin"
    ]
  }
}
```

## Пример рабочего процесса
1. Поиск нужного функционала:
   ```cursor
   @ext:search database
   ```
2. Установка:
   ```cursor
   @ext:install sql-navigator --version 2.1.0
   ```
3. Настройка:
   ```cursor
   @ext:configure sql-navigator --param connectionTimeout=5000
   ```

## Советы по безопасности
1. Всегда проверяйте рейтинг расширения
2. Регулярно обновляйте расширения
3. Отключайте неиспользуемые плагины
4. Проверяйте разрешения через `@ext:permissions`