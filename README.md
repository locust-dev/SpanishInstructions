# Spanish AI - Instructions Repository

Репозиторий с инструкциями для уроков испанского языка, развернутый на Firebase Hosting.

## 📁 Структура проекта

```
SpanishInstructions/
├── .github/
│   └── workflows/
│       └── firebase-hosting.yml    # GitHub Actions для автодеплоя
├── public/                         # Корень для Firebase Hosting
│   ├── a1/                        # Уроки уровня A1 (22 intro + instruction + test)
│   │   ├── lesson_intro_1
│   │   ├── lesson_intro_2
│   │   ├── lesson_instruction_1
│   │   ├── lesson_instruction_test_1
│   │   └── ...
│   ├── a2/                        # Уроки уровня A2 (12 instruction + intro)
│   │   ├── lesson_instruction_1
│   │   ├── lesson_intro_2
│   │   └── ...
│   └── common.txt                 # Общая инструкция для всех уроков
├── firebase.json                   # Конфигурация Firebase Hosting
├── .firebaserc                     # ID проекта Firebase
└── README.md                       # Документация (этот файл)
```

## 🌐 URL структура

После деплоя все инструкции доступны по следующим URL:

### Уроки A1
```
https://spanish-ai-d5645.web.app/a1/lesson_intro_1
https://spanish-ai-d5645.web.app/a1/lesson_intro_2
...
https://spanish-ai-d5645.web.app/a1/lesson_instruction_1
https://spanish-ai-d5645.web.app/a1/lesson_instruction_test_1
```

### Уроки A2
```
https://spanish-ai-d5645.web.app/a2/lesson_instruction_1
https://spanish-ai-d5645.web.app/a2/lesson_intro_2
...
```

### Общая инструкция
```
https://spanish-ai-d5645.web.app/common.txt
```

## 📝 Как редактировать инструкции

1. Отредактируйте нужный файл в папке `public/a1/` или `public/a2/`
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
http://localhost:5000/a1/lesson_intro_1
http://localhost:5000/a2/lesson_instruction_5
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

## 📚 Именование файлов

Все файлы хранятся без расширения (кроме `common.txt`) и следуют паттернам:

- `lesson_intro_N` - Вводные сообщения для урока N
- `lesson_instruction_N` - Инструкции для урока N
- `lesson_instruction_test_N` - Инструкции для тестового урока N

Уровень языка (A1, A2, B1, B2) определяется папкой, а не именем файла.

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

