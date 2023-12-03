<!-- TOC start (generated with https://github.com/derlin/bitdowntoc) -->

# Java Development Crash Course

   * [Section 1: Core Java](#section-1-core-java)
   * [Section 2: Maven ](#section-2-maven)
      + [Maven Introduction:  ](#maven-introduction)
      + [Maven in IDE ](#maven-in-ide)
      + [Getting Dependencies:  ](#getting-dependencies)
      + [Effective POM:  ](#effective-pom)
      + [Maven Archetype:  ](#maven-archetype)
      + [How Maven Works:](#how-maven-works)
   * [Section 3: JDBC](#section-3-jdbc)
   * [Section 4: Getting Started](#section-4-getting-started)
   * [Section 5: Spring Boot](#section-5-spring-boot)
   * [Section 6: Spring Core - loC](#section-6-spring-core---loc)
   * [Section 7: Spring MVC](#section-7-spring-mvc)
   * [Section 8: Spring ORM](#section-8-spring-orm)
   * [Section 9: Spring Data JPA](#section-9-spring-data-jpa)
   * [Section 10: Spring REST](#section-10-spring-rest)
   * [Section 11: Spring AOP](#section-11-spring-aop)
   * [Section 12: Spring Security](#section-12-spring-security)
   * [Section 13: Docker](#section-13-docker)
   * [Section 14: Microservices](#section-14-microservices)
   * [Section 15: DSA (Optional)](#section-15-dsa-optional)

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
