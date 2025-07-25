# Символ @team - Командная работа

## Синтаксис
```
@team:<название-команды> <запрос>
@team:<роль> <запрос>
```

## Основные функции
1. **Командная аналитика**:
   - Активность участников
   - Распределение задач
   - Анализ code review

2. **Совместная работа**:
   ```cursor
   @team:frontend Оптимизируйте работу с API
   @team:code-reviewers Проверьте этот PR
   ```

## Типы команд
1. **По проектам**:
   ```cursor
   @team:project-alpha Назначьте ответственных
   ```

2. **По ролям**:
   ```cursor
   @team:devops Настройте deployment
   ```

3. **Гибридные**:
   ```cursor
   @team:mobile-frontend Синхронизируйте компоненты
   ```

## Примеры использования
1. Планирование:
   ```cursor
   @team:backend Спланируйте миграцию на новую версию
   ```

2. Координация:
   ```cursor
   @team:qa Протестируйте новые фичи
   ```

3. Аналитика:
   ```cursor
   @team:all Покажите метрики за последний месяц
   ```

## Настройки
```json
{
  "@team": {
    "defaultTeams": {
      "frontend": ["user1", "user2"],
      "backend": ["user3", "user4"]
    },
    "notifications": {
      "mentions": true,
      "statusUpdates": true
    },
    "accessControl": {
      "viewStats": "all",
      "editTeams": "admins"
    }
  }
}
```

## Советы
1. Создавайте именованные команды для частых задач
2. Используйте роли для гибкого назначения
3. Настройте автоматические уведомления
4. Регулярно обновляйте состав команд
5. Комбинируйте с @project для проектно-командной работы