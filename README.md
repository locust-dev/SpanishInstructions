# Spanish AI - Instructions Repository

Репозиторий с инструкциями для уроков испанского языка, развернутый на Firebase Hosting.

## 📁 Структура проекта

```
SpanishInstructions/
├── .github/
│   └── workflows/
│       └── firebase-hosting.yml    # GitHub Actions для автодеплоя
├── public/                         # Корень для Firebase Hosting
│   ├── lessons/                   # Уроки испанского языка
│   │   ├── a1/                    # Уровень A1
│   │   │   ├── intro/             # Вводные сообщения
│   │   │   │   ├── 1
│   │   │   │   ├── 2
│   │   │   │   └── ...
│   │   │   └── instruction/       # Инструкции
│   │   │       ├── 1
│   │   │       ├── 2
│   │   │       ├── test_1
│   │   │       └── ...
│   │   └── a2/                    # Уровень A2
│   │       ├── intro/             # Вводные сообщения
│   │       │   ├── 2
│   │       │   ├── 3
│   │       │   └── ...
│   │       └── instruction/       # Инструкции
│   │           ├── 1
│   │           ├── 2
│   │           └── ...
│   ├── rolePlay/                  # RolePlay сценарии
│   │   ├── 1
│   │   └── ...
│   ├── common.txt                 # Общая инструкция для всех уроков
│   └── index.html                 # Информационная страница
├── firebase.json                   # Конфигурация Firebase Hosting
├── .firebaserc                     # ID проекта Firebase
└── README.md                       # Документация (этот файл)
```

## 🌐 URL структура

После деплоя все инструкции доступны по следующим URL:

### Уроки A1
```
https://spanish-ai-d5645.web.app/lessons/a1/intro/1
https://spanish-ai-d5645.web.app/lessons/a1/intro/2
https://spanish-ai-d5645.web.app/lessons/a1/instruction/1
https://spanish-ai-d5645.web.app/lessons/a1/instruction/2
https://spanish-ai-d5645.web.app/lessons/a1/instruction/test_1
```

### Уроки A2
```
https://spanish-ai-d5645.web.app/lessons/a2/intro/2
https://spanish-ai-d5645.web.app/lessons/a2/intro/3
https://spanish-ai-d5645.web.app/lessons/a2/instruction/1
https://spanish-ai-d5645.web.app/lessons/a2/instruction/2
```

### RolePlay сценарии
```
https://spanish-ai-d5645.web.app/rolePlay/1
```

### Общая инструкция
```
https://spanish-ai-d5645.web.app/common.txt
```

## 📝 Как редактировать инструкции

1. Отредактируйте нужный файл:
   - Интро: `public/lessons/a1/intro/1` или `public/lessons/a2/intro/2`
   - Инструкции: `public/lessons/a1/instruction/1` или `public/lessons/a2/instruction/5`
   - Тестовые: `public/lessons/a1/instruction/test_1`
   - RolePlay: `public/rolePlay/1`
   - Общая: `public/common.txt`
2. Закоммитьте изменения в ветку `feature/hosting`
3. Запушьте изменения: `git push origin feature/hosting`
4. GitHub Actions автоматически задеплоит изменения на Firebase Hosting

## 🔧 Локальная разработка и тестирование

### Установка Firebase CLI

```bash
npm install -g firebase-tools
```

### Авторизация

```bash
firebase login
```

### Локальный запуск

```bash
firebase serve
```

После запуска инструкции будут доступны по адресу:
```
http://localhost:5000/lessons/a1/intro/1
http://localhost:5000/lessons/a1/instruction/5
http://localhost:5000/lessons/a1/instruction/test_1
http://localhost:5000/lessons/a2/intro/2
http://localhost:5000/lessons/a2/instruction/1
http://localhost:5000/rolePlay/1
http://localhost:5000/common.txt
```

## 🚀 Деплой

### Автоматический деплой

При push в ветку `feature/hosting` GitHub Actions автоматически деплоит изменения.

Требуется настройка GitHub Secret:
- `FIREBASE_SERVICE_ACCOUNT` - Service Account из Firebase Console

### Ручной деплой

```bash
firebase deploy --only hosting
```

## 📊 Конфигурация

### firebase.json

- **Корневая директория**: `public/`
- **CORS**: Включен для всех источников (`Access-Control-Allow-Origin: *`)
- **Content-Type**: Все файлы отдаются как `text/plain; charset=utf-8`

### .firebaserc

- **Project ID**: `spanish-ai-d5645`

## 📚 Структура и именование

Все файлы хранятся без расширения (кроме `common.txt` и `index.html`) и организованы следующим образом:

### Уроки (`lessons/`)
- **Уровень** определяется папкой: `lessons/a1/`, `lessons/a2/`, и т.д.
- **Тип** определяется подпапкой:
  - `intro/` - Вводные сообщения
  - `instruction/` - Инструкции для уроков
- **Номер урока** - это имя файла: `1`, `2`, `15`, и т.д.
- **Тестовые уроки** имеют префикс `test_`: `instruction/test_1`

Примеры:
- `lessons/a1/intro/5` - Вводное сообщение для урока 5 уровня A1
- `lessons/a2/instruction/10` - Инструкция для урока 10 уровня A2
- `lessons/a1/instruction/test_2` - Инструкция для тестового урока 2 уровня A1

### RolePlay (`rolePlay/`)
- **Номер сценария** - это имя файла: `1`, `2`, и т.д.

Примеры:
- `rolePlay/1` - RolePlay сценарий №1

## 🔐 Настройка GitHub Actions

Для работы автодеплоя необходимо добавить в GitHub Secrets репозитория:

1. Перейдите в Firebase Console → Project Settings → Service Accounts
2. Создайте новый private key (JSON)
3. Скопируйте содержимое JSON
4. В GitHub: Settings → Secrets and variables → Actions → New repository secret
5. Имя: `FIREBASE_SERVICE_ACCOUNT`
6. Значение: вставьте JSON из шага 3

## 📞 Контакты

При возникновении вопросов или проблем создайте Issue в этом репозитории.

