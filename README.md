# Airbnb-
A clone of the AirBnB platform built for learning full-stack development.
# Airbnb Clone Project  

## Overview  
This project is a simplified clone of Airbnb, built as part of a learning exercise.  
The goal is to understand how full-stack applications are structured and developed.  

## Tech Stack  
- **Frontend**: HTML, CSS, JavaScript (React if needed)  
- **Backend**: Python/Flask or Node.js/Express  
- **Database**: MySQL or MongoDB  

## Goals  
- Build a functional user interface similar to Airbnb  
- Implement user authentication (signup/login)  
- Add booking and listing features  
- Practice full-stack deployment  
## Team Roles

### 1. Backend Developer  
Responsible for building the server-side of the application. They handle business logic, user authentication, and integration with the database and frontend.  

### 2. Frontend Developer  
Focuses on the user interface and user experience. They ensure the website is visually appealing, interactive, and communicates smoothly with the backend.  

### 3. Database Administrator (DBA)  
Manages the project’s database. Responsible for designing database schemas, optimizing queries, ensuring data security, and performing backups.  

### 4. Project Manager  
Oversees the project’s progress, coordinates tasks among team members, ensures deadlines are met, and facilitates communication within the team.  

### 5. QA Engineer (Quality Assurance)  
Tests the system to ensure that features work as intended. Identifies bugs, documents issues, and verifies that fixes meet quality standards.  

### 6. UI/UX Designer  
Designs the look and feel of the platform. Creates wireframes, mockups, and ensures that the application is intuitive and user-friendly.  

### 7. DevOps Engineer  
Handles deployment, continuous integration/continuous delivery (CI/CD), server setup, and ensures the app runs smoothly in production.  
## Technology Stack

### 1. Django  
A high-level Python web framework used for building robust and scalable web applications. In this project, Django provides the server-side logic and manages the connection between frontend, backend, and database.

### 2. PostgreSQL  
An advanced open-source relational database system. PostgreSQL stores and manages all project data such as user accounts, listings, bookings, and reviews.

### 3. GraphQL  
A query language and runtime for APIs. It allows the frontend to request exactly the data it needs from the backend, making data fetching more efficient compared to traditional REST APIs.

### 4. HTML, CSS, and JavaScript  
The core building blocks for the frontend of the application.  
- **HTML**: Structures the web pages.  
- **CSS**: Styles the web pages for a clean and responsive design.  
- **JavaScript**: Adds interactivity and dynamic features.  

### 5. React (Optional Enhancement)  
A popular JavaScript library for building user interfaces. React could be used to create reusable components and a smoother, faster user experience.

### 6. Git & GitHub  
- **Git**: Version control system used to track changes in code.  
- **GitHub**: A platform for hosting the repository, enabling collaboration and code sharing.  

### 7. Docker (Optional Enhancement)  
A containerization platform used to package the application and its dependencies, ensuring consistent environments during development and deployment.  

### 8. CI/CD Tools (e.g., GitHub Actions)  
Used to automate testing, integration, and deployment so that new changes can be released faster and with fewer errors.  
## Database Design

The database for the Airbnb Clone project will store and manage all critical information related to users, properties, bookings, reviews, and payments. Below are the key entities and their fields:

### 1. Users
Represents the people using the platform, either as guests or hosts.  
**Fields:**
- `user_id` (Primary Key)  
- `name`  
- `email`  
- `password_hash`  
- `role` (guest, host, admin)  

### 2. Properties
Represents the listings added by hosts.  
**Fields:**
- `property_id` (Primary Key)  
- `host_id` (Foreign Key → Users)  
- `title`  
- `description`  
- `location`  
- `price_per_night`  

### 3. Bookings
Represents reservations made by guests.  
**Fields:**
- `booking_id` (Primary Key)  
- `user_id` (Foreign Key → Users)  
- `property_id` (Foreign Key → Properties)  
- `check_in_date`  
- `check_out_date`  
- `status` (confirmed, cancelled, completed)  

### 4. Reviews
Represents feedback left by guests for properties.  
**Fields:**
- `review_id` (Primary Key)  
- `user_id` (Foreign Key → Users)  
- `property_id` (Foreign Key → Properties)  
- `rating` (1–5)  
- `comment`  

### 5. Payments
Represents payment transactions made for bookings.  
**Fields:**
- `payment_id` (Primary Key)  
- `booking_id` (Foreign Key → Bookings)  
- `amount`  
- `payment_date`  
- `status` (paid, pending, failed)  

---

### 🔗 Relationships
- A **User** can be a **Host** (owning multiple properties) or a **Guest** (making multiple bookings).  
- A **Property** belongs to a **Host** and can have multiple **Bookings** and **Reviews**.  
- A **Booking** belongs to a **User** and a **Property**, and it generates a **Payment**.  
- A **Review** is created by a **User** for a specific **Property** after a booking.  
- A **Payment** is linked to a single **Booking**.  
