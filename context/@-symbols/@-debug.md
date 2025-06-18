# Символ @debug - Инструменты отладки

## Синтаксис
```
@debug:<файл> <запрос>
@debug:<процесс> <запрос>
```

## Основные возможности
1. **Трассировка выполнения**:
   ```cursor
   @debug:app.js Трассируй выполнение функции
   ```

2. **Анализ памяти**:
   ```cursor
   @debug:memory Найди утечки
   ```

3. **Профилирование**:
   ```cursor
   @debug:profile Оптимизируй производительность
   ```

## Поддерживаемые языки
1. **JavaScript/TypeScript**:
   - Node.js inspector
   - Chrome DevTools Protocol

2. **Python**:
   - pdb
   - cProfile

3. **Другие**:
   - gdb (C/C++)
   - delve (Go)

## Примеры использования
1. Точки останова:
   ```cursor
   @debug:utils.js:15 Установи точку останова
   ```

2. Переменные:
   ```cursor
   @debug:state Покажи текущие значения
   ```

3. Исключения:
   ```cursor
   @debug:error Найди источник исключения
   ```

## Настройки
```json
{
  "@debug": {
    "defaultTool": "inspector",
    "breakpoints": {
      "persist": true,
      "maxCount": 20
    },
    "profiling": {
      "samplingRate": 1000,
      "duration": 30
    },
    "logging": {
      "level": "verbose",
      "output": "debug.log"
    }
  }
}
```

## Советы
1. Используйте условные точки останова
2. Сохраняйте сессии отладки
3. Комбинируйте с @test для отладки тестов
4. Используйте @doc для записи решений
5. Настройте автоматический дамп при ошибках