# AIRPORT_MANAGEMENT
# Flight Ticket Booking System (Python + MySQL)
## Built as a beginner-friendly mini project to practice full-stack basics using Python and MySQL.


A command-line based *Flight Ticket Management System* built using **Python** and **MySQL**. This project allows airline staff to register passengers, calculate ticket prices based on travel class and luggage, and display customer billing information.

FEATURES
- Register new passengers with journey details
- Ticket pricing based on class and number of passengers
- Extra luggage charge calculation (₹100 per kg)
- Displays individual and full customer bills
- All data stored in a **MySQL database** (`seat`)



## Tech Stack

- **Language:** Python 3  
- **Database:** MySQL  
- **Libraries Used:**  
  - `mysql.connector`  
  - `os`  
  - `platform` 
  - `datetime`


## 📂 Database Schema

### 📄 Table 1: 'pdata' (Passenger Data)

sql:
CREATE TABLE pdata (
  custno INT PRIMARY KEY,
  custname VARCHAR(100),
  addr VARCHAR(100),
  jrdate DATE,
  source VARCHAR(50),
  destination VARCHAR(50)
);

### Table 2 : 'tkt' (Ticket info)
CREATE TABLE tkt (
  custno INT,
  tkt_tot INT,
  lug_tot INT,
  g_tot INT,
  FOREIGN KEY (custno) REFERENCES pdata(custno)
);


## MENU OPTIONS:
1. Enter customer data
2. Calculate ticket amount
3. Display customer-wise bill
4. Display all bills
5. Exit


## *How to Run the Project*
1.Set up MySQL and create a database named **seat**
2.Create the required tables (pdata and tkt) using the schemas above
3.Install the required Python library:
**pip install mysql-connector-python**
4.Ensure your database connection details match the script:
**mydb = mysql.connector.connect(
    host="localhost",
    user="root",
    passwd="root",
    database="seat",
    charset="utf8"
)**
5.Run the script:
**python flight_ticket.py**
