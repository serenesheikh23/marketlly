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
