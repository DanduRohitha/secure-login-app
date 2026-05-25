# Secure Login Application

A robust full-stack web application built using **Spring Boot**, **Spring Security**, and **Thymeleaf**. This project features a custom user authentication system that bypasses Spring Security's default auto-generated login page, replacing it with tailored, custom-designed user registration, sign-in, and session-managed dashboard interfaces.

---

## 🚀 Features

* **Custom Authentication Forms:** Fully styled custom login and registration interfaces built using Thymeleaf templates.
* **Secure Password Hashing:** Uses Spring Security's `BCryptPasswordEncoder` to securely hash and store passwords in the database.
* **Robust Access Control:** Restricts unauthorized dashboard access (`/dashboard`) while keeping public endpoints (`/`, `/login`, `/register`) open to everyone.
* **Custom Session Management:** Tracks active logged-in sessions natively to maintain state across pages and handles secure manual session invalidation via `/logout`.
* **Dynamic Data Binding:** Real-time database verification to check if usernames are already taken during registration.

---

## 🛠️ Architecture & Package Layout

To ensure optimal configuration scanning, the project is structured under a unified root package hierarchy:

```text
com.klu
 │
 ├── SecureLoginAppApplication.java   # Main Spring Boot Runner
 ├── config
 │    └── SecurityConfig.java         # Password Encoding & Security Filter Chains
 ├── controller
 │    └── WebViewController.java      # GET/POST Application Endpoints & Routing
 ├── model
 │    └── User.java                   # JPA Hibernate Entity Mapping Table
 └── repository
      └── UserRepository.java         # Data Repository for MySQL Crud Methods
