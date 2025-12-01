# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_fitness.png)

### Entities and Attributes

| Entity  | Attributes (PK, FK)                                            | Notes                          |
| ------- | -------------------------------------------------------------- | ------------------------------ |
| Member  | member_id (PK), name, membership_type, start_date              | Stores registered members      |
| Program | program_id (PK), name, duration, schedule                      | Yoga, Zumba, Weight Training   |
| Trainer | trainer_id (PK), name, specialty                               | Assigned to programs           |
| Session | session_id (PK), member_id (FK), trainer_id (FK), session_date | Personal training sessions     |
| Payment | payment_id (PK), member_id (FK), amount, payment_date, type    | Membership or session payments |


### Relationships and Constraints

| Relationship    | Cardinality  | Participation | Notes                                   |
| --------------- | ------------ | ------------- | --------------------------------------- |
| Member–Program  | Many-to-Many | Optional      | Members can join multiple programs      |
| Program–Trainer | Many-to-Many | Mandatory     | Programs must have at least one trainer |
| Member–Session  | One-to-Many  | Optional      | Members may book sessions               |
| Session–Trainer | Many-to-One  | Mandatory     | Each session has a trainer              |
| Member–Payment  | One-to-Many  | Optional      | Payments linked to members              |


### Assumptions
Assumptions

Members can participate in multiple programs simultaneously.

Attendance records are captured within Session entity.

Payments may cover either membership or personal sessions.

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_library.png)

### Entities and Attributes

| Entity  | Attributes (PK, FK)                                                      | Notes                       |
| ------- | ------------------------------------------------------------------------ | --------------------------- |
| Member  | member_id (PK), name, email                                              | Library users               |
| Book    | book_id (PK), title, author, category                                    | Books in the library        |
| Loan    | loan_id (PK), book_id (FK), member_id (FK), loan_date, return_date, fine | Tracks borrowing            |
| Event   | event_id (PK), name, date, room_id                                       | Library events              |
| Speaker | speaker_id (PK), name                                                    | Speakers/authors for events |
| Room    | room_id (PK), name, capacity                                             | Rooms for events and study  |


### Relationships and Constraints

| Relationship  | Cardinality  | Participation | Notes                                |
| ------------- | ------------ | ------------- | ------------------------------------ |
| Member–Loan   | One-to-Many  | Optional      | Members may borrow multiple books    |
| Book–Loan     | One-to-Many  | Optional      | Books may be borrowed multiple times |
| Event–Speaker | Many-to-Many | Mandatory     | Each event has at least one speaker  |
| Member–Event  | Many-to-Many | Optional      | Members may register for events      |
| Room–Event    | One-to-Many  | Mandatory     | Each event occurs in one room        |

### Assumptions
Overdue fines are calculated in the Loan entity.

Each book can belong to one category only.

Members can attend multiple events.

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_restaurant.png)

### Entities and Attributes

| Entity      | Attributes (PK, FK)                                             | Notes                    |
| ----------- | --------------------------------------------------------------- | ------------------------ |
| Customer    | customer_id (PK), name, phone                                   | Walk-in or reservation   |
| Reservation | reservation_id (PK), customer_id (FK), date, time, guests       | Table bookings           |
| Dish        | dish_id (PK), name, category_id, price                          | Menu items               |
| Order       | order_id (PK), reservation_id (FK), order_date                  | Linked to reservations   |
| OrderItem   | order_item_id (PK), order_id (FK), dish_id (FK), quantity       | Each dish in an order    |
| Category    | category_id (PK), name                                          | Starter, main, dessert   |
| Bill        | bill_id (PK), reservation_id (FK), total_amount, service_charge | Billing                  |
| Waiter      | waiter_id (PK), name                                            | Assigned to reservations |


### Relationships and Constraints

| Entity      | Attributes (PK, FK)                                             | Notes                    |
| ----------- | --------------------------------------------------------------- | ------------------------ |
| Customer    | customer_id (PK), name, phone                                   | Walk-in or reservation   |
| Reservation | reservation_id (PK), customer_id (FK), date, time, guests       | Table bookings           |
| Dish        | dish_id (PK), name, category_id, price                          | Menu items               |
| Order       | order_id (PK), reservation_id (FK), order_date                  | Linked to reservations   |
| OrderItem   | order_item_id (PK), order_id (FK), dish_id (FK), quantity       | Each dish in an order    |
| Category    | category_id (PK), name                                          | Starter, main, dessert   |
| Bill        | bill_id (PK), reservation_id (FK), total_amount, service_charge | Billing                  |
| Waiter      | waiter_id (PK), name                                            | Assigned to reservations |

### Assumptions
Walk-in customers can also place orders without a reservation.

Service charges are included in the Bill entity.

A dish belongs to exactly one category.

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
