# Расширения и плагины редактора

## Установка расширений

1. **Из маркетплейса**:
   ```cursor
   /install-extension <имя-расширения>
   ```
   Пример:
   ```cursor
   /install-extension cursor-js-utils
   ```

2. **Из файла**:
   ```cursor
   /install-extension --from-file=extension.vsix
   ```

3. **Из Git-репозитория**:
   ```cursor
   /install-extension --git=https://github.com/user/repo
   ```

## Популярные расширения

| Название             | Описание                          |
|----------------------|----------------------------------|
| Cursor JS Utils      | Утилиты для JavaScript разработки |
| Cursor AI Pack       | Дополнительные ИИ-функции        |
| Cursor Theme Pack    | Коллекция тем оформления         |
| Cursor Git Pro       | Расширенные Git-инструменты      |

## Создание своих расширений

1. **Структура проекта**:
   ```
   my-extension/
   ├── package.json
   ├── extension.js
   ├── README.md
   └── snippets/
   ```

2. **Пример package.json**:
   ```json
   {
     "name": "my-extension",
     "version": "1.0.0",
     "cursor": {
       "minimumVersion": "2.5.0",
       "contributes": {
         "commands": [{
           "command": "sayHello",
           "title": "Hello World"
         }]
       }
     }
   }
   ```

## Управление расширениями

1. **Список установленных**:
   ```cursor
   /list-extensions
   ```

2. **Обновление**:
   ```cursor
   /update-extensions --all
   ```

3. **Удаление**:
   ```cursor
   /uninstall-extension <имя-расширения>
   ```

## Настройки расширений

1. Глобальные настройки:
   ```json
   {
     "extensions": {
       "autoUpdate": true,
       "allowedSources": ["official", "verified"],
       "installPath": "./.cursor/extensions"
     }
   }
   ```

2. Настройки конкретного расширения:
   ```json
   {
     "[extension-id]": {
       "setting1": "value",
       "setting2": 42
     }
   }
   ```

## Отладка расширений
1. Запуск в режиме разработки:
   ```cursor
   /debug-extension ./path/to/extension
   ```
2. Просмотр логов:
   ```cursor
   /show-extension-logs --name=my-extension
   ```