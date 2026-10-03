# PDR Center Uzbekistan

**E-commerce and service platform for a Paintless Dent Repair centre** — [pdrcenteruzbekistan.com](https://pdrcenteruzbekistan.com). Tool shop, PDR courses, service booking, gallery, reviews and blog, with Telegram order notifications and a full admin panel.

![React 19](https://img.shields.io/badge/React%2019-61DAFB?logo=react&logoColor=white) ![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white) ![Vite](https://img.shields.io/badge/Vite-646CFF?logo=vite&logoColor=white) ![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-06B6D4?logo=tailwindcss&logoColor=white) ![Express 5](https://img.shields.io/badge/Express%205-000000?logo=express&logoColor=white) ![Drizzle ORM](https://img.shields.io/badge/Drizzle%20ORM-C5F74F?logo=drizzle&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql&logoColor=white) ![pnpm](https://img.shields.io/badge/pnpm-F69220?logo=pnpm&logoColor=white)

## Features

- **Shop** — marketplace-style catalogue: category sidebar, grid / list views, discounts, stock, product pages with zoom and related products
- **Orders and payments** — cart, wishlist, promo codes, checkout with **Click** and **Payme**, Telegram notifications to the team
- **Courses and services** — PDR training sign-up and service booking
- **Gallery, reviews, blog, delivery, contacts**
- **Admin panel** — products, orders, finances and exports, courses, bookings, ads, content: every text on the site is editable (database overrides on top of the default translations), contacts and links, working hours, admins and roles
- **Auth** — JWT access + refresh tokens (HTTP-only cookie), rate limiting
- **Multilingual** interface

## Architecture

```
pnpm monorepo
├── artifacts/
│   ├── pdrc-website/      # React + Vite + Tailwind, Zustand, TanStack Query, wouter
│   ├── api-server/        # Express 5 + TypeScript, JWT, multer uploads
│   └── mockup-sandbox/    # UI prototyping (dev only)
├── lib/
│   ├── db/                # Drizzle ORM schema (PostgreSQL)
│   ├── api-zod/           # shared Zod validation
│   └── api-client-react/  # typed API client
└── scripts/               # seed and utilities
```

Full technical blueprint: [PDRC_Center_Uzbekistan_Documentation.md](PDRC_Center_Uzbekistan_Documentation.md).

## Getting started

```bash
pnpm install
# .env: DATABASE_URL, JWT_SECRET, JWT_REFRESH_SECRET, APP_URL,
#       TELEGRAM_BOT_TOKEN, TELEGRAM_CHAT_ID, CLICK_*, PAYME_*
pnpm run typecheck
pnpm --filter ./artifacts/api-server run dev
pnpm --filter ./artifacts/pdrc-website run dev
```

In production the API refuses to start without `JWT_SECRET` / `JWT_REFRESH_SECRET`.

## Author

Built by **Bluecore Dev** — IT agency · Omonjon, full-stack developer (4+ years)

[+998 91 911 99 88](tel:+998919119988) · [socialmarketing.uz](https://socialmarketing.uz) · Telegram [@anvarov_911](https://t.me/anvarov_911) · [anvarov1170@gmail.com](mailto:anvarov1170@gmail.com)
