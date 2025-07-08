# 📌 Laravel Routing

## 🚀 What is Routing?

Routing in Laravel is how your application knows **what to do when a user visits a specific URL**.

For example:
- Visiting `/about` shows the About page.
- Visiting `/contact` shows the Contact page.



---

## 📂 Where Are Routes Defined?

Laravel has two main route files:

- `routes/web.php` → For web pages (uses sessions, CSRF protection)
- `routes/api.php` → For APIs (stateless, uses `/api` prefix automatically)

---

## ✍️ Example Web Route

```php
// routes/web.php

Route::get('/hello', function () {
    return 'Hello, world!';
});
