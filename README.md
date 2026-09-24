# 🎓 SIMS - Student Information Management System (Monorepo)

**SIMS (Student Information Management System)** is a comprehensive, centralized electronic platform developed for the **Ministry Of Education Office -Hadramout Coast, Mukalla**. 

The system is designed to streamline and automate core administrative operations across educational stages, including student registration, academic management, data updates, temporary admissions, inter-school transfers, grade processing, and official document generation.

---

## 📂 Monorepo Architecture

This repository is structured as a **Monorepo** to house both the backend API and frontend client under a unified roof, ensuring seamless version control, easier project maintenance, and a streamlined developer experience:

- **`sims-backend/`** → Laravel 12 RESTful API handling business logic, authentication (Sanctum), role-based access control (Spatie), database migrations, and PDF report generation.
- **`sims-frontend/`** → React 19 & TypeScript modern dashboard interface powered by Tailwind CSS, consuming the backend APIs to deliver an intuitive administrative experience.

---

## 🎨 UI/UX Design

## 🎨 UI/UX Design
The complete user interface wireframes, component systems, and interactive prototypes for this system were meticulously designed and planned prior to development. You can inspect the design workflow and prototypes here:
- [🔗 SIMS Figma Design System & Prototypes](https://www.figma.com/proto/eiDsEX7xILcmENFIM6wXNo/Mohammed-system--Community-?node-id=1-4&t=RUNMWjrvjDRqPJJk-1) *(Tip: Hold `Ctrl` or `Cmd` while clicking to open in a new tab)*
---

## 🎯 Purpose & Scope

This project serves as an advanced electronic solution to modernize student data management, eliminate paperwork, secure administrative records through comprehensive audit logs, and provide real-time reporting capabilities for educational authorities.

---

## 🚀 Quick Navigation & Setup

To get started with the project locally, please navigate to the respective directories and follow their specific setup guides:

1. **Backend Setup:** Refer to the [Backend README](./sims-backend/README.md) for installation, database configuration, and seeder credentials.
2. **Frontend Setup:** Refer to the [Frontend README](./sims-frontend/README.md) for client-side configuration and development server execution.

---

## 📄 License

This project is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
