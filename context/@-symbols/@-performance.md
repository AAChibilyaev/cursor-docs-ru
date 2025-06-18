# Символ @performance - Оптимизация производительности

## Синтаксис
```
@performance:<область> <запрос>
@performance:<метрика> <запрос>
```

## Поддерживаемые метрики
1. **Загрузка**:
   - Time to Interactive
   - First Contentful Paint
   - Speed Index

2. **Рендеринг**:
   - Frames per Second
   - Layout Shifts
   - Paint Times

3. **Ресурсы**:
   - Bundle Size
   - Network Requests
   - Cache Efficiency

## Основные возможности
1. **Анализ**:
   ```cursor
   @performance:analyze Проанализируй текущие показатели
   ```

2. **Оптимизация**:
   ```cursor
   @performance:optimize Улучши время загрузки
   ```

3. **Мониторинг**:
   ```cursor
   @performance:monitor Отслеживай изменения
   ```

## Примеры использования
1. Бандлы:
   ```cursor
   @performance:bundles Оптимизируй размер
   ```

2. Изображения:
   ```cursor
   @performance:images Сожми без потерь качества
   ```

3. API:
   ```cursor
   @performance:api Кэшируй частые запросы
   ```

## Настройки
```json
{
  "@performance": {
    "thresholds": {
      "fcp": 2000,
      "tti": 3500,
      "size": 500
    },
    "tools": {
      "lighthouse": true,
      "webpack-bundle-analyzer": true
    },
    "reporting": {
      "format": "html",
      "frequency": "weekly"
    }
  }
}
```

## Советы
1. Устанавливайте четкие цели
2. Используйте @analyze для диагностики
3. Комбинируйте с @ui для рендеринга
4. Документируйте улучшения через @doc
5. Тестируйте изменения через @experiment