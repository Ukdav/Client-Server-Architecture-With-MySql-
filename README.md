# Client-Server-Architecture-With-MySql-

**Implementing a Client-Server Architecture Using MySQL server and MYSQL client**

Understanding client-server architecture with MySQL involves grasping how the MySQL database management system (DBMS) fits into the broader client-server model. MySQL is a popular relational database management system that operates within a client-server framework. Here's how it works:

**MySQL Server:**

* The MySQL server is a software application that manages databases. It stores, retrieves, and manipulates data according to SQL (Structured Query Language) commands.
  
* The MySQL server acts as the server component in the client-server architecture. It listens for incoming connections from clients and responds to their requests.

**MySQL Client:**

* The MySQL client is any software application or tool that interacts with the MySQL server to perform database operations.

* Examples of MySQL clients include web applications, command-line interfaces (e.g., MySQL Command Line Client), and graphical user interface (GUI) tools (e.g., phpMyAdmin, MySQL 
  Workbench).

**Communication:**

* Clients communicate with the MySQL server using the MySQL protocol. The client sends SQL queries or commands to the server, which interprets and processes them.

* The MySQL server processes the SQL queries, retrieves or modifies data in the database, and sends the results back to the client.
  Query Example: A common example involves a web application (client) interacting with a MySQL database (server). The web application might send SQL queries like "SELECT," "INSERT," 
  "UPDATE," or "DELETE" to the MySQL server to read from or write data in the database.

* The MySQL server processes the queries, performs the necessary database operations, and sends the query results (e.g., retrieved data) back to the web application for display or 
  further processing.

**Database Connection:**

* When a client wants to interact with a MySQL database, it establishes a connection to the MySQL server. This connection typically includes authentication and authorization to ensure 
  secure access.
  
* Once the connection is established, the client can send multiple queries and receive responses over the same connection.

**Concurrency and Scalability:**

* MySQL is designed to handle concurrent connections from multiple clients simultaneously. It manages transactions, locking, and isolation levels to ensure data consistency and integrity in multi-user environments.

* For scalability, MySQL can be deployed in configurations like master-slave replication or sharding to distribute the database workload across multiple servers.

**Security:**

Security is crucial in a client-server architecture with MySQL. Access control, authentication, and encryption are employed to protect sensitive data and ensure that only authorized clients can access the database.

**Backup and Recovery:**

MySQL offers data backup and recovery mechanisms to safeguard against data loss or system failures. This includes tools for creating backups, restoring data, and maintaining data consistency.

**Project Architecture Diagram**

![furthe diagram](https://github.com/Ukdav/Client-Server-Architecture-With-MySql-/assets/139593350/cdb682b9-1317-49b3-a740-32b658054e01)

![project server](https://github.com/Ukdav/Client-Server-Architecture-With-MySql-/assets/139593350/dbf6f0b4-a0be-49e6-b2a1-532927815a31)

![sudo apt install curl](https://github.com/Ukdav/Client-Server-Architecture-With-MySql-/assets/139593350/dc2a8e88-f323-4084-8691-b69523063558)

![proxihome](https://github.com/Ukdav/Client-Server-Architecture-With-MySql-/assets/139593350/39eb232d-6375-4849-a029-344639f01400)

To demonstrate Client-Server architecture we will be using two Ec2 instances with mysql-server and mysql-client respectively.

Create and configure two Linux-based virtual servers (EC2 instances in AWS).

Name one instance of Mysql-server and the other Mysql-client

![ec2vinstance server installation](https://github.com/Ukdav/Client-Server-Architecture-With-MySql-/assets/139593350/e0c59a61-c569-4146-a226-090707eba8d5)

**Note:** Make sure they are both in the same subnet

On the MySQL server, Linux Server installs MySQL Server software while the Client installs Mysql-client

![sudo apt install server](https://github.com/Ukdav/Client-Server-Architecture-With-MySql-/assets/139593350/2c7a29f9-ce8b-4e41-8fc2-afc942cd6f57)

![sysmctl](https://github.com/Ukdav/Client-Server-Architecture-With-MySql-/assets/139593350/542c9046-8723-4592-b228-21ea878273a8)

On the MySQL client Linux Server install MySQL Client software.

![sudo apt install client](https://github.com/Ukdav/Client-Server-Architecture-With-MySql-/assets/139593350/5d1feda6-c4c4-40fb-9d67-6cd6e21f2bf4)

Open port 3306 on Mysql server to allow for connection. Both servers can communicate using private IPs since they belong to the same subnet.

![inbound rules](https://github.com/Ukdav/Client-Server-Architecture-With-MySql-/assets/139593350/5af84736-b669-46bb-be8f-f8365da6869b)

Change bind-address on Mysql-server to allow for connection from any IP address. Set the bind address to 0.0.0.0 using the command below:

*sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf* 

![change ip](https://github.com/Ukdav/Client-Server-Architecture-With-MySql-/assets/139593350/ad0087c9-3ca7-4061-b546-79ddfcc95df0)

Configure MySQL server and create a database and user

* Set up password with *sudo mysql_secure_installation* and create a user

* Create database

![SUDO MYSQL](https://github.com/Ukdav/Client-Server-Architecture-With-MySql-/assets/139593350/9e1dc696-704c-424a-8c10-d56bb238bfee)

![showdatabases](https://github.com/Ukdav/Client-Server-Architecture-With-MySql-/assets/139593350/92c79667-e134-4edc-b3bb-8b546fd41403)

* Grant all permission on the database

![GRANT PERMISSION](https://github.com/Ukdav/Client-Server-Architecture-With-MySql-/assets/139593350/ffbb0690-4ac7-4eee-821f-71b8729fab65)

From MySQL client Linux Server connects remotely to MySQL server Database Engine without using SSH, You'll need to use the Mysql utility to perform this action.

![connecting to server](https://github.com/Ukdav/Client-Server-Architecture-With-MySql-/assets/139593350/53cc4b66-b185-4a71-9fcb-1c667b5d3ec6)

In summary, Client-Server Architecture with MySQL forms the foundation of many modern applications, enabling secure, scalable, and efficient data management and retrieval. 

It separates the presentation layer (client) from the data storage and processing layer (server), facilitating collaborative and distributed application development.






* 














