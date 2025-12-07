# 🛒 MicroShop – Modern E-commerce Platform with Microservices

**Django REST Framework** + **Vue.js 3**.

## ✨ Features
- 🔐 JWT authentication and user profiles
- 📦 Product catalog with categories and search
- 🛒 Real-time shopping cart
- 📋 Order lifecycle management
- 🌐 API Gateway with rate limiting
- ⚡ Event handling via Redis pub/sub
- 📱 Responsive frontend with Vue.js 3 + Tailwind CSS

## 🏗️ Architecture
```mermaid
graph TB
    Frontend[Vue.js Frontend] --> Gateway[API Gateway]
    Gateway --> UserService[User Service]
    Gateway --> ProductService[Product Service]
    Gateway --> CartService[Cart Service]
    Gateway --> OrderService[Order Service]

    UserService --> UserDB[(User Database)]
    ProductService --> ProductDB[(Product Database)]
    CartService --> CartDB[(Cart Database)]
    OrderService --> OrderDB[(Order Database)]

    UserService --> Redis[(Redis)]
    CartService --> Redis
    OrderService --> Redis
    ProductService --> Redis
