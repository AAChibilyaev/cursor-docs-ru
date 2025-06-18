# Символ @backup - Резервное копирование и восстановление

## Синтаксис
```
@backup:<действие> <запрос>
@backup:<цель> <запрос>
```

## Поддерживаемые операции
1. **Создание**:
   ```cursor
   @backup:create Создай резервную копию БД
   ```

2. **Восстановление**:
   ```cursor
   @backup:restore Восстанови из последней копии
   ```

3. **Управление**:
   ```cursor
   @backup:list Покажи доступные бэкапы
   ```

## Основные возможности
1. **Автоматизация**:
   ```cursor
   @backup:schedule Настрой ежедневное копирование
   ```

2. **Проверка**:
   ```cursor
   @backup:verify Проверь целостность бэкапа
   ```

3. **Шифрование**:
   ```cursor
   @backup:encrypt Зашифруй резервные копии
   ```

## Примеры использования
1. Базы данных:
   ```cursor
   @backup:pgdump Создай дамп PostgreSQL
   ```

2. Файлы:
   ```cursor
   @backup:files Сохрани конфигурации
   ```

3. Полная система:
   ```cursor
   @backup:full Полный бэкап сервера
   ```

## Настройки
```json
{
  "@backup": {
    "schedule": {
      "interval": "daily",
      "retention": 7
    },
    "storage": {
      "local": "/backups",
      "remote": "s3://backup-bucket"
    },
    "encryption": {
      "enabled": true,
      "method": "aes-256"
    },
    "verification": {
      "checksum": true,
      "testRestore": false
    }
  }
}
```

## Советы
1. Храните копии в разных местах
2. Тестируйте восстановление
3. Используйте @security для защиты
4. Документируйте через @doc
5. Интегрируйте с @monitor для контроля