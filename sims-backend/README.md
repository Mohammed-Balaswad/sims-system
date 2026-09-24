# 🎓 SIMS - Student Information Management System (Backend)

![Laravel](https://img.shields.io/badge/Laravel-12.x-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)
![PHP](https://img.shields.io/badge/PHP-8.4-777BB4?style=for-the-badge&logo=php&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)

**SIMS (Student Information Management System)** backend API developed for the **Ministry of Education, Yemen - Hadhramaut Coast Branch**. 
This system provides a robust centralized electronic platform for managing student records across various educational stages, supporting core administrative workflows such as student registration, data updates, temporary admissions, transfers, grade management, certificate issuance, and reporting.

---

## ✨ Key Features

- **🔐 Advanced Role-Based Access Control (RBAC):** Precise management of users, roles, and permissions protecting API endpoints via `spatie/laravel-permission`.
- **🏫 Academic Management:** Full control over Academic Years, Schools, Levels, Classes, and Subjects.
- **🧑‍🎓 Student Affairs Management:** Register new students, handle temporary/suspended admissions, and manage inter-school transfer requests and replacement certificates.
- **📊 Grades & Results Management:** Integrated platform for recording grades with high-efficiency Excel import/export capabilities (`maatwebsite/excel`).
- **📄 PDF Document Generation:** Generate official documents (certificates, transfer forms, and reports) using `spatie/laravel-pdf` powered by `Puppeteer`.
- **📝 Activity Logging (Audit Trail):** Automatically track and log all sensitive user actions for full transparency using `spatie/laravel-activitylog`.
- **🗄️ Automated Backups:** Built-in database backup system (`spatie/laravel-backup`).
- **📚 API Documentation:** Interactive RESTful API documentation generated via `knuckleswtf/scribe`.

---

## 🛠️ Tech Stack

- **Framework:** PHP 8.4, Laravel 12.x
- **Authentication:** Laravel Sanctum (Token-based API Authentication)
- **Database:** MySQL
- **Permissions:** Spatie Laravel Permission
- **Excel Processing:** Maatwebsite Excel
- **PDF Engine:** Spatie Laravel PDF & Puppeteer (Node.js)
- **Auditing:** Spatie Laravel Activitylog
- **API Docs:** Knuckles Scribe

---

## 🚀 Installation & Local Setup

Follow these steps to set up and run the backend locally:

### 1. Prerequisites
Ensure you have the following installed on your machine:
- PHP >= 8.4 & Composer
- Node.js & NPM (Required for Puppeteer PDF rendering)
- MySQL (via Laragon, XAMPP, or MySQL Server)

### 2. Clone the Repository & Navigate
```bash
git clone <repository-url>
cd sims-system/sims-backend
```

### 3. Install Dependencies
```bash
composer install
npm install
```
### 4. Create MySQL Database
Open your database manager (e.g., phpMyAdmin or MySQL Workbench) and create a new, empty database named:
```bash
CREATE DATABASE sims;
```

### 5. Environment Configuration
Copy the `.env.example` file to create a new `.env` file.
```bash
cp .env.example .env
```
Open the `.env` file and update your database connection credentials:
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=sims
DB_USERNAME=root
DB_PASSWORD=
```

### 6. Generate Application Key
```bash
php artisan key:generate
```

### 7. Run Migrations & Seeders
Build the database schema and populate it with initial data, roles, and permissions.
```bash
php artisan migrate --seed
```

### 8. Link Storage Directory
Create a symbolic link to allow public access to uploaded files (like generated documents and exported files).
```bash
php artisan storage:link
```

### 9. Run the Local Development Server
Now you can start the backend development server:
```bash
php artisan serve
```
The system will be accessible at: `http://localhost:8000`

---

## 🔑 Default Testing Credentials

After running the database seeders, you can use the following default local administrator account to log in via the frontend interface:

- Email: admin@test.dev
- Password: password

*(Note: These credentials are intended for local evaluation and testing purposes only).*

---

## 📖 API Documentation

The backend includes auto-generated interactive documentation. To view or re-generate the documentation:

```bash
php artisan scribe:generate
```
Access the interactive docs in your browser at:
`http://localhost:8000/docs`

---

## 🗂️ Main API Routes Overview

All core system routes are located inside `routes/api.php` and are protected by `Sanctum` authentication (`auth:sanctum`). Some of the key endpoints include:

- **🔐 Authentication & Users:** Login, user creation, and user management (`/api/users`).
- **🛡️ Permissions:** Manage roles and permissions (`/api/roles`, `/api/permissions`).
- **📅 Academic Settings:** Setup and manage Academic Years, Levels, Schools, Classes, and Subjects.
- **🧑‍🎓 Student Affairs:** Register students (`/api/students`), manage suspended students (`/api/suspended-students`).
- **📑 Transfers & Admissions:** Issue replacement certificates, transfer students between schools (`/api/transfers-admissions`).
- **📊 Grades:** Add grades, and import final results from Excel files (`/api/import/final-result`).
- **📄 PDF Export:** Generate and print official documents as PDF streams (`/api/pdf/...`).

---

## 🔒 System Auditing

To ensure the highest administrative security standards, the system is configured to automatically record all significant user activities (Create, Update, Delete) on sensitive records.
System administrators can review these audit logs either through the system dashboard or by querying the `activity_log` table directly in the database.

---

## 📄 License

This system follows the standards of the [Laravel](https://laravel.com/) ecosystem and is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
