# 🛡️ Laravel CSRF Protection – Simple Guide

## 🚀 What is CSRF?

CSRF stands for **Cross-Site Request Forgery**.

It's a type of attack where a bad website tricks your browser into sending a request to another site (like your bank) **as if it came from you** – even though you didn't do it!

Imagine you're logged into your bank, and an attacker’s site secretly sends a money transfer request using your session. 😱

---

## 🔐 How Laravel Protects You

Laravel automatically protects your application from CSRF attacks by using **CSRF tokens**.

A CSRF token is like a **secret password** Laravel generates for each user session and expects to receive with every sensitive request (like `POST`, `PUT`, `DELETE`).

If the request doesn’t have the correct token – Laravel rejects it with:

---

## ✅ Using CSRF in Forms

Just add `@csrf` in any HTML form in your Blade files:

```blade
<form method="POST" action="/submit">
    @csrf
    <!-- form fields here -->
</form>
This adds a hidden input field like:

<input type="hidden" name="_token" value="SECRET_TOKEN">

