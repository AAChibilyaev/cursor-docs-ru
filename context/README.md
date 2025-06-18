# Документация по работе с контекстом в Cursor

## Содержание

1. [Обзор контекста](./overview.md)
2. [Управление контекстом](./management.md)
3. [Шаблоны контекста](./templates.md)
4. [Символы @](./@-symbols/overview.md)
   - [@code](./@-symbols/@-code.md)
   - [@file](./@-symbols/@-file.md)
   - [@folder](./@-symbols/@-folder.md)
   - [@git](./@-symbols/@-git.md)
   - [@web](./@-symbols/@-web.md)
5. [Отладка контекста](./debugging.md)
6. [Совместное использование](./sharing.md)
7. [Интеграция с VCS](./version-control.md)
8. [API для разработчиков](./api.md)
9. [Лучшие практики](./best-practices.md)
10. [Устранение проблем](./troubleshooting.md)
11. [Ограничения](./limitations.md)

## Быстрый старт

1. Просмотр текущего контекста:
   ```cursor
   /context-show
   ```

2. Сохранение контекста:
   ```cursor
   /context-save my-context
   ```

3. Загрузка контекста:
   ```cursor
   /context-load my-context
   ```

## Полезные команды

| Команда               | Описание                  |
|-----------------------|--------------------------|
| `/context-help`       | Справка по всем командам |
| `/context-examples`   | Примеры использования    |
| `/context-cheatsheet` | Шпаргалка по синтаксису  |

## Обратная связь

Нашли ошибку или есть предложения? Сообщите через:
```cursor
/feedback --category=context
```

## Последние обновления
- Добавлена поддержка Git LFS (2025-06-15)
- Оптимизирована работа с большими файлами (2025-06-10)
- Исправлены проблемы с кодировками (2025-06-05)