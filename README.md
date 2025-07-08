# 🛡️ Laravel Middleware – Simple Guide

## 🚀 What is Middleware?

Middleware in Laravel acts like a **filter** for HTTP requests that enter your application.

Think of it like:
> "A security guard that checks every request before it reaches your routes or controllers."

It can:
- Check if the user is logged in
- Verify CSRF tokens
- Log requests
- Restrict access (like admin only)
- Modify requests or responses

---

## 🧠 How Middleware Works

When a request comes in, Laravel passes it through a **stack of middleware** before it reaches your controller.

Example:
User → Middleware → Route → Controller → Response → Middleware → User


---

## 📁 Where Is Middleware Defined?

All middleware classes live in:
app/Http/Middleware/

To register middleware, open:
app/Http/Kernel.php


You’ll see:
- `$middleware`: Global middleware (runs on every request)
- `$middlewareGroups`: Like `web`, `api`
- `$routeMiddleware`: Middleware you can use on specific routes

---

## 🔄 Middleware Types

| Type           | Description                         |
|----------------|-------------------------------------|
| Global         | Runs on every request               |
| Group          | Runs on grouped routes (like `web`) |
| Route-specific | Used for one or more specific routes|

---

## ✅ Built-in Middleware Examples

- `auth` → Checks if user is logged in
- `guest` → Redirects if user is logged in
- `throttle` → shapes traffic (manages flow of requests to prevent overloading in the system)
- `verified` → Checks if user has verified email
- `csrf` → Protects forms from CSRF attacks (web only)

---

## ✍️ Using Middleware on Routes

```php
// Single route
Route::get('/dashboard', function () {
    return view('dashboard');
})->middleware('auth');

// Multiple middleware
Route::post('/submit', 'FormController@submit')->middleware(['auth', 'verified']);


