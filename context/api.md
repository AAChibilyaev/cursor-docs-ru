# API для работы с контекстом

## Базовые методы
1. **Получение контекста**:
   ```javascript
   cursor.context.get({
     include: ['file.js', '@git:HEAD'],
     exclude: ['*.test.js']
   })
   ```
2. **Сохранение контекста**:
   ```javascript
   cursor.context.save('feature-ctx', {
     description: 'Контекст разработки фичи',
     ttl: '7d'
   })
   ```

## Расширенное API
1. **Подписка на изменения**:
   ```javascript
   cursor.context.watch({
     patterns: ['src/**'],
     callback: (changes) => {}
   })
   ```
2. **Сравнение контекстов**:
   ```javascript
   cursor.context.diff('ctx1', 'ctx2', {
     depth: 2,
     ignoreWhitespace: true
   })
   ```

## Типы данных
```typescript
interface Context {
  id: string;
  name?: string;
  files: ContextFile[];
  git?: GitContext;
  metadata: Record<string, any>;
  createdAt: Date;
  expiresAt?: Date;
}

interface ContextFile {
  path: string;
  content?: string;
  ranges?: number[][];
  language?: string;
}
```

## Пример интеграции
1. Плагин для JIRA:
   ```javascript
   cursor.context.on('save', (ctx) => {
     jira.createTicket({
       title: `Context snapshot: ${ctx.name}`,
       description: ctx.metadata
     })
   })
   ```

## Ограничения
1. **Квоты**:
   - Максимальный размер: 10MB
   - Максимальная длительность: 30 дней
   - Лимит запросов: 100/мин

2. **Безопасность**:
   - Шифрование при передаче
   - Изоляция между проектами
   - Валидация входных данных

## Обработка ошибок
```javascript
try {
  const ctx = await cursor.context.load('invalid-id')
} catch (err) {
  if (err.code === 'CONTEXT_NOT_FOUND') {
    // Специфичная обработка
  }
}
```

## Советы по разработке
1. Используйте кэширование для частых запросов
2. Оптимизируйте включаемые файлы
3. Добавляйте метаданные для поиска
4. Тестируйте на больших кодовых базах