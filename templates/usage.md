# Работа с шаблонами проектов (Русский перевод)

## Основные команды

### 1. Инициализация проекта
```cursor
@template:init react-ts-admin --name my-app
```
Доступные шаблоны:
- `react-ts-admin` - Админ-панель на React+TypeScript
- `python-data-science` - Шаблон для анализа данных
- `nestjs-microservice` - Микросервис на NestJS

### 2. Управление шаблонами
```cursor
@template:manage
```
Функционал:
- Добавление/удаление шаблонов
- Обновление из репозиториев
- Создание пользовательских шаблонов

### 3. Конфигурация шаблона
```cursor
@template:config --db postgres --auth jwt
```
Опции настройки:
- Выбор СУБД
- Настройка аутентификации
- Подключение дополнительных модулей

## Таблица популярных шаблонов

| Категория       | Шаблон              | Описание                     |
|-----------------|---------------------|------------------------------|
| Веб            | `vue3-shop`        | Интернет-магазин на Vue 3    |
| Мобильные      | `react-native-auth`| Авторизация для React Native |
| API            | `fastapi-jwt`      | REST API с JWT аутентификацией|

## Пример рабочего процесса
1. Создание проекта:
   ```cursor
   @template:create node-microservice --name payment-service
   ```
2. Настройка окружения:
   ```cursor
   @template:env --prod --db mongodb
   ```
3. Запуск разработки:
   ```cursor
   @template:dev --hot-reload
   ```

## Конфигурация
```json
{
  "projectTemplates": {
    "defaultRepo": "https://templates.cursor.sh",
    "customRepos": [
      "https://github.com/company/templates"
    ],
    "cache": {
      "autoRefresh": true,
      "location": "~/.cursor/templates"
    },
    "creation": {
      "autoInstall": true,
      "gitInit": true
    }
  }
}
```

## Советы
1. Используйте `@template:preview` для предварительного просмотра
2. Экспортируйте шаблоны через `@template:export`
3. Комбинируйте шаблоны через `@template:combine`