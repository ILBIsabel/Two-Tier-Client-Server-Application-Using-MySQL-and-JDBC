# Two-Tier-Client-Server-Application-Using-MySQL-and-JDBC

To develop two-tier Java-based client-server applications that interact with a MySQL database, using JDBC for connectivity.

Develop a Java-based GUI front-end (client-side) application that will connect to your MySQL server via JDBC. The application will let clients with various permissions execute SQL commands against different databases. You will also develop a more specialized GUI interface as a monitoring application.

What It Does
This is a two-tier client-server database application in which a Java Swing GUI connects directly to a MySQL database via JDBC. There are two separate applications — a general client interface and a specialized accountant interface.
The general client supports three user roles: root, client1, and client2. Each role has different database privileges enforced both at the MySQL level and inside the application before any command is sent. Root can do everything. Client1 can only SELECT. Client2 can SELECT and UPDATE. If a user tries something they don't have permission for, a warning pop-up stops the command before it ever reaches the database.
Users pick a database and credentials from dropdown menus, enter their username and password manually, and the app verifies those credentials against the properties file before allowing a connection. SELECT results display in a scrollable table with auto-sized columns. Non-SELECT commands show a pop-up with the rows affected. Every successful command is silently logged to a separate audit database in the background without the user ever seeing it.
The accountant interface is a read-only app hardcoded to the operationslog database. It exists solely to let the accountant user query the audit log to see how many operations each user has performed.

Getting Started
Requirements

Java 17+
MySQL 8.x
MySQL Connector/J 9.6.0
Eclipse IDE

Database Setup
Run the following SQL scripts in MySQL Workbench in this order:

project3dbscript.sql
bikedb script (from course Module 3)
project3operationslog.sql
UserCreationScriptProject3.sql
UserPermissionsScriptProject3.sql

Eclipse Setup

Add mysql-connector-j-9.6.0.jar to the build path — right-click the project, Build Path, Configure Build Path, Libraries, Add External JARs
Edit root.properties and set your MySQL root password
Place all 8 .properties files in the project root folder, not inside src/

Running
Right-click SQLClientAppSpring2026.java or TheAccountantAppSpring2026.java and select Run As → Java Application.
