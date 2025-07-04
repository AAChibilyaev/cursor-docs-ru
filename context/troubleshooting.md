# Устранение проблем с контекстом

## Распространенные проблемы и решения

1. **Контекст не загружается**
   - *Симптомы*: Ошибка "Context not found" или пустой контекст
   - *Проверьте*:
     ```cursor
     /context-verify <имя-контекста>
     ```
   - *Решение*:
     - Убедитесь в правильности имени
     - Проверьте доступ к хранилищу
     - Восстановите из резервной копии

2. **Несоответствие версий**
   - *Симптомы*: Расхождения в поведении между окружениями
   - *Диагностика*:
     ```cursor
     /context-diff <ctx1> <ctx2>
     ```
   - *Решение*:
     - Синхронизируйте зависимости
     - Обновите шаблоны контекста
     - Проверьте настройки IDE

3. **Производительность**
   - *Симптомы*: Медленная работа, таймауты
   - *Оптимизация*:
     ```json
     {
       "optimize": {
         "maxFileSize": 500,
         "excludePatterns": ["*.min.*"],
         "cacheTTL": "1h"
       }
     }
     ```

## Диагностические команды

| Команда                | Назначение                          |
|------------------------|------------------------------------|
| `/context-stats`       | Показать статистику использования   |
| `/context-clean`       | Очистить кэш                       |
| `/context-rebuild`     | Перестроить индекс                 |
| `/context-debug-log`   | Включить подробное логирование     |

## Логи и диагностика

1. **Просмотр логов**:
   ```cursor
   /show-context-logs --last=30min
   ```
2. **Сбор информации**:
   ```cursor
   /context-debug-info --output=report.json
   ```
3. **Тестирование**:
   ```cursor
   /context-test --validate-all
   ```

## Взаимодействие с поддержкой

1. Подготовьте:
   - Версию Cursor
   - Описание проблемы
   - Соответствующие логи
   - Пример для воспроизведения

2. Используйте:
   ```cursor
   /support-bundle --include=context
   ```
   для автоматического сбора информации

## Профилактические меры

1. Регулярно:
   - Проверяйте целостность контекстов
   - Обновляйте шаблоны
   - Очищайте кэш

2. Настройте мониторинг:
   ```json
   {
     "monitoring": {
       "alertOnSize": 10000,
       "dailyReport": true
     }
   }
   ```