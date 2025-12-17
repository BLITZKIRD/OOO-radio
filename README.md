# ПРИЛОЖЕНИЕ 4
## СОСТАВ РЕПОЗИТОРИЯ ПРОЕКТА

ООО "Радио"  
Проект: Информационная система управления магазином радиоэлектроники (ИСУМ) v2.0

## 1. ИНФОРМАЦИЯ О РЕПОЗИТОРИИ

- Платформа: GitHub
- Система контроля версий: Git
- **Дата создания:** 15.01.2024
- **Последнее обновление:** 28.02.2024
- **Версия:** 2.0.1

---

## 2. СТРУКТУРА РЕПОЗИТОРИЯ

```
isu-m-v2/
│
├── .gitignore                      # Игнорируемые файлы Git
├── README.md                       # Описание проекта
├── LICENSE                         # Лицензия проекта
├── CHANGELOG.md                    # История изменений
├── .env.example                    # Пример файла конфигурации
│
├── docs/                           # Документация проекта
│   ├── architecture.md             # Архитектура системы
│   ├── api/                        # Документация API
│   │   ├── v1/
│   │   │   ├── products.md         # API товаров
│   │   │   ├── sales.md            # API продаж
│   │   │   └── warehouse.md        # API склада
│   ├── database/                   # Схема базы данных
│   │   ├── schema.sql              # SQL-схема БД
│   │   └── migrations/             # Миграции БД
│   └── user-guide/                 # Руководство пользователя
│       └── user-manual.md
│
├── backend/                        # Backend приложение
│   ├── src/
│   │   ├── config/                 # Конфигурация
│   │   │   ├── database.php
│   │   │   └── app.php
│   │   ├── controllers/            # Контроллеры
│   │   │   ├── ProductController.php
│   │   │   ├── SaleController.php
│   │   │   ├── WarehouseController.php
│   │   │   ├── ClientController.php
│   │   │   └── UserController.php
│   │   ├── models/                 # Модели данных
│   │   │   ├── Product.php
│   │   │   ├── Sale.php
│   │   │   ├── Client.php
│   │   │   ├── Supplier.php
│   │   │   └── User.php
│   │   ├── services/               # Бизнес-логика
│   │   │   ├── ProductService.php
│   │   │   ├── SaleService.php
│   │   │   └── WarehouseService.php
│   │   ├── middleware/             # Промежуточное ПО
│   │   │   ├── AuthMiddleware.php
│   │   │   └── ValidationMiddleware.php
│   │   ├── routes/                 # Маршруты
│   │   │   └── api.php
│   │   └── index.php               # Точка входа
│   ├── tests/                      # Тесты
│   │   ├── unit/
│   │   └── integration/
│   ├── composer.json               # Зависимости PHP
│   └── phpunit.xml                 # Конфигурация PHPUnit
│
├── frontend/                       # Frontend приложение
│   ├── src/
│   │   ├── components/             # React компоненты
│   │   │   ├── Products/
│   │   │   │   ├── ProductList.jsx
│   │   │   │   ├── ProductForm.jsx
│   │   │   │   └── ProductCard.jsx
│   │   │   ├── Sales/
│   │   │   │   ├── SaleForm.jsx
│   │   │   │   └── SaleList.jsx
│   │   │   ├── Warehouse/
│   │   │   │   └── WarehouseStatus.jsx
│   │   │   └── common/             # Общие компоненты
│   │   │       ├── Header.jsx
│   │   │       ├── Sidebar.jsx
│   │   │       └── Modal.jsx
│   │   ├── pages/                  # Страницы
│   │   │   ├── Dashboard.jsx
│   │   │   ├── Products.jsx
│   │   │   ├── Sales.jsx
│   │   │   └── Warehouse.jsx
│   │   ├── services/               # API-сервисы
│   │   │   ├── api.js
│   │   │   └── auth.js
│   │   ├── store/                  # Redux store
│   │   │   ├── slices/
│   │   │   │   ├── productSlice.js
│   │   │   │   ├── saleSlice.js
│   │   │   │   ├── warehouseSlice.js
│   │   │   │   └── authSlice.js
│   │   │   └── store.js
│   │   ├── utils/                  # Утилиты
│   │   │   └── helpers.js
│   │   ├── App.jsx                 # Главный компонент
│   │   └── index.jsx               # Точка входа
│   ├── public/
│   │   ├── index.html
│   │   └── assets/                 # Статические ресурсы
│   ├── package.json                # Зависимости Node.js
│   └── .eslintrc.js                # Конфигурация ESLint
│
├── database/                       # База данных
│   ├── migrations/                 # Миграции
│   │   ├── 001_create_users_table.sql
│   │   ├── 002_create_products_table.sql
│   │   ├── 003_create_sales_table.sql
│   │   ├── 004_create_clients_table.sql
│   │   └── 005_create_suppliers_table.sql
│   ├── seeds/                      # Начальные данные
│   │   └── initial_data.sql
│   └── backups/                    # Резервные копии (игнорируется)
│
├── scripts/                        # Вспомогательные скрипты
│   ├── deploy.sh                   # Скрипт развёртывания
│   ├── backup.sh                   # Скрипт резервного копирования
│   └── migrate.sh                  # Скрипт миграции БД
│
├── docker/                         # Docker конфигурация
│   ├── Dockerfile.backend
│   ├── Dockerfile.frontend
│   └── docker-compose.yml
│
└── tests/                          # Общие тесты
    ├── e2e/                        # End-to-end тесты
    └── performance/                # Тесты производительности
```

## 3. ОПИСАНИЕ ВЕТОК (BRANCHES)

### 3.1. Основные ветки

- main - основная ветка для продакшн-версии
  - Последний коммит: v2.0.1
  - Защищена от прямых коммитов
  - Требует pull request для изменений

- develop - ветка разработки
  - Текущая рабочая ветка для новых функций
  - Используется для интеграции изменений

- hotfix/ - ветки для срочных исправлений
  - Создаются от main
  - После исправления мержатся в main и develop

### 3.2. Вспомогательные ветки

- feature/ - ветки для новых функций
  - Примеры: `feature/schedule-calendar`, `feature/content-upload`

- bugfix/ - ветки для исправления ошибок
  - Примеры: `bugfix/login-error`, `bugfix/schedule-display`

- release/ - ветки для подготовки релизов
  - Примеры: `release/v2.0.1`, `release/v2.1.0`

---

## 4. ОСНОВНЫЕ ФАЙЛЫ И ИХ НАЗНАЧЕНИЕ

### 4.1. Корневые файлы

| Файл | Назначение |
|------|------------|
| `.gitignore` | Список файлов и директорий, игнорируемых Git |
| `README.md` | Основная информация о проекте, инструкции по установке и запуску |
| `LICENSE` | Лицензионное соглашение проекта |
| `CHANGELOG.md` | История изменений по версиям |
| `.env.example` | Пример файла с переменными окружения |

### 4.2. Backend файлы

| Файл/Директория | Назначение |
|-----------------|------------|
| `backend/src/controllers/` | Обработка HTTP-запросов, бизнес-логика на уровне контроллеров |
| `backend/src/models/` | Модели данных, работа с базой данных |
| `backend/src/services/` | Бизнес-логика приложения |
| `backend/src/routes/` | Определение маршрутов API |
| `backend/composer.json` | Зависимости PHP, конфигурация проекта |

### 4.3. Frontend файлы

| Файл/Директория | Назначение |
|-----------------|------------|
| `frontend/src/components/` | React компоненты пользовательского интерфейса |
| `frontend/src/pages/` | Страницы приложения |
| `frontend/src/store/` | Redux store для управления состоянием |
| `frontend/src/services/` | Сервисы для работы с API |
| `frontend/package.json` | Зависимости Node.js, скрипты сборки |

### 4.4. Документация

| Файл/Директория | Назначение |
|-----------------|------------|
| `docs/architecture.md` | Архитектурная документация системы |
| `docs/api/` | Документация REST API |
| `docs/database/` | Схема базы данных, миграции |
| `docs/user-guide/` | Руководство пользователя |

## 5. СТАТИСТИКА РЕПОЗИТОРИЯ

### 5.1. Количество файлов

- Всего файлов: 127
- Файлов исходного кода: 89
- Файлов документации: 15
- Файлов конфигурации: 12
- Тестовых файлов: 11

### 5.2. Языки программирования

- JavaScript/JSX: 45 файлов (42%)
- PHP: 28 файлов (26%)
- SQL: 8 файлов (7%)
- Markdown: 15 файлов (14%)
- Конфигурационные: 12 файлов (11%)

### 5.3. Коммиты

- Всего коммитов: 247
- Коммитов в main: 89
- Коммитов в develop: 158
- Последний коммит: 28.02.2024

## 6. ПРАВИЛА РАБОТЫ С РЕПОЗИТОРИЕМ

### 6.1. Процесс разработки

1. Создание ветки от `develop` для новой функции
2. Разработка и коммиты в feature-ветку
3. Создание Pull Request в `develop`
4. Code review
5. Мердж в `develop` после одобрения
6. Тестирование в `develop`
7. Создание Pull Request из `develop` в `main` для релиза

### 6.2. Стандарты коммитов

Формат коммитов: `type(scope): subject`

- type: feat, fix, docs, style, refactor, test, chore
- scope: область изменений (schedule, content, advertising, auth)
- subject: краткое описание изменений

Примеры:
- `feat(schedule): add calendar view for schedule`
- `fix(content): resolve file upload error`
- `docs(api): update schedule API documentation`

## 7. ТРЕБОВАНИЯ К РАЗВЕРТЫВАНИЮ

### 7.1. Минимальные требования

- Backend:
  - PHP 7.4+
  - PostgreSQL 12+ или MySQL 8.0+
  - Composer 2.0+

- Frontend:
  - Node.js 16+
  - npm 7+ или yarn 1.22+

### 7.2. Зависимости

- Backend зависимости указаны в `backend/composer.json`
- Frontend зависимости указаны в `frontend/package.json`

**Документ составлен:** _______________  
**Дата:** _______________

**Проверено:** _______________  
**Дата:** _______________

