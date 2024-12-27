Library Management System

A desktop application designed to streamline the management of books, patrons, and library transactions. Powered by MariaDB, this system offers an efficient backend to handle the core functionalities of a library.

Features

📚 Manage books, authors, and categories
Organize your library's collection effectively.

🧾 Track borrowing and returns
Maintain accurate transaction records.

👥 Manage patrons and their borrowing history
Provide personalized service and insights.

🚨 Overdue reports
Automatically generate reports for overdue items.

🔐 Role-based access
Ensure secure access for admins and users.

Getting Started

Prerequisites
Ensure you have the following installed before proceeding:

MariaDB 11.6.2 or later

Java (for application execution)

Git (for cloning the repository)

Installation

1. Clone the Repository

bash
Copy code
git clone https://github.com/your-username/library-management-system.git
cd library-management-system

2. Set Up the Database

Start the MariaDB server
bash
Copy code
sudo systemctl start mariadb
Create the Database
sql
Copy code
CREATE DATABASE library;
Import the Initial Schema
bash
Copy code
mysql -u root -p library < database/schema.sql

3. Configure the Application

Update the application.properties file (located in src/main/resources) with your database credentials:
properties
Copy code
spring.datasource.url=jdbc:mariadb://localhost:3306/library
spring.datasource.username=your_username
spring.datasource.password=your_password

4. Run the Application

Build the application
bash
Copy code
mvn clean install
Start the application
bash
Copy code
java -jar target/library-management-system.jar

5. Access the Application

Run the application on your desktop.


Project Structure

library-management-system/
├── src/
│   ├── main/
│   │   ├── java/               # Application source code
│   │   ├── resources/          # Configuration files
│   └── test/                   # Unit tests
├── database/
│   ├── schema.sql              # Initial database schema
│   ├── seed.sql                # Sample data for testing
├── README.md                   # Project documentation
└── pom.xml                     # Maven build configuration

Default Credentials

Admin User

Username: admin

Password: admin123

Troubleshooting

Error: Socket failed to connect to address=(host=localhost)(port=3306)

Ensure the port in the application.properties file is set to 3306 (default MariaDB port).
Verify MariaDB is running with:
bash
Copy code:

sudo systemctl status mariadb

Error: Access denied for user 'root'@'localhost'

Confirm your database credentials are accurate.
Grant access to the user in MariaDB:
sql
Copy code:

GRANT ALL PRIVILEGES ON library.* TO 'root'@'localhost' IDENTIFIED BY 'your_password';
FLUSH PRIVILEGES;

Contributing

Contributions are welcome! Follow these steps to contribute:

(1)Fork the repository.

(2)Create a new branch:

bash
Copy code:

git checkout -b feature/your-feature-name

(3)Commit your changes:
bash
Copy code:

git commit -m 'Add some feature'
(4)Push the branch:
bash
Copy code:

git push origin feature/your-feature-name

(5)Open a Pull Request.
License
This project is licensed under the MIT License.


Acknowledgments

💾 MariaDB for powering the database.

🛠️ Open-source contributors for their valuable tools and frameworks.
