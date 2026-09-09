# 🎓 # Feedback-Mentoring-Quality-Assessment-System

A full-stack enterprise web application designed to streamline mentorship evaluations. Built with a robust **Java Spring Boot** backend and a dynamic frontend, the platform enables **Admins**, **Mentors**, and **Students** to interact seamlessly, generate customizable feedback forms, collect structured responses, and visualize quality analytics using interactive charts.

---

## 🚀 System Architecture & Key Features

### 👥 Role-Based Portals (RBAC)

| Role | Core Capabilities |
| :--- | :--- |
| **ADMIN** | Full system control, user management (Mentors/Students), global form templates, system-wide analytics, quality metrics. |
| **MENTOR** | Form creation for assigned cohorts, individual and group response reviews, visual analytics dashboards, report exports. |
| **STUDENT** | View assigned feedback forms, submit evaluations (ratings, multiple choice, text), track historical feedback entries. |

### 📊 Feedback Creation & Visualization
* **Dynamic Form Engine:** Admins and Mentors can create custom surveys with rating scales (1–5), multiple-choice options, and open text.
* **Automated Data Analytics:** Aggregated analytics powered by SQL views and exposed via REST APIs for charts (Bar, Pie, Radar).
* **Quality Benchmarks:** Automated scoring calculations to track mentorship trends over time.

---

## 🛠 Tech Stack

* **Backend:** Java 17 / 21, Spring Boot 3.x, Spring Data JPA (Hibernate), Spring Security (JWT + RBAC), Validation (Jakarta)
* **Build Tool:** Apache Maven / Gradle
* **Database:** PostgreSQL / MySQL, Flyway (Database Migrations)
* **Frontend:** React.js / Next.js, Tailwind CSS, Chart.js / Recharts


---

## 📂 Project Directory Structure

```text
mentoring-feedback-system/
├── backend/                        # Java Spring Boot Service
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/app/feedback/
│   │   │   │   ├── config/         # Security & App Configurations
│   │   │   │   ├── controller/     # REST Endpoints
│   │   │   │   ├── dto/            # Data Transfer Objects (Requests/Responses)
│   │   │   │   ├── entity/         # JPA Data Entities (User, Form, Response)
│   │   │   │   ├── exception/      # Global Exception Handling
│   │   │   │   ├── repository/     # Spring Data JPA Repositories
│   │   │   │   └── service/        # Business Logic Layers
│   │   │   └── resources/
│   │   │       ├── application.yml # Environment Configuration
│   │   │       └── db/migration/   # Flyway SQL Scripts
│   │   └── test/                   # JUnit & Integration Tests
│   └── pom.xml                     # Maven Dependencies
│
├── frontend/                       # Client Web Application
│   ├── src/
│   └── package.json
│
└── README.md
