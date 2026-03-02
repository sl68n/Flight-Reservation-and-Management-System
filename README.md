# Flight Reservation and Management System

![Course](https://img.shields.io/badge/Course-CPCS241-orange)
![Type](https://img.shields.io/badge/Project-Database%20Design-blue)
![DBMS](https://img.shields.io/badge/DBMS-Oracle%20SQL-red)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

A database system designed to manage airline reservations, flights, passengers, payments, employees, airports, and airplanes efficiently.

This project was developed for the CPCS241 – Database I course.

---

## Project Overview

The system automates airline reservation operations and manages:

- Passenger information
- Flight scheduling
- Crew assignments
- Payments tracking
- Airport & airplane management
- Reservation management

It improves efficiency, reduces errors, and ensures data consistency through proper normalization and constraints.

---

## Business Rules

1. A reservation cannot be confirmed unless successful payment has been made.
2. A payment must be linked to an existing reservation.
3. A payment may include more than one reservation.
4. A reservation cannot be split into more than one payment.
5. A flight must have both departure and arrival airports.
6. Each flight must have at least one assigned Pilot.
7. An employee’s general job title can differ from their assigned role in a flight.
8. A payment status must be either:
   - 1 → Paid
   - 0 → Unpaid
9. An airplane cannot be assigned to more than one flight at the same time.
10. A flight must be managed by exactly one airplane.
11. Employees can work on multiple flights.
12. Each flight can have multiple employees (M:N relationship).

---

## Database Design

### Main Entities

- Passenger
- Reservation
- Payment
- Flight
- Employee
- Airport
- Airplane
- Flight_Crew (Associative Entity)

---

## ER Design

- 1:N relationships:
  - Passenger → Reservation
  - Flight → Reservation
  - Airplane → Flight

- M:N relationship:
  - Employee ↔ Flight
  - Resolved using: Flight_Crew table

- Composite Attributes:
  - Name split into: Fname, Mname, Lname

---

## Normalization

### First Normal Form (1NF)
- All attributes hold atomic values.
- Composite name fields separated.
- Junction table used for payment relationships.

### Second Normal Form (2NF)
- Flight_crew table uses composite primary key:
  (employee_id, flight_id)
- role_in_flight depends on full composite key.

### Third Normal Form (3NF)
- City and country moved from Flight to Airport table.
- Eliminated transitive dependencies.

---

## Tables Implemented

- PASSENGER
- PAYMENT
- AIRPLANE
- AIRPORT
- EMPLOYEE
- FLIGHT
- RESERVATION
- FLIGHT_CREW

Includes:
- Primary Keys
- Foreign Keys
- CHECK constraints
- ON DELETE CASCADE rules

---

## Advanced Queries Implemented

1. Booked and Available Seats per Flight  
2. List of Employees that work in most flights  
3. Flights with at Least One Cancelled Reservation  
4. Get passengers who paid more than the average payment  
5. Total Price for each flight  
6. Employees Not Assigned to Any Flight  

---

## System Outputs

The system can:

- Calculate reserved and available seats per flight
- Show total payments per flight
- Display crew assignments
- Track paid/unpaid reservations
- Identify busiest employees
- Detect cancelled reservations

---

## Technologies Used

- Oracle SQL
- ER Modeling
- Relational Schema Mapping
- Normalization (1NF, 2NF, 3NF)

---

## Academic Information

Course: CPCS241 – Database I  
University: King Abdulaziz University  
Year: 2023  
Group: 6  

---

## Authors

Ryan Ahmed Asiri  
Rami Saed Alsulami  
Sultan Yasir Alasami  
Basel Al-Qurashi  
Sultan Shaikh Omar  
Mohammed Fahad Alharbi
