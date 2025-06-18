# Оптимальные горячие клавиши Cursor IDE

## Основные комбинации
- `Cmd/Ctrl+K` → Открыть командную палитру
- `Cmd/Ctrl+Shift+P` → Активировать ИИ-режим
- `Cmd/Ctrl+\` → Разделить редактор
- `Cmd/Ctrl+Shift+Enter` → Запустить текущий файл

## Продвинутая настройка
```json
// settings.json (Cursor)
{
  "keyboard.shortcuts": [
    {
      "command": "editor.action.quickFix",
      "key": "Ctrl+.",
      "when": "editorTextFocus"
    },
    {
      "command": "cursorAI.explain",
      "key": "Ctrl+Shift+E"
    }
  ]
}
```

## Советы
1. Используйте `Cmd/Ctrl+,` для быстрого доступа к настройкам
2. Назначьте удобные комбинации для часто используемых ИИ-команд
3. Экспортируйте настройки через `Cursor > Preferences > Export Keybindings`