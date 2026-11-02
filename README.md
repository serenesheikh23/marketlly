# Marketlly

A full-stack, multi-role digital marketplace featuring VIP tiers, automated crypto payment processing, an automated fulfillment bot, and a comprehensive admin dashboard. 

## 🚀 Tech Stack

*   **Frontend:** React 19, Vite, TypeScript, Redux Toolkit, Tailwind CSS, i18next (Arabic/English RTL support)
*   **Backend:** Laravel 13 (PHP 8.3), MySQL, Redis, Sanctum (Auth), Spatie Permissions (RBAC)
*   **Bot:** Node.js (Telegram/Webhook automation)
*   **Infrastructure:** Docker, Nginx, GitHub Actions CI

## ✨ Core Features

*   **Multi-Role Access Control:** Distinct dashboards and permissions for Users, Moderators, and Admins.
*   **Crypto & Fiat Payments:** Pluggable payment gateway architecture integrating Binance Pay, USDT (BEP-20), and manual wallet transfers with idempotent webhook handling.
*   **VIP Tier System:** Tiered user levels (VIP1 through VIP4) that automatically adjust withdrawal limits, fee percentages, and pricing.
*   **Partner API:** Token-authenticated endpoints allowing external sellers to interact with the marketplace programmatically.
*   **Bilingual Interface:** Full Arabic and English localization with native RTL (Right-to-Left) layout support.
*   **Automated Fulfillment:** Integration with upstream providers (Oranos Market API) for automated digital product delivery.
*   **Admin Control Center:** Manage users, products, categories, orders, transactions, and website leads.

## 📂 Project Structure

```text
marketlly/
├── backend/            # Laravel API (Routes, Controllers, Models, Tests)
├── frontend/           # React SPA (Pages, Components, Redux Store)
├── bot/                # Node.js automation bot
├── docs/               # Project documentation and specs
└── docker-compose.yml  # Containerized local environment
```

## 🛠️ Local Development Setup

### 1. Backend (Laravel API)
```bash
cd backend
cp .env.example .env
composer install
php artisan key:generate
php artisan migrate --seed
php artisan serve
```

### 2. Frontend (React SPA)
```bash
cd frontend
npm install
npm run dev
```
*(Ensure your `.env` has `VITE_API_URL=http://localhost:8000`)*

### 3. Bot (Node.js)
```bash
cd bot
npm install
node index.js
```

### 🐳 Running with Docker (Recommended)
To spin up the entire stack (PHP-FPM, Nginx, MySQL, Redis) instantly:
```bash
docker-compose up -d --build
```

## 🧪 Testing

**Backend (PHPUnit):**
```bash
cd backend
./vendor/bin/phpunit
```
*Coverage includes auth flows, payment safety, VIP logic, webhooks, and partner APIs.*

**Frontend (Vitest):**
```bash
cd frontend
npm run test
```

## 🔒 Security & Best Practices

*   **Idempotent Webhooks:** Prevents double-crediting accounts on payment retries.
*   **Server-Enforced Logic:** VIP limits and fees are locked on the backend (`VipService`), preventing frontend manipulation.
*   **Precise Money Handling:** Custom `PreciseMoney` service ensures 24-decimal precision for crypto transactions.
*   **Rate Limiting:** Protected API routes and login attempts.