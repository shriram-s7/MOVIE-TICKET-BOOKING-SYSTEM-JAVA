# 🎟️ BookMyShow Deluxe  
*A Java-based Desktop Movie Ticket Booking System*

---

## 📖 Overview
**BookMyShow Deluxe** is a desktop-based ticket booking application built using **Java Swing** and **SQLite**.  
It provides two interfaces:  
- **User Panel** → for login, movie selection, seat booking, and simulated payments.  
- **Admin Panel** → for managing movies, showtimes, users, and bookings.

This project aims to digitize ticket management for small theatres or institutions without needing a web server.

---

## 🚀 Features
### 👤 User Features
- Register and login to book tickets.
- Browse movies and available showtimes.
- Interactive seat layout with color-coded pricing.
- Booking confirmation and simulated payment dialog.

### 🛠️ Admin Features
- Add or remove movies and showtimes.
- View all user bookings.
- Cancel specific bookings or entire shows.
- Manage users (delete inactive or test accounts).
- Live seat occupancy view.

---

## 🧩 Architecture
**Tech Stack**
- **Language:** Java 8+  
- **UI Framework:** Swing (JFrame, JPanel, Dialog)  
- **Database:** SQLite (via JDBC)  
- **Design Pattern:** MVC-inspired modular structure  

**Core Classes**
- `MovieTicketBookingSystem.java` → Main application and navigation logic.  
- `DatabaseManager.java` → All database operations and connection handling.  
- `BookingPage.java`, `AdminPage.java`, `LoginPage.java` → UI layers for users/admins.  

---

## 🗄️ Database Schema
| Table | Fields | Notes |
|--------|---------|-------|
| **users** | username (PK), password | Stores user credentials |
| **admins** | admin_username (PK), admin_password | Stores admin credentials |
| **movies** | movie_title (PK) | List of movies |
| **showtimes** | show_time (PK) | Available showtimes |
| **bookings** | booking_id (PK), username (FK), movie_title (FK), show_time (FK), seat_id, price, booking_date | Linked bookings table with ON DELETE CASCADE |

> ⚙️ **Important:** SQLite foreign key constraints are only active if `PRAGMA foreign_keys = ON` is set for every connection.

---

## 💻 How to Run

### 🧱 Prerequisites
- Java JDK 8 or higher  
- SQLite JDBC Driver (`sqlite-jdbc-3.50.3.0.jar`)  

### ▶️ Steps to Compile & Run
1. Clone this repository:
   ```bash
   git clone https://github.com/your-repo-name.git
   cd BookMyShow-Deluxe
2. Compile:
   javac -cp lib/sqlite-jdbc.jar -d out src/src/*.java
3. Run:
   java -cp out;lib/sqlite-jdbc.jar src.MovieTicketBookingSystem
4. The app launches at the Login Page.
	Default admin:
        Username: admin  
        Password: admin123