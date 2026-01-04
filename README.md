# Online Bookstore

A comprehensive full-stack online bookstore application built with a **React** frontend and **Spring Boot** backend. It features a robust content management system (CMS), full e-commerce functionality, and secure JWT-based authentication.

---

## 🚀 Features

### Core E-commerce
* 🔐 **JWT Authentication**: Secure login and registration.
* 📚 **Book Catalog**: Advanced browsing, search, and filtering.
* 🛒 **Shopping Cart**: Real-time management of selected items.
* 📦 **Order History**: Track and view previous purchases.
* 🎯 **RBAC**: Role-Based Access Control (User vs. Admin permissions).

### Content Management System (CMS)
* 📝 **Blog Engine**: Full article management system for book news and reviews.
* 🏷️ **Categorization**: Organize content by Books, Authors, Publishing, Reviews, or News.
* 📸 **Media Support**: Image support for all articles and book covers.
* ✍️ **Draft System**: Control "Published" vs. "Draft" status for content.
* 🔒 **Admin Suite**: Exclusive dashboard for creating, editing, and deleting inventory.

---

## 📁 Project Structure

```text
Online-bookstore/
├── backend/                  # Spring Boot backend (Java 17)
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/bookstore/backend/
│   │   │   │   ├── config/   # Security & CORS configuration
│   │   │   │   ├── controller/# REST API controllers
│   │   │   │   ├── dto/      # Data Transfer Objects
│   │   │   │   ├── entity/   # JPA/MongoDB entities
│   │   │   │   ├── repository/# Data access layer
│   │   │   │   └── service/  # Business logic layer
│   │   │   └── resources/
│   │   │       └── application.properties
│   └── pom.xml
├── frontend/                 # React frontend (v19+)
│   ├── src/
│   │   ├── components/       # Reusable UI components
│   │   ├── pages/            # Page-level components
│   │   ├── services/         # API service layer (Axios)
│   │   └── utils/            # Helper functions
│   └── package.json
└── README.md
```
Technologies
Backend
Spring Boot 4.0.0 - Core Framework
Spring Security - Auth & Authorization
Spring Data MongoDB - Database Abstraction
JWT (jjwt) - Secure Token Handling
Lombok - Boilerplate reduction
Java 17 - Language Runtime

Frontend
React 19.2.3 - UI Library
React Router DOM 6.20 - Navigation
Axios - HTTP Client
CSS3 - Custom Styling

Prerequisites
Java 17 or higher
Node.js (v16.x or v18.x recommended)
MongoDB (Local instance or Atlas)
Maven 3.6+

Backend Setup
```
cd backend
# Edit src/main/resources/application.properties with your MongoDB URI

./mvnw spring-boot:run
```
The backend will be available at http://localhost:8081


📡 API Endpoints
Authentication
POST /api/users/register - Register a new user
POST /api/users/login - Login and get JWT token
Books Management
GET /api/books - Get all books (public)
GET /api/books/{id} - Get book by ID (public)
POST /api/books - Create a book (admin only)
PUT /api/books/{id} - Update a book (admin only)
DELETE /api/books/{id} - Delete a book (admin only)
Articles/Blog Management
GET /api/articles - Get all published articles (public)
GET /api/articles/{id} - Get single article (public)
GET /api/articles/category/{category} - Get articles by category (public)
GET /api/articles/search?keyword={keyword} - Search articles (public)
POST /api/articles - Create new article (admin only)
PUT /api/articles/{id} - Update article (admin only)
DELETE /api/articles/{id} - Delete article (admin only)
PUT /api/articles/{id}/publish - Publish article (admin only)
PUT /api/articles/{id}/unpublish - Unpublish article (admin only)
Orders Management
GET /api/orders - Get all orders (admin only)
GET /api/orders/history/{userId} - Get user's order history (authenticated)
POST /api/orders - Place an order (authenticated)
Users Management
GET /api/users - Get all users (admin only)
GET /api/users/{id} - Get user by ID (admin only)
PUT /api/users/{id} - Update user (admin only)
DELETE /api/users/{id} - Delete user (admin only)


Default Admin Setup
To access admin features:

Register a new user account
Manually update the user role to "ADMIN" in MongoDB
Login with admin credentials to access:
Book management
Article/blog management
Order management

Article Categories
The blog system supports the following categories:

Books - Book reviews, recommendations, literary analysis
Authors - Author profiles, interviews, biographies
Publishing - Industry news, publishing trends
Reviews - Critical reviews, reader opinions
News - Book-related news, events, announcements
