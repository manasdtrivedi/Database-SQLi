# Database SQLi
## Description
The project 'Database_SQLi' is a Java application that accesses a MySQL database, where a sign up/login interface, vulnerable to SQL injections, is provided to the users.
A patch for the SQLi vulnerability in the login interface has also been provided, as commented code, in the `enterButtonActionPerformed()` method in the file `Database_SQLi.java`.

To perform an SQL injection, a user may enter any user ID, and the password `password' OR '1' = '1`, in the login frame. This shall log the user in, without an actual login ID. The user will be logged in as the user whose record is present at the first position in the `User` table in the database.

The patch for the SQLi vulnerability involves using SQL prepared statements.

## Technical specifications
* Java 7 or above
* MySQL version 5.1 or above

## Task list
- [x] SQLi vulnerability confirmed
- [x] Create patch for vulnerability
- [x] UI created for demonstration

## Installation guide

#### Java
To check if Java is already installed on your system, execute the following command in the Terminal:
```
$ java -version
```

If Java is not present, execute the following command to install the default Java Runtime Environment (JRE), which will install the JRE from OpenJDK 11:
```
$ sudo apt install default-jre
```

To check if the Java compiler is already installed on your system, execute the following command:
```
$ javac -version
```

If the Java compiler is not present, execute the following command to install the default Java Development Kit (JDK):
```
$ sudo apt install default-jdk
```

#### MySQL
To install MySQL, follow all three steps given in [this](https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-18-04) tutorial, and set `1234` as the `root` password when prompted for the same.

#### NetBeans IDE 8.2
Install NetBeans IDE 8.2 from [here](https://netbeans.org/downloads/old/8.2/), by selecting the Java SE or Java EE bundle.

## Usage

#### 1. MySQL database creation

Issue the following commands in the MySQL Command Line Client for building the database used by the application:
```
CREATE DATABASE Database_SQLi;
USE Database_SQLi;

CREATE TABLE User
(
UserID varchar(100) PRIMARY KEY,
Password varchar(100)
);

INSERT INTO User VALUES('admin', '1234');
```

#### 2. View SQLi vulnerable code and the patch

Open the NetBeans IDE, click on File -> Open Project, and open the Java application. Once opened, in the Projects section, expand the 'Database_SQLi' project node, expand the `Source Packages` subnode, expand the `<default package>` subnode, and double click `Database_SQLi.java`. Click the `Source` tab. In the `enterButtonActionPerformed()` function, the uncommented code is vulnerable to SQL injections, and the commented code is a replacement of the uncommented code, and acts as a patch for the vulnerability.

#### 3. Clean and build project

Click the `Run` tab, and click `Clean and Build Project`. Alternatively, press Shift+F11. This produces Database_SQLi.jar, which is the executable file to be run. This file is present at Database_SQLi/dist.

#### 4. Execute the application

To execute the application from within the IDE, click the `Run` tab, and click `Run File`. Alternatively, press Shift+F6.
To execute the application from outside the IDE, double-click Database_SQLi.jar. If it doesn't run, right click it, go to Properties, and under the Permissions tab tick the 'Allow executing file as program' checkbox.

#### 5. Apply patch

To apply the patch, comment the uncommented code and uncomment the commented code in the `enterButtonActionPerformed()` function. After this, repeat steps 3 and 4.

#### 6. Distribution

To distribute the application, create a zip file of the dist folder, and send it to the users of the application, along with the installation and usage instructions.
