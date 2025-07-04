# Команда /ask (Задать вопрос)

## Основные возможности
- Получение ответов на технические вопросы
- Контекстно-зависимые объяснения
- Примеры кода по запросу
- Альтернативные решения

## Синтаксис запросов
```cursor
/ask Как реализовать сортировку на Python?
/ask @file.js: Как исправить эту ошибку?
/ask [выделенный код]: Почему это не работает?
```

## Особенности работы
1. **Понимание контекста**:
   - Анализирует открытые файлы
   - Учитывает историю чата
   - Распознает технологический стек

2. **Форматирование ответов**:
   - Подсветка синтаксиса
   - Разделение на шаги
   - Ссылки на документацию
   - Примеры кода

3. **Уточняющие вопросы**:
   - При недостаточном контексте
   - Для выбора между вариантами
   - Для уточнения требований

## Примеры использования
1. Получение справки по API:
   `/ask Как использовать fetch() в JavaScript?`

2. Анализ ошибки:
   `/ask Почему я получаю "TypeError: undefined is not a function"?`

3. Запрос лучших практик:
   `/ask Какие есть лучшие практики для React hooks?`

## Советы по эффективным запросам
- Указывайте язык/технологию
- Приводите примеры ошибок
- Разделяйте сложные вопросы
- Используйте @ для привязки к файлам