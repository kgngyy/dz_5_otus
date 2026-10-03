# HabitFlow — трекер привычек

Fullstack-приложение: **React + TypeScript + Vite** на фронтенде и **Supabase**
(PostgreSQL + Auth + RLS) на бэкенде.

## Возможности
- Регистрация и вход (Supabase Auth, подтверждение email).
- Создание / редактирование / удаление привычек.
- Отметка выполнения «на сегодня», статистика за 7 дней.
- Row Level Security: каждый пользователь видит и меняет только свои данные.

## Технологии
- Frontend: React 19, TypeScript, Vite, React Router, Vitest + Testing Library.
- Backend: Supabase (PostgreSQL 15+, PostgREST REST API, Auth, RLS).

## Структура
```
habitflow/
├── 001_init.sql              # миграция БД (таблицы, RLS, триггеры, гранты)
├── backend_documentation.md  # описание архитектуры, API, развёртывания
├── .env.example              # шаблон переменных окружения
├── src/
│   ├── lib/                  # supabase.ts, auth.ts, api.ts
│   ├── components/           # HabitForm, HabitList, ProgressBar
│   ├── pages/                # HomePage, StatsPage, LoginPage
│   ├── types.ts
│   └── storage.ts            # утилиты дат
└── ...
```

## Требования
- Node.js >= 22.22.2 (рекомендуется 24 LTS) — иначе `npm run test`/`build` упадут.

## Быстрый старт
```bash
cd habitflow
npm install
cp .env.example .env          # Windows: copy .env.example .env
# заполнить VITE_SUPABASE_URL и VITE_SUPABASE_ANON_KEY
# Supabase -> SQL Editor -> выполнить 001_init.sql
npm run dev
```

## Скрипты
- `npm run dev` — dev-сервер Vite.
- `npm run build` — production-сборка (tsc + vite build).
- `npm run test` — тесты (Vitest).
- `npm run lint` — линтер (Oxlint).

## Документация
Полное описание — в [backend_documentation.md](backend_documentation.md).
