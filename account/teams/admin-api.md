# API для администраторов команд

## Обзор возможностей
- Управление участниками команды
- Настройка прав доступа
- Получение статистики использования
- Управление подписками

## Аутентификация
```javascript
const headers = {
  'Authorization': 'Bearer YOUR_API_KEY',
  'Content-Type': 'application/json'
}
```

## Основные endpoints
1. `GET /team/members` - список участников
2. `POST /team/invite` - приглашение новых участников
3. `PUT /team/roles` - изменение прав доступа
4. `GET /team/usage` - статистика использования

## Пример запроса
```python
import requests

response = requests.get(
  'https://api.cursor.com/v1/team/members',
  headers={'Authorization': 'Bearer YOUR_API_KEY'}
)
```

## Ограничения
- 100 запросов в минуту
- Только для корпоративных аккаунтов
- Требуется подтверждение домена

## Логирование действий
Все изменения через API фиксируются в журнале аудита.