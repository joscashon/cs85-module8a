# Laravel Database Environment Setup

This project demonstrates Laravel application configuration with MySQL database connectivity using local development tools.

## Prerequisites

- **Laravel** installed globally using Composer
- **Herd** (for macOS users) or **XAMPP** (for Windows users)
- **Visual Studio Code** as the IDE
- **Git** and **GitHub** account for version control and submission

## Setup Instructions

### Step 1: Install Laravel
If Laravel is not already installed globally:
```bash
composer global require laravel/installer
```

### Step 2: Create Laravel Project
This project was created using:
```bash
laravel new orm_practice
cd orm_practice
```

### Step 3: Start MySQL Server
- **For Windows (XAMPP)**: Launch XAMPP control panel and start Apache and MySQL services
- **For macOS (Herd)**: Launch Herd and ensure MySQL is running
  - Default settings: Host: 127.0.0.1, Port: 3306, Username: root, Password: (blank)

### Step 4: Configure Environment File
Update the `.env` file with your database configuration:
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=orm_practice_db
DB_USERNAME=root
DB_PASSWORD=
```

### Step 5: Create Database
Create a new database named `orm_practice_db` in your MySQL management tool (phpMyAdmin for XAMPP or Herd's database manager).

### Step 6: Run Migrations
Execute the database migrations to create the required tables:
```bash
php artisan migrate
```

### Step 7: Verify Setup
Start the Laravel development server:
```bash
php artisan serve
```
Visit `http://localhost:8000` to confirm the application is running correctly.

## Troubleshooting/Testing the Setup

1. Verify database connection:
   ```bash
   php artisan tinker
   >>> DB::connection()->getPdo()
   ```

2. Check if migrations ran successfully:
   ```bash
   php artisan migrate:status
   ```

3. If your database is configured with a password, don't forget to add it to your .env file