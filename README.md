# 🏥 Hospital Management System (Console-Based)

A Java-based console application designed to manage hospital operations, including patients, doctors, and appointments. Built using **JDBC** and **MySQL**, this system supports real-time **CRUD operations** via terminal input.

---

## 🚀 Features

- 🧑‍⚕️ **Doctor Management**: Add, view, and manage doctor records
- 🧑‍💼 **Patient Registration**: Register and maintain patient data
- 📅 **Appointment Booking**: Schedule and manage appointments
- 🔄 **Real-Time CRUD**: Terminal-based Create, Read, Update, and Delete operations
- 🔐 **Data Security**: Uses parameterized queries to prevent SQL injection

---

## 💻 Tech Stack

- **Language**: Java
- **Database**: MySQL
- **Connectivity**: JDBC (Java Database Connectivity)

---

## 🧱 Project Modules

| Module         | Description                                       |
|----------------|---------------------------------------------------|
| PatientModule  | Register, update, delete, and list patients       |
| DoctorModule   | Add, list, and update doctor records              |
| AppointmentModule | Book, list, and cancel appointments             |
| DatabaseUtil   | Handles DB connection using JDBC                  |

---

## 🛠️ Setup Instructions

### 1. 📦 Requirements

- Java 17+
- MySQL Server
- JDBC Driver

### 2. 🗃️ Database Setup

```sql
CREATE DATABASE hospital_db;

USE hospital_db;

CREATE TABLE doctors (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(100),
  specialty VARCHAR(100)
);

CREATE TABLE patients (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(100),
  age INT,
  gender VARCHAR(10)
);

CREATE TABLE appointments (
  id INT AUTO_INCREMENT PRIMARY KEY,
  patient_id INT,
  doctor_id INT,
  appointment_date DATE,
  FOREIGN KEY (patient_id) REFERENCES patients(id),
  FOREIGN KEY (doctor_id) REFERENCES doctors(id)
);
