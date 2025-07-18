# Основы работы в редакторе (Русский перевод)

## Горячие клавиши
| Комбинация | Действие |
|------------|----------|
| `Ctrl+Space` | ИИ-дополнение |
| `Ctrl+Shift+P` | Палитра команд |
| `Alt+Click` | Мультикурсор |

## Основные функции
1. **Умное выделение**:
   ```cursor
   @select Выдели весь блок if-else
   ```

2. **Форматирование**:
   ```cursor
   @format Отформатируй этот файл
   ```

3. **Навигация**:
   ```cursor
   @go Перейди к определению функции
   ```

## Пример рабочего процесса
1. Откройте файл
2. Используйте `@generate` для создания кода
3. Примените `@refactor` для улучшения
4. Проверьте через `@debug`
5. Сохраните в контекст `@context:save`

## Настройки редактора
```json
{
  "editor": {
    "fontSize": 14,
    "autoSave": true,
    "suggestions": {
      "ai": true,
      "delay": 300
    }
  }
}
```