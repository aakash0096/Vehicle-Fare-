# 🚗 Smart Vehicle Fare System

A menu-driven **C++ Smart Vehicle Fare System** designed to calculate and manage fares for multiple vehicle types while demonstrating major **Object-Oriented Programming (OOP)** concepts.

The project supports customer management, vehicle selection, dynamic fare calculation, discounts, surge pricing, trip history, fare comparison, and an administrative panel.

## ✨ Features

* 🚘 Multiple vehicle types:

  * Car
  * Bus
  * Bike
  * Auto
  * Luxury Car
* 💰 Vehicle-specific fare calculation
* 📈 Surge pricing controlled through the admin panel
* 🌙 Night and peak-hour charges
* ⏳ Waiting-time charges
* 🧳 Luggage charges
* 🎟️ Customer discounts and coupon codes
* 🧾 Automatic receipt generation
* 📜 Customer trip history
* 💾 Persistent trip records using file handling
* ⚖️ Fare comparison between vehicles
* 🔎 Lambda-based trip filtering
* ➕ Customer trip-history merging using operator overloading
* 🔐 Password-protected admin panel
* ⚠️ Custom exception handling
* 📊 Session-level earnings and customer statistics

## 🧠 OOP Concepts Demonstrated

This project is primarily designed to demonstrate practical implementation of C++ OOP concepts.

### 1. Abstraction

`Vehicle` is implemented as an abstract base class containing the pure virtual function:

```cpp
virtual double calculateFare(double distanceKm) = 0;
```

### 2. Inheritance

The following classes inherit from `Vehicle`:

```text
Vehicle
├── Car
├── Bus
├── Bike
├── Auto
└── LuxuryCar
```

### 3. Runtime Polymorphism

Vehicle objects are accessed through base-class pointers, allowing the appropriate overridden fare-calculation and display functions to be selected at runtime.

### 4. Encapsulation

Vehicle, customer, fare-calculation, administrative, and file-handling data are organized inside dedicated classes with controlled access through public methods and getters.

### 5. Constructors & Destructors

Constructors initialize vehicle and customer objects, while virtual destructors ensure proper cleanup of derived vehicle objects.

### 6. Static Members

Static members maintain global statistics such as:

* Total vehicles created
* Total customers
* Total earnings

### 7. Friend Function

`compareFares()` is implemented as a friend function to compare the fares of two vehicle objects for a specified distance.

### 8. Operator Overloading

The `+` operator is overloaded for the `Customer` class to combine the trip histories of two customers.

### 9. Exception Handling

Custom exceptions handle invalid conditions such as:

* Negative distance
* Invalid input
* Invalid coupon codes
* Invalid surge multiplier

### 10. Lambda Expression

A lambda expression is used to filter trips based on a user-defined fare threshold.

## 🚕 Fare Structure

| Vehicle    | Base/Minimum Fare | Pricing           |
| ---------- | ----------------: | ----------------- |
| Car        |               ₹80 | Slab-based        |
| Bus        |               ₹30 | ₹5/km after 10 km |
| Bike       |               ₹40 | ₹8/km after 3 km  |
| Auto       |               ₹50 | ₹10/km after 4 km |
| Luxury Car |              ₹200 | ₹25/km            |

Additional charges can be applied for:

* Surge pricing
* Night rides
* Peak hours
* Waiting time
* Luggage

Customer-specific discounts are also supported for **students, senior citizens, and members**.

## 🎟️ Coupon System

Supported coupon codes include:

| Coupon    | Discount |
| --------- | -------: |
| `SAVE10`  |      10% |
| `FIRST50` |      50% |
| `VIT25`   |      25% |

The total discount is capped at **50%**.

## 📋 Main Menu

```text
1. Register / Switch Customer
2. Book a Ride
3. View Available Vehicles
4. My Trip History
5. Compare Two Vehicle Fares
6. Filter Trips by Fare
7. Merge Two Customers
8. Admin Panel
9. Exit
```

## 👨‍💼 Admin Panel

The password-protected admin panel provides:

* Total vehicles created
* Total earnings
* Total customers
* Complete saved trip records
* Surge multiplier configuration

Default admin password:

```text
admin123
```

> For demonstration purposes only. Production applications should use secure authentication and password hashing.

## 💾 File Handling

Trip records are automatically stored in:

```text
trip_history.txt
```

Each record contains:

* Customer name
* Vehicle type
* Distance
* Final fare
* Date and time

This allows trip information to remain available beyond the current program session.

## 🛠️ Technologies Used

* **Language:** C++
* **Programming Paradigm:** Object-Oriented Programming
* **Standard Library:** STL
* **File Handling:** `fstream`
* **Exception Handling:** C++ Exceptions
* **Collections:** `vector`
* **Functional Programming:** Lambda Expressions
* **Compilation:** Any standard C++ compiler

## ▶️ How to Run

### 1. Clone the repository

```bash
git clone <repository-url>
cd <repository-folder>
```

### 2. Compile

Using `g++`:

```bash
g++ Vehicle_Fare.cpp -o Vehicle_Fare
```

### 3. Run

```bash
./Vehicle_Fare
```

On Windows:

```bash
Vehicle_Fare.exe
```

## 📁 Project Structure

```text
Smart-Vehicle-Fare-System/
│
├── Vehicle_Fare.cpp
├── trip_history.txt
└── README.md
```

`trip_history.txt` is generated automatically when trips are saved.

## 🔄 System Workflow

```text
Start
  ↓
Initialize Vehicle Fleet
  ↓
Register Customer
  ↓
Select Vehicle
  ↓
Enter Trip Details
  ↓
Calculate Base Fare
  ↓
Apply Surge & Additional Charges
  ↓
Apply Customer/Coupon Discounts
  ↓
Generate Receipt
  ↓
Store Trip History
  ↓
Update Earnings
  ↓
Continue / Admin / Exit
```

## 🎯 Academic Objective

The primary objective of this project is to provide a practical implementation of **Structured and Object-Oriented Programming concepts in C++** through a real-world transportation fare-management scenario.

Instead of implementing isolated examples of OOP features, the concepts are integrated into a single functional application involving vehicle management, customer management, fare calculation, transaction records, and administrative operations.

## 🚀 Future Enhancements

Possible improvements include:

* Database integration using MySQL/Oracle
* GUI-based application
* Online payment integration
* GPS-based distance calculation
* User authentication and role management
* Driver management
* Real-time vehicle availability
* Dynamic pricing based on demand
* PDF invoice generation
* REST API integration
* Analytics dashboard
* Multi-file modular architecture


---

⭐ If you found this project useful, consider giving the repository a star!
