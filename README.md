# swoley-fit — генератор тренировок (React + Vite + Tailwind)

**UPDATE по проекту**
Проект не обновлялся так как не было времени на это. Сейчас я вернулся к разработке и обновления будут происходить

**Кратко (30 сек):** одностраничное приложение, которое генерирует тренировочные планы по выбранным параметрам (формат/мышечные группы/цели). Лёгкий UI на Tailwind, без бэкенда.

## Демо / скриншоты
- Деплой: _добавь ссылку (Netlify)_
- Скриншоты: `./docs/screenshots/` (главный экран, генератор, карточки упражнений, Lighthouse mobile)

## Стек
- **Frontend:** React 18, Vite 5, JSX
- **UI:** Tailwind CSS (через `tailwind.config.js` + `postcss.config.js`), собственные компоненты (Button/ExerciseCard/SectionWrapper)
- **Состояние:** `useState`
- **Данные:** локальные утилиты генерации (`src/utils/functions.js`), без внешних API
- **Качество:** ESLint

## Фичи (то, что есть сейчас)
- Выбор **poison** (формат тренировки), **muscles** (группы мышц), **goal** (цель)
- Генерация плана по параметрам (алгоритмы в `utils/functions.js`)
- Просмотр сгенерированной тренировки: упражнения/подходы/повторы/темп (через компоненты `Workout`/`ExerciseCard`)
- Базовые модальные окна/переключатели из `Generator`/`Hero`

## Архитектура (фактическая)
```
src/
  components/
    Button.jsx
    ExerciseCard.jsx
    Generator.jsx       # форма выбора параметров (poison/muscles/goal)
    Hero.jsx            # шапка/презентация
    SectionWrapper.jsx
    Workout.jsx         # вывод сгенерированного плана
  utils/
    functions.js        # генерация по словарям/схемам/темпам/воркаутам
  App.jsx               # состояние: workout/poison/muscles/goal
  main.jsx
  index.css             # Tailwind директивы
index.html
vite.config.js
tailwind.config.js
postcss.config.js
```

## Запуск
```bash
npm i
npm run dev        # http://localhost:5173
npm run build
npm run preview
```

## Метрики (цели для мобильных)
- Lighthouse: **90–100**
- Web Vitals: **LCP < 2.0 s**, **CLS ~ 0.01**
- Bundle: **≤ 300 KB**
> Скриншоты с Lighthouse положи в `./docs/screenshots/`.

## Доступность (A11y)
- Клавиатурная навигация и видимые фокусы (Tailwind focus классы)
- Контраст и понятные заголовки секций
- Рекомендуется добавить ARIA-атрибуты для модальных элементов

## Roadmap
- [ ] Сохранение/экспорт плана (JSON/PDF)
- [ ] Состояния loading/empty/error для генерации
- [ ] Фильтры по уровню (novice/intermediate/advanced)
- [ ] Локализация RU/EN
- [ ] Юнит-тесты на `utils/functions.js`
- [ ] GitHub Actions (lint/build) и скрины Lighthouse
- [ ] (опц.) Перевод на TypeScript и Storybook для UI

## Цель проекта
Показать аккуратную UI-витрину на React + Tailwind и продемонстрировать алгоритмическую генерацию тренировок без бэкенда — как портфолио-проект/витрина.
