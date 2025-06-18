# Конфигурация редактора

## Основные настройки

1. **Языковые**:
   ```json
   {
     "editor": {
       "defaultLanguage": "typescript",
       "languageServers": {
         "python": "pylance",
         "go": "gopls"
       }
     }
   }
   ```

2. **Форматирование**:
   ```json
   {
     "editor.formatOnSave": true,
     "editor.formatOnPaste": false,
     "formatter": {
       "prettier": {
         "singleQuote": true,
         "semi": false
       }
     }
   }
   ```

## Расширенные параметры

1. **Производительность**:
   ```json
   {
     "editor.performance": {
       "memoryLimit": 4096,
       "workerThreads": 4,
       "fileSizeThreshold": 5000
     }
   }
   ```

2. **ИИ-ассистент**:
   ```json
   {
     "ai": {
       "suggestionDelay": 300,
       "maxSuggestions": 5,
       "acceptanceThreshold": 0.7
     }
   }
   ```

## Рабочая область

1. **Макет**:
   - Режимы разделения экрана
   - Закрепление вкладок
   - Группы редакторов

2. **Внешний вид**:
   ```json
   {
     "workbench": {
       "theme": "Cursor Dark",
       "iconTheme": "material-icons",
       "fontFamily": "Fira Code"
     }
   }
   ```

## Специальные режимы

1. **Режим разработчика**:
   ```cursor
   /enable-dev-mode
   ```
   - Расширенные логи
   - Экспериментальные функции
   - Профилирование

2. **Минималистичный режим**:
   ```json
   {
     "minimalMode": {
       "enabled": true,
       "hideToolbar": true,
       "focusOnly": true
     }
   }
   ```

## Импорт/экспорт
1. Экспорт настроек:
   ```cursor
   /export-settings --file=my-settings.json
   ```
2. Импорт настроек:
   ```cursor
   /import-settings --file=team-settings.json
   ```