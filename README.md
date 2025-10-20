# AirBnB Clone Project

## Overview

This repository contains the AirBnB Clone project, a backend-focused implementation inspired by the core functionalities of the AirBnB platform. The goal is to build a scalable, modular, and testable system that supports user management, property listings, bookings, and reviews all through a RESTful API.

This project is part of the ALX Pro Dev Software Engineering (Backend) program and serves as a hands-on exercise in backend architecture, API design, and DevOps practices.

## Project Goals

- Build a robust backend system using Python and Flask
- Implement RESTful APIs for core AirBnB features
- Integrate automated testing and CI/CD pipelines
- Deploy the application using Docker and cloud-native tools
- Practice infrastructure as code and monitoring strategies

## Technology Stack

- **Language**: Python
- **Framework**: Django
- **Database**: MySQL or SQLite (depending on environment)
- **Testing**: Unittest, Robot Framework
- **Containerization**: Docker
- **CI/CD**: GitHub Actions
- **Deployment**: AWS (EC2, S3, or Lambda), Terraform
- **Monitoring**: Prometheus, Grafana (optional)
- **Version Control**: Git

## 🚀 Getting Started

To clone the repository:

> git clone https://github.com/<your-username>/airbnb-clone-project.git

## 👥 Team Roles

This section outlines the key roles and responsibilities within the AirBnB Clone project. Each role contributes to building a scalable, reliable, and user-friendly backend system.

### Backend Developer
Responsible for designing and implementing the core application logic, RESTful APIs, and server-side functionality. Ensures code quality, modularity, and performance. Collaborates with other roles to integrate features and maintain system reliability.

### Database Administrator (DBA)
Manages the database schema, relationships, indexing, and performance tuning. Ensures data integrity, backups, and secure access. Works closely with backend developers to optimize queries and support multi-tenant architecture.

### QA/Test Automation Engineer
Designs and maintains automated test suites using tools like Robot Framework, Cypress, and Unittest. Validates functionality, performance, and edge cases. Integrates testing into CI/CD pipelines to ensure continuous quality.

### DevOps Engineer
Sets up and maintains CI/CD pipelines, containerization (Docker), and cloud deployment strategies (AWS, Terraform). Automates infrastructure provisioning and monitors system health. Ensures scalability, fault tolerance, and fast delivery cycles.

### SRE (Site Reliability Engineer)
Focuses on system reliability, observability, and incident response. Implements monitoring tools (Prometheus, Grafana), defines SLIs/SLOs, and conducts chaos testing. Bridges development and operations to maintain uptime and performance.

### Project Manager / Scrum Master
Coordinates tasks, timelines, and team communication. Facilitates Agile ceremonies, removes blockers, and ensures alignment with project goals. Tracks progress and fosters collaboration across roles.


## Database Design

This section outlines the core entities and relationships in the AirBnB Clone backend system. The database is designed to support user management, property listings, bookings, reviews, and payments.

### 👤 Users
Represents individuals using the platform, either as hosts or guests.

**Key Fields:**
- `id` (Primary Key)
- `name`
- `email`
- `password_hash`
- `role` (e.g., host, guest)

**Relationships:**
- A user can list multiple properties.
- A user can make multiple bookings.
- A user can leave multiple reviews.

---

### Properties
Represents accommodations listed by hosts.

**Key Fields:**
- `id` (Primary Key)
- `title`
- `description`
- `location`
- `host_id` (Foreign Key -> Users)

**Relationships:**
- A property belongs to one host (user).
- A property can have multiple bookings.
- A property can have multiple reviews.

---

### Bookings
Represents reservations made by guests.

**Key Fields:**
- `id` (Primary Key)
- `user_id` (Foreign Key → Users)
- `property_id` (Foreign Key → Properties)
- `start_date`
- `end_date`

**Relationships:**
- A booking is made by one user.
- A booking is for one property.
- A booking may be linked to a payment.

---

### Reviews
Represents feedback left by users about properties.

**Key Fields:**
- `id` (Primary Key)
- `user_id` (Foreign Key -> Users)
- `property_id` (Foreign Key -> Properties)
- `rating` (e.g., 1–5)
- `comment`

**Relationships:**
- A review is written by one user.
- A review is about one property.

---

### Payments
Represents financial transactions for bookings.

**Key Fields:**
- `id` (Primary Key)
- `booking_id` (Foreign Key -> Bookings)
- `amount`
- `payment_method`
- `status` (e.g., pending, completed)

**Relationships:**
- A payment is linked to one booking.

---

This relational structure supports scalability, data integrity, and efficient querying for core platform features.


## Feature Breakdown

This section outlines the core features implemented in the AirBnB Clone project. Each feature is designed to replicate key functionalities of the original platform while showcasing backend development, testing, and deployment skills.

### User Management
Handles user registration, authentication, and role-based access control. Supports secure login using hashed passwords and distinguishes between hosts and guests for personalized experiences.

### Property Management
Allows hosts to create, update, and delete property listings. Each listing includes details such as title, description, location, and availability, enabling guests to browse and book accommodations.

### Booking System
Enables guests to book available properties for specific dates. Includes conflict detection, booking history, and integration with payment processing to simulate real-world reservation workflows.

### Review System
Allows users to leave ratings and comments on properties they’ve stayed in. Helps build trust and transparency by surfacing feedback from previous guests.

### Payment Integration
Simulates payment processing for bookings using mock transactions. Tracks payment status, method, and amount, laying the foundation for future integration with real payment gateways.

### Authentication & Authorization
Implements secure login and access control using JWT or OAuth2. Ensures that only authorized users can perform actions based on their roles (e.g., host vs guest).

### CI/CD & Deployment
Automates testing and deployment using GitHub Actions, Docker, and Terraform. Supports scalable cloud deployment and infrastructure as code for reproducible environments.

### Monitoring & Logging (Optional)
Integrates Prometheus and Grafana for system metrics and observability. Helps track uptime, performance, and error rates to support future SRE practices.

---

These features collectively demonstrate backend engineering, DevOps, and platform reliability skills while laying the groundwork for a scalable educational platform like Mmụta.

