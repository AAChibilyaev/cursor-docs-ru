# Быстрый старт с Cursor (Русский перевод)

## 1. Установка
```bash
npm install -g cursor-ide
```

## 2. Первый запуск
```bash
cursor init
cursor start
```

## 3. Основные команды
| Команда | Описание |
|---------|----------|
| `@help` | Справка |
| `@doc`  | Документирование кода |
| `@fix`  | Исправление ошибок |

## 4. Пример работы
```python
# Напишите:
@create функция калькулятора

# Cursor предложит:
def calculator(a, b, operation):
    if operation == '+':
        return a + b
    elif operation == '-':
        return a - b
    # ...
```