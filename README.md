# Database SQLi
The project 'Database_SQLi' is a Java-MySQL application where a sign up/login interface, vulnerable to SQL injections, is provided to the users.

Database_SQLi.jar is the executable file to be run, which is present at Database_SQLi/dist.

To run this file, first check if Java is installed on your system by issuing the following command in the Terminal:
```
java -version
```

If Java is not present, issue this command:
```
sudo apt install default-jre
```

This downloads the Java Runtime Environment. Now, in MySQL, issue the following commands:
```
CREATE DATABASE Database_SQLi;
USE Database_SQLi;

CREATE TABLE User
(
UserID varchar(100) PRIMARY KEY,
Password varchar(100)
);
```

Next, ensure that your MySQL 'Root' password is set to "1234".

Now, double-click Database_SQLi.jar to run it. If it doesn't run, right click it, go to Properties, and under the Permissions tab tick the 'Allow executing file as program' checkbox.