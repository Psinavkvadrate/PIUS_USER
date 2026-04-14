# USER Service

## 1. Название и назначение сервиса

**USER Service** — это fullstack приложение интернет-магазина, состоящее из backend и frontend частей.

### Роль в системе

Сервис реализует основную бизнес-логику маркетплейса:

- работа с корзиной товаров
- оформление заказов
- просмотр истории заказов и их деталей
- взаимодействие с сервисом продавцов (seller-service)

### Основные функции

- добавление, изменение и удаление товаров в корзине
- создание заказов из корзины
- просмотр списка заказов
- просмотр деталей заказа
- получение информации о товарах через внешний сервис

---

## 2. Архитектура и зависимости

Проект состоит из двух частей:

- **Frontend**: React + TypeScript + Vite + MUI + RTK Query
- **Backend**: FastAPI + PostgreSQL + SQLAlchemy (async)

---

### Backend технологии

- FastAPI
- SQLAlchemy 2.0 (async)
- asyncpg
- Pydantic v2
- Alembic (миграции)
- python-jose (JWT)
- httpx (HTTP-клиент)
- pytest / pytest-asyncio

---

### Frontend технологии

- React 18
- TypeScript
- Redux Toolkit + RTK Query
- Material UI (MUI)
- Vitest + Testing Library

---

### Взаимодействие с микросервисами

#### Seller Service

Используется для получения данных о товарах и подтверждения заказов.


---

### 🗄 База данных

- PostgreSQL (asyncpg)
- Alembic для миграций

Используется для хранения:

- пользователей
- корзины
- заказов
- товаров в заказах
- токенов пользователей

---

## 3. Способы запуска сервиса

---

### Запуск через Docker (рекомендуется)

TO DO

### Запуск локально
#### Frontend
```
cd user-frontend
yarn install
yarn dev
```
#### Backend
```
cd back
puthon -m venv venv
source venv/bin/activate.fish
pip install -r requirements.txt
alembic init alembic
alembic revision --autogenerate -m "init"
alembic upgrade head
uvicorn src.app.application:get_app --factory --reload --host 0.0.0.0 --port 8001
```
---

## 4. API Документация
Ссылка на Swagger TO DO

## 5. Как тестировать?
### Запуск Backend тестов
```
pytest
```
### Запуск Frontend тестов
```
yarn test
```

---

## 6. Контакты и поддержка
Автор: Новиков П.А., Виницкий Е.Р. Селивон С.И. | ПИН-36
GitHub: [Мой Github](https://github.com/Psinavkvadrate)
Связь: tg: @psina_v_kvadrate
