# Оптимизация производительности Cursor IDE

## Рекомендуемые настройки
```json
// settings.json
{
  "editor.fontSize": 14,
  "files.exclude": {
    "**/.git": true,
    "**/node_modules": true
  },
  "cursor.ai.largeFileThreshold": 5000
}
```

## Топ-5 советов от сообщества
1. **Используйте .cursorignore**:
   ```
   *.log
   /dist/
   /.cache/
   ```

2. **Отключите ненужные расширения** через `Ctrl+P > Disable Extension`

3. **Лимит размера файлов** для ИИ-анализа:
   ```json
   "cursor.ai.maxFileSizeKB": 200
   ```

4. **Горячие клавиши для очистки**:
   - `Ctrl+Shift+P > Clear Cache`
   - `Ctrl+Shift+P > Reload Window`

5. **Профилирование** через встроенный мониторинг (`Help > Open Process Explorer`)