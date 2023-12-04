# Java Development Crash Course

<!-- TOC start (generated with https://github.com/derlin/bitdowntoc) -->

- [Section 1: Core Java](#section-1-core-java)
- [Section 2: Maven ](#section-2-maven)
   * [Maven Introduction:  ](#maven-introduction)
   * [Maven in IDE ](#maven-in-ide)
   * [Getting Dependencies:  ](#getting-dependencies)
   * [Effective POM:  ](#effective-pom)
   * [Maven Archetype:  ](#maven-archetype)
   * [How Maven Works:](#how-maven-works)
- [Section 3: JDBC](#section-3-jdbc)
   * [JDBC Introduction ](#jdbc-introduction)
   * [Postgres Setup ](#postgres-setup)
   * [JDBC Steps  ](#jdbc-steps)
   * [Postgres Library jar](#postgres-library-jar)
   * [Connecting Java and DB](#connecting-java-and-db)
   * [Execute and Process](#execute-and-process)
   * [Crud operations](#crud-operations)
   * [Problems with Statement](#problems-with-statement)
- [Section 4: Getting Started](#section-4-getting-started)
- [Section 5: Spring Boot](#section-5-spring-boot)
- [Section 6: Spring Core - loC](#section-6-spring-core---loc)
- [Section 7: Spring MVC](#section-7-spring-mvc)
- [Section 8: Spring ORM](#section-8-spring-orm)
- [Section 9: Spring Data JPA](#section-9-spring-data-jpa)
- [Section 10: Spring REST](#section-10-spring-rest)
- [Section 11: Spring AOP](#section-11-spring-aop)
- [Section 12: Spring Security](#section-12-spring-security)
- [Section 13: Docker](#section-13-docker)
- [Section 14: Microservices](#section-14-microservices)
- [Section 15: DSA (Optional)](#section-15-dsa-optional)

<!-- TOC end -->

## Section 1: Core Java
## Section 2: Maven 
### Maven Introduction:  
  - Introduction to Maven: 
      - Maven is a project management tool.
      - It is essential beyond syntax and concepts when building a project.
  - Project Building Steps:
      - Compilation of files.
      - Running files.
      - Testing files.
      - Creating a package.
      - Deployment.
  - External Libraries and Dependencies:
      - Projects often require external libraries.
      - Examples include connectors for database interaction (e.g., MySQL Connector for MySQL, Postgres Connector for Postgres).
      - Introduction to Hibernate as a tool for saving data in a database without SQL queries.
  - Library Retrieval in Java:
      - Libraries are obtained as JAR files.
      - Process involves searching and downloading from the internet.
      - Different IDEs support adding JAR files to the project.
  - Transitive Dependencies in Hibernate:
      - Hibernate requires multiple JAR files due to transitive dependencies.
      - Upgrading dependencies in the future may require redownloading.
  - Compatibility and Versioning:
      - Different frameworks may have their own dependencies.
      - Version compatibility between frameworks is crucial.
      - Matching versions ensures proper collaboration between frameworks.
  - Challenges with Manual Dependency Management:
      - Time-consuming process.
      - Potential issues when sharing projects with colleagues.
      - Synchronization of versions is critical.
  - Introduction to Maven as a Solution:
      - Maven streamlines the process of managing dependencies.
      - Automates the retrieval of dependencies.
      - Helps maintain version compatibility.
  - Other Project Management Tools:
      - Mention of other tools like Gradle and Ivy.
      - Selection of Maven for its beginner-friendly nature.
  - Focus on Dependency Management:
      - Emphasis on understanding Maven for handling dependencies.
      - Mention of Maven plugins for various project phases (compiling, testing, running), but the focus in this section is on dependencies.

###  Maven in IDE 
  - Project Collaboration with Maven:
      - Emphasizes the collaborative aspect of Maven, where project configurations and dependencies are easily shared among team members.
      - The video concludes with a teaser for the next video, where the workings behind the scenes will be explained.
  - Maven Installation: 
      - Maven can be installed locally on the machine and accessed through the command line.
      - IDEs, such as Eclipse or IntelliJ, also support Maven.
  - Getting Maven from Official Website:
      - Visit the official Maven website: Maven Apache.
      - Download Maven from the website and set the path for command line usage.
  - Using Maven with IDEs:
      - IntelliJ and Eclipse provide Maven support.
      - Create a new project and choose Maven as the build system to ensure consistency in project structure.
      - Project structure remains the same regardless of the IDE used.
  - Project Creation in IntelliJ:
      - Create a new project in IntelliJ.
      - Specify project name (e.g., Maven Demo), language (Java), and choose Maven as the build system.
      - Default project structure is established.
  - Maven Plugins in IDEs:
      - Maven plugins facilitate various stages of project development.
      - In IntelliJ, the Maven option is typically found in the top right.
      - The project life cycle includes compilation, testing, packaging, installing, and deploying.
  - Maven Life Cycle Options in IDE:
      - Life cycle options include compile, test, package, install, and deploy.
      - Maven automates these processes, reducing manual effort.
      - Example: Clicking "compile" initiates Maven to compile the project.
  - Maven Plugins and Features:
      - Maven provides plugins to achieve different tasks in the development life cycle.
      - Plugins assist in compiling, testing, packaging, installing, and deploying the project.
  - Maven Archetype:
      - Maven has an archetype feature.
      - Further details about Maven archetypes and plugins are discussed in upcoming videos.
  - Simplifying Project Tasks with Maven:
      - Demonstrates how Maven simplifies tasks like compilation, testing, packaging, installation, and deployment.
      - Emphasizes the convenience of using IDE features for these tasks.
      - Introduction to Maven plugins that automate these tasks.

### Getting Dependencies:  
  - Introduction to Archetypes: 
      - Maven provides archetypes, which are templating tools for project setup.
      - Archetypes simplify the process of creating project configurations and dependencies.
  - Usage of Archetypes:
      - Archetypes are useful for building specific types of projects, such as web projects.
      - They provide pre-configured templates that can be customized or used as is.
  - Creating Project Templates:
      - Archetypes allow users to create their own templates for specific project types.
      - Templates can include configurations and dependencies for consistent project setups.
  - Dependency Handling in Maven:
      - Maven helps in managing project dependencies, specifically JAR files.
      - The process involves searching for libraries online, downloading them, and adding them to the project.
  - Dependency Search and Download:
      - Demonstrates how to search for a library, e.g., MySQL Connector, online.
      - Shows the manual process of downloading and adding the JAR file to the project.
  - Repository Usage in Maven:
      - Introduces the Maven Repository (repository.com) as an alternative to manual downloads.
      - Shows how to search for and download a library using Maven dependency syntax.
  - Understanding Maven's POM.xml:
      - Focuses on the POM.xml file (Project Object Model) in Maven.
      - Explains the significance of group ID, artifact ID, and version in identifying and managing dependencies.
  - Group ID in Maven:
      - Group ID ensures uniqueness for a library throughout the world.
      - It is often derived from the organization's domain name, ensuring global uniqueness.
  - Artifact ID in Maven:
      - Artifact ID is the project name.
      - Used in combination with the group ID and version to uniquely identify the library.
  - Dependency Management in POM.xml:
      - Demonstrates how to add dependencies to the POM.xml file.
      - Every library is specified with group ID, artifact ID, and version.
  - Refreshing Maven Project in IDE:
      - Shows how to refresh or reload a Maven project in the IDE after updating the POM.xml file.
      - Maven automatically downloads and adds the specified dependencies.
  - Transitive Dependencies:
      - Introduces the concept of transitive dependencies.
      - Explains that a library may have dependencies of its own, known as transitive dependencies.
  - Adding Multiple Dependencies:
      - Demonstrates adding multiple dependencies, such as MySQL Connector and Hibernate, to the POM.xml.
      - After saving and reloading, Maven downloads and adds all required JAR files.
  - Sharing Projects with Dependencies:
      - Highlights the convenience of sharing projects by sharing the POM.xml file.
      - Recipients can reload Maven, and the IDE will automatically download and manage dependencies.
### Effective POM:  
  - POM File Configuration: 
      - The pom.xml file is crucial for Maven configuration.
      - Configuration involves specifying group ID, artifact ID, and version for creating JAR files or libraries.
      - Dependencies for the project are also mentioned in the dependencies tag.
      - Dependencies can include transitive dependencies.
  - Working with Plugins:
      - Plugins can be added to the pom.xml file for additional functionality.
      - A separate plugins tag allows the configuration of various plugins.
  - Effective POM:
      - The concept of the effective POM or super POM is introduced.
      - Maven looks at the effective POM when working with a project.
      - Changes made in the pom.xml file are reflected in the effective POM.
  - Viewing Effective POM in IntelliJ:
      - In IntelliJ, right-click on pom.xml.
      - Navigate to the "Maven" option and choose "Show Effective POM."
      - The effective POM includes more settings than those explicitly added in the pom.xml file.
  - Default Plugins in Effective POM:
      - The effective POM includes default plugins even if not explicitly added.
      - Examples of default plugins include Auto Run, clean, resources, Jar, package, and compiler.
  - Understanding Effective POM:
      - Changes made in the pom.xml file result in the creation of an effective POM.
      - Developers should focus on modifying the pom.xml file rather than directly altering the effective POM.
      - Effective POM provides a comprehensive view of the project configuration, including default settings and plugins.
  - Different IDEs and Effective POM:
      - Various IDEs may have different methods of displaying the effective POM.
      - A demonstration in IntelliJ is provided, and a future demonstration in Eclipse will be shown.
  - Importance of POM.xml:
      - The pom.xml file is the primary configuration file for Maven projects.
      - Developers specify project details, dependencies, and plugins in the pom.xml.
      - Maven uses the effective POM, created from the pom.xml, when executing tasks for the project.
### Maven Archetype:  
  - Archetypes in Maven: 
      - Archetypes are templates in Maven that can be used to create project structures with predefined configurations.
      - Developers can use existing archetypes or create custom ones.
      - Archetypes simplify project setup by providing predefined configurations for specific frameworks or project types.
  - Creating a New Project with Archetypes:
      - To create a new project using archetypes, navigate to the new project creation option.
      - Choose the Maven archetype option and provide a name for the project (e.g., "Demo Spring project").
      - Select an archetype based on the type of project you want to create (e.g., J2EE, Quickstart, Web App).
      - Archetypes provide predefined configurations for common project types.
  - Archetype Catalogs:
      - Maven has an internal catalog of archetypes that comes with the Maven installation.
      - External catalogs, such as Maven Central, can be accessed to get a wider range of archetypes.
      - Maven Central provides numerous archetypes from the internet, expanding the available options.
  - Downloading Dependencies:
      - When an archetype is selected, Maven downloads the necessary dependencies and sets up the project structure.
      - Dependencies may include frameworks, libraries, and configurations required for the selected archetype.
      - Downloading from the internet may take some time as it fetches the required resources.
  - Example: Spring Boot MVC Archetype:
      - Demonstrates selecting a Spring Boot MVC archetype from Maven Central.
      - The selected archetype provides a default project structure and configurations for a Spring Boot MVC application.
      - Dependencies for Spring Boot Starter, Web MVC, Jersey, Jdbc, and H2 are automatically added to the project.
  - Advantages of Using Archetypes:
      - Archetypes save time and effort by providing ready-made project structures.
      - Developers don't have to manually configure dependencies or project settings.
      - Archetypes are especially useful for projects involving popular frameworks like Spring Boot.
  - Usage in Eclipse:
      - Similar options for choosing archetypes are available in Eclipse when creating a Maven project.
      - Developers can select archetypes during the initial project setup process in Eclipse.
  - Simplified Project Setup:
      - Archetypes abstract away the complexity of setting up a project from scratch.
      - They enable developers to start with a predefined structure and configurations, making the project setup process more efficient.
### How Maven Works:
  - Maven Dependency Resolution: 
      - Maven resolves dependencies for projects based on the information provided in the pom.xml file.
      - When a project specifies dependencies, Maven searches for them in the local machine first.
  - Local Repository (M2 Folder):
      - Each machine with Maven installed has a local repository known as the M2 folder.
      - The local repository stores copies of dependencies that have been downloaded previously.
  - Dependency Search Process:
      - Maven checks the local repository first for the requested dependencies.
      - If the dependencies are found locally, Maven uses the local copies, avoiding the need to download from the internet.
  - Maven Central Repository:
      - If a dependency is not found in the local repository, Maven then looks for it in the remote repository, typically Maven Central.
      - Maven Central is a central repository on the internet that hosts a vast collection of libraries and dependencies.
  - Dependency Update and Vulnerabilities:
      - Dependencies fetched from remote repositories may have vulnerabilities.
      - Maven may warn about vulnerable versions, and developers are encouraged to update to secure versions.
  - Security Measures and Company Repository:
      - Companies often prioritize security and may have an additional layer between Maven and the remote repository.
      - Company-wide repositories are maintained, containing only well-tested and secure libraries.
      - Maven first checks the local repository, then the company repository before attempting to download from the internet.
  - Version Issues and Resolution:
      - If there are issues with versions or dependencies not working as expected, developers can go to the local repository (M2 folder) and delete the specific file causing problems.
      - Deleting the file prompts Maven to download the dependency again, potentially resolving version or compatibility issues.
  - Best Practices:
      - Developers should ensure the security of dependencies, considering vulnerabilities and updates.
      - Companies may implement measures to verify and manage dependencies before they are added to the project.
  - Conclusion:
      - Understanding Maven's dependency resolution process can help developers troubleshoot issues related to dependencies.
      - It's essential to prioritize security and follow best practices when working with external libraries and dependencies.
  
## Section 3: JDBC


### JDBC Introduction 
  - Introduction to JDBC: 
      - Stands for Java Database Connectivity.
      - In the software industry, data interaction is crucial, and applications are built to store, fetch, and update data.
      - Initial data handling involves storing data in variables, but this is temporary, and data is lost when the application is closed.
  - Permanent Data Storage:
      - Need arises to store data permanently.
      - Storing data in a plain text (TXT) file is an option but is limited in terms of searchability and relational structure.
  - Relational Database Management System (RDBMS):
      - RDBMS allows data storage in a tabular format.
      - Provides a structured way to store and manage data permanently.
  - SQL (Structured Query Language):
      - SQL is used to interact with databases.
      - Learning SQL may not be practical for regular users or clients.
  - Database Connectivity with Java:
      - Application acts as an intermediary between the user and the database.
      - The application is built in Java, allowing users to interact with a console-based application.
  - JDBC (Java Database Connectivity):
      - JDBC is an API (Application Programming Interface) in the Java Development Kit (JDK).
      - Provides a standardized way for Java applications to connect with databases.
  - Challenges with Multiple DBMS:
      - Various database management systems (DBMS) exist, such as Oracle, Postgres, MySQL, H2, DB2.
      - Connecting Java applications to different DBMS requires specific implementation code.
  - Dynamic Implementation with JDBC:
      - JDBC API provides interfaces and classes for connectivity but requires actual implementation from the DBMS.
      - Each DBMS, like Postgres or MySQL, provides its implementation library for Java applications to connect.
  - Changing DBMS and Code Adaptation:
      - Changing DBMS, for example, from Postgres to MySQL, may require significant changes to the code.
      - JDBC simplifies this by providing a consistent API while leaving the implementation details to the specific DBMS library.
  - Series Focus on Postgres:
      - The series will use Postgres as the DBMS.
      - Installation of the chosen DBMS and acquiring the necessary library (JAR file) for connectivity will be covered in upcoming videos.
  - Next Steps:
      - Ensure the installation of the chosen DBMS.
      - Acquire the required JAR file/library for JDBC connectivity.
      - Explore the implementation of JDBC for connecting Java applications with the chosen database.

### Postgres Setup 
  - Setting Up Postgres: 
      - Download Postgres from the official website: postgresql.org.
      - Install the appropriate version based on the operating system (Mac, Windows, Linux).
      - During installation, set a secure password for Postgres.
  - PgAdmin Interface:
      - PgAdmin is installed along with Postgres and provides a graphical interface for database management.
      - Access PgAdmin using the set password.
      - Familiarize with the Object Explorer, Servers, Database, and Dashboard sections.
  - Creating a Database:
      - In PgAdmin, right-click on Servers > Postgres version > Databases.
      - Create a new database, e.g., "Demo," with default settings and owner as "Postgres."
      - Explore the Database dashboard, schemas, and tables.
  - Creating a Table:
      - Right-click on Tables > Create Table.
      - Define a table name, e.g., "Student."
      - Specify columns like "Sid" (integer, primary key), "Sname" (text), "Marks" (integer).
      - Save to create the table.
  - Inserting Data:
      - Use the SQL query tool to insert data into the "Student" table.
      - Example query: INSERT INTO Student VALUES (1, 'Ahmed', 99); 
      - Execute the query to insert data into the table.
      - View the inserted data in the table.
  - Troubleshooting Data Types:
      - Be mindful of data types during table creation (e.g., use "text" for string in Postgres).
      - In case of errors, alter the table structure or recreate columns with correct data types.
  - Viewing Data:
      - Use PgAdmin's graphical interface to view all rows in the table.
      - Explore the query tool to write SQL queries for data manipulation.
  - Next Steps:
      - The tutorial introduces manual database setup and data insertion.
      - Future lessons will focus on using JDBC to interact with the database from Java code.
      - JDBC will provide a programmatic way to connect, query, and manipulate the database using Java.

### JDBC Steps  
  - Steps for JDBC: 
      - 1. Import Packages:
          - Import the java.sql package in Java, which contains classes and interfaces for JDBC operations.
      - 2. Load and Register Driver:
          - Load and register the JDBC driver specific to your database.
          - In JDBC versions prior to 4.0, this step was crucial, but newer versions (JDBC 4.0 onwards) often handle this automatically when adding the JDBC driver JAR to the project.
      - 3. Create a Connection:
          - Establish a connection to the database.
          - This is akin to having a working phone and network in a real-world analogy.
      - 4. Execute a Statement:
          - Prepare and execute SQL statements.
          - Analogous to thinking about what you want to say before making a call.
      - 5. Process the Result:
          - Handle the results obtained from the executed SQL statements.
          - Similar to processing the response received during a phone call.
      - 6. Close the Connection:
          - Properly close the connection to release resources and avoid memory leaks.
          - Similar to ending a phone call to prevent additional charges.
      - 7. Optional Steps (Depending on Version and Context):
          - Load and Register Driver (Optional):
              - Loading and registering the driver can be optional in certain JDBC versions and contexts, especially after JDBC 4.0.
          - Importing Packages (Optional):
              - Some tutorials or books might consider package importing as optional, focusing on essential steps.
      - Note:
          - The number of steps may vary in different resources, ranging from five to seven.
          - Steps 2 (Load and Register Driver) and 1 (Import Packages) can be optional depending on the JDBC version and project setup.
          - The key is to focus on the essential steps of creating a connection, executing statements, processing results, and closing the connection.
       
### Postgres Library jar
  - 1. IDE Selection:
      - IntelliJ IDEA is chosen for coding in this section.
      - Both community (free) and ultimate (paid) versions are available, and the community version is used in this case.
  - 2. Project Setup:
      - A new project named "Jdbc course" is created in IntelliJ IDEA.
      - The language selected is Java, and the build system used is IntelliJ's default.
  - 3. JDK Version:
      - JDK 19 is used for the project, but any version above 8 is considered suitable.
  - 4. External Libraries (JDBC Driver):
      - The JDBC driver for PostgreSQL is required to establish a connection between Java and PostgreSQL.
      - The process involves downloading the JDBC driver JAR file from the official PostgreSQL website or Maven Repository.
  - 5. Library Integration:
      - In IntelliJ IDEA, the downloaded JAR file is added as an external library.
      - The steps include going to "File" > "Project Structure," selecting "Libraries," and adding the downloaded JAR.
  - 6. Code Development Steps (7 Steps in JDBC):
      - The speaker introduces the seven steps involved in JDBC, which include:
          - 1. Importing the necessary packages (e.g., java.sql).
          - 2. Loading and registering the JDBC driver (Note: JDBC 4.0 onwards may not require explicit loading and registration).
          - 3. Establishing a connection to the database.
          - 4. Executing a statement (equivalent to deciding what to say in a phone call analogy).
          - 5. Processing the results obtained from the database.
          - 6. Closing the connection to avoid memory leaks.
          - 7. Note: Some versions or sources may have different step counts, but the core steps remain the same.
  - 7. Coding Environment:
      - IntelliJ IDEA is suggested for coding in Java with JDBC.
      - The speaker indicates that the actual code implementation will follow in the next video.

### Connecting Java and DB
  - 1. Coding Steps in JDBC:
      - The coding steps in JDBC are divided into seven key steps.
      - These steps are:
          - 1. Importing the necessary package (java.sql).
          - 2. Loading and registering the JDBC driver (optional in some cases).
          - 3. Creating a connection to the database.
          - 4. Creating a statement (equivalent to deciding what to say in a phone call analogy).
          - 5. Executing the statement.
          - 6. Processing the results obtained from the database.
          - 7. Closing the connection to avoid memory leaks.
  - 2. Importing Packages:
      - In the Java file, the first step involves importing the necessary package:
          - import java.sql.*;
  - 3. Loading and Registering Driver:
      - The second step, loading and registering the driver, is optional.
      - Example for PostgreSQL:
          - Class.forName("org.postgresql.Driver");
  - 4. Creating a Connection:
      - The third step involves creating a connection to the database using DriverManager.getConnection.
      - Example:
          - Connection con = DriverManager.getConnection(URL, username, password);
  - 5. Connection URL, Username, and Password:
      - The connection URL is specific to the type of database (e.g., PostgreSQL, MySQL, Oracle).
      - Example variables:
          - String URL = "jdbc:postgresql://localhost:5432/demo";
          - String username = "yourname";
          - String password = "pass";
  - 6. Testing Connection:
      - A test is performed to print "Connection established" on the console.
      - Initial mistakes are intentionally made to demonstrate error handling.
      - The test includes incorrect database type and incorrect password.
  - 7. Optional Driver Loading:
      - The driver loading step is optional, and in many cases, it's not explicitly required, especially with JDBC 4.0 and later versions.
  - 8. Error Handling:
      - The lecture emphasizes the use of try-catch for exception handling.
  - 9. Executing and Testing:
      - The code is tested with intentional errors for incorrect database type and password.
      - Corrections are made to ensure the successful establishment of a connection.
  - 10. Optional Steps:
      - Some steps are considered optional based on the specific JDBC version or use case.
      - The video demonstrates commenting out the driver loading step to show it's not compulsory in certain scenarios.

### Execute and Process
  - 1. Connection Establishment:
      - Successful establishment of the database connection is confirmed.
      - Importing the package, loading the driver, and creating a connection are completed.
  - 2. Purpose of Database Connection:
      - The goal is to connect to a database using Java code for data retrieval.
      - The example uses a database named "demo" with a table named "Student" having three columns and one row.
  - 3. Objective: Fetching Data:
      - The primary purpose of connecting to the database is to fetch data, specifically the name of a student based on their ID.
  - 4. SQL Query for Data Retrieval:
      - The SQL query for fetching the name of a student with ID 1 is demonstrated.
      - Example: SELECT * FROM Student WHERE ID = 1
  - 5. Statement Creation:
      - To interact with the database, a Statement object is required.
      - A reference object for Statement is created using the createStatement method of the Connection object.
  - 6. Query Execution:
      - The executeQuery method of the Statement interface is used to execute the SQL query.
      - The result set is stored in a ResultSet object.
  - 7. Result Set Handling:
      - The ResultSet object is used to check if there is a next row using the next method.
      - The method returns true if there is a next row, false otherwise.
  - 8. Closing the Connection:
      - The importance of closing the connection is emphasized.
      - The close method is used to close the connection, ensuring proper resource management.
  - 9. Data Retrieval and Printing:
      - To retrieve and print data from the result set, methods like getString are used.
      - Data is fetched based on column names or column numbers.
      - Example: String name = rs.getString("sname");
  - 10. Error Handling:
      - The lecture mentions a crucial step that was initially overlooked: closing the connection.
      - No specific error-handling mechanisms are discussed in this segment.
  - 11. Pointer Positioning in Result Set:
      - Explanation of the default position of the result set pointer before the first row.
      - The importance of calling next to position the pointer correctly before fetching data.
  - 12. Successful Data Retrieval:
      - The successful execution of the program is demonstrated by fetching and printing the name of a student (Naveen) from the database.
  - 13. Teaser for Advanced Concepts:
      - The lecture ends with a teaser for upcoming topics, suggesting that more complex database interactions will be covered in the future.
  - Code
       ```java import java.sql.*;
import static java.lang.Class.*;
public class JDBCDemo {
  public static void main(String[] args) throws ClassNotFoundException, SQLException {

      String URL = "jdbc:postgresql://localhost:5432/Demo";
      String username = "postgres";
      String password = "root";

      Class.forName("org.postgresql.Driver");
      Connection con = DriverManager.getConnection(URL, username, password);

      System.out.println("Connection Established");

      // Your SQL query
      String sql = "SELECT sname FROM student WHERE sid = 1";

      // Create a statement
      Statement st = con.createStatement();

      // Execute the query
      ResultSet rs = st.executeQuery(sql);

      // Move to the first row in the result set
      if (rs.next()) {
          // Retrieve the value of the "sname" column
          String name = rs.getString("sname");

          // Print the result
          System.out.println("Name of a student is " + name);
      } else {
          System.out.println("No records found.");
      }

      // Close the resources
      rs.close();
      st.close();
      con.close();
      System.out.println("Connection Closed");
  }
} ```

### Fetching all Records
  - 1. Objective: Inserting Data into Database
      - Goal: Insert data into the database for fetching with different IDs.
      - Utilize SQL queries for inserting records into the "Student" table.
  - 2. SQL Insert Queries:
      - Example SQL queries:
          - Inserting data for ID 2: INSERT INTO student VALUES (2, 'Kiran', 50);
          - Inserting data for ID 3: INSERT INTO student VALUES (3, 'Hirsch', 55);
          - Inserting data for ID 4: INSERT INTO student VALUES (4, 'Social', 45); 
  - 3. Verifying Inserted Data:
      - Execute a SELECT query to verify that the data has been successfully inserted.
      - Example: SELECT * FROM student;
  - 4. Updating Java Code for Data Retrieval:
      - Modify the Java code to fetch and print all rows and columns from the "Student" table.
  - 5. Using ResultSet for Data Retrieval:
      - Utilize the ResultSet object to iterate over rows and retrieve data for each column.
  - 6. Automating Data Retrieval with a Loop:
      - Use a while loop to iterate over rows until there is no next row.
      - The next method checks for the next row and moves the pointer.
  - 7. Fetching Data Using Column Numbers:
      - Fetch data from the result set using both column numbers and column names.
      - Example: int id = rs.getInt(1); or String name = rs.getString("sname");
  - 8. Printing Data in a Readable Format:
      - Print data with appropriate formatting to distinguish between rows and columns.
  - Now, here is the complete code snippet used in this tutorial:
    ```java
    import java.sql.*;
    public class JDBCDemo {
      public static void main(String[] args) {
          try {
              String URL = "jdbc:postgresql://localhost:5432/Demo";
              String username = "postgres";
              String password = "root";
    
              // Load the PostgreSQL JDBC driver
              Class.forName("org.postgresql.Driver");
    
              // Establish a connection
              Connection con = DriverManager.getConnection(URL, username, password);
    
              System.out.println("Connection Established");
    
              // Create a statement
              Statement st = con.createStatement();
    
              // Fetching all rows and columns
              String query = "SELECT * FROM student";
              ResultSet rs = st.executeQuery(query);
    
              // Iterating over rows and printing all columns
              while (rs.next()) {
                  int id = rs.getInt("sid");
                  String name = rs.getString("sname");
                  int marks = rs.getInt("smarks");
    
                  // Printing data with proper formatting
                  System.out.println("ID: " + id + " - Name: " + name + " - Marks: " + marks);
              }
    
              // Closing the resources
              rs.close();
              st.close();
              con.close();
              System.out.println("Connection closed");
          } catch (ClassNotFoundException | SQLException e) {
              e.printStackTrace();
          }
      }
    }```

          
### Crud operations
  - Fetching Data 
      - Fetching a single data item and printing the entire table.
      - Use of a while loop to count the number of rows.
      - Possibility of automating column retrieval with an additional loop.
      - Use of a for loop for columns to execute queries.
  - Inserting Data
      - Explanation of CRUD operations (Create, Read, Update, Delete).
      - Changing SQL query to an insert query for adding a new record.
      - Executing the insert query using execute method.
      - Handling the Boolean status returned by execute.
  - Updating Data
      - Changing SQL query to an update query.
      - Updating a specific record (e.g., changing a name from John to Max).
      - Executing the update query using execute.
  - Deleting Data
      - Changing SQL query to a delete query.
      - Deleting a specific record (e.g., deleting the record with ID 5).
      - Executing the delete query using execute.
  - Code Snippet:
  - ```java
      - // Establishing the connection (common for all operations)
    Connection con = DriverManager.getConnection(URL, username, password);
    Statement stmt = con.createStatement();
    
    // Inserting Data
    String insertQuery = "INSERT INTO student VALUES (5, 'John', 48)";
    boolean insertStatus = stmt.execute(insertQuery);
    System.out.println("Insert Status: " + insertStatus);
    
    // Updating Data
    String updateQuery = "UPDATE student SET name = 'Max' WHERE ID = 5";
    boolean updateStatus = stmt.execute(updateQuery);
    System.out.println("Update Status: " + updateStatus);
    
    // Deleting Data
    String deleteQuery = "DELETE FROM student WHERE ID = 5";
    boolean deleteStatus = stmt.execute(deleteQuery);
    System.out.println("Delete Status: " + deleteStatus);
    
    // Closing the connection
    stmt.close();
    con.close();```

### Problems with Statement
  - 1. Introduction to Prepared Statements:
      - Prepared statements are used in SQL to improve performance, avoid SQL injection, and simplify the process of inserting data into a database.
      - They are particularly useful when dealing with user input, as they help prevent SQL injection vulnerabilities.
  - 2. Need for Prepared Statements:
      - Directly inserting data using concatenation and double quotes can lead to issues.
      - Problems include treating values as strings, complex concatenation, and the risk of SQL injection attacks.
      - Performance improvement is achieved by caching queries in the database.
  - 3. Issues with Direct Insertion:
      - Direct insertion involves concatenating values within double quotes, making it error-prone and confusing.
      - SQL injection vulnerabilities arise when user input is directly incorporated into queries.
  - 4. Benefits of Prepared Statements:
      - Improved performance by caching queries.
      - Prevention of SQL injection attacks.
      - Simplification of the process of inserting data into a database.
  - 5. Preventing SQL Injection:
      - SQL injection occurs when user input contains malicious SQL code.
      - Prepared statements help prevent SQL injection by separating SQL code from user input.
  - 6. Improving Performance with Prepared Statements:
      - Caching queries in the database is a key feature of prepared statements.
      - Reusing the same query multiple times without resending it from Java to the database.
  - Code Snippet: 
      ```java
    - // Direct insertion with concatenation (not recommended)
    String query = "INSERT INTO student VALUES (" + CID + ", '" + name + "', " + marks + ")";
    Statement statement = connection.createStatement();
    statement.executeUpdate(query);
    
    // Issues with direct insertion and potential SQL injection vulnerabilities
    
    // Prepared statement example (to be covered in the next video)
    String preparedQuery = "INSERT INTO student VALUES (?, ?, ?)";
    PreparedStatement preparedStatement = connection.prepareStatement(preparedQuery);
    preparedStatement.setInt(1, CID);
    preparedStatement.setString(2, name);
    preparedStatement.setInt(3, marks);
    preparedStatement.executeUpdate(); ```


  ### PreparedStatement
  - 1. Introduction to Prepared Statements:
      - Prepared statements are used to improve code readability, prevent SQL injection, and enhance performance.
      - They are particularly useful when dealing with dynamic data coming from variables.
  - 2. Building a Prepared Statement:
      - Instead of directly inserting values into the SQL query, use placeholders (question marks) for dynamic data.
      - Example: INSERT INTO student VALUES (?, ?, ?)
  - 3. Using Prepared Statement in Java:
      - Replace Statement with PreparedStatement when working with dynamic data.
      - PreparedStatement pstmt = con.prepareStatement(sql);
  - 4. Precompilation of Query:
      - Prepared statements are precompiled, allowing for better performance and caching of queries.
      - The SQL query is set during the creation of the prepared statement.
  - 5. Setting Parameters in Prepared Statement:
      - Use set methods to set parameters for the prepared statement.
      - setInt(int parameterIndex, int x), setString(int parameterIndex, String x), etc.
      - Parameters are replaced with actual data during execution.
  - 6. Column Index in Prepared Statement:
      - Columns are indexed starting from 1 in prepared statements.
      - Example: setInt(1, CID) sets the value of the first parameter to the value of CID.
  - 7. Data Types in Prepared Statement:
      - Specify the data type using appropriate set methods (e.g., setInt, setString) based on the column type.
  - 8. Benefits of Prepared Statements:
      - Cleaner and clearer code compared to concatenation.
      - Prevention of SQL injection vulnerabilities.
      - Improved performance through precompilation and caching.
  - 9. Example Code:
    ```java
    - // Creating a prepared statement
    String sql = "INSERT INTO student VALUES (?, ?, ?)";
    PreparedStatement pstmt = con.prepareStatement(sql);
    
    // Setting parameters for the prepared statement
    pstmt.setInt(1, CID);
    pstmt.setString(2, name);
    pstmt.setInt(3, marks);
    // Executing the prepared statement
    pstmt.executeUpdate();``` 
  - 10. Versatility of Prepared Statements:
      - Prepared statements can be used not only for insertion but also for deletion, update, and select operations.
      - Dynamic data is handled using placeholders that are replaced at runtime.
  - 11. Verification and Testing:
      - Execute the prepared statement to ensure it works as expected.
        - Verify the results in the database to confirm the insertion.

 

## Section 4: Getting Started
## Section 5: Spring Boot
## Section 6: Spring Core - loC
## Section 7: Spring MVC
## Section 8: Spring ORM
## Section 9: Spring Data JPA
## Section 10: Spring REST
## Section 11: Spring AOP
## Section 12: Spring Security
## Section 13: Docker
## Section 14: Microservices
## Section 15: DSA (Optional)
