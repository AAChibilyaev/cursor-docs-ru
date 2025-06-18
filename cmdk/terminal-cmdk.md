# Терминальная интеграция CMDK

## Активация терминального режима
1. В терминале введите `cursor`
2. Или используйте горячую клавишу `Ctrl+Shift+``

## Основные команды терминала
| Команда          | Описание                          |
|------------------|----------------------------------|
| cursor --help    | Справка по командам              |
| cursor --search  | Поиск по кодовой базе           |
| cursor --fix     | Автоисправление кода             |
| cursor --ask     | Задать вопрос в чате             |
| cursor --viz     | Визуализировать код              |

## Контекстные действия
1. Навигация:
   ```bash
   cursor --go-to-definition utils.js:42
   ```
2. Рефакторинг:
   ```bash
   cursor --refactor --rename-variable oldName newName
   ```
3. Анализ:
   ```bash
   cursor --analyze --complexity src/
   ```

## Интеграция с shell
1. Добавьте алиасы в `.bashrc`/`.zshrc`:
   ```bash
   alias cfix='cursor --fix'
   alias cask='cursor --ask'
   ```
2. Используйте в пайплайнах:
   ```bash
   git diff | cursor --explain-changes
   ```

## Настройки терминала
```json
{
  "terminal": {
    "defaultShell": "zsh",
    "enableAI": true,
    "promptFormat": "[cursor] $ ",
    "historySize": 1000
  }
}
```

## Примеры использования
1. Быстрый поиск:
   ```bash
   cursor --search "function parseData"
   ```
2. Генерация кода:
   ```bash
   cursor --generate "React component" > Button.js
   ```
3. Пакетная обработка:
   ```bash
   find . -name "*.js" | xargs cursor --lint
   ```