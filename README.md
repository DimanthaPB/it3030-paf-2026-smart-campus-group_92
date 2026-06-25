# Smart Campus Operations Hub

## Overview

Smart Campus Operations Hub is a full-stack university operations management platform developed for the **SLIIT IT3030 - Programming Applications and Frameworks (PAF) 2026 Assignment**.

The platform is designed to streamline campus operations by integrating facility management, resource booking, maintenance ticketing, notifications, and role-based access control into a single centralized system.

The application enables students, staff, technicians, managers, and administrators to efficiently manage university resources such as lecture halls, laboratories, meeting rooms, and equipment while providing a structured workflow for incident reporting and maintenance operations.

---

## Features

### Resource Management

* Create, update, search, and deactivate campus resources
* Manage lecture halls, laboratories, meeting rooms, and equipment
* Track resource capacity, location, availability, and status
* Advanced filtering and search capabilities

### Booking Management

* Submit resource booking requests
* View and manage personal bookings
* Edit pending bookings
* Cancel approved bookings with reasons
* Admin approval and rejection workflow
* Booking conflict detection and validation

### Maintenance & Incident Ticketing

* Create maintenance and incident tickets
* Upload evidence attachments
* Assign technicians to tickets
* Status tracking and lifecycle management
* Comment and discussion system
* Resolution note management

### Notification System

* Real-time in-app notifications
* Booking approval and rejection alerts
* Ticket status update notifications
* Comment event notifications
* User notification preference management

### Authentication & Authorization

* Email/password authentication
* Google OAuth 2.0 login
* JWT-based API security
* Role-Based Access Control (RBAC)

### Administration Dashboard

* Resource management
* User management
* Booking monitoring
* Ticket assignment and tracking
* System-wide operational oversight

---

## Supported User Roles

| Role       | Permissions                                                                      |
| ---------- | -------------------------------------------------------------------------------- |
| USER       | Browse resources, create bookings, submit tickets, manage personal notifications |
| ADMIN      | Manage resources, bookings, users, technicians, and monitor campus operations    |
| TECHNICIAN | Handle assigned maintenance tickets and update ticket statuses                   |
| MANAGER    | Operational monitoring and management workflows                                  |

---

## Technology Stack

### Backend

* Java 21
* Spring Boot
* Spring Security
* Spring Data JPA
* PostgreSQL
* JWT Authentication
* Google OAuth 2.0
* Lombok
* Maven

### Frontend

* React 19
* Vite
* React Router
* Axios
* Lucide React

### DevOps & Tools

* Git & GitHub
* GitHub Actions
* Postman
* JUnit Testing

---

## System Architecture

```text
React Frontend
       │
       ▼
Spring Boot REST API
       │
       ▼
Business Logic Layer
       │
       ▼
PostgreSQL Database
```

### Architecture Components

* React-based Client Application
* Spring Boot REST API
* OAuth 2.0 Authentication Provider
* Business Logic Layer
* PostgreSQL Persistence Layer
* File Upload Storage
* Notification Service

---

## Project Structure

```text
Smart-Campus-Operations-Hub/
│
├── backend/
│   ├── src/main/java/
│   ├── src/main/resources/
│   ├── uploads/
│   ├── application.yml
│   └── env.properties
│
├── frontend/
│   ├── src/
│   ├── public/
│   └── vite.config.js
│
├── .github/
│   └── workflows/
│
└── README.md
```

---

## Core Modules

### Facilities & Assets Catalogue

* Resource browsing
* Search and filtering
* Capacity and availability management
* Resource administration

### Booking Management

* Booking requests
* Approval and rejection workflow
* Conflict detection
* Booking tracking

### Incident Ticketing

* Ticket creation
* Image attachment uploads
* Ticket assignment
* Resolution management

### Notifications

* Event-driven notifications
* Notification preferences
* Read/unread management

### User Management

* Role management
* Authentication
* Authorization
* User administration

---

## Prerequisites

Before running this project, ensure you have installed:

* Java 21
* Node.js 18+ (20+ recommended)
* npm
* PostgreSQL Database
* Git

Verify installations:

```bash
java -version
node -v
npm -v
git --version
```

---

# Installation Guide

## 1. Clone the Repository

```bash
git clone <your-github-repository-url>
```

Navigate to the project directory:

```bash
cd Smart-Campus-Operations-Hub
```

---

## 2. Configure PostgreSQL Database

Create a PostgreSQL database:

```sql
CREATE DATABASE smart_campus_db;
```

Update your database connection settings in:

```text
backend/src/main/resources/application.yml
```

Example:

```yaml
spring:
  datasource:
    url: jdbc:postgresql://localhost:5432/smart_campus_db
    username: postgres
    password: your_password
```

---

## 3. Configure Environment Variables

Create or update:

```text
backend/env.properties
```

Example:

```properties
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
JWT_SECRET=your_jwt_secret
```

---

## 4. Configure Frontend Environment

Create:

```text
frontend/.env
```

Example:

```properties
VITE_API_BASE_URL=http://localhost:8080/api
```

---

# Running the Application

## Start Backend Server

Navigate to backend:

```bash
cd backend
```

### Windows

```powershell
.\mvnw.cmd spring-boot:run
```

### macOS / Linux

```bash
./mvnw spring-boot:run
```

Backend runs on:

```text
http://localhost:8080
```

---

## Start Frontend Application

Open a second terminal:

```bash
cd frontend
```

Install dependencies:

```bash
npm install
```

Start development server:

```bash
npm run dev
```

Frontend runs on:

```text
http://localhost:5173
```

---

## Running the Complete Project

### Terminal 1

```bash
cd backend
./mvnw spring-boot:run
```

### Terminal 2

```bash
cd frontend
npm install
npm run dev
```

Open:

```text
http://localhost:5173
```

Login using:

* Local account credentials
* Google OAuth Sign-In

---

## API Modules

### Authentication API

```text
/api/auth
/oauth2/authorization/google
```

### Resource Management API

```text
/api/resources
```

### Booking Management API

```text
/api/bookings
```

### Incident Ticket API

```text
/api/tickets
```

### Notifications API

```text
/notifications
```

### User Management API

```text
/api/admin/users
```

---

## Testing

### Backend Tests

```bash
cd backend
./mvnw test
```

Windows:

```powershell
.\mvnw.cmd test
```

Specific test:

```bash
./mvnw -Dtest=ResourceControllerTest test
```

---

### Frontend Build Validation

```bash
cd frontend
npm run build
```

Additional commands:

```bash
npm run lint
npm run preview
```

---

## Additional Features

### Smart Booking Conflict Detection

* Prevents overlapping bookings
* Suggests available time slots
* Improves resource utilization

### Ticket Resolution Enforcement

* Admins cannot close tickets without resolution notes

### Resource Expiry Monitoring

* Dashboard alerts for resources nearing expiration

### User Preference Management

* Notification preference customization
* Personalized alert management

### Password Reset Support

* Local account password recovery functionality

---

## Team Members

| Student ID | Student Name        |
| ---------- | ------------------- |
| IT23828834 | T.M.P.B. Dimantha   |
| IT23823334 | W.M.S. Methara      |
| IT23664494 | D.M.P. Jayasinghe   |
| IT23828766 | P.G.R.M. Senarathna |

---

## Academic Information

**Project:** Smart Campus Operations Hub

**Module:** IT3030 – Programming Applications and Frameworks (PAF)

**Institution:** Sri Lanka Institute of Information Technology (SLIIT)

**Academic Year:** 2026

---

## Future Enhancements

* Mobile application support
* Email and SMS notifications
* Advanced analytics dashboard
* AI-powered resource recommendations
* Calendar integration
* Real-time technician tracking
* Predictive maintenance analytics

---

## License

This project was developed for academic and educational purposes as part of the SLIIT IT3030 Programming Applications and Frameworks module.

---

## Repository

GitHub Repository:

```text
[https://github.com/<your-username>/<your-repository-name>](https://github.com/DimanthaPB/it3030-paf-2026-smart-campus-group_92)
```
