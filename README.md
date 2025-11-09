# 🛒 MicroShop – Сучасна E-commerce платформа на мікросервісах

 **Django REST Framework** + **Vue.js 3**.

## ✨ Можливості
- 🔐 JWT авторизація та профілі користувачів
- 📦 Каталог товарів з категоріями та пошуком
- 🛒 Кошик покупок у реальному часі
- 📋 Життєвий цикл замовлення
- 🌐 API Gateway з обмеженням швидкості
- ⚡ Події через Redis pub/sub
- 📱 Відзивчивий фронтенд на Vue.js 3 + Tailwind CSS

## 🏗️ Архітектура
```mermaid
graph TB
    Frontend[Vue.js Фронтенд] --> Gateway[API Gateway]
    Gateway --> UserService[Сервіс користувачів]
    Gateway --> ProductService[Сервіс товарів]
    Gateway --> CartService[Сервіс кошика]
    Gateway --> OrderService[Сервіс замовлень]

    UserService --> UserDB[(БД користувачів)]
    ProductService --> ProductDB[(БД товарів)]
    CartService --> CartDB[(БД кошика)]
    OrderService --> OrderDB[(БД замовлень)]

    UserService --> Redis[(Redis)]
    CartService --> Redis
    OrderService --> Redis
    ProductService --> Redis
