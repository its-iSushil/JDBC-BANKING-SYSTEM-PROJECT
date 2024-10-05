# JDBC-PROJECT
-------------------------
BANKING SYSTEM WITH JDBC
-------------------------

# Prerequisites:

Before you run the project, ensure that the following software and libraries are installed on your system:

1. Java Development Kit (JDK) (Version 8 or higher)
2. MySQL (or any other relational database)
3. JDBC Driver for MySQL (Connector/J)
4. IDE (Optional, but recommended: IntelliJ IDEA)

# Setup Instructions

Step 1: Clone or Download the Project
Step 2: Database Setup
	
a. Start MySQL on your machine.
b. Create a Database for the project = > "CREATE DATABASE banking_system_db;"
c. Create Account Table: 


| Field          | Type          | Null | Key | Default | Extra |

| account_number | bigint        | NO   | PRI | NULL    |       |

| full_name      | varchar(30)   | YES  |     | NULL    |       |

| email          | varchar(30)   | YES  | UNI | NULL    |       |

| balance        | decimal(10,2) | YES  |     | NULL    |       |

| security_pin   | char(4)       | YES  |     | NULL    |       |


d. Create User Table:

+-----------+-------------+------+-----+---------+-------+

| Field     | Type        | Null | Key | Default | Extra |

+-----------+-------------+------+-----+---------+-------+

| full_name | varchar(30) | YES  |     | NULL    |       |

| email     | varchar(30) | YES  | UNI | NULL    |       |

| password  | varchar(30) | YES  |     | NULL    |       |

+-----------+-------------+------+-----+---------+-------+

Step 3: Configure JDBC
Download MySQL Connector/J if not already present. You can download it from the MySQL website.

Add the MySQL JDBC Driver (Connector/J) to your project’s classpath.
In your IDE, right-click on the project → Select “Build Path” → Add External JARs → Add the MySQL JDBC Driver JAR.

Step 4: Update Database Credentials

In the DatabaseConfig.java file, update the database connection details:

    public static final String URL = "jdbc:mysql://localhost:3306/banking_system_db";
    public static final String USER = "root";    // Change to your MySQL username
    public static final String PASSWORD = "password";  // Change to your MySQL password

#Project Overview

This Banking System is a command-line application built using Java and JDBC to interact with a MySQL database. The system allows users to manage their bank accounts by performing various banking operations, such as creating accounts, managing profiles, and conducting transactions like deposits, withdrawals, and transfers. The application is secured with a login system and offers advanced account management options.

# Project Flow & Structure

1. Home Page
Upon launching the application, users are presented with the following options:
Log In: For users with an existing profile to log into their accounts.
Create a Profile: For new users to create their profiles.
Log Out: Exits the application.

2. Profile Management
Create Profile: A new user can register by entering details such as name, email, password, etc. This profile is stored in the database.
Log In: An existing user can log in using their registered credentials. Upon successful login, the application checks whether the user has a bank account.
3. Newly Logged-In User (Without Bank Account)

After logging in, if the user does not have an existing bank account, they are given the following options:
Create a Bank Account: The user can create a bank account by providing necessary details like initial deposit, account type, etc.
Change Profile Password: The user can change their profile password.
Log Out: Logs out the user and returns to the home page.
4. Existing User (With Bank Account)

If the user has an existing bank account, they are presented with the Bank Account Menu. The menu offers the following operations:
Banking Operations:

Deposit Money: The user can deposit funds into their account by specifying the amount.
Withdraw Money: The user can withdraw money, ensuring sufficient balance exists.
Transfer Money: The user can transfer funds to another bank account by entering the recipient’s account number.
Check Account Balance: Displays the current balance of the user’s account.

Advanced Account Management:

Retrieve Account Number: Displays the user's bank account number.
Change Security Pin: The user can change their account’s security pin for added security.
Close Account Permanently: The user can close their bank account, which deletes their banking records from the database.
Log Out: Ends the session and returns to the home page.

!!!!! Thank You !!!!!
