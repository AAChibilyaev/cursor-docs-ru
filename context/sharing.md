# Совместное использование контекста

## Методы совместной работы
1. **Экспорт/импорт**:
   ```cursor
   /context-export team-review.json
   /context-import team-review.json
   ```
2. **Облачные шаблоны**:
   - Доступ через организацию
   - Версионность
   - Контроль доступа

3. **Ссылки для совместной работы**:
   ```
   cursor://context/share/abc123
   ```

## Настройки доступа
| Уровень       | Права                          |
|--------------|-------------------------------|
| Чтение       | Просмотр контекста            |
| Комментарий  | Добавление заметок            |
| Редактирование| Изменение контекста          |
| Администратор| Управление доступом           |

## Примеры workflow
1. **Код-ревью**:
   - Экспорт контекста ревью
   - Добавление комментариев
   - Отслеживание изменений

2. **Обучение**:
   - Шаблоны с учебными примерами
   - Пошаговые руководства
   - Интерактивные демонстрации

3. **Командная разработка**:
   - Общий контекст фичи
   - Синхронизация изменений
   - История модификаций

## Интеграции
1. **Системы контроля версий**:
   - Привязка к веткам
   - Diff контекстов
   - Конфликты и разрешения

2. **Мессенджеры**:
   - Быстрая отправка сниппетов
   - Обсуждение в контексте
   - Уведомления об изменениях

## Безопасность
```json
{
  "sharing": {
    "encryption": true,
    "linkExpiration": "7d",
    "watermark": true,
    "accessLogs": true
  }
}
```

## Советы
1. Ограничивайте доступ к чувствительным данным
2. Используйте срок действия для временных ссылок
3. Добавляйте метаданные для удобства поиска
4. Ведите историю изменений общих контекстов