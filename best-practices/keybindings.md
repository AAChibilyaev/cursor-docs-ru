# ⌨️ Горячие клавиши Cursor IDE (версия 1.1)

```mermaid
graph TD
    A[Основные клавиши] --> B[Командная палитра]
    A --> C[ИИ-режим]
    A --> D[Навигация]
```

## Основные комбинации
| Комбинация | Действие | Частота использования |
|------------|----------|----------------------|
| `Cmd/Ctrl+K` | Командная палитра | ⭐⭐⭐⭐⭐ |
| `Cmd/Ctrl+Shift+P` | ИИ-режим | ⭐⭐⭐⭐ |
| `Cmd/Ctrl+\` | Разделить редактор | ⭐⭐⭐ |

## Реальные кейсы
```python
# Быстрый рефакторинг через Ctrl+.
def old_func():
    # @refactor: преобразовать в list comprehension
    result = []
    for i in range(10):
        result.append(i*2)
```
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