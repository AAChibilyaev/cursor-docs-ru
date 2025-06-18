# Установка Cursor (Русский перевод)

## Системные требования
- Операционная система: Windows 10+, macOS 10.15+, Linux (Ubuntu 20.04+)
- Оперативная память: минимум 8 ГБ (рекомендуется 16 ГБ)
- Дисковое пространство: 2 ГБ свободного места

## Варианты установки
1. **Через npm** (для разработчиков):
```bash
npm install -g cursor-ide --save-dev
```

2. **Standalone версия**:
```bash
curl -fsSL https://install.cursor.sh | bash
```

3. **Docker образ**:
```bash
docker pull cursoride/stable
```

## Проверка установки
```bash
cursor --version
# Должен показать: cursor 2.3.1 или новее
```

## Первая настройка
После установки выполните:
```bash
cursor setup
```
И следуйте инструкциям мастера настройки.