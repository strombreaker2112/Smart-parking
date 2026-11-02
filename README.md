# 🚗 Smart Parking System

## 📌 Overview

The Smart Parking System is an IoT-enabled parking management solution designed to automate slot booking, entry verification, and exit processing using QR-based authentication.

The system eliminates manual parking management by integrating:

Web-based booking interface

QR code validation

Backend database management

Automated gate control

## 🎯 Problem Statement

Traditional parking systems suffer from:

Manual slot allocation

Entry verification delays

Poor record management

Slot misuse and inefficiency

This project provides an automated, low-cost, and scalable parking solution using QR authentication and microcontroller-based gate control.

## 🏗️ System Architecture
### 🔹 Core Components

ESP32 (Gate Control Unit)

Servo Motor (Barrier Mechanism)

Web Application (PHP Backend)

MySQL Database

Static QR Code System

### 🔹 Database Structure

users → Stores registered user data

parking_slots → Tracks slot availability

entry_logs → Records entry & exit details

## ⚙️ Working Flow
### 🔹 Slot Booking

User books a parking slot via web interface.

System stores booking in database.

If user does not exist, automatic registration occurs.

### 🔹 Entry Process

User scans static QR code at entry gate.

Redirected to web verification page.

User enters vehicle number.

Backend verifies booking record.

If valid → Server sends command to ESP32.

Gate opens automatically.

### 🔹 Exit Process

User scans exit QR code.

Vehicle number verified.

Parking slot is automatically released.

Exit log updated in database.

Gate opens.

## 🔧 Hardware Implementation

Hardware Highlights:

ESP32 receives command from server

Servo motor controls gate barrier

Serial communication used for debugging

Separate APIs for entry & exit commands

## 💻 Backend Architecture

Developed using PHP

MySQL database integration

REST-style endpoints:

verify_entry.php

get_entry_command.php

get_exit_command.php

Real-time command fetching by ESP32

## ✨ Key Features

QR-based authentication (No hardware QR scanner required)

Automatic user registration

Real-time slot allocation

Automatic slot release at exit

Database-driven logging system

Low-cost deployment architecture

## 🧠 Technical Highlights

Server-client IoT communication

Database transaction handling

Command polling mechanism (ESP32 ↔ Server)

Modular backend design

Hardware-software integration

## 📊 Applications

Residential societies

College campuses

Commercial parking lots

Smart city infrastructure

## 🔬 Future Enhancements

Payment gateway integration

Mobile app interface

License plate recognition

Cloud hosting deployment

Real-time parking analytics dashboard

## 🏗️ Project Type

Full-Stack IoT System (Hardware + Backend Integration)

## 🛠️ Installation & Local Setup
### 🔹 Prerequisites

XAMPP / WAMP / Any PHP-supported local server

MySQL Database

Web Browser

### 🔹 Steps to Run Locally

Clone the repository:

git clone https://github.com/yourusername/smart-parking-system.git

Move the project folder into your server directory:

For XAMPP:

C:/xampp/htdocs/

Start Apache and MySQL from XAMPP control panel.

Open phpMyAdmin and:

Create a new database

Import the provided database.sql file

Open db.php and update database credentials:

$host = "localhost";
$user = "root";
$password = "";
$database = "your_database_name";

Run the project in your browser:

http://localhost/smart-parking-system/
