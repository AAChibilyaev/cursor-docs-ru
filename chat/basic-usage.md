# Работа с чатом (Русский перевод)

## Основные команды
1. **Открыть чат**:
   ```cursor
   @chat Открой чат-интерфейс
   ```

2. **Задать вопрос**:
   ```cursor
   @ask Как реализовать сортировку?
   ```

3. **Поиск по истории**:
   ```cursor
   @history Покажи обсуждения про API
   ```

## Примеры диалогов
**Пользователь**:
```cursor
@ask Как улучшить этот код?
```
**Cursor**:
```python
# Вот оптимизированная версия:
def calculate_stats(data):
    return {
        'mean': sum(data)/len(data),
        'min': min(data),
        'max': max(data)
    }
```

## Настройки чата
```json
{
  "chat": {
    "model": "cursor-ai-pro",
    "temperature": 0.7,
    "context": {
      "includeCode": true,
      "includeDocs": false
    }
  }
}
```

## Советы
1. Используйте `@examples` для запроса примеров кода
2. Уточняйте запросы через `@clarify`
3. Сохраняйте полезные ответы через `@save`