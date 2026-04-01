# API Users - Laravel + Docker + MySQL

A simple CRUD API project for users built with Laravel, MySQL, Docker and Nginx.

The main goal of this project is to practice backend development concepts while also learning how Docker works in a real-world application.

---

# Project Idea

This project is a REST API that allows basic user management.

The API will support:

* Create users
* List all users
* Get a user by ID
* Update users
* Delete users

The project will also be used to practice:

* Laravel fundamentals
* REST API concepts
* CRUD operations
* Migrations
* Database modeling
* Docker
* Docker Compose
* Nginx
* MySQL
* Postman

---

# Tech Stack

* PHP
* Laravel
* MySQL
* Docker
* Docker Compose
* Nginx
* Postman

---

# Architecture

```text
Nginx -> Laravel/PHP -> MySQL
```

---

# User Entity

The API will use the following structure:

```json
{
  "id": 1,
  "name": "John Doe",
  "email": "john@example.com",
  "password": "12345678",
  "age": 25,
  "role": "Developer"
}
```

---

# API Endpoints

## Get all users

```http
GET /api/users
```

## Get user by ID

```http
GET /api/users/{id}
```

## Create a user

```http
POST /api/users
```

Example body:

```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "age": 25,
  "role": "Developer"
}
```

## Update a user

```http
PUT /api/users/{id}
```

## Delete a user

```http
DELETE /api/users/{id}
```

---

# Database Fields

| Field      | Type      |
| ---------- | --------- |
| id         | bigint    |
| name       | string    |
| email      | string    |
| password   | string    |
| birth_date | date   |
| role       | string    |
| created_at | timestamp |
| updated_at | timestamp |

---

# Requirements

Before running the project, make sure you have installed:

* PHP
* Composer
* MySQL
* Docker
* Docker Compose
* Git

---

# How to Create the Project

Create a new Laravel project:

```bash
composer create-project laravel/laravel api-users
```

Enter the project folder:

```bash
cd api-users
```

---

# Basic Laravel Setup

Create the model, migration and controller:

```bash
php artisan make:model UserProfile -mcr
```

Edit the migration file:

```php
$table->string('name');
$table->string('email')->unique();
$table->string('password');
$table->integer('age');
$table->string('role');
```

Run the migrations:

```bash
php artisan migrate
```

Start the local server:

```bash
php artisan serve
```

---

# Environment Variables

Example database configuration in the `.env` file:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=api_users
DB_USERNAME=root
DB_PASSWORD=password
```

---

# Docker Containers

The project will eventually use three containers:

* app
* nginx
* mysql

Example structure:

```yaml
services:
  app:
    build: .

  nginx:
    image: nginx:alpine

  mysql:
    image: mysql:8
```

---

# Testing

You can test the endpoints using Postman.

Example URL:

```text
http://localhost:8000/api/users
```

---

# Testing Strategy

The project will include automated tests to improve reliability and code quality.

## PHPUnit

PHPUnit will be used for unit and feature tests inside Laravel.

Examples:

* Test if a user can be created
* Test validation rules
* Test if a user can be updated
* Test if a user can be deleted
* Test API response status codes

Example command:

```bash
php artisan test
```

Or:

```bash
vendor/bin/phpunit
```

## Cypress API Tests

Cypress will also be added to perform end-to-end API testing.

Examples:

* Send requests to the API
* Validate response body
* Validate status codes
* Validate error messages
* Validate CRUD flow

Example test scenarios:

* Create a user and verify response
* Get all users
* Update a user
* Delete a user
* Test invalid request payloads

# Future Improvements

* Validation rules
* Authentication with Sanctum or JWT
* Pagination
* Search filters
* Unit tests
* Swagger documentation
* Redis cache
* CI/CD pipeline

---

# Author

Developed as a study project to practice backend and Docker concepts.
