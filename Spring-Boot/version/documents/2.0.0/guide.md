# Spring Boot Reference Guide

### [中文文档](README_CN.md)
## Authors
> Phillip Webb, Dave Syer, Josh Long, Stéphane Nicoll, Rob Winch, Andy Wilkinson, Marcel Overdijk, Christian Dupuis, Sébastien Deleuze, Michael Simons, Vedran Pavić, Jay Bryant, Madhura Bhave
### 2.0.0.BUILD-SNAPSHOT

> Copyright © 2012-2018

> Copies of this document may be made for your own use and for distribution to others, provided that you do not charge any fee for such copies and further provided that each copy contains this Copyright Notice, whether distributed in print or electronically.
---------------------------------------------------------------------------------------------------------------------------
### Table of Contents

* [I. Spring Boot Documentation](#Part-I-Spring-Boot-Documentation)
   * [1. About the Documentation](#1-About-the-Documentation)
   * [2. Getting Help](#2-Getting-Help)
   * [3. First Steps](#3-First-Steps)
   * [4. Working with Spring Boot](#4-Working-with-Spring-Boot)
   * [5. Learning about Spring Boot Features](#5-Learning-about-Spring-Boot-Features)
   * [6. Moving to Production](#6-Moving-to-Production)
   * [7. Advanced Topics](#7-Advanced-Topics)
* [II. Getting Started](#Part-II-Getting-started)
   * [8. Introducing Spring Boot](#8-Introducing-Spring-Boot)
   * [9. System Requirements](#9-System-Requirements)
     * [9.1. Servlet Containers](#91-Servlet-Containers)
   * [10. Installing Spring Boot](#10-Installing-Spring-Boot)
     * [10.1. Installation Instructions for the Java Developer](#101-Installation-Instructions-for-the-Java-Developer)
       * [10.1.1. Maven Installation](#1011-Maven-Installation)
       * [10.1.2. Gradle Installation](#1012-Gradle-Installation)
     * [10.2. Installing the Spring Boot CLI](#102-Installing-the-Spring-Boot-CLI）
       * [10.2.1. Manual Installation](#1021-Manua-Installation）
       * [10.2.2. Installation with SDKMAN!](#1022-Installation-with-SDKMAN!）
       * [10.2.3. OSX Homebrew Installation](#1023-OSX-Homebrew-Installation）
       * [10.2.4. MacPorts Installation](#1024-MacPorts-Installation）
       * [10.2.5. Command-line Completion](#1025-Command--line-Completion）
       * [10.2.6. Quick-start Spring CLI Example](#1026-Quick--start-Spring-CLI-Example)
     * [10.3. Upgrading from an Earlier Version of Spring Boot](#103-Upgrading-from-an-Earlier-Version-of-Spring-Boot)
    * [11. Developing Your First Spring Boot Application](#11-Developing-Your-First-Spring-Boot-Application)
      * [11.1. Creating the POM](#111-Creating-the-POM)
      * [11.2. Adding Classpath Dependencies](#112-Adding-Classpath-Dependencies)
      * [11.3. Writing the Code](#113-Writing-the-Code)
        * [11.3.1. The @RestController and @RequestMapping Annotations](#1131-The-@RestController-and-@RequestMapping-Annotations)
        * [11.3.2. The @EnableAutoConfiguration Annotation](#1132-The-@EnableAutoConfiguration-Annotation)
        * [11.3.3. The “main” Method](#1133-The-“main”-Method)
      * [11.4. Running the Example](#114-Running-the-Example)
      * [11.5. Creating an Executable Jar](#115-Creating-an-Executable-Jar)
    * [12. What to Read Next](#12-What-to-Read-Next)
* [III. Using Spring Boot](#Part-III-Using-Spring-Boot)
    * [13. Build Systems](#13-Build-Systems)
      * [13.1. Dependency Management](#131-Dependency-Management)
      * [13.2. Maven](#132-Maven)
        * [13.2.1. Inheriting the Starter Parent](#1321-Inheriting-the-Starter-Parent)
        * [13.2.2. Using Spring Boot without the Parent POM](#1322-Using-Spring-Boot-without-the-Parent-POM)
        * [13.2.3. Using the Spring Boot Maven Plugin](#1323-Using-the-Spring-Boot-Maven-Plugin)
      * [13.3. Gradle](#133-Gradle)
      * [13.4. Ant](#134-Ant)
      * [13.5. Starters](#135-Starters)
   * [14. Structuring Your Code](#14-Structuring-Your-Code)
      * [14.1. Using the “default” Package](#141-Using-the-“default”-Package)
      * [14.2. Locating the Main Application Class](#142-Locating-the-Main-Application-Class)
   * [15. Configuration Classes](#15-Configuration-Classes)
      * [15.1. Importing Additional Configuration Classes](#15.1. Importing Additional Configuration Classes)
      * [15.2. Importing XML Configuration](#15.2. Importing XML Configuration)
   * [16. Auto-configuration](#16. Auto-configuration)
      * [16.1. Gradually Replacing Auto-configuration](#16.1. Gradually Replacing Auto-configuration)
      * [16.2. Disabling Specific Auto-configuration Classes](#16.2. Disabling Specific Auto-configuration Classes)
   * [17. Spring Beans and Dependency Injection](#17. Spring Beans and Dependency Injection)
   * [18. Using the @SpringBootApplication Annotation](#18. Using the @SpringBootApplication Annotation)
   * [19. Running Your Application](#19. Running Your Application)
      * [19.1. Running from an IDE](#19.1. Running from an IDE)
      * [19.2. Running as a Packaged Application](#19.2. Running as a Packaged Application)
      * [19.3. Using the Maven Plugin](#19.3. Using the Maven Plugin)
      * [19.4. Using the Gradle Plugin](#19.4. Using the Gradle Plugin)
      * [19.5. Hot Swapping](#19.5. Hot Swapping)
   * [20. Developer Tools](#20-Developer-Tools)
      * [20.1. Property Defaults](#20.1. Property Defaults)
      * [20.2. Automatic Restart](#20.2. Automatic Restart)
        * [20.2.1. Logging changes in condition evaluation](#20.2.1. Logging changes in condition evaluation)
        * [20.2.2. Excluding Resources](#20.2.2. Excluding Resources)
        * [20.2.3. Watching Additional Paths](#20.2.3. Watching Additional Paths)
        * [20.2.4. Disabling Restart](#20.2.4. Disabling Restart)
        * [20.2.5. Using a Trigger File](#20.2.5. Using a Trigger File)
        * [20.2.6. Customizing the Restart Classloader](#20.2.6. Customizing the Restart Classloader)
        * [20.2.7. Known Limitations](#20.2.7. Known Limitations)
      * [20.3. LiveReload](#20.3. LiveReload)
      * [20.4. Global Settings](20.4. Global Settings)
      * [20.5. Remote Applications](#20.5. Remote Application)
        * [20.5.1. Running the Remote Client Application](#20.5.1. Running the Remote Client Application)
        * [20.5.2. Remote Update](#20.5.2. Remote Update)
   * [21. Packaging Your Application for Production](#21. Packaging Your Application for Production)
   * [22. What to Read Next](#22. What to Read Next)
* [IV. Spring Boot features](#Part IV. Spring Boot features)
   * [23. SpringApplication](#23. SpringApplication)
     * [23.1. Startup Failure](#23.1. Startup Failure)
     * [23.2. Customizing the Banner](#23.2. Customizing the Banner)
     * [23.3. Customizing SpringApplication](#23.3. Customizing SpringApplication)
     * [23.4. Fluent Builder API](#23.4. Fluent Builder API)
     * [23.5. Application Events and Listeners](#23.5. Application Events and Listeners)
     * [23.6. Web Environment](#23.6. Web Environment)
     * [23.7. Accessing Application Arguments](#23.7. Accessing Application Arguments)
     * [23.8. Using the ApplicationRunner or CommandLineRunner](#23.8. Using the ApplicationRunner or CommandLineRunner)
     * [23.9. Application Exit](#23.9. Application Exit)
     * [23.10. Admin Features](#23.10. Admin Features)
   * [24. Externalized Configuration](#24. Externalized Configuration)
     * [24.1. Configuring Random Values](#24.1. Configuring Random Values)
     * [24.2. Accessing Command Line Properties](#24.2. Accessing Command Line Properties)
     * [24.3. Application Property Files](#24.3. Application Property Files)
     * [24.4. Profile-specific Properties](#24.4. Profile-specific Properties)
     * [24.5. Placeholders in Properties](#24.5. Placeholders in Properties)
     * [24.6. Using YAML Instead of Properties](#24.6. Using YAML Instead of Properties)
       * [24.6.1. Loading YAML](#24.6.1. Loading YAML)
       * [24.6.2. Exposing YAML as Properties in the Spring Environment](#24.6.2. Exposing YAML as Properties in the Spring Environment)
       * [24.6.3. Multi-profile YAML Documents](#24.6.3. Multi-profile YAML Documents)
       * [24.6.4. YAML Shortcomings](#24.6.4. YAML Shortcomings)
       * [24.6.5. Merging YAML Lists](#24.6.5. Merging YAML Lists)
     * [24.7. Type-safe Configuration Properties](#24.7. Type-safe Configuration Properties)
       * [24.7.1. Third-party Configuration](#24.7.1. Third-party Configuration)
       * [24.7.2. Relaxed Binding](#24.7.2. Relaxed Binding)
       * [24.7.3. Properties Conversion](#24.7.3. Properties Conversion)
         * [Converting durations](#Converting durations)
       * [24.7.4. @ConfigurationProperties Validation](#24.7.4. @ConfigurationProperties Validation)
       * [24.7.5. @ConfigurationProperties vs. @Value](#24.7.5. @ConfigurationProperties vs. @Value)
   * [25. Profiles](#25. Profiles)
     * [25.1. Adding Active Profiles](#25.1. Adding Active Profiles)
     * [25.2. Programmatically Setting Profiles](#25.2. Programmatically Setting Profiles)
     * [25.3. Profile-specific Configuration Files](#25.3. Profile-specific Configuration Files)
   * [26. Logging](#26. Logging)
     * [26.1. Log Format](#26.1. Log Format)
     * [26.2. Console Output](#26.2. Console Output)
       * [26.2.1. Color-coded Output](#26.2.1. Color-coded Output)
     * [26.3. File Output](#26.3. File Output)
     * [26.4. Log Levels](#26.4. Log Levels)
     * [26.5. Custom Log Configuration](#26.5. Custom Log Configuration)
     * [26.6. Logback Extensions](#26.6. Logback Extensions)
       * [26.6.1. Profile-specific Configuration](#26.6.1. Profile-specific Configuration)
       * [26.6.2. Environment Properties](#26.6.2. Environment Properties)
   * [27. Developing Web Applications](#27. Developing Web Applications)
     * [27.1. The “Spring Web MVC Framework”](#27.1. The “Spring Web MVC Framework”)
       * [27.1.1. Spring MVC Auto-configuration](#27.1.1. Spring MVC Auto-configuration)
       * [27.1.2. HttpMessageConverters](#27.1.2. HttpMessageConverters)
       * [27.1.3. Custom JSON Serializers and Deserializers](#27.1.3. Custom JSON Serializers and Deserializers)
       * [27.1.4. MessageCodesResolver](#27.1.4. MessageCodesResolver)
       * [27.1.5. Static Content](#27.1.5. Static Content)
       * [27.1.6. Welcome Page](#27.1.6. Welcome Page)
       * [27.1.7. Custom Favicon](#27.1.7. Custom Favicon)
       * [27.1.8. Path Matching and Content Negotiation]
       * [27.1.9. ConfigurableWebBindingInitializer](#27.1.9. ConfigurableWebBindingInitializer)
       * [27.1.10. Template Engines
       * [27.1.11. Error Handling
         * [Custom Error Pages](#Custom Error Pages)
         * [Mapping Error Pages outside of Spring MVC](#Mapping Error Pages outside of Spring MVC)
       * [27.1.12. Spring HATEOAS](#27.1.12. Spring HATEOAS)
       * [27.1.13. CORS Support](#27.1.13. CORS Support)
     * [27.2. The “Spring WebFlux Framework”](#27.2. The “Spring WebFlux Framework”)
       * [27.2.1. Spring WebFlux Auto-configuration](#27.2.1. Spring WebFlux Auto-configuration)
       * [27.2.2. HTTP Codecs with HttpMessageReaders and HttpMessageWriters](#27.2.2. HTTP Codecs with HttpMessageReaders and HttpMessageWriters)
       * [27.2.3. Static Content](#27.2.3. Static Content)
       * [27.2.4. Template Engines](#27.2.4. Template Engines)
       * [27.2.5. Error Handling](#27.2.5. Error Handling)
         * [Custom Error Pages](#Custom Error Pages)
       * [27.2.6. Web Filters](#27.2.6. Web Filters)
     * [27.3. JAX-RS and Jersey](#27.3. JAX-RS and Jersey)
     * [27.4. Embedded Servlet Container Support](#27.4. Embedded Servlet Container Support)
       * [27.4.1. Servlets, Filters, and listeners](#27.4.1. Servlets, Filters, and listeners)
         * [Registering Servlets, Filters, and Listeners as Spring Beans](#Registering Servlets, Filters, and Listeners as Spring Beans)
       * [27.4.2. Servlet Context Initialization](#27.4.2. Servlet Context Initialization)
         * [Scanning for Servlets, Filters, and listeners](#Scanning for Servlets, Filters, and listeners)
       * [27.4.3. The ServletWebServerApplicationContext](#27.4.3. The ServletWebServerApplicationContext)
       * [27.4.4. Customizing Embedded Servlet Containers](#27.4.4. Customizing Embedded Servlet Containers)
         * [Programmatic Customization](#Programmatic Customization)
         * [Customizing ConfigurableServletWebServerFactory Directly](#Customizing ConfigurableServletWebServerFactory Directly)
       * [27.4.5. JSP Limitations](#27.4.5. JSP Limitations)
   * [28. Security](#28. Security)
     * [28.1. MVC Security](#28.1. MVC Security)
     * [28.2. WebFlux Security](#28.2. WebFlux Security)
     * [28.3. OAuth2](#28.3. OAuth2)
       * [28.3.1. Client](#28.3.1. Client)
     * [28.4. Actuator Security](#28.4. Actuator Security)
       * [28.4.1. Cross Site Request Forgery Protection](#28.4.1. Cross Site Request Forgery Protection)
   * [29. Working with SQL Databases](#29. Working with SQL Databases)
     * [29.1. Configure a DataSource](#29.1. Configure a DataSource)
       * [29.1.1. Embedded Database Support](#29.1.1. Embedded Database Support)
       * [29.1.2. Connection to a Production Database](#29.1.2. Connection to a Production Database)
       * [29.1.3. Connection to a JNDI DataSource](#29.1.3. Connection to a JNDI DataSource)
     * [29.2. Using JdbcTemplate](#29.2. Using JdbcTemplate)
     * [29.3. JPA and “Spring Data”](#29.3. JPA and “Spring Data”)
       * [29.3.1. Entity Classes](#29.3.1. Entity Classes)
       * [29.3.2. Spring Data JPA Repositories](#29.3.2. Spring Data JPA Repositories)
       * [29.3.3. Creating and Dropping JPA Databases](#29.3.3. Creating and Dropping JPA Databases)
       * [29.3.4. Open EntityManager in View](#29.3.4. Open EntityManager in View)
     * [29.4. Using H2’s Web Console](#29.4. Using H2’s Web Console)
       * [29.4.1. Changing the H2 Console’s Path](#29.4.1. Changing the H2 Console’s Path)
     * [29.5. Using jOOQ](#29.5. Using jOOQ)
       * [29.5.1. Code Generation](#29.5.1. Code Generation)
       * [29.5.2. Using DSLContext](#29.5.2. Using DSLContext)
       * [29.5.3. jOOQ SQL Dialect](#29.5.3. jOOQ SQL Dialect)
       * [29.5.4. Customizing jOOQ](#29.5.4. Customizing jOOQ)
   * [30. Working with NoSQL Technologies](#30. Working with NoSQL Technologies)
     * [30.1. Redis](#30.1. Redis)
       * [30.1.1. Connecting to Redis](#30.1.1. Connecting to Redis)
     * [30.2. MongoDB](#30.2. MongoDB)
       * [30.2.1. Connecting to a MongoDB Database](#30.2.1. Connecting to a MongoDB Database)
       * [30.2.2. MongoTemplate](#30.2.2. MongoTemplate)
       * [30.2.3. Spring Data MongoDB Repositories](#30.2.3. Spring Data MongoDB Repositories)
       * [30.2.4. Embedded Mongo](#30.2.4. Embedded Mongo)
     * [30.3. Neo4j](#30.3. Neo4j)
       * [30.3.1. Connecting to a Neo4j Database](#30.3.1. Connecting to a Neo4j Database)
       * [30.3.2. Using the Embedded Mode](#30.3.2. Using the Embedded Mode)
       * [30.3.3. Neo4jSession](#30.3.3. Neo4jSession)
       * [30.3.4. Spring Data Neo4j Repositories](#30.3.4. Spring Data Neo4j Repositories)
       * [30.3.5. Repository Example](#30.3.5. Repository Example）
     * [30.4. Gemfire](#30.4. Gemfire)
     * [30.5. Solr](#30.5. Solr)
       * [30.5.1. Connecting to Solr](#30.5.1. Connecting to Solr)
       * [30.5.2. Spring Data Solr Repositories](#30.5.2. Spring Data Solr Repositories)
     * [30.6. Elasticsearch](#30.6. Elasticsearch)
       * [30.6.1. Connecting to Elasticsearch by Using Jest](#30.6.1. Connecting to Elasticsearch by Using Jest)
       * [30.6.2. Connecting to Elasticsearch by Using Spring Data](#30.6.2. Connecting to Elasticsearch by Using Spring Data)
       * [30.6.3. Spring Data Elasticsearch Repositories](#30.6.3. Spring Data Elasticsearch Repositories)
     * [30.7. Cassandra](#30.7. Cassandra)
       * [30.7.1. Connecting to Cassandra](#30.7.1. Connecting to Cassandra)
       * [30.7.2. Spring Data Cassandra Repositories](#30.7.2. Spring Data Cassandra Repositories)
     * [30.8. Couchbase](#30.8. Couchbase)
       * [30.8.1. Connecting to Couchbase](#30.8.1. Connecting to Couchbase)
       * [30.8.2. Spring Data Couchbase Repositories](#30.8.2. Spring Data Couchbase Repositories)
     * [30.9. LDAP](#30.9. LDAP)
       * [30.9.1. Connecting to an LDAP Server](#30.9.1. Connecting to an LDAP Server)
       * [30.9.2. Spring Data LDAP Repositories](#30.9.2. Spring Data LDAP Repositories)
       * [30.9.3. Embedded In-memory LDAP Server](#30.9.3. Embedded In-memory LDAP Server)
     * [30.10. InfluxDB](#30.10. InfluxDB)
       * [30.10.1. Connecting to InfluxDB](#30.10.1. Connecting to InfluxDB)
   * [31. Caching](#31. Caching)
     * [31.1. Supported Cache Providers](#31.1. Supported Cache Providers)
       * [31.1.1. Generic](#31.1.1. Generic)
       * [31.1.2. JCache (JSR-107)](#31.1.2. JCache (JSR-107))
       * [31.1.3. EhCache 2.x](#31.1.3. EhCache 2.x)
       * [31.1.4. Hazelcast](#31.1.4. Hazelcast)
       * [31.1.5. Infinispan](#31.1.5. Infinispan)
       * [31.1.6. Couchbase](#31.1.6. Couchbase)
       * [31.1.7. Redis](#31.1.7. Redis)
       * [31.1.8. Caffeine](#31.1.8. Caffeine)
       * [31.1.9. Simple](#31.1.9. Simple)
       * [31.1.10. None](#31.1.10. None)
   * [32. Messaging](#32. Messaging)
     * [32.1. JMS](#32.1. JMS)
       * [32.1.1. ActiveMQ Support](#32.1.1. ActiveMQ Support)
       * [32.1.2. Artemis Support](#32.1.2. Artemis Support)
       * [32.1.3. Using a JNDI ConnectionFactory](#32.1.3. Using a JNDI ConnectionFactory)
       * [32.1.4. Sending a Message](#32.1.4. Sending a Message)
       * [32.1.5. Receiving a Message](#32.1.5. Receiving a Message)
     * [32.2. AMQP](#32.2. AMQP)
       * [32.2.1. RabbitMQ support](#32.2.1. RabbitMQ support)
       * [32.2.2. Sending a Message](#32.2.2. Sending a Message)
       * [32.2.3. Receiving a Message](#32.2.3. Receiving a Message)
     * [32.3. Apache Kafka Support](#32.3. Apache Kafka Support)
       * [32.3.1. Sending a Message](#32.3.1. Sending a Message)
       * [32.3.2. Receiving a Message](#32.3.2. Receiving a Message)
       * [32.3.3. Additional Kafka Properties](#32.3.3. Additional Kafka Properties）
   * [33. Calling REST Services with RestTemplate](#33. Calling REST Services with RestTemplate）
     * [33.1. RestTemplate Customization](#33.1. RestTemplate Customization)
   * [34. Calling REST Services with WebClient](#34. Calling REST Services with WebClient)
     * [34.1. WebClient Customization](#34.1. WebClient Customization)
   * [35. Validation](#35. Validation)
   * [36. Sending Email](#36. Sending Email)
   * [37. Distributed Transactions with JTA](#37. Distributed Transactions with JTA)
     * [37.1. Using an Atomikos Transaction Manager](#37.1. Using an Atomikos Transaction Manager)
     * [37.2. Using a Bitronix Transaction Manager](#37.2. Using a Bitronix Transaction Manage)
     * [37.3. Using a Narayana Transaction Manager](#37.3. Using a Narayana Transaction Manager)
     * [37.4. Using a Java EE Managed Transaction Manager](#37.4. Using a Java EE Managed Transaction Manager)
     * [37.5. Mixing XA and Non-XA JMS Connections](#37.5. Mixing XA and Non-XA JMS Connections)
     * [37.6. Supporting an Alternative Embedded Transaction Manager](#37.6. Supporting an Alternative Embedded Transaction Manager)
   * [38. Hazelcast](#38. Hazelcast)
   * [39. Quartz Scheduler](#39. Quartz Scheduler)
   * [40. Spring Integration](#40. Spring Integration)
   * [41. Spring Session](#41. Spring Session)
   * [42. Monitoring and Management over JMX](#42. Monitoring and Management over JMX)
   * [43. Testing](#43. Testing)
     * [43.1. Test Scope Dependencies](#43.1. Test Scope Dependencies)
     * [43.2. Testing Spring Applications](#43.2. Testing Spring Applications)
     * [43.3. Testing Spring Boot Applications](#43.3. Testing Spring Boot Applications)
       * [43.3.1. Detecting Web Application Type](#43.3.1. Detecting Web Application Type)
       * [43.3.2. Detecting Test Configuration](#43.3.2. Detecting Test Configuration)
       * [43.3.3. Excluding Test Configuration](#43.3.3. Excluding Test Configuration)
       * [43.3.4. Testing with a running server](#43.3.4. Testing with a running server)
       * [43.3.5. Mocking and Spying Beans](#43.3.5. Mocking and Spying Beans)
       * [43.3.6. Auto-configured Tests](#43.3.6. Auto-configured Tests)
       * [43.3.7. Auto-configured JSON Tests](#43.3.7. Auto-configured JSON Tests)
       * [43.3.8. Auto-configured Spring MVC Tests](#43.3.8. Auto-configured Spring MVC Tests)
       * [43.3.9. Auto-configured Spring WebFlux Tests](#43.3.9. Auto-configured Spring WebFlux Tests)
       * [43.3.10. Auto-configured Data JPA Tests](#43.3.10. Auto-configured Data JPA Tests)
       * [43.3.11. Auto-configured JDBC Tests](#43.3.11. Auto-configured JDBC Tests)
       * [43.3.12. Auto-configured jOOQ Tests](#43.3.12. Auto-configured jOOQ Tests)
       * [43.3.13. Auto-configured Data MongoDB Tests](#43.3.13. Auto-configured Data MongoDB Tests)
       * [43.3.14. Auto-configured Data Neo4j Tests](#43.3.14. Auto-configured Data Neo4j Tests)
       * [43.3.15. Auto-configured Data Redis Tests](#43.3.15. Auto-configured Data Redis Tests)
       * [43.3.16. Auto-configured Data LDAP Tests](#43.3.16. Auto-configured Data LDAP Tests)
       * [43.3.17. Auto-configured REST Clients](#43.3.17. Auto-configured REST Clients)
       * [43.3.18. Auto-configured Spring REST Docs Tests](#43.3.18. Auto-configured Spring REST Docs Tests)
         * [Auto-configured Spring REST Docs Tests with Mock MVC](#Auto-configured Spring REST Docs Tests with Mock MVC)
         * [Auto-configured Spring REST Docs Tests with REST Assured](#Auto-configured Spring REST Docs Tests with REST Assured)
       * [43.3.19. User Configuration and Slicing](#43.3.19. User Configuration and Slicing)
       * [43.3.20. Using Spock to Test Spring Boot Applications](#43.3.20. Using Spock to Test Spring Boot Applications)
     * [43.4. Test Utilities](#43.4. Test Utilities)
       * [43.4.1. ConfigFileApplicationContextInitializer](#43.4.1. ConfigFileApplicationContextInitializer)
       * [43.4.2. EnvironmentTestUtils](#43.4.2. EnvironmentTestUtils)
       * [43.4.3. OutputCapture](#43.4.3. OutputCapture)
       * [43.4.4. TestRestTemplate](#43.4.4. TestRestTemplate)
   * [44. WebSockets](#44. WebSockets)
   * [45. Web Services](#45. Web Services)
   * [46. Creating Your Own Auto-configuration](#46. Creating Your Own Auto-configuration)
     * [46.1. Understanding Auto-configured Beans](#46.1. Understanding Auto-configured Beans)
     * [46.2. Locating Auto-configuration Candidates](#46.2. Locating Auto-configuration Candidates)
     * [46.3. Condition Annotations](#46.3. Condition Annotations)
       * [46.3.1. Class Conditions](#46.3.1. Class Conditions)
       * [46.3.2. Bean Conditions](#46.3.2. Bean Conditions)
       * [46.3.3. Property Conditions](#46.3.3. Property Conditions)
       * [46.3.4. Resource Conditions](#46.3.4. Resource Conditions)
       * [46.3.5. Web Application Conditions](#46.3.5. Web Application Conditions)
       * [46.3.6. SpEL Expression Conditions](#46.3.6. SpEL Expression Conditions)
     * [46.4. Testing your Auto-configuration](#46.4. Testing your Auto-configuration)
       * [46.4.1. Simulating a Web Context](#46.4.1. Simulating a Web Context)
       * [46.4.2. Overriding the Classpath](#46.4.2. Overriding the Classpath)
     * [46.5. Creating Your Own Starter](#46.5. Creating Your Own Starter)
       * [46.5.1. Naming](#46.5.1. Naming)
       * [46.5.2. autoconfigure Module](#46.5.2. autoconfigure Module)
       * [46.5.3. Starter Module](#46.5.3. Starter Module)
   * [47. Kotlin support](#47. Kotlin support)
     * [47.1. Requirements](#47.1. Requirements)
     * [47.2. Null-safety](#47.2. Null-safety)
     * [47.3. Kotlin API](#47.3. Kotlin API)
       * [47.3.1. runApplication](#47.3.1. runApplication)
       * [47.3.2. Extensions](#47.3.2. Extensions)
     * [47.4. Dependency management](#47.4. Dependency management)
     * [47.5. @ConfigurationProperties](#47.5. @ConfigurationProperties)
     * [47.6. Testing](#47.6. Testing)
     * [47.7. Resources](#47.7. Resources)
       * [47.7.1. Further reading](#47.7.1. Further reading)
       * [47.7.2. Examples](#47.7.2. Examples)
   * [48. What to Read Next](#48. What to Read Next)
* [V. Spring Boot Actuator: Production-ready features](#Part V. Spring Boot Actuator: Production-ready features)
   * [49. Enabling Production-ready Features](#49. Enabling Production-ready Features)
   * [50. Endpoints](#50. Endpoints)
     * [50.1. Enabling Endpoints](#50.1. Enabling Endpoints)
     * [50.2. Exposing Endpoints](#50.2. Exposing Endpoints)
     * [50.3. Securing HTTP Endpoints](#50.3. Securing HTTP Endpoints)
     * [50.4. Configuring Endpoints](#50.4. Configuring Endpoints)
     * [50.5. Hypermedia for Actuator Web Endpoints](#50.5. Hypermedia for Actuator Web Endpoints)
     * [50.6. Actuator Web Endpoint Paths](#50.6. Actuator Web Endpoint Paths)
     * [50.7. CORS Support](#50.7. CORS Support)
     * [50.8. Implementing Custom Endpoints](#50.8. Implementing Custom Endpoints)
       * [50.8.1. Receiving Input](#50.8.1. Receiving Input)
         * [Input type conversion](#Input type conversion)
       * [50.8.2. Custom Web Endpoints](#50.8.2. Custom Web Endpoints)
         * [Web Endpoint Request Predicates](#Web Endpoint Request Predicates)
         * [Path](#Path)
         * [HTTP method](#HTTP method)
         * [Consumes](#Consumes)
         * [Produces](#Produces)
         * [Web Endpoint Response Status](#Web Endpoint Response Status)
         * [Web Endpoint Range Requests](#Web Endpoint Range Requests)
         * [Web Endpoint Security](#Web Endpoint Security)
       * [50.8.3. Servlet endpoints](#50.8.3. Servlet endpoints)
       * [50.8.4. Controller endpoints](#50.8.4. Controller endpoints)
     * [50.9. Health Information](#50.9. Health Information)
       * [50.9.1. Auto-configured HealthIndicators](#50.9.1. Auto-configured HealthIndicators)
       * [50.9.2. Writing Custom HealthIndicators](#50.9.2. Writing Custom HealthIndicators)
       * [50.9.3. Reactive Health Indicators](#50.9.3. Reactive Health Indicators)
       * [50.9.4. Auto-configured ReactiveHealthIndicators](#50.9.4. Auto-configured ReactiveHealthIndicators)
     * [50.10. Application Information](#50.10. Application Information)
       * [50.10.1. Auto-configured InfoContributors](#50.10.1. Auto-configured InfoContributors)
       * [50.10.2. Custom Application Information](#50.10.2. Custom Application Information)
       * [50.10.3. Git Commit Information](#50.10.3. Git Commit Information)
       * [50.10.4. Build Information](#50.10.4. Build Information)
       * [50.10.5. Writing Custom InfoContributors](#50.10.5. Writing Custom InfoContributors)
   * [51. Monitoring and Management over HTTP](#51. Monitoring and Management over HTTP)
     * [51.1. Customizing the Management Endpoint Paths](#51.1. Customizing the Management Endpoint Paths)
     * [51.2. Customizing the Management Server Port](#51.2. Customizing the Management Server Port)
     * [51.3. Configuring Management-specific SSL](#51.3. Configuring Management-specific SSL)
     * [51.4. Customizing the Management Server Address](#51.4. Customizing the Management Server Address)
     * [51.5. Disabling HTTP Endpoints](#51.5. Disabling HTTP Endpoints)
   * [52. Monitoring and Management over JMX](#52. Monitoring and Management over JMX)
     * [52.1. Customizing MBean Names](#52.1. Customizing MBean Names)
     * [52.2. Disabling JMX Endpoints](#52.2. Disabling JMX Endpoints)
     * [52.3. Using Jolokia for JMX over HTTP](#52.3. Using Jolokia for JMX over HTTP)
       * [52.3.1. Customizing Jolokia](#52.3.1. Customizing Jolokia)
       * [52.3.2. Disabling Jolokia](#52.3.2. Disabling Jolokia)
   * [53. Loggers](#53. Loggers)
     * [53.1. Configure a Logger](#53.1. Configure a Logger)
   * [54. Metrics](#54. Metrics)
     * [54.1. Getting started](#54.1. Getting started)
     * [54.2. Supported monitoring systems](#54.2. Supported monitoring systems)
       * [54.2.1. Atlas](#54.2.1. Atlas)
       * [54.2.2. Datadog](#54.2.2. Datadog)
       * [54.2.3. Ganglia](#54.2.3. Ganglia)
       * [54.2.4. Graphite](#54.2.4. Graphite)
       * [54.2.5. Influx](#54.2.5. Influx)
       * [54.2.6. JMX](#54.2.6. JMX)
       * [54.2.7. New Relic](#54.2.7. New Relic)
       * [54.2.8. Prometheus](#54.2.8. Prometheus)
       * [54.2.9. SignalFx](#54.2.9. SignalFx)
       * [54.2.10. Simple](#54.2.10. Simple)
       * [54.2.11. StatsD](#54.2.11. StatsD)
       * [54.2.12. Wavefront](#54.2.12. Wavefront)
     * [54.3. Supported Metrics](#54.3. Supported Metrics)
       * [54.3.1. Spring MVC Metrics](#54.3.1. Spring MVC Metrics)
       * [54.3.2. Spring WebFlux Metrics](#54.3.2. Spring WebFlux Metrics)
       * [54.3.3. RestTemplate Metrics](#54.3.3. RestTemplate Metrics)
       * [54.3.4. Spring Integration metrics](#54.3.4. Spring Integration metrics)
       * [54.3.5. Cache Metrics](#54.3.5. Cache Metrics)
       * [54.3.6. DataSource Metrics](#54.3.6. DataSource Metrics)
       * [54.3.7. RabbitMQ Metrics](#54.3.7. RabbitMQ Metrics)
     * [54.4. Registering custom metrics](#54.4. Registering custom metrics)
     * [54.5. Customizing individual metrics](#54.5. Customizing individual metrics)
       * [54.5.1. Per-meter properties](#54.5.1. Per-meter properties)
     * [54.6. Metrics endpoint](#54.6. Metrics endpoint)
   * [55. Auditing](#55. Auditing)
   * [56. HTTP Tracing](#56. HTTP Tracing)
     * [56.1. Custom HTTP tracing](#56.1. Custom HTTP tracing)
   * [57. Process Monitoring](#57. Process Monitoring)
     * [57.1. Extending Configuration](#57.1. Extending Configuration)
     * [57.2. Programmatically](#57.2. Programmatically)
   * [58. Cloud Foundry Support](#58. Cloud Foundry Support)
     * [58.1. Disabling Extended Cloud Foundry Actuator Support](#58.1. Disabling Extended Cloud Foundry Actuator Support)
     * [58.2. Cloud Foundry Self-signed Certificates](#58.2. Cloud Foundry Self-signed Certificates)
     * [58.3. Custom context path](#58.3. Custom context path)
   * [59. What to Read Next](#59. What to Read Next)
* [VI. Deploying Spring Boot Applications](#Part VI. Deploying Spring Boot Applications)
   * [60. Deploying to the Cloud](#60. Deploying to the Cloud)
     * [60.1. Cloud Foundry](#60.1. Cloud Foundry)
       * [60.1.1. Binding to Services](#60.1.1. Binding to Services)
     * [60.2. Heroku](#60.2. Heroku)
     * [60.3. OpenShift](#60.3. OpenShift)
     * [60.4. Amazon Web Services (AWS)](#60.4. Amazon Web Services (AWS))
       * [60.4.1. AWS Elastic Beanstalk](#60.4.1. AWS Elastic Beanstalk)
         * [Using the Tomcat Platform](#Using the Tomcat Platform)
         * [Using the Java SE Platform](#Using the Java SE Platform)
       * [60.4.2. Summary](#60.4.2. Summary)
     * [60.5. Boxfuse and Amazon Web Services](#60.5. Boxfuse and Amazon Web Services)
     * [60.6. Google Cloud](#60.6. Google Cloud)
   * [61. Installing Spring Boot Applications](#61. Installing Spring Boot Applications)
     * [61.1. Supported Operating Systems](#61.1. Supported Operating Systems)
     * [61.2. Unix/Linux Services](#61.2. Unix/Linux Services)
       * [61.2.1. Installation as an init.d Service (System V)](#61.2.1. Installation as an init.d Service (System V))
         * [Securing an init.d Service](#Securing an init.d Service)
       * [61.2.2. Installation as a systemd Service](#61.2.2. Installation as a systemd Service)
       * [61.2.3. Customizing the Startup Script](#61.2.3. Customizing the Startup Script)
         * [Customizing the Start Script when It Is Written](#Customizing the Start Script when It Is Written)
         * [Customizing a Script When It Runs](#Customizing a Script When It Runs)
     * [61.3. Microsoft Windows Services](#61.3. Microsoft Windows Services)
   * [62. What to Read Next](#62. What to Read Next)
* [VII. Spring Boot CLI](#Part VII. Spring Boot CLI)
   * [63. Installing the CLI](#63. Installing the CLI)
   * [64. Using the CLI](#64. Using the CLI)
     * [64.1. Running Applications with the CLI](#64.1. Running Applications with the CLI)
       * [64.1.1. Deduced “grab” Dependencies](#64.1.1. Deduced “grab” Dependencies)
       * [64.1.2. Deduced “grab” Coordinates](#64.1.2. Deduced “grab” Coordinates)
       * [64.1.3. Default Import Statements](#64.1.3. Default Import Statements)
       * [64.1.4. Automatic Main Method](#64.1.4. Automatic Main Method)
       * [64.1.5. Custom Dependency Management](#64.1.5. Custom Dependency Management)
     * [64.2. Applications with Multiple Source Files](#64.2. Applications with Multiple Source Files)
     * [64.3. Packaging Your Application](#64.3. Packaging Your Application)
     * [64.4. Initialize a New Project](#64.4. Initialize a New Project)
     * [64.5. Using the Embedded Shell](#64.5. Using the Embedded Shell)
     * [64.6. Adding Extensions to the CLI](#64.6. Adding Extensions to the CLI)
   * [65. Developing Applications with the Groovy Beans DSL](#65. Developing Applications with the Groovy Beans DSL)
   * [66. Configuring the CLI with settings.xml](#66. Configuring the CLI with settings.xml)
   * [67. What to Read Next](#67. What to Read Next)
* [VIII. Build tool plugins](#Part VIII. Build tool plugins)
   * [68. Spring Boot Maven Plugin](#68. Spring Boot Maven Plugin)
     * [68.1. Including the Plugin](#68.1. Including the Plugin)
     * [68.2. Packaging Executable Jar and War Files](#68.2. Packaging Executable Jar and War Files)
   * [69. Spring Boot Gradle Plugin](#69. Spring Boot Gradle Plugin)
   * [70. Spring Boot AntLib Module](#70. Spring Boot AntLib Module)
     * [70.1. Spring Boot Ant Tasks](#70.1. Spring Boot Ant Tasks)
       * [70.1.1. spring-boot:exejar](#70.1.1. spring-boot:exejar)
       * [70.1.2. Examples](#70.1.2. Examples)
     * [70.2. spring-boot:findmainclass](#70.2. spring-boot:findmainclass)
       * [70.2.1. Examples](#70.2.1. Examples)
   * [71. Supporting Other Build Systems](#71. Supporting Other Build Systems)
     * [71.1. Repackaging Archives](#71.1. Repackaging Archives)
     * [71.2. Nested Libraries](#71.2. Nested Libraries)
     * [71.3. Finding a Main Class](#71.3. Finding a Main Class)
     * [71.4. Example Repackage Implementation](#71.4. Example Repackage Implementation)
   * [72. What to Read Next](#72. What to Read Next)
* [IX. ‘How-to’ guides](#Part-IX-How-to-guides)
   * [73. Spring Boot Application](#73. Spring Boot Application)
     * [73.1. Create Your Own FailureAnalyzer](#73.1. Create Your Own FailureAnalyzer)
     * [73.2. Troubleshoot Auto-configuration](#73.2. Troubleshoot Auto-configuration)
     * [73.3. Customize the Environment or ApplicationContext Before It Starts](#73.3. Customize the Environment or ApplicationContext Before It Starts)
     * [73.4. Build an ApplicationContext Hierarchy (Adding a Parent or Root Context)](#73.4. Build an ApplicationContext Hierarchy (Adding a Parent or Root Context))
     * [73.5. Create a Non-web Application](#73.5. Create a Non-web Application)
   * [74. Properties and Configuration](#74. Properties and Configuration)
     * [74.1. Automatically Expand Properties at Build Time](#74.1. Automatically Expand Properties at Build Time)
       * [74.1.1. Automatic Property Expansion Using Maven](#74.1.1. Automatic Property Expansion Using Maven)
       * [74.1.2. Automatic Property Expansion Using Gradle](#74.1.2. Automatic Property Expansion Using Gradle)
     * [74.2. Externalize the Configuration of SpringApplication](#74.2. Externalize the Configuration of SpringApplication)
     * [74.3. Change the Location of External Properties of an Application](#74.3. Change the Location of External Properties of an Application)
     * [74.4. Use ‘Short’ Command Line Arguments](#74.4. Use ‘Short’ Command Line Arguments)
     * [74.5. Use YAML for External Properties](#74.5. Use YAML for External Properties)
     * [74.6. Set the Active Spring Profiles](#74.6. Set the Active Spring Profiles)
     * [74.7. Change Configuration Depending on the Environment](#74.7. Change Configuration Depending on the Environment)
     * [74.8. Discover Built-in Options for External Properties](#74.8. Discover Built-in Options for External Properties)
   * [75. Embedded Web Servers](#75. Embedded Web Servers)
     * [75.1. Use Another Web Server](#75.1. Use Another Web Server)
     * [75.2. Configure Jetty](#75.2. Configure Jetty)
     * [75.3. Add a Servlet, Filter, or Listener to an Application](#75.3. Add a Servlet, Filter, or Listener to an Application)
       * [75.3.1. Add a Servlet, Filter, or Listener by Using a Spring Bean](#75.3.1. Add a Servlet, Filter, or Listener by Using a Spring Bean)
         * [Disable Registration of a Servlet or Filter](#Disable Registration of a Servlet or Filter)
       * [75.3.2. Add Servlets, Filters, and Listeners by Using Classpath Scanning](#75.3.2. Add Servlets, Filters, and Listeners by Using Classpath Scanning)
     * [75.4. Change the HTTP Port](#75.4. Change the HTTP Port)
     * [75.5. Use a Random Unassigned HTTP Port](#75.5. Use a Random Unassigned HTTP Port)
     * [75.6. Discover the HTTP Port at Runtime](#75.6. Discover the HTTP Port at Runtime)
     * [75.7. Configure SSL](#75.7. Configure SSL)
     * [75.8. Configure HTTP/2](#75.8. Configure HTTP/2)
       * [75.8.1. HTTP/2 with Undertow](#75.8.1. HTTP/2 with Undertow)
       * [75.8.2. HTTP/2 with Jetty](#75.8.2. HTTP/2 with Jetty)
       * [75.8.3. HTTP/2 with Tomcat](#75.8.3. HTTP/2 with Tomcat)
     * [75.9. Configure Access Logging](#75.9. Configure Access Logging)
     * [75.10. Running Behind a Front-end Proxy Server](#75.10. Running Behind a Front-end Proxy Server)
       * [75.10.1. Customize Tomcat’s Proxy Configuration](#75.10.1. Customize Tomcat’s Proxy Configuration)
     * [75.11. Configure Tomcat](#75.11. Configure Tomcat)
     * [75.12. Enable Multiple Connectors with Tomcat](#75.12. Enable Multiple Connectors with Tomcat)
     * [75.13. Use Tomcat’s LegacyCookieProcessor](#75.13. Use Tomcat’s LegacyCookieProcessor)
     * [75.14. Configure Undertow](#75.14. Configure Undertow)
     * [75.15. Enable Multiple Listeners with Undertow](#75.15. Enable Multiple Listeners with Undertow)
     * [75.16. Create WebSocket Endpoints Using @ServerEndpoint](#75.16. Create WebSocket Endpoints Using @ServerEndpoint)
     * [75.17. Enable HTTP Response Compression](#75.17. Enable HTTP Response Compression)
   * [76. Spring MVC](#76. Spring MVC)
     * [76.1. Write a JSON REST Service](#76.1. Write a JSON REST Service)
     * [76.2. Write an XML REST Service](#76.2. Write an XML REST Service)
     * [76.3  Customize the Jackson ObjectMapper](#76.3. Customize the Jackson ObjectMapper)
     * [76.4. Customize the @ResponseBody Rendering](#76.4. Customize the @ResponseBody Rendering)
     * [76.5. Handling Multipart File Uploads](#76.5. Handling Multipart File Uploads)
     * [76.6. Switch Off the Spring MVC DispatcherServlet](#76.6. Switch Off the Spring MVC DispatcherServlet)
     * [76.7. Switch off the Default MVC Configuration](#76.7. Switch off the Default MVC Configuration)
     * [76.8. Customize ViewResolvers](#76.8. Customize ViewResolvers)
   * [77. HTTP Clients](#77. HTTP Clients)
     * [77.1. Configure RestTemplate to Use a Proxy](#77.1. Configure RestTemplate to Use a Proxy)
   * [78. Logging](#78. Logging)
     * [78.1. Configure Logback for Logging](#78.1. Configure Logback for Logging)
       * [78.1.1. Configure Logback for File-only Output](#78.1.1. Configure Logback for File-only Output)
     * [78.2. Configure Log4j for Logging](#78.2. Configure Log4j for Logging)
       * [78.2.1. Use YAML or JSON to Configure Log4j 2](#78.2.1. Use YAML or JSON to Configure Log4j 2)
   * [79. Data Access](#79. Data Access)
     * [79.1. Configure a Custom DataSource](#79.1. Configure a Custom DataSource)
     * [79.2. Configure Two DataSources](#79.2. Configure Two DataSources)
     * [79.3. Use Spring Data Repositories](#79.3. Use Spring Data Repositories)
     * [79.4. Separate @Entity Definitions from Spring Configuration](#79.4. Separate @Entity Definitions from Spring Configuration)
     * [79.5. Configure JPA Properties](#79.5. Configure JPA Properties)
     * [79.6. Configure Hibernate Naming Strategy](#79.6. Configure Hibernate Naming Strategy)
     * [79.7. Use a Custom EntityManagerFactory](#79.7. Use a Custom EntityManagerFactory)
     * [79.8. Use Two EntityManagers](#79.8. Use Two EntityManagers)
     * [79.9. Use a Traditional persistence.xml File](#79.9. Use a Traditional persistence.xml File)
     * [79.10. Use Spring Data JPA and Mongo Repositories](#79.10. Use Spring Data JPA and Mongo Repositories)
     * [79.11. Expose Spring Data Repositories as REST Endpoint](#79.11. Expose Spring Data Repositories as REST Endpoint)
     * [79.12. Configure a Component that is Used by JPA](#79.12. Configure a Component that is Used by JPA)
     * [79.13. Configure jOOQ with Two DataSources](#79.13. Configure jOOQ with Two DataSources)
   * [80. Database Initialization](#80. Database Initialization)
     * [80.1. Initialize a Database Using JPA](#80.1. Initialize a Database Using JPA)
     * [80.2. Initialize a Database Using Hibernate](#80.2. Initialize a Database Using Hibernate)
     * [80.3. Initialize a Database](#80.3. Initialize a Database)
     * [80.4. Initialize a Spring Batch Database](#80.4. Initialize a Spring Batch Database)
     * [80.5. Use a Higher-level Database Migration Tool](#80.5. Use a Higher-level Database Migration Tool)
       * [80.5.1. Execute Flyway Database Migrations on Startup](#80.5.1. Execute Flyway Database Migrations on Startup)
       * [80.5.2. Execute Liquibase Database Migrations on Startup](#80.5.2. Execute Liquibase Database Migrations on Startup)
   * [81. Messaging](#81. Messaging)
     * [81.1. Disable Transacted JMS Session](#81.1. Disable Transacted JMS Session)
   * [82. Batch Applications](#82. Batch Applications)
     * [82.1. Execute Spring Batch Jobs on Startup](#82.1. Execute Spring Batch Jobs on Startup)
   * [83. Actuator](#83. Actuator)
     * [83.1. Change the HTTP Port or Address of the Actuator Endpoints](#83.1. Change the HTTP Port or Address of the Actuator Endpoints)
     * [83.2. Customize the ‘whitelabel’ Error Page](#83.2. Customize the ‘whitelabel’ Error Page)
   * [84. Security](#84. Security)
     * [84.1. Switch off the Spring Boot Security Configuration](#84.1. Switch off the Spring Boot Security Configuration)
     * [84.2. Change the AuthenticationManager and Add User Accounts](#84.2. Change the AuthenticationManager and Add User Accounts)
     * [84.3. Enable HTTPS When Running behind a Proxy Server](#84.3. Enable HTTPS When Running behind a Proxy Server)
   * [85. Hot Swapping](#85. Hot Swapping)
     * [85.1. Reload Static Content](#85.1. Reload Static Content)
     * [85.2. Reload Templates without Restarting the Container](#85.2. Reload Templates without Restarting the Container)
       * [85.2.1. Thymeleaf Templates](#85.2.1. Thymeleaf Templates)
       * [85.2.2. FreeMarker Templates](#85.2.2. FreeMarker Templates)
       * [85.2.3. Groovy Templates](#85.2.3. Groovy Templates)
     * [85.3. Fast Application Restarts](#85.3. Fast Application Restarts)
     * [85.4. Reload Java Classes without Restarting the Container](#85.4. Reload Java Classes without Restarting the Container)
   * [86. Build](#86. Build)
     * [86.1. Generate Build Information](#86.1. Generate Build Information)
     * [86.2. Generate Git Information](#86.2. Generate Git Information)
     * [86.3. Customize Dependency Versions](#86.3. Customize Dependency Versions)
     * [86.4. Create an Executable JAR with Maven](#86.4. Create an Executable JAR with Maven)
     * [86.5. Use a Spring Boot Application as a Dependency](#86.5. Use a Spring Boot Application as a Dependency)
     * [86.6. Extract Specific Libraries When an Executable Jar Runs](#86.6. Extract Specific Libraries When an Executable Jar Runs)
     * [86.7. Create a Non-executable JAR with Exclusions](#86.7. Create a Non-executable JAR with Exclusions)
     * [86.8. Remote Debug a Spring Boot Application Started with Maven](#86.8. Remote Debug a Spring Boot Application Started with Maven)
     * [86.9. Build an Executable Archive from Ant without Using spring-boot-antlib](#86.9. Build an Executable Archive from Ant without Using spring-boot-antlib)
   * [87. Traditional Deployment](#87. Traditional Deployment)
     * [87.1. Create a Deployable War File](#87.1. Create a Deployable War File)
     * [87.2. Create a Deployable War File for Older Servlet Containers](#87.2. Create a Deployable War File for Older Servlet Containers)
     * [87.3. Convert an Existing Application to Spring Boot](#87.3. Convert an Existing Application to Spring Boot)
     * [87.4. Deploying a WAR to WebLogic](#87.4. Deploying a WAR to WebLogic)
     * [87.5. Deploying a WAR in an Old (Servlet 2.5) Container](#87.5. Deploying a WAR in an Old (Servlet 2.5) Container)
     * [87.6. Use Jedis Instead of Lettuce](#87.6. Use Jedis Instead of Lettuce)
* [X. Appendices](#Part X. Appendices)
   * [A. Common application properties](#A. Common application properties)
   * [B. Configuration Metadata](#B. Configuration Metadata)
     * [B.1. Metadata Format](#B.1. Metadata Format)
       * [B.1.1. Group Attributes](#B.1.1. Group Attributes)
       * [B.1.2. Property Attributes](#B.1.2. Property Attributes)
       * [B.1.3. Hint Attributes](#B.1.3. Hint Attributes)
       * [B.1.4. Repeated Metadata Items](#B.1.4. Repeated Metadata Items)
     * [B.2. Providing Manual Hints](#B.2. Providing Manual Hints)
       * [B.2.1. Value Hint](#B.2.1. Value Hint)
       * [B.2.2. Value Providers](#B.2.2. Value Providers)
         * [Any](#Any)
         * [Class Reference](#Class Reference)
         * [Handle As](#Handle As)
         * [Logger Name](#Logger Name)
         * [Spring Bean Reference](#Spring Bean Reference)
         * [Spring Profile Name](#Spring Profile Name)
     * [B.3. Generating Your Own Metadata by Using the Annotation Processor](#B.3. Generating Your Own Metadata by Using the Annotation Processor)
       * [B.3.1. Nested Properties](#B.3.1. Nested Properties)
       * [B.3.2. Adding Additional Metadata](#B.3.2. Adding Additional Metadata)
   * [C. Auto-configuration classes](#C. Auto-configuration classes)
     * [C.1. From the “spring-boot-autoconfigure” module](#C.1. From the “spring-boot-autoconfigure” module)
     * [C.2. From the “spring-boot-actuator-autoconfigure” module](#C.2. From the “spring-boot-actuator-autoconfigure” module)
   * [D. Test auto-configuration annotations](#D. Test auto-configuration annotations)
   * [E. The Executable Jar Format](#E. The Executable Jar Format)
     * [E.1. Nested JARs](#E.1. Nested JARs)
       * [E.1.1. The Executable Jar File Structure](#E.1.1. The Executable Jar File Structure)
       * [E.1.2. The Executable War File Structure](#E.1.2. The Executable War File Structure)
     * [E.2. Spring Boot’s “JarFile” Class](#E.2. Spring Boot’s “JarFile” Class)
       * [E.2.1. Compatibility with the Standard Java “JarFile”](#E.2.1. Compatibility with the Standard Java “JarFile”)
     * [E.3. Launching Executable Jars](#E.3. Launching Executable Jars)
       * [E.3.1. Launcher Manifest](#E.3.1. Launcher Manifest)
       * [E.3.2. Exploded Archives](#E.3.2. Exploded Archives)
     * [E.4. PropertiesLauncher Features](#E.4. PropertiesLauncher Features)
     * [E.5. Executable Jar Restrictions](#E.5. Executable Jar Restrictions)
     * [E.6. Alternative Single Jar Solutions](#E.6. Alternative Single Jar Solutions)
   * [F. Dependency versions](#F. Dependency versions)

## Part I Spring Boot Documentation

This section provides a brief overview of Spring Boot reference documentation. It serves as a map for the rest of the document.

### 1 About the Documentation
The Spring Boot reference guide is available as
* [HTML](https://docs.spring.io/spring-boot/docs/2.0.0.BUILD-SNAPSHOT/reference/html/)
* [PDF](https://docs.spring.io/spring-boot/docs/2.0.0.BUILD-SNAPSHOT/reference/pdf/spring-boot-reference.pdf)
* [EPUB](https://docs.spring.io/spring-boot/docs/2.0.0.BUILD-SNAPSHOT/reference/epub/spring-boot-reference.epub)

The latest copy is available at [docs.spring.io/spring-boot/docs/current/reference](docs.spring.io/spring-boot/docs/current/reference).

Copies of this document may be made for your own use and for distribution to others, provided that you do not charge any fee for such copies and further provided that each copy contains this Copyright Notice, whether distributed in print or electronically.

### 2 Getting Help
If you have trouble with Spring Boot, we would like to help.
* Try the [How-to documents](#Part-IX-How-to-guides). They provide solutions to the most common questions.
* Learn the Spring basics. Spring Boot builds on many other Spring projects. Check the spring.io web-site for a wealth of reference documentation. If you are starting out with Spring, try one of the [guides](https://spring.io/guides).
* Ask a question. We monitor [stackoverflow.com](https://stackoverflow.com) for questions tagged with [`spring-boot`](https://stackoverflow.com/tags/spring-boot).
* Report bugs with Spring Boot at [github.com/spring-projects/spring-boot/issues](github.com/spring-projects/spring-boot/issues).

> All of Spring Boot is open source, including the documentation. If you find problems with the docs or if you want to improve them, please [get involved](https://github.com/spring-projects/spring-boot/tree/master).

### 3 First Steps
If you are getting started with Spring Boot or 'Spring' in general, start with [the following topics](Part-II-Getting-Started):
* From scratch: [Overview]() | [Requirements]() | [Installation]()
* Tutorial: [Part 1]() | [Part 2]()
* Running your example: [Part 1]() | [Part 2]()

### 4 Working with Spring Boot
Ready to actually start using Spring Boot? [We have you covered](Part-III-Using-Spring-Boot):
* Build systems: [Maven]() | [Gradle]() | [Ant]() | [Starters]()
* Best practices: [Code Structure]() | [@Configuration]() | [@EnableAutoConfiguration]() | [Beans and Dependency Injection]()
* Running your code: [IDE]() | [Packaged]() | [Maven]() | [Gradle]()
* Packaging your app: [Production jars]()
* Spring Boot CLI: [Using the CLI]()

### 5 Learning about Spring Boot Features
Need more details about Spring Boot’s core features? [The following content is for you](Part-IV-Spring-Boot-features):
* Core Features: [SpringApplication]() | [External Configuration]() | [Profiles]() | [Logging]()
* Web Applications: [MVC]() | [Embedded Containers]()
* Working with data: [SQL]() | [NO-SQL]()
* Messaging: [Overview]() | [JMS]()
* Testing: [Overview]() | [Boot Applications]() | [Utils]()
* Extending: [Auto-configuration]() | [@Conditions]()

### 6 Moving to Production
When you are ready to push your Spring Boot application to production, we have [some tricks](Part-V-Spring-Boot-Actuator:-Production-ready-features) that you might like:
* Management endpoints: [Overview]() | [Customization]()
* Connection options: [HTTP]() | [JMX]()
* Monitoring: [Metrics]() | [Auditing]() | [Tracing]() | [Process]()

### 7 Advanced Topics
Finally, we have a few topics for more advanced users:
* Spring Boot Applications Deployment: [Cloud Deployment]() | [OS Service]()
* Build tool plugins: [Maven]() | [Gradle]()
* Appendix: [Application Properties]() | [Auto-configuration classes]() | [Executable Jars]()

## Part II Getting Started
If you are getting started with Spring Boot, or “Spring” in general, start by reading this section. It answers the basic “what?”, “how?” and “why?” questions. It includes an introduction to Spring Boot, along with installation instructions. We then walk you through building your first Spring Boot application, discussing some core principles as we go.

### 8 Introducing Spring Boot
Spring Boot makes it easy to create stand-alone, production-grade Spring-based Applications that you can run. We take an opinionated view of the Spring platform and third-party libraries, so that you can get started with minimum fuss. Most Spring Boot applications need very little Spring configuration.

You can use Spring Boot to create Java applications that can be started by using `java -jar` or more traditional war deployments. We also provide a command line tool that runs “spring scripts”.

Our primary goals are:

* Provide a radically faster and widely accessible getting-started experience for all Spring development.
* Be opinionated out of the box but get out of the way quickly as requirements start to diverge from the defaults.
* Provide a range of non-functional features that are common to large classes of projects (such as embedded servers, security, metrics, health checks, and externalized configuration).
* Absolutely no code generation and no requirement for XML configuration.

### 9 System Requirements
Spring Boot 2.0.0.BUILD-SNAPSHOT requires [Java 8 or 9](https://www.java.com/zh_CN/) and [Spring Framework 5.0.4.RELEASE](https://docs.spring.io/spring/docs/5.0.4.RELEASE/spring-framework-reference/) or above. Explicit build support is provided for Maven 3.2+ and Gradle 4.

#### 9.1 Servlet Containers
Spring Boot supports the following embedded servlet containers:

|      Name     | Servlet Version |
| ------------- | --------------- |
|   Tomcat 8.5  |       3.1       |
|   Jetty  9.4  |       3.1       |
|  Undertow 1.4 |       3.1       |

You can also deploy Spring Boot applications to any Servlet 3.0+ compatible container.

### 10 Installing Spring Boot
Spring Boot can be used with “classic” Java development tools or installed as a command line tool. Either way, you need [Java SDK v1.8](https://www.java.com/) or higher. Before you begin, you should check your current Java installation by using the following command:

```
$ java -version
```

If you are new to Java development or if you want to experiment with Spring Boot, you might want to try the [Spring Boot CLI](#10.2-Installing-the-Spring-Boot-CLI) (Command Line Interface) first. Otherwise, read on for “classic” installation instructions.

#### 10.1 Installation Instructions for the Java Developer
You can use Spring Boot in the same way as any standard Java library. To do so, include the appropriate `spring-boot-*.jar `files on your classpath. Spring Boot does not require any special tools integration, so you can use any IDE or text editor. Also, there is nothing special about a Spring Boot application, so you can run and debug a Spring Boot application as you would any other Java program.

Although you could copy Spring Boot jars, we generally recommend that you use a build tool that supports dependency management (such as Maven or Gradle).

##### 10.1.1 Maven Installation
Spring Boot is compatible with Apache Maven 3.2 or above. If you do not already have Maven installed, you can follow the instructions at [maven.apache.org](https://maven.apache.org/).

> On many operating systems, Maven can be installed with a package manager. If you use OSX Homebrew, try `brew install` maven.Ubuntu users can run `sudo apt-get install maven`. Windows users with [Chocolatey](https://chocolatey.org/) can run `choco install maven` from an elevated (administrator) prompt.

Spring Boot dependencies use the `org.springframework.boot` `groupId`. Typically, your Maven POM file inherits from the `spring-boot-starter-parent` project and declares dependencies to one or more “[Starters](13.5-Starters)”. Spring Boot also provides an optional [Maven plugin](68-Spring Boot Maven Plugin) to create executable jars.

The following listing shows a typical `pom.xml` file:

```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>

	<groupId>com.example</groupId>
	<artifactId>myproject</artifactId>
	<version>0.0.1-SNAPSHOT</version>

	<!-- Inherit defaults from Spring Boot -->
	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>2.0.0.BUILD-SNAPSHOT</version>
	</parent>

	<!-- Add typical dependencies for a web application -->
	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>
	</dependencies>

	<!-- Package as an executable jar -->
	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
		</plugins>
	</build>

	<!-- Add Spring repositories -->
	<!-- (you don't need this if you are using a .RELEASE version) -->
	<repositories>
		<repository>
			<id>spring-snapshots</id>
			<url>https://repo.spring.io/snapshot</url>
			<snapshots><enabled>true</enabled></snapshots>
		</repository>
		<repository>
			<id>spring-milestones</id>
			<url>https://repo.spring.io/milestone</url>
		</repository>
	</repositories>
	<pluginRepositories>
		<pluginRepository>
			<id>spring-snapshots</id>
			<url>https://repo.spring.io/snapshot</url>
		</pluginRepository>
		<pluginRepository>
			<id>spring-milestones</id>
			<url>https://repo.spring.io/milestone</url>
		</pluginRepository>
	</pluginRepositories>
</project>
```

> The `spring-boot-starter-parent` is a great way to use Spring Boot, but it might not be suitable all of the time. Sometimes you may need to inherit from a different parent POM, or you might not like our default settings. In those cases, see Section 13.2.2, “Using Spring Boot without the Parent POM” for an alternative solution that uses an `import` scope.

##### 10.1.2 Gradle Installation
Spring Boot is compatible with Gradle 4. If you do not already have Gradle installed, you can follow the instructions at [gradle.org](https://gradle.org).

Spring Boot dependencies can be declared by using the `org.springframework.boot` `group`. Typically, your project declares dependencies to one or more [“Starters”](#13.5-Starters). Spring Boot provides a useful [Gradle plugin](69-Spring-Boot-Gradle-Plugin) that can be used to simplify dependency declarations and to create executable jars.

> #### Gradle Wrapper

> The Gradle Wrapper provides a nice way of “obtaining” Gradle when you need to build a project. It is a small script and library that you commit alongside your code to bootstrap the build process. See [docs.gradle.org/4.2.1/userguide/gradle_wrapper.html](https://docs.gradle.org/4.2.1/userguide/gradle_wrapper.html) for details.

The following example shows a typical `build.gradle` file:

```
buildscript {
	repositories {
		jcenter()
		maven { url 'https://repo.spring.io/snapshot' }
		maven { url 'https://repo.spring.io/milestone' }
	}
	dependencies {
		classpath 'org.springframework.boot:spring-boot-gradle-plugin:2.0.0.BUILD-SNAPSHOT'
	}
}

apply plugin: 'java'
apply plugin: 'org.springframework.boot'
apply plugin: 'io.spring.dependency-management'

jar {
	baseName = 'myproject'
	version =  '0.0.1-SNAPSHOT'
}

repositories {
	jcenter()
	maven { url "https://repo.spring.io/snapshot" }
	maven { url "https://repo.spring.io/milestone" }
}

dependencies {
	compile("org.springframework.boot:spring-boot-starter-web")
	testCompile("org.springframework.boot:spring-boot-starter-test")
}
```
#### 10.2 Installing the Spring Boot CLI
The Spring Boot CLI (Command Line Interface) is a command line tool that you can use to quickly prototype with Spring. It lets you run Groovy scripts, which means that you have a familiar Java-like syntax without so much boilerplate code.

You do not need to use the CLI to work with Spring Boot, but it is definitely the quickest way to get a Spring application off the ground.

##### 10.2.1 Manual Installation
You can download the Spring CLI distribution from the Spring software repository:

spring-boot-cli-2.0.0.BUILD-SNAPSHOT-bin.zip
spring-boot-cli-2.0.0.BUILD-SNAPSHOT-bin.tar.gz
Cutting edge snapshot distributions are also available.

Once downloaded, follow the INSTALL.txt instructions from the unpacked archive. In summary, there is a spring script (spring.bat for Windows) in a bin/ directory in the .zip file. Alternatively, you can use java -jar with the .jar file (the script helps you to be sure that the classpath is set correctly).

##### 10.2.2 Installation with SDKMAN!
SDKMAN! (The Software Development Kit Manager) can be used for managing multiple versions of various binary SDKs, including Groovy and the Spring Boot CLI. Get SDKMAN! from sdkman.io and install Spring Boot by using the following commands:

$ sdk install springboot
$ spring --version
Spring Boot v2.0.0.BUILD-SNAPSHOT
If you develop features for the CLI and want easy access to the version you built, use the following commands:

$ sdk install springboot dev /path/to/spring-boot/spring-boot-cli/target/spring-boot-cli-2.0.0.BUILD-SNAPSHOT-bin/spring-2.0.0.BUILD-SNAPSHOT/
$ sdk default springboot dev
$ spring --version
Spring CLI v2.0.0.BUILD-SNAPSHOT
The preceding instructions install a local instance of spring called the dev instance. It points at your target build location, so every time you rebuild Spring Boot, spring is up-to-date.

You can see it by running the following command:

$ sdk ls springboot

================================================================================
Available Springboot Versions
================================================================================
> + dev
* 2.0.0.BUILD-SNAPSHOT

================================================================================
+ - local version
* - installed
> - currently in use
================================================================================
##### 10.2.3 OSX Homebrew Installation
If you are on a Mac and use Homebrew, you can install the Spring Boot CLI by using the following commands:

$ brew tap pivotal/tap
$ brew install springboot
Homebrew installs spring to /usr/local/bin.

If you do not see the formula, your installation of brew might be out-of-date. In that case, run brew update and try again.

##### 10.2.4 MacPorts Installation
If you are on a Mac and use MacPorts, you can install the Spring Boot CLI by using the following command:

$ sudo port install spring-boot-cli
##### 10.2.5 Command-line Completion
The Spring Boot CLI includes scripts that provide command completion for the BASH and zsh shells. You can source the script (also named spring) in any shell or put it in your personal or system-wide bash completion initialization. On a Debian system, the system-wide scripts are in /shell-completion/bash and all scripts in that directory are executed when a new shell starts. For example, to run the script manually if you have installed by using SDKMAN!, use the following commands:

$ . ~/.sdkman/candidates/springboot/current/shell-completion/bash/spring
$ spring <HIT TAB HERE>
  grab  help  jar  run  test  version
[Note]
If you install the Spring Boot CLI by using Homebrew or MacPorts, the command-line completion scripts are automatically registered with your shell.

##### 10.2.6 Quick-start Spring CLI Example
You can use the following web application to test your installation. To start, create a file called app.groovy, as follows:

@RestController
class ThisWillActuallyRun {

	@RequestMapping("/")
	String home() {
		"Hello World!"
	}

}
Then run it from a shell, as follows:

$ spring run app.groovy
[Note]
The first run of your application is slow, as dependencies are downloaded. Subsequent runs are much quicker.

Open localhost:8080 in your favorite web browser. You should see the following output:

Hello World!
#### 10.3 Upgrading from an Earlier Version of Spring Boot
If you are upgrading from an earlier release of Spring Boot, check the “migration guide” on the project wiki that provides detailed upgrade instructions. Check also the “release notes” for a list of “new and noteworthy” features for each release.

To upgrade an existing CLI installation, use the appropriate package manager command (for example, brew upgrade) or, if you manually installed the CLI, follow the standard instructions, remembering to update your PATH environment variable to remove any older references.

### 11. Developing Your First Spring Boot Application
This section describes how to develop a simple “Hello World!” web application that highlights some of Spring Boot’s key features. We use Maven to build this project, since most IDEs support it.

[Tip]
The spring.io web site contains many “Getting Started” guides that use Spring Boot. If you need to solve a specific problem, check there first.

You can shortcut the steps below by going to start.spring.io and choosing the "Web" starter from the dependencies searcher. Doing so generates a new project structure so that you can start coding right away. Check the Spring Initializr documentation for more details.

Before we begin, open a terminal and run the following commands to ensure that you have valid versions of Java and Maven installed:

$ java -version
java version "1.8.0_102"
Java(TM) SE Runtime Environment (build 1.8.0_102-b14)
Java HotSpot(TM) 64-Bit Server VM (build 25.102-b14, mixed mode)
$ mvn -v
Apache Maven 3.3.9 (bb52d8502b132ec0a5a3f4c09453c07478323dc5; 2015-11-10T16:41:47+00:00)
Maven home: /usr/local/Cellar/maven/3.3.9/libexec
Java version: 1.8.0_102, vendor: Oracle Corporation
[Note]
This sample needs to be created in its own folder. Subsequent instructions assume that you have created a suitable folder and that it is your current directory.

11.1 Creating the POM
We need to start by creating a Maven pom.xml file. The pom.xml is the recipe that is used to build your project. Open your favorite text editor and add the following:

<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>

	<groupId>com.example</groupId>
	<artifactId>myproject</artifactId>
	<version>0.0.1-SNAPSHOT</version>

	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>2.0.0.BUILD-SNAPSHOT</version>
	</parent>

	<!-- Additional lines to be added here... -->

	<!-- (you don't need this if you are using a .RELEASE version) -->
	<repositories>
		<repository>
			<id>spring-snapshots</id>
			<url>https://repo.spring.io/snapshot</url>
			<snapshots><enabled>true</enabled></snapshots>
		</repository>
		<repository>
			<id>spring-milestones</id>
			<url>https://repo.spring.io/milestone</url>
		</repository>
	</repositories>
	<pluginRepositories>
		<pluginRepository>
			<id>spring-snapshots</id>
			<url>https://repo.spring.io/snapshot</url>
		</pluginRepository>
		<pluginRepository>
			<id>spring-milestones</id>
			<url>https://repo.spring.io/milestone</url>
		</pluginRepository>
	</pluginRepositories>
</project>
The preceding listing should give you a working build. You can test it by running mvn package (for now, you can ignore the “jar will be empty - no content was marked for inclusion!” warning).

[Note]
At this point, you could import the project into an IDE (most modern Java IDEs include built-in support for Maven). For simplicity, we continue to use a plain text editor for this example.

11.2 Adding Classpath Dependencies
Spring Boot provides a number of “Starters” that let you add jars to your classpath. Our sample application has already used spring-boot-starter-parent in the parent section of the POM. The spring-boot-starter-parent is a special starter that provides useful Maven defaults. It also provides a dependency-management section so that you can omit version tags for “blessed” dependencies.

Other “Starters” provide dependencies that you are likely to need when developing a specific type of application. Since we are developing a web application, we add a spring-boot-starter-web dependency. Before that, we can look at what we currently have by running the following command:

$ mvn dependency:tree

[INFO] com.example:myproject:jar:0.0.1-SNAPSHOT
The mvn dependency:tree command prints a tree representation of your project dependencies. You can see that spring-boot-starter-parent provides no dependencies by itself. To add the necessary dependencies, edit your pom.xml and add the spring-boot-starter-web dependency immediately below the parent section:

<dependencies>
	<dependency>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-web</artifactId>
	</dependency>
</dependencies>
If you run mvn dependency:tree again, you see that there are now a number of additional dependencies, including the Tomcat web server and Spring Boot itself.

11.3 Writing the Code
To finish our application, we need to create a single Java file. By default, Maven compiles sources from src/main/java, so you need to create that folder structure and then add a file named src/main/java/Example.java to contain the following code:

import org.springframework.boot.*;
import org.springframework.boot.autoconfigure.*;
import org.springframework.web.bind.annotation.*;

@RestController
@EnableAutoConfiguration
public class Example {

	@RequestMapping("/")
	String home() {
		return "Hello World!";
	}

	public static void main(String[] args) throws Exception {
		SpringApplication.run(Example.class, args);
	}

}
Although there is not much code here, quite a lot is going on. We step through the important parts in the next few sections.

11.3.1 The @RestController and @RequestMapping Annotations
The first annotation on our Example class is @RestController. This is known as a stereotype annotation. It provides hints for people reading the code and for Spring that the class plays a specific role. In this case, our class is a web @Controller, so Spring considers it when handling incoming web requests.

The @RequestMapping annotation provides “routing” information. It tells Spring that any HTTP request with the / path should be mapped to the home method. The @RestController annotation tells Spring to render the resulting string directly back to the caller.

[Tip]
The @RestController and @RequestMapping annotations are Spring MVC annotations. (They are not specific to Spring Boot.) See the MVC section in the Spring Reference Documentation for more details.

11.3.2 The @EnableAutoConfiguration Annotation
The second class-level annotation is @EnableAutoConfiguration. This annotation tells Spring Boot to “guess” how you want to configure Spring, based on the jar dependencies that you have added. Since spring-boot-starter-web added Tomcat and Spring MVC, the auto-configuration assumes that you are developing a web application and sets up Spring accordingly.

Starters and Auto-Configuration

Auto-configuration is designed to work well with “Starters”, but the two concepts are not directly tied. You are free to pick and choose jar dependencies outside of the starters. Spring Boot still does its best to auto-configure your application.

11.3.3 The “main” Method
The final part of our application is the main method. This is just a standard method that follows the Java convention for an application entry point. Our main method delegates to Spring Boot’s SpringApplication class by calling run. SpringApplication bootstraps our application, starting Spring, which, in turn, starts the auto-configured Tomcat web server. We need to pass Example.class as an argument to the run method to tell SpringApplication which is the primary Spring component. The args array is also passed through to expose any command-line arguments.

11.4 Running the Example
At this point, your application should work. Since you used the spring-boot-starter-parent POM, you have a useful run goal that you can use to start the application. Type mvn spring-boot:run from the root project directory to start the application. You should see output similar to the following:

$ mvn spring-boot:run

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::  (v2.0.0.BUILD-SNAPSHOT)
....... . . .
....... . . . (log output here)
....... . . .
........ Started Example in 2.222 seconds (JVM running for 6.514)
If you open a web browser to localhost:8080, you should see the following output:

Hello World!
To gracefully exit the application, press ctrl-c.

11.5 Creating an Executable Jar
We finish our example by creating a completely self-contained executable jar file that we could run in production. Executable jars (sometimes called “fat jars”) are archives containing your compiled classes along with all of the jar dependencies that your code needs to run.

Executable jars and Java

Java does not provide a standard way to load nested jar files (jar files that are themselves contained within a jar). This can be problematic if you are looking to distribute a self-contained application.

To solve this problem, many developers use “uber” jars. An uber jar packages all the classes from all the application’s dependencies into a single archive. The problem with this approach is that it becomes hard to see which libraries are in your application. It can also be problematic if the same filename is used (but with different content) in multiple jars.

Spring Boot takes a different approach and lets you actually nest jars directly.

To create an executable jar, we need to add the spring-boot-maven-plugin to our pom.xml. To do so, insert the following lines just below the dependencies section:

<build>
	<plugins>
		<plugin>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-maven-plugin</artifactId>
		</plugin>
	</plugins>
</build>
[Note]
The spring-boot-starter-parent POM includes <executions> configuration to bind the repackage goal. If you do not use the parent POM, you need to declare this configuration yourself. See the plugin documentation for details.

Save your pom.xml and run mvn package from the command line, as follows:

$ mvn package

[INFO] Scanning for projects...
[INFO]
[INFO] ------------------------------------------------------------------------
[INFO] Building myproject 0.0.1-SNAPSHOT
[INFO] ------------------------------------------------------------------------
[INFO] .... ..
[INFO] --- maven-jar-plugin:2.4:jar (default-jar) @ myproject ---
[INFO] Building jar: /Users/developer/example/spring-boot-example/target/myproject-0.0.1-SNAPSHOT.jar
[INFO]
[INFO] --- spring-boot-maven-plugin:2.0.0.BUILD-SNAPSHOT:repackage (default) @ myproject ---
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
If you look in the target directory, you should see myproject-0.0.1-SNAPSHOT.jar. The file should be around 10 MB in size. If you want to peek inside, you can use jar tvf, as follows:

$ jar tvf target/myproject-0.0.1-SNAPSHOT.jar
You should also see a much smaller file named myproject-0.0.1-SNAPSHOT.jar.original in the target directory. This is the original jar file that Maven created before it was repackaged by Spring Boot.

To run that application, use the java -jar command, as follows:

$ java -jar target/myproject-0.0.1-SNAPSHOT.jar

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::  (v2.0.0.BUILD-SNAPSHOT)
....... . . .
....... . . . (log output here)
....... . . .
........ Started Example in 2.536 seconds (JVM running for 2.864)
As before, to exit the application, press ctrl-c.

12. What to Read Next
Hopefully, this section provided some of the Spring Boot basics and got you on your way to writing your own applications. If you are a task-oriented type of developer, you might want to jump over to spring.io and check out some of the getting started guides that solve specific “How do I do that with Spring?” problems. We also have Spring Boot-specific “How-to” reference documentation.

The Spring Boot repository also has a bunch of samples you can run. The samples are independent of the rest of the code (that is, you do not need to build the rest to run or use the samples).

Otherwise, the next logical step is to read Part III, “Using Spring Boot”. If you are really impatient, you could also jump ahead and read about Spring Boot features.

Part III. Using Spring Boot
This section goes into more detail about how you should use Spring Boot. It covers topics such as build systems, auto-configuration, and how to run your applications. We also cover some Spring Boot best practices. Although there is nothing particularly special about Spring Boot (it is just another library that you can consume), there are a few recommendations that, when followed, make your development process a little easier.

If you are starting out with Spring Boot, you should probably read the Getting Started guide before diving into this section.

13. Build Systems
It is strongly recommended that you choose a build system that supports dependency management and that can consume artifacts published to the “Maven Central” repository. We would recommend that you choose Maven or Gradle. It is possible to get Spring Boot to work with other build systems (Ant, for example), but they are not particularly well supported.

13.1 Dependency Management
Each release of Spring Boot provides a curated list of dependencies that it supports. In practice, you do not need to provide a version for any of these dependencies in your build configuration, as Spring Boot manages that for you. When you upgrade Spring Boot itself, these dependencies are upgraded as well in a consistent way.

[Note]
You can still specify a version and override Spring Boot’s recommendations if you need to do so.

The curated list contains all the spring modules that you can use with Spring Boot as well as a refined list of third party libraries. The list is available as a standard Bills of Materials (spring-boot-dependencies) that can be used with both Maven and Gradle.

[Warning]
Each release of Spring Boot is associated with a base version of the Spring Framework. We highly recommend that you not specify its version.

13.2 Maven
Maven users can inherit from the spring-boot-starter-parent project to obtain sensible defaults. The parent project provides the following features:

Java 1.8 as the default compiler level.
UTF-8 source encoding.
A Dependency Management section, inherited from the spring-boot-dependencies pom, that manages the versions of common dependencies. This dependency management lets you omit <version> tags for those dependencies when used in your own pom.
Sensible resource filtering.
Sensible plugin configuration (exec plugin, Git commit ID, and shade).
Sensible resource filtering for application.properties and application.yml including profile-specific files (for example, application-dev.properties and application-dev.yml)
Note that, since the application.properties and application.yml files accept Spring style placeholders (${…​}), the Maven filtering is changed to use @..@ placeholders. (You can override that by setting a Maven property called resource.delimiter.)

13.2.1 Inheriting the Starter Parent
To configure your project to inherit from the spring-boot-starter-parent, set the parent as follows:

<!-- Inherit defaults from Spring Boot -->
<parent>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-parent</artifactId>
	<version>2.0.0.BUILD-SNAPSHOT</version>
</parent>
[Note]
You should need to specify only the Spring Boot version number on this dependency. If you import additional starters, you can safely omit the version number.

With that setup, you can also override individual dependencies by overriding a property in your own project. For instance, to upgrade to another Spring Data release train, you would add the following to your pom.xml:

<properties>
	<spring-data-releasetrain.version>Fowler-SR2</spring-data-releasetrain.version>
</properties>
[Tip]
Check the spring-boot-dependencies pom for a list of supported properties.

13.2.2 Using Spring Boot without the Parent POM
Not everyone likes inheriting from the spring-boot-starter-parent POM. You may have your own corporate standard parent that you need to use or you may prefer to explicitly declare all your Maven configuration.

If you do not want to use the spring-boot-starter-parent, you can still keep the benefit of the dependency management (but not the plugin management) by using a scope=import dependency, as follows:

<dependencyManagement>
		<dependencies>
		<dependency>
			<!-- Import dependency management from Spring Boot -->
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-dependencies</artifactId>
			<version>2.0.0.BUILD-SNAPSHOT</version>
			<type>pom</type>
			<scope>import</scope>
		</dependency>
	</dependencies>
</dependencyManagement>
The preceding sample setup does not let you override individual dependencies by using a property, as explained above. To achieve the same result, you need to add an entry in the dependencyManagement of your project before the spring-boot-dependencies entry. For instance, to upgrade to another Spring Data release train, you could add the following element to your pom.xml:

<dependencyManagement>
	<dependencies>
		<!-- Override Spring Data release train provided by Spring Boot -->
		<dependency>
			<groupId>org.springframework.data</groupId>
			<artifactId>spring-data-releasetrain</artifactId>
			<version>Fowler-SR2</version>
			<type>pom</type>
			<scope>import</scope>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-dependencies</artifactId>
			<version>2.0.0.BUILD-SNAPSHOT</version>
			<type>pom</type>
			<scope>import</scope>
		</dependency>
	</dependencies>
</dependencyManagement>
[Note]
In the preceding example, we specify a BOM, but any dependency type can be overridden in the same way.

13.2.3 Using the Spring Boot Maven Plugin
Spring Boot includes a Maven plugin that can package the project as an executable jar. Add the plugin to your <plugins> section if you want to use it, as shown in the following example:

<build>
	<plugins>
		<plugin>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-maven-plugin</artifactId>
		</plugin>
	</plugins>
</build>
[Note]
If you use the Spring Boot starter parent pom, you need to add only the plugin. There is no need to configure it unless you want to change the settings defined in the parent.

13.3 Gradle
To learn about using Spring Boot with Gradle, please refer to the documentation for Spring Boot’s Gradle plugin:

Reference (HTML and PDF)
API
13.4 Ant
It is possible to build a Spring Boot project using Apache Ant+Ivy. The spring-boot-antlib “AntLib” module is also available to help Ant create executable jars.

To declare dependencies, a typical ivy.xml file looks something like the following example:

<ivy-module version="2.0">
	<info organisation="org.springframework.boot" module="spring-boot-sample-ant" />
	<configurations>
		<conf name="compile" description="everything needed to compile this module" />
		<conf name="runtime" extends="compile" description="everything needed to run this module" />
	</configurations>
	<dependencies>
		<dependency org="org.springframework.boot" name="spring-boot-starter"
			rev="${spring-boot.version}" conf="compile" />
	</dependencies>
</ivy-module>
A typical build.xml looks like the following example:

<project
	xmlns:ivy="antlib:org.apache.ivy.ant"
	xmlns:spring-boot="antlib:org.springframework.boot.ant"
	name="myapp" default="build">

	<property name="spring-boot.version" value="2.0.0.BUILD-SNAPSHOT" />

	<target name="resolve" description="--> retrieve dependencies with ivy">
		<ivy:retrieve pattern="lib/[conf]/[artifact]-[type]-[revision].[ext]" />
	</target>

	<target name="classpaths" depends="resolve">
		<path id="compile.classpath">
			<fileset dir="lib/compile" includes="*.jar" />
		</path>
	</target>

	<target name="init" depends="classpaths">
		<mkdir dir="build/classes" />
	</target>

	<target name="compile" depends="init" description="compile">
		<javac srcdir="src/main/java" destdir="build/classes" classpathref="compile.classpath" />
	</target>

	<target name="build" depends="compile">
		<spring-boot:exejar destfile="build/myapp.jar" classes="build/classes">
			<spring-boot:lib>
				<fileset dir="lib/runtime" />
			</spring-boot:lib>
		</spring-boot:exejar>
	</target>
</project>
[Tip]
If you do not want to use the spring-boot-antlib module, see the Section 86.9, “Build an Executable Archive from Ant without Using spring-boot-antlib” “How-to” .

13.5 Starters
Starters are a set of convenient dependency descriptors that you can include in your application. You get a one-stop shop for all the Spring and related technologies that you need without having to hunt through sample code and copy-paste loads of dependency descriptors. For example, if you want to get started using Spring and JPA for database access, include the spring-boot-starter-data-jpa dependency in your project.

The starters contain a lot of the dependencies that you need to get a project up and running quickly and with a consistent, supported set of managed transitive dependencies.

What’s in a name

All official starters follow a similar naming pattern; spring-boot-starter-*, where * is a particular type of application. This naming structure is intended to help when you need to find a starter. The Maven integration in many IDEs lets you search dependencies by name. For example, with the appropriate Eclipse or STS plugin installed, you can press ctrl-space in the POM editor and type “spring-boot-starter” for a complete list.

As explained in the “Creating Your Own Starter” section, third party starters should not start with spring-boot, as it is reserved for official Spring Boot artifacts. Rather, a third-party starter typically starts with the name of the project. For example, a third-party starter project called thirdpartyproject would typically be named thirdpartyproject-spring-boot-starter.

The following application starters are provided by Spring Boot under the org.springframework.boot group:

Table 13.1. Spring Boot application starters

Name	Description	Pom
spring-boot-starter

Core starter, including auto-configuration support, logging and YAML

Pom

spring-boot-starter-activemq

Starter for JMS messaging using Apache ActiveMQ

Pom

spring-boot-starter-amqp

Starter for using Spring AMQP and Rabbit MQ

Pom

spring-boot-starter-aop

Starter for aspect-oriented programming with Spring AOP and AspectJ

Pom

spring-boot-starter-artemis

Starter for JMS messaging using Apache Artemis

Pom

spring-boot-starter-batch

Starter for using Spring Batch

Pom

spring-boot-starter-cache

Starter for using Spring Framework’s caching support

Pom

spring-boot-starter-cloud-connectors

Starter for using Spring Cloud Connectors which simplifies connecting to services in cloud platforms like Cloud Foundry and Heroku

Pom

spring-boot-starter-data-cassandra

Starter for using Cassandra distributed database and Spring Data Cassandra

Pom

spring-boot-starter-data-cassandra-reactive

Starter for using Cassandra distributed database and Spring Data Cassandra Reactive

Pom

spring-boot-starter-data-couchbase

Starter for using Couchbase document-oriented database and Spring Data Couchbase

Pom

spring-boot-starter-data-couchbase-reactive

Starter for using Couchbase document-oriented database and Spring Data Couchbase Reactive

Pom

spring-boot-starter-data-elasticsearch

Starter for using Elasticsearch search and analytics engine and Spring Data Elasticsearch

Pom

spring-boot-starter-data-jpa

Starter for using Spring Data JPA with Hibernate

Pom

spring-boot-starter-data-ldap

Starter for using Spring Data LDAP

Pom

spring-boot-starter-data-mongodb

Starter for using MongoDB document-oriented database and Spring Data MongoDB

Pom

spring-boot-starter-data-mongodb-reactive

Starter for using MongoDB document-oriented database and Spring Data MongoDB Reactive

Pom

spring-boot-starter-data-neo4j

Starter for using Neo4j graph database and Spring Data Neo4j

Pom

spring-boot-starter-data-redis

Starter for using Redis key-value data store with Spring Data Redis and the Lettuce client

Pom

spring-boot-starter-data-redis-reactive

Starter for using Redis key-value data store with Spring Data Redis reactive and the Lettuce client

Pom

spring-boot-starter-data-rest

Starter for exposing Spring Data repositories over REST using Spring Data REST

Pom

spring-boot-starter-data-solr

Starter for using the Apache Solr search platform with Spring Data Solr

Pom

spring-boot-starter-freemarker

Starter for building MVC web applications using FreeMarker views

Pom

spring-boot-starter-groovy-templates

Starter for building MVC web applications using Groovy Templates views

Pom

spring-boot-starter-hateoas

Starter for building hypermedia-based RESTful web application with Spring MVC and Spring HATEOAS

Pom

spring-boot-starter-integration

Starter for using Spring Integration

Pom

spring-boot-starter-jdbc

Starter for using JDBC with the Tomcat JDBC connection pool

Pom

spring-boot-starter-jersey

Starter for building RESTful web applications using JAX-RS and Jersey. An alternative to spring-boot-starter-web

Pom

spring-boot-starter-jooq

Starter for using jOOQ to access SQL databases. An alternative to spring-boot-starter-data-jpa or spring-boot-starter-jdbc

Pom

spring-boot-starter-json

Starter for reading and writing json

Pom

spring-boot-starter-jta-atomikos

Starter for JTA transactions using Atomikos

Pom

spring-boot-starter-jta-bitronix

Starter for JTA transactions using Bitronix

Pom

spring-boot-starter-jta-narayana

Spring Boot Narayana JTA Starter

Pom

spring-boot-starter-mail

Starter for using Java Mail and Spring Framework’s email sending support

Pom

spring-boot-starter-mustache

Starter for building web applications using Mustache views

Pom

spring-boot-starter-quartz

Spring Boot Quartz Starter

Pom

spring-boot-starter-security

Starter for using Spring Security

Pom

spring-boot-starter-test

Starter for testing Spring Boot applications with libraries including JUnit, Hamcrest and Mockito

Pom

spring-boot-starter-thymeleaf

Starter for building MVC web applications using Thymeleaf views

Pom

spring-boot-starter-validation

Starter for using Java Bean Validation with Hibernate Validator

Pom

spring-boot-starter-web

Starter for building web, including RESTful, applications using Spring MVC. Uses Tomcat as the default embedded container

Pom

spring-boot-starter-web-services

Starter for using Spring Web Services

Pom

spring-boot-starter-webflux

Starter for building WebFlux applications using Spring Framework’s Reactive Web support

Pom

spring-boot-starter-websocket

Starter for building WebSocket applications using Spring Framework’s WebSocket support

Pom


In addition to the application starters, the following starters can be used to add production ready features:

Table 13.2. Spring Boot production starters

Name	Description	Pom
spring-boot-starter-actuator

Starter for using Spring Boot’s Actuator which provides production ready features to help you monitor and manage your application

Pom


Finally, Spring Boot also includes the following starters that can be used if you want to exclude or swap specific technical facets:

Table 13.3. Spring Boot technical starters

Name	Description	Pom
spring-boot-starter-jetty

Starter for using Jetty as the embedded servlet container. An alternative to spring-boot-starter-tomcat

Pom

spring-boot-starter-log4j2

Starter for using Log4j2 for logging. An alternative to spring-boot-starter-logging

Pom

spring-boot-starter-logging

Starter for logging using Logback. Default logging starter

Pom

spring-boot-starter-reactor-netty

Starter for using Reactor Netty as the embedded reactive HTTP server.

Pom

spring-boot-starter-tomcat

Starter for using Tomcat as the embedded servlet container. Default servlet container starter used by spring-boot-starter-web

Pom

spring-boot-starter-undertow

Starter for using Undertow as the embedded servlet container. An alternative to spring-boot-starter-tomcat

Pom


[Tip]
For a list of additional community contributed starters, see the README file in the spring-boot-starters module on GitHub.

14. Structuring Your Code
Spring Boot does not require any specific code layout to work. However, there are some best practices that help.

14.1 Using the “default” Package
When a class does not include a package declaration, it is considered to be in the “default package”. The use of the “default package” is generally discouraged and should be avoided. It can cause particular problems for Spring Boot applications that use the @ComponentScan, @EntityScan, or @SpringBootApplication annotations, since every class from every jar is read.

[Tip]
We recommend that you follow Java’s recommended package naming conventions and use a reversed domain name (for example, com.example.project).

14.2 Locating the Main Application Class
We generally recommend that you locate your main application class in a root package above other classes. The @EnableAutoConfiguration annotation is often placed on your main class, and it implicitly defines a base “search package” for certain items. For example, if you are writing a JPA application, the package of the @EnableAutoConfiguration annotated class is used to search for @Entity items.

Using a root package also lets the @ComponentScan annotation be used without needing to specify a basePackage attribute. You can also use the @SpringBootApplication annotation if your main class is in the root package.

The following listing shows a typical layout:

com
 +- example
     +- myapplication
         +- Application.java
         |
         +- customer
         |   +- Customer.java
         |   +- CustomerController.java
         |   +- CustomerService.java
         |   +- CustomerRepository.java
         |
         +- order
             +- Order.java
             +- OrderController.java
             +- OrderService.java
             +- OrderRepository.java
The Application.java file would declare the main method, along with the basic @Configuration, as follows:

package com.example.myapplication;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.EnableAutoConfiguration;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;

@Configuration
@EnableAutoConfiguration
@ComponentScan
public class Application {

	public static void main(String[] args) {
		SpringApplication.run(Application.class, args);
	}

}
15. Configuration Classes
Spring Boot favors Java-based configuration. Although it is possible to use SpringApplication with XML sources, we generally recommend that your primary source be a single @Configuration class. Usually the class that defines the main method is a good candidate as the primary @Configuration.

[Tip]
Many Spring configuration examples have been published on the Internet that use XML configuration. If possible, always try to use the equivalent Java-based configuration. Searching for Enable* annotations can be a good starting point.

15.1 Importing Additional Configuration Classes
You need not put all your @Configuration into a single class. The @Import annotation can be used to import additional configuration classes. Alternatively, you can use @ComponentScan to automatically pick up all Spring components, including @Configuration classes.

15.2 Importing XML Configuration
If you absolutely must use XML based configuration, we recommend that you still start with a @Configuration class. You can then use an @ImportResource annotation to load XML configuration files.

16. Auto-configuration
Spring Boot auto-configuration attempts to automatically configure your Spring application based on the jar dependencies that you have added. For example, if HSQLDB is on your classpath, and you have not manually configured any database connection beans, then Spring Boot auto-configures an in-memory database.

You need to opt-in to auto-configuration by adding the @EnableAutoConfiguration or @SpringBootApplication annotations to one of your @Configuration classes.

[Tip]
You should only ever add one @EnableAutoConfiguration annotation. We generally recommend that you add it to your primary @Configuration class.

16.1 Gradually Replacing Auto-configuration
Auto-configuration is non-invasive. At any point, you can start to define your own configuration to replace specific parts of the auto-configuration. For example, if you add your own DataSource bean, the default embedded database support backs away.

If you need to find out what auto-configuration is currently being applied, and why, start your application with the --debug switch. Doing so enables debug logs for a selection of core loggers and logs a conditions report to the console.

16.2 Disabling Specific Auto-configuration Classes
If you find that specific auto-configuration classes that you do not want are being applied, you can use the exclude attribute of @EnableAutoConfiguration to disable them, as shown in the following example:

import org.springframework.boot.autoconfigure.*;
import org.springframework.boot.autoconfigure.jdbc.*;
import org.springframework.context.annotation.*;

@Configuration
@EnableAutoConfiguration(exclude={DataSourceAutoConfiguration.class})
public class MyConfiguration {
}
If the class is not on the classpath, you can use the excludeName attribute of the annotation and specify the fully qualified name instead. Finally, you can also control the list of auto-configuration classes to exclude by using the spring.autoconfigure.exclude property.

[Tip]
You can define exclusions both at the annotation level and by using the property.

17. Spring Beans and Dependency Injection
You are free to use any of the standard Spring Framework techniques to define your beans and their injected dependencies. For simplicity, we often find that using @ComponentScan (to find your beans) and using @Autowired (to do constructor injection) works well.

If you structure your code as suggested above (locating your application class in a root package), you can add @ComponentScan without any arguments. All of your application components (@Component, @Service, @Repository, @Controller etc.) are automatically registered as Spring Beans.

The following example shows a @Service Bean that uses constructor injection to obtain a required RiskAssessor bean:

package com.example.service;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;

@Service
public class DatabaseAccountService implements AccountService {

	private final RiskAssessor riskAssessor;

	@Autowired
	public DatabaseAccountService(RiskAssessor riskAssessor) {
		this.riskAssessor = riskAssessor;
	}

	// ...

}
If a bean has one constructor, you can omit the @Autowired, as shown in the following example:

@Service
public class DatabaseAccountService implements AccountService {

	private final RiskAssessor riskAssessor;

	public DatabaseAccountService(RiskAssessor riskAssessor) {
		this.riskAssessor = riskAssessor;
	}

	// ...

}
[Tip]
Notice how using constructor injection lets the riskAssessor field be marked as final, indicating that it cannot be subsequently changed.

18. Using the @SpringBootApplication Annotation
Many Spring Boot developers always have their main class annotated with @Configuration, @EnableAutoConfiguration, and @ComponentScan. Since these annotations are so frequently used together (especially if you follow the best practices above), Spring Boot provides a convenient @SpringBootApplication alternative.

The @SpringBootApplication annotation is equivalent to using @Configuration, @EnableAutoConfiguration, and @ComponentScan with their default attributes, as shown in the following example:

package com.example.myapplication;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication // same as @Configuration @EnableAutoConfiguration @ComponentScan
public class Application {

	public static void main(String[] args) {
		SpringApplication.run(Application.class, args);
	}

}
[Note]
@SpringBootApplication also provides aliases to customize the attributes of @EnableAutoConfiguration and @ComponentScan.

19. Running Your Application
One of the biggest advantages of packaging your application as a jar and using an embedded HTTP server is that you can run your application as you would any other. Debugging Spring Boot applications is also easy. You do not need any special IDE plugins or extensions.

[Note]
This section only covers jar based packaging. If you choose to package your application as a war file, you should refer to your server and IDE documentation.

19.1 Running from an IDE
You can run a Spring Boot application from your IDE as a simple Java application. However, you first need to import your project. Import steps vary depending on your IDE and build system. Most IDEs can import Maven projects directly. For example, Eclipse users can select Import…​ → Existing Maven Projects from the File menu.

If you cannot directly import your project into your IDE, you may be able to generate IDE metadata by using a build plugin. Maven includes plugins for Eclipse and IDEA. Gradle offers plugins for various IDEs.

[Tip]
If you accidentally run a web application twice, you see a “Port already in use” error. STS users can use the Relaunch button rather than the Run button to ensure that any existing instance is closed.

19.2 Running as a Packaged Application
If you use the Spring Boot Maven or Gradle plugins to create an executable jar, you can run your application using java -jar, as shown in the following example:

$ java -jar target/myapplication-0.0.1-SNAPSHOT.jar
It is also possible to run a packaged application with remote debugging support enabled. Doing so lets you attach a debugger to your packaged application, as shown in the following example:

$ java -Xdebug -Xrunjdwp:server=y,transport=dt_socket,address=8000,suspend=n \
       -jar target/myapplication-0.0.1-SNAPSHOT.jar
19.3 Using the Maven Plugin
The Spring Boot Maven plugin includes a run goal that can be used to quickly compile and run your application. Applications run in an exploded form, as they do in your IDE. The following example shows a typical Maven command to run a Spring Boot application:

$ mvn spring-boot:run
You might also want to use the MAVEN_OPTS operating system environment variable, as shown in the following example:

$ export MAVEN_OPTS=-Xmx1024m
19.4 Using the Gradle Plugin
The Spring Boot Gradle plugin also includes a bootRun task that can be used to run your application in an exploded form. The bootRun task is added whenever you apply the org.springframework.boot and java plugins and is shown in the following example:

$ gradle bootRun
You might also want to use the JAVA_OPTS operating system environment variable, as shown in the following example:

$ export JAVA_OPTS=-Xmx1024m
19.5 Hot Swapping
Since Spring Boot applications are just plain Java applications, JVM hot-swapping should work out of the box. JVM hot swapping is somewhat limited with the bytecode that it can replace. For a more complete solution, JRebel can be used.

The spring-boot-devtools module also includes support for quick application restarts. See the Chapter 20, Developer Tools section later in this chapter and the Hot swapping “How-to” for details.

20. Developer Tools
Spring Boot includes an additional set of tools that can make the application development experience a little more pleasant. The spring-boot-devtools module can be included in any project to provide additional development-time features. To include devtools support, add the module dependency to your build, as shown in the following listings for Maven and Gradle:

Maven. 

<dependencies>
	<dependency>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-devtools</artifactId>
		<optional>true</optional>
	</dependency>
</dependencies>
Gradle. 

dependencies {
	compile("org.springframework.boot:spring-boot-devtools")
}
[Note]
Developer tools are automatically disabled when running a fully packaged application. If your application is launched from java -jar or if it is started from a special classloader, then it is considered a “production application”. Flagging the dependency as optional is a best practice that prevents devtools from being transitively applied to other modules that use your project. Gradle does not support optional dependencies out-of-the-box, so you may want to have a look at the propdeps-plugin.

[Tip]
Repackaged archives do not contain devtools by default. If you want to use a certain remote devtools feature, you need to disable the excludeDevtools build property to include it. The property is supported with both the Maven and Gradle plugins.

20.1 Property Defaults
Several of the libraries supported by Spring Boot use caches to improve performance. For example, template engines cache compiled templates to avoid repeatedly parsing template files. Also, Spring MVC can add HTTP caching headers to responses when serving static resources.

While caching is very beneficial in production, it can be counter-productive during development, preventing you from seeing the changes you just made in your application. For this reason, spring-boot-devtools disables the caching options by default.

Cache options are usually configured by settings in your application.properties file. For example, Thymeleaf offers the spring.thymeleaf.cache property. Rather than needing to set these properties manually, the spring-boot-devtools module automatically applies sensible development-time configuration.

[Tip]
For a complete list of the properties that are applied by the devtools, see DevToolsPropertyDefaultsPostProcessor.

20.2 Automatic Restart
Applications that use spring-boot-devtools automatically restart whenever files on the classpath change. This can be a useful feature when working in an IDE, as it gives a very fast feedback loop for code changes. By default, any entry on the classpath that points to a folder is monitored for changes. Note that certain resources, such as static assets and view templates, do not need to restart the application.

Triggering a restart

As DevTools monitors classpath resources, the only way to trigger a restart is to update the classpath. The way in which you cause the classpath to be updated depends on the IDE that you are using. In Eclipse, saving a modified file causes the classpath to be updated and triggers a restart. In IntelliJ IDEA, building the project (Build -> Make Project) has the same effect.

[Note]
As long as forking is enabled, you can also start your application by using the supported build plugins (Maven and Gradle), since DevTools needs an isolated application classloader to operate properly. By default, Gradle and Maven do that when they detect DevTools on the classpath.

[Tip]
Automatic restart works very well when used with LiveReload. See the LiveReload section for details. If you use JRebel, automatic restarts are disabled in favor of dynamic class reloading. Other devtools features (such as LiveReload and property overrides) can still be used.

[Note]
DevTools relies on the application context’s shutdown hook to close it during a restart. It does not work correctly if you have disabled the shutdown hook (SpringApplication.setRegisterShutdownHook(false)).

[Note]
When deciding if an entry on the classpath should trigger a restart when it changes, DevTools automatically ignores projects named spring-boot, spring-boot-devtools, spring-boot-autoconfigure, spring-boot-actuator, and spring-boot-starter.

[Note]
DevTools needs to customize the ResourceLoader used by the ApplicationContext. If your application provides one already, it is going to be wrapped. Direct override of the getResource method on the ApplicationContext is not supported.

Restart vs Reload

The restart technology provided by Spring Boot works by using two classloaders. Classes that do not change (for example, those from third-party jars) are loaded into a base classloader. Classes that you are actively developing are loaded into a restart classloader. When the application is restarted, the restart classloader is thrown away and a new one is created. This approach means that application restarts are typically much faster than “cold starts”, since the base classloader is already available and populated.

If you find that restarts are not quick enough for your applications or you encounter classloading issues, you could consider reloading technologies such as JRebel from ZeroTurnaround. These work by rewriting classes as they are loaded to make them more amenable to reloading.

20.2.1 Logging changes in condition evaluation
By default, each time your application restarts, a report showing the condition evaluation delta is logged. The report shows the changes to your application’s auto-configuration as you make changes such as adding or removing beans and setting configuration properties.

To disable the logging of the report, set the following property:

spring.devtools.restart.log-condition-evaluation-delta=false
20.2.2 Excluding Resources
Certain resources do not necessarily need to trigger a restart when they are changed. For example, Thymeleaf templates can be edited in-place. By default, changing resources in /META-INF/maven, /META-INF/resources, /resources, /static, /public, or /templates does not trigger a restart but does trigger a live reload. If you want to customize these exclusions, you can use the spring.devtools.restart.exclude property. For example, to exclude only /static and /public you would set the following property:

spring.devtools.restart.exclude=static/**,public/**
[Tip]
If you want to keep those defaults and add additional exclusions, use the spring.devtools.restart.additional-exclude property instead.

20.2.3 Watching Additional Paths
You may want your application to be restarted or reloaded when you make changes to files that are not on the classpath. To do so, use the spring.devtools.restart.additional-paths property to configure additional paths to watch for changes. You can use the spring.devtools.restart.exclude property described earlier to control whether changes beneath the additional paths trigger a full restart or a live reload.

20.2.4 Disabling Restart
If you do not want to use the restart feature, you can disable it by using the spring.devtools.restart.enabled property. In most cases, you can set this property in your application.properties (doing so still initializes the restart classloader, but it does not watch for file changes).

If you need to completely disable restart support (for example, because it does not work with a specific library), you need to set the spring.devtools.restart.enabled System property to false before calling SpringApplication.run(…​), as shown in the following example:

public static void main(String[] args) {
	System.setProperty("spring.devtools.restart.enabled", "false");
	SpringApplication.run(MyApp.class, args);
}
20.2.5 Using a Trigger File
If you work with an IDE that continuously compiles changed files, you might prefer to trigger restarts only at specific times. To do so, you can use a “trigger file”, which is a special file that must be modified when you want to actually trigger a restart check. Changing the file only triggers the check and the restart only occurs if Devtools has detected it has to do something. The trigger file can be updated manually or with an IDE plugin.

To use a trigger file, set the spring.devtools.restart.trigger-file property to the path of your trigger file.

[Tip]
You might want to set spring.devtools.restart.trigger-file as a global setting, so that all your projects behave in the same way.

20.2.6 Customizing the Restart Classloader
As described earlier in the Restart vs Reload section, restart functionality is implemented by using two classloaders. For most applications, this approach works well. However, it can sometimes cause classloading issues.

By default, any open project in your IDE is loaded with the “restart” classloader, and any regular .jar file is loaded with the “base” classloader. If you work on a multi-module project, and not every module is imported into your IDE, you may need to customize things. To do so, you can create a META-INF/spring-devtools.properties file.

The spring-devtools.properties file can contain properties prefixed with restart.exclude and restart.include. The include elements are items that should be pulled up into the “restart” classloader, and the exclude elements are items that should be pushed down into the “base” classloader. The value of the property is a regex pattern that is applied to the classpath, as shown in the following example:

restart.exclude.companycommonlibs=/mycorp-common-[\\w-]+\.jar
restart.include.projectcommon=/mycorp-myproj-[\\w-]+\.jar
[Note]
All property keys must be unique. As long as a property starts with restart.include. or restart.exclude. it is considered.

[Tip]
All META-INF/spring-devtools.properties from the classpath are loaded. You can package files inside your project, or in the libraries that the project consumes.

20.2.7 Known Limitations
Restart functionality does not work well with objects that are deserialized by using a standard ObjectInputStream. If you need to deserialize data, you may need to use Spring’s ConfigurableObjectInputStream in combination with Thread.currentThread().getContextClassLoader().

Unfortunately, several third-party libraries deserialize without considering the context classloader. If you find such a problem, you need to request a fix with the original authors.

20.3 LiveReload
The spring-boot-devtools module includes an embedded LiveReload server that can be used to trigger a browser refresh when a resource is changed. LiveReload browser extensions are freely available for Chrome, Firefox and Safari from livereload.com.

If you do not want to start the LiveReload server when your application runs, you can set the spring.devtools.livereload.enabled property to false.

[Note]
You can only run one LiveReload server at a time. Before starting your application, ensure that no other LiveReload servers are running. If you start multiple applications from your IDE, only the first has LiveReload support.

20.4 Global Settings
You can configure global devtools settings by adding a file named .spring-boot-devtools.properties to your $HOME folder (note that the filename starts with “.”). Any properties added to this file apply to all Spring Boot applications on your machine that use devtools. For example, to configure restart to always use a trigger file, you would add the following property:

~/.spring-boot-devtools.properties. 

spring.devtools.reload.trigger-file=.reloadtrigger
20.5 Remote Applications
The Spring Boot developer tools are not limited to local development. You can also use several features when running applications remotely. Remote support is opt-in. To enable it, you need to make sure that devtools is included in the repackaged archive, as shown in the following listing:

<build>
	<plugins>
		<plugin>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-maven-plugin</artifactId>
			<configuration>
				<excludeDevtools>false</excludeDevtools>
			</configuration>
		</plugin>
	</plugins>
</build>
Then you need to set a spring.devtools.remote.secret property, as shown in the following example:

spring.devtools.remote.secret=mysecret
[Warning]
Enabling spring-boot-devtools on a remote application is a security risk. You should never enable support on a production deployment.

Remote devtools support is provided in two parts: a server-side endpoint that accepts connections and a client application that you run in your IDE. The server component is automatically enabled when the spring.devtools.remote.secret property is set. The client component must be launched manually.

20.5.1 Running the Remote Client Application
The remote client application is designed to be run from within your IDE. You need to run org.springframework.boot.devtools.RemoteSpringApplication with the same classpath as the remote project that you connect to. The application’s single required argument is the remote URL to which it connects.

For example, if you are using Eclipse or STS and you have a project named my-app that you have deployed to Cloud Foundry, you would do the following:

Select Run Configurations…​ from the Run menu.
Create a new Java Application “launch configuration”.
Browse for the my-app project.
Use org.springframework.boot.devtools.RemoteSpringApplication as the main class.
Add https://myapp.cfapps.io to the Program arguments (or whatever your remote URL is).
A running remote client might resemble the following listing:

  .   ____          _                                              __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _          ___               _      \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` |        | _ \___ _ __  ___| |_ ___ \ \ \ \
 \\/  ___)| |_)| | | | | || (_| []::::::[]   / -_) '  \/ _ \  _/ -_) ) ) ) )
  '  |____| .__|_| |_|_| |_\__, |        |_|_\___|_|_|_\___/\__\___|/ / / /
 =========|_|==============|___/===================================/_/_/_/
 :: Spring Boot Remote :: 2.0.0.BUILD-SNAPSHOT

2015-06-10 18:25:06.632  INFO 14938 --- [           main] o.s.b.devtools.RemoteSpringApplication   : Starting RemoteSpringApplication on pwmbp with PID 14938 (/Users/pwebb/projects/spring-boot/code/spring-boot-devtools/target/classes started by pwebb in /Users/pwebb/projects/spring-boot/code/spring-boot-samples/spring-boot-sample-devtools)
2015-06-10 18:25:06.671  INFO 14938 --- [           main] s.c.a.AnnotationConfigApplicationContext : Refreshing org.springframework.context.annotation.AnnotationConfigApplicationContext@2a17b7b6: startup date [Wed Jun 10 18:25:06 PDT 2015]; root of context hierarchy
2015-06-10 18:25:07.043  WARN 14938 --- [           main] o.s.b.d.r.c.RemoteClientConfiguration    : The connection to http://localhost:8080 is insecure. You should use a URL starting with 'https://'.
2015-06-10 18:25:07.074  INFO 14938 --- [           main] o.s.b.d.a.OptionalLiveReloadServer       : LiveReload server is running on port 35729
2015-06-10 18:25:07.130  INFO 14938 --- [           main] o.s.b.devtools.RemoteSpringApplication   : Started RemoteSpringApplication in 0.74 seconds (JVM running for 1.105)
[Note]
Because the remote client is using the same classpath as the real application it can directly read application properties. This is how the spring.devtools.remote.secret property is read and passed to the server for authentication.

[Tip]
It is always advisable to use https:// as the connection protocol, so that traffic is encrypted and passwords cannot be intercepted.

[Tip]
If you need to use a proxy to access the remote application, configure the spring.devtools.remote.proxy.host and spring.devtools.remote.proxy.port properties.

20.5.2 Remote Update
The remote client monitors your application classpath for changes in the same way as the local restart. Any updated resource is pushed to the remote application and (if required) triggers a restart. This can be helpful if you iterate on a feature that uses a cloud service that you do not have locally. Generally, remote updates and restarts are much quicker than a full rebuild and deploy cycle.

[Note]
Files are only monitored when the remote client is running. If you change a file before starting the remote client, it is not pushed to the remote server.

21. Packaging Your Application for Production
Executable jars can be used for production deployment. As they are self-contained, they are also ideally suited for cloud-based deployment.

For additional “production ready” features, such as health, auditing, and metric REST or JMX end-points, consider adding spring-boot-actuator. See Part V, “Spring Boot Actuator: Production-ready features” for details.

22. What to Read Next
You should now understand how you can use Spring Boot and some best practices that you should follow. You can now go on to learn about specific Spring Boot features in depth, or you could skip ahead and read about the “production ready” aspects of Spring Boot.

Part IV. Spring Boot features
This section dives into the details of Spring Boot. Here you can learn about the key features that you may want to use and customize. If you have not already done so, you might want to read the "Part II, “Getting Started”" and "Part III, “Using Spring Boot”" sections, so that you have a good grounding of the basics.

23. SpringApplication
The SpringApplication class provides a convenient way to bootstrap a Spring application that is started from a main() method. In many situations, you can delegate to the static SpringApplication.run method, as shown in the following example:

public static void main(String[] args) {
	SpringApplication.run(MySpringConfiguration.class, args);
}
When your application starts, you should see something similar to the following output:

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::   v2.0.0.BUILD-SNAPSHOT

2013-07-31 00:08:16.117  INFO 56603 --- [           main] o.s.b.s.app.SampleApplication            : Starting SampleApplication v0.1.0 on mycomputer with PID 56603 (/apps/myapp.jar started by pwebb)
2013-07-31 00:08:16.166  INFO 56603 --- [           main] ationConfigServletWebServerApplicationContext : Refreshing org.springframework.boot.web.servlet.context.AnnotationConfigServletWebServerApplicationContext@6e5a8246: startup date [Wed Jul 31 00:08:16 PDT 2013]; root of context hierarchy
2014-03-04 13:09:54.912  INFO 41370 --- [           main] .t.TomcatServletWebServerFactory : Server initialized with port: 8080
2014-03-04 13:09:56.501  INFO 41370 --- [           main] o.s.b.s.app.SampleApplication            : Started SampleApplication in 2.992 seconds (JVM running for 3.658)
By default, INFO logging messages are shown, including some relevant startup details, such as the user that launched the application. If you need a log level other than INFO, you can set it, as described in Section 26.4, “Log Levels”,

23.1 Startup Failure
If your application fails to start, registered FailureAnalyzers get a chance to provide a dedicated error message and a concrete action to fix the problem. For instance, if you start a web application on port 8080 and that port is already in use, you should see something similar to the following message:

***************************
APPLICATION FAILED TO START
***************************

Description:

Embedded servlet container failed to start. Port 8080 was already in use.

Action:

Identify and stop the process that's listening on port 8080 or configure this application to listen on another port.
[Note]
Spring Boot provides numerous FailureAnalyzer implementations, and you can add your own.

If no failure analyzers are able to handle the exception, you can still display the full conditions report to better understand what went wrong. To do so, you need to enable the debug property or enable DEBUG logging for org.springframework.boot.autoconfigure.logging.ConditionEvaluationReportLoggingListener.

For instance, if you are running your application by using java -jar, you can enable the debug property as follows:

$ java -jar myproject-0.0.1-SNAPSHOT.jar --debug
23.2 Customizing the Banner
The banner that is printed on start up can be changed by adding a banner.txt file to your classpath or by setting the spring.banner.location property to the location of such a file. If the file has an encoding other than UTF-8, you can set spring.banner.charset. In addition to a text file, you can also add a banner.gif, banner.jpg, or banner.png image file to your classpath or set the spring.banner.image.location property. Images are converted into an ASCII art representation and printed above any text banner.

Inside your banner.txt file, you can use any of the following placeholders:

Table 23.1. Banner variables

Variable	Description
${application.version}

The version number of your application, as declared in MANIFEST.MF. For example, Implementation-Version: 1.0 is printed as 1.0.

${application.formatted-version}

The version number of your application, as declared in MANIFEST.MF and formatted for display (surrounded with brackets and prefixed with v). For example (v1.0).

${spring-boot.version}

The Spring Boot version that you are using. For example 2.0.0.BUILD-SNAPSHOT.

${spring-boot.formatted-version}

The Spring Boot version that you are using, formatted for display (surrounded with brackets and prefixed with v). For example (v2.0.0.BUILD-SNAPSHOT).

${Ansi.NAME} (or ${AnsiColor.NAME}, ${AnsiBackground.NAME}, ${AnsiStyle.NAME})

Where NAME is the name of an ANSI escape code. See AnsiPropertySource for details.

${application.title}

The title of your application, as declared in MANIFEST.MF. For example Implementation-Title: MyApp is printed as MyApp.


[Tip]
The SpringApplication.setBanner(…​) method can be used if you want to generate a banner programmatically. Use the org.springframework.boot.Banner interface and implement your own printBanner() method.

You can also use the spring.main.banner-mode property to determine if the banner has to be printed on System.out (console), sent to the configured logger (log), or not produced at all (off).

The printed banner is registered as a singleton bean under the following name: springBootBanner.

[Note]
YAML maps off to false, so be sure to add quotes if you want to disable the banner in your application, as shown in the following example:

spring:
	main:
		banner-mode: "off"
23.3 Customizing SpringApplication
If the SpringApplication defaults are not to your taste, you can instead create a local instance and customize it. For example, to turn off the banner, you could write:

public static void main(String[] args) {
	SpringApplication app = new SpringApplication(MySpringConfiguration.class);
	app.setBannerMode(Banner.Mode.OFF);
	app.run(args);
}
[Note]
The constructor arguments passed to SpringApplication are configuration sources for Spring beans. In most cases, these are references to @Configuration classes, but they could also be references to XML configuration or to packages that should be scanned.

It is also possible to configure the SpringApplication by using an application.properties file. See Chapter 24, Externalized Configuration for details.

For a complete list of the configuration options, see the SpringApplication Javadoc.

23.4 Fluent Builder API
If you need to build an ApplicationContext hierarchy (multiple contexts with a parent/child relationship) or if you prefer using a “fluent” builder API, you can use the SpringApplicationBuilder.

The SpringApplicationBuilder lets you chain together multiple method calls and includes parent and child methods that let you create a hierarchy, as shown in the following example:

new SpringApplicationBuilder()
		.sources(Parent.class)
		.child(Application.class)
		.bannerMode(Banner.Mode.OFF)
		.run(args);
[Note]
There are some restrictions when creating an ApplicationContext hierarchy. For example, Web components must be contained within the child context, and the same Environment is used for both parent and child contexts. See the SpringApplicationBuilder Javadoc for full details.

23.5 Application Events and Listeners
In addition to the usual Spring Framework events, such as ContextRefreshedEvent, a SpringApplication sends some additional application events.

[Note]
Some events are actually triggered before the ApplicationContext is created, so you cannot register a listener on those as a @Bean. You can register them with the SpringApplication.addListeners(…​) method or the SpringApplicationBuilder.listeners(…​) method.

If you want those listeners to be registered automatically, regardless of the way the application is created, you can add a META-INF/spring.factories file to your project and reference your listener(s) by using the org.springframework.context.ApplicationListener key, as shown in the following example:

org.springframework.context.ApplicationListener=com.example.project.MyListener
Application events are sent in the following order, as your application runs:

An ApplicationStartingEvent is sent at the start of a run but before any processing, except for the registration of listeners and initializers.
An ApplicationEnvironmentPreparedEvent is sent when the Environment to be used in the context is known but before the context is created.
An ApplicationPreparedEvent is sent just before the refresh is started but after bean definitions have been loaded.
An ApplicationStartedEvent is sent after the context has been refreshed but before any application and command-line runners have been called.
An ApplicationReadyEvent is sent after any application and command-line runners have been called. It indicates that the application is ready to service requests.
An ApplicationFailedEvent is sent if there is an exception on startup.
[Tip]
You often need not use application events, but it can be handy to know that they exist. Internally, Spring Boot uses events to handle a variety of tasks.

Application events are sent by using Spring Framework’s event publishing mechanism. Part of this mechanism ensures that an event published to the listeners in a child context is also published to the listeners in any ancestor contexts. As a result of this, if your application uses a hierarchy of SpringApplication instances, a listener may receive multiple instances of the same type of application event.

To allow your listener to distinguish between an event for its context and an event for a descendant context, it should request that its application context is injected and then compare the injected context with the context of the event. The context can be injected by implementing ApplicationContextAware or, if the listener is a bean, by using @Autowired.

23.6 Web Environment
A SpringApplication attempts to create the right type of ApplicationContext on your behalf. By default, an AnnotationConfigApplicationContext or AnnotationConfigServletWebServerApplicationContext is used, depending on whether you are developing a web application or not.

The algorithm used to determine a “web environment” is fairly simplistic (it is based on the presence of a few classes). If you need to override the default, you can use setWebEnvironment(boolean webEnvironment).

It is also possible to take complete control of the ApplicationContext type that is used by calling setApplicationContextClass(…​).

[Tip]
It is often desirable to call setWebEnvironment(false) when using SpringApplication within a JUnit test.

23.7 Accessing Application Arguments
If you need to access the application arguments that were passed to SpringApplication.run(…​), you can inject a org.springframework.boot.ApplicationArguments bean. The ApplicationArguments interface provides access to both the raw String[] arguments as well as parsed option and non-option arguments, as shown in the following example:

import org.springframework.boot.*
import org.springframework.beans.factory.annotation.*
import org.springframework.stereotype.*

@Component
public class MyBean {

	@Autowired
	public MyBean(ApplicationArguments args) {
		boolean debug = args.containsOption("debug");
		List<String> files = args.getNonOptionArgs();
		// if run with "--debug logfile.txt" debug=true, files=["logfile.txt"]
	}

}
[Tip]
Spring Boot also registers a CommandLinePropertySource with the Spring Environment. This lets you also inject single application arguments by using the @Value annotation.

23.8 Using the ApplicationRunner or CommandLineRunner
If you need to run some specific code once the SpringApplication has started, you can implement the ApplicationRunner or CommandLineRunner interfaces. Both interfaces work in the same way and offer a single run method, which is called just before SpringApplication.run(…​) completes.

The CommandLineRunner interfaces provides access to application arguments as a simple string array, whereas the ApplicationRunner uses the ApplicationArguments interface discussed earlier. The following example shows a CommandLineRunner with a run method:

import org.springframework.boot.*
import org.springframework.stereotype.*

@Component
public class MyBean implements CommandLineRunner {

	public void run(String... args) {
		// Do something...
	}

}
If several CommandLineRunner or ApplicationRunner beans are defined that must be called in a specific order, you can additionally implement the org.springframework.core.Ordered interface or use the org.springframework.core.annotation.Order annotation.

23.9 Application Exit
Each SpringApplication registers a shutdown hook with the JVM to ensure that the ApplicationContext closes gracefully on exit. All the standard Spring lifecycle callbacks (such as the DisposableBean interface or the @PreDestroy annotation) can be used.

In addition, beans may implement the org.springframework.boot.ExitCodeGenerator interface if they wish to return a specific exit code when SpringApplication.exit() is called. This exit code can then be passed to System.exit() to return it as a status code, as shown in the following example:

@SpringBootApplication
public class ExitCodeApplication {

	@Bean
	public ExitCodeGenerator exitCodeGenerator() {
		return () -> 42;
	}

	public static void main(String[] args) {
		System.exit(SpringApplication
				.exit(SpringApplication.run(ExitCodeApplication.class, args)));
	}

}
Also, the ExitCodeGenerator interface may be implemented by exceptions. When such an exception is encountered, Spring Boot returns the exit code provided by the implemented getExitCode() method.

23.10 Admin Features
It is possible to enable admin-related features for the application by specifying the spring.application.admin.enabled property. This exposes the SpringApplicationAdminMXBean on the platform MBeanServer. You could use this feature to administer your Spring Boot application remotely. This feature could also be useful for any service wrapper implementation.

[Tip]
If you want to know on which HTTP port the application is running, get the property with a key of local.server.port.

[Caution]	Caution
Take care when enabling this feature, as the MBean exposes a method to shutdown the application.

24. Externalized Configuration
Spring Boot lets you externalize your configuration so that you can work with the same application code in different environments. You can use properties files, YAML files, environment variables, and command-line arguments to externalize configuration. Property values can be injected directly into your beans by using the @Value annotation, accessed through Spring’s Environment abstraction, or be bound to structured objects through @ConfigurationProperties.

Spring Boot uses a very particular PropertySource order that is designed to allow sensible overriding of values. Properties are considered in the following order:

Devtools global settings properties on your home directory (~/.spring-boot-devtools.properties when devtools is active).
@TestPropertySource annotations on your tests.
@SpringBootTest#properties annotation attribute on your tests.
Command line arguments.
Properties from SPRING_APPLICATION_JSON (inline JSON embedded in an environment variable or system property).
ServletConfig init parameters.
ServletContext init parameters.
JNDI attributes from java:comp/env.
Java System properties (System.getProperties()).
OS environment variables.
A RandomValuePropertySource that has properties only in random.*.
Profile-specific application properties outside of your packaged jar (application-{profile}.properties and YAML variants).
Profile-specific application properties packaged inside your jar (application-{profile}.properties and YAML variants).
Application properties outside of your packaged jar (application.properties and YAML variants).
Application properties packaged inside your jar (application.properties and YAML variants).
@PropertySource annotations on your @Configuration classes.
Default properties (specified by setting SpringApplication.setDefaultProperties).
To provide a concrete example, suppose you develop a @Component that uses a name property, as shown in the following example:

import org.springframework.stereotype.*
import org.springframework.beans.factory.annotation.*

@Component
public class MyBean {

    @Value("${name}")
    private String name;

    // ...

}
On your application classpath (for example, inside your jar) you can have an application.properties file that provides a sensible default property value for name. When running in a new environment, an application.properties file can be provided outside of your jar that overrides the name. For one-off testing, you can launch with a specific command line switch (for example, java -jar app.jar --name="Spring").

[Tip]
The SPRING_APPLICATION_JSON properties can be supplied on the command line with an environment variable. For example, you could use the following line in a UN*X shell:

$ SPRING_APPLICATION_JSON='{"acme":{"name":"test"}}' java -jar myapp.jar
In the preceding example, you end up with acme.name=test in the Spring Environment. You can also supply the JSON as spring.application.json in a System property, as shown in the following example:

$ java -Dspring.application.json='{"name":"test"}' -jar myapp.jar
You can also supply the JSON by using a command line argument, as shown in the following example:

$ java -jar myapp.jar --spring.application.json='{"name":"test"}'
You can also supply the JSON as a JNDI variable, as follows: java:comp/env/spring.application.json.

24.1 Configuring Random Values
The RandomValuePropertySource is useful for injecting random values (for example, into secrets or test cases). It can produce integers, longs, uuids, or strings, as shown in the following example:

my.secret=${random.value}
my.number=${random.int}
my.bignumber=${random.long}
my.uuid=${random.uuid}
my.number.less.than.ten=${random.int(10)}
my.number.in.range=${random.int[1024,65536]}
The random.int* syntax is OPEN value (,max) CLOSE where the OPEN,CLOSE are any character and value,max are integers. If max is provided, then value is the minimum value and max is the maximum value (exclusive).

24.2 Accessing Command Line Properties
By default, SpringApplication converts any command line option arguments (that is, arguments starting with --, such as --server.port=9000) to a property and adds them to the Spring Environment. As mentioned previously, command line properties always take precedence over other property sources.

If you do not want command line properties to be added to the Environment, you can disable them by using SpringApplication.setAddCommandLineProperties(false).

24.3 Application Property Files
SpringApplication loads properties from application.properties files in the following locations and adds them to the Spring Environment:

A /config subdirectory of the current directory
The current directory
A classpath /config package
The classpath root
The list is ordered by precedence (properties defined in locations higher in the list override those defined in lower locations).

[Note]
You can also use YAML ('.yml') files as an alternative to '.properties'.

If you do not like application.properties as the configuration file name, you can switch to another file name by specifying a spring.config.name environment property. You can also refer to an explicit location by using the spring.config.location environment property (which is a comma-separated list of directory locations or file paths). The following example shows how to specify a different file name:

$ java -jar myproject.jar --spring.config.name=myproject
The following example shows how to specify two locations:

$ java -jar myproject.jar --spring.config.location=classpath:/default.properties,classpath:/override.properties
[Warning]
spring.config.name and spring.config.location are used very early to determine which files have to be loaded, so they must be defined as an environment property (typically an OS environment variable, a system property, or a command-line argument).

If spring.config.location contains directories (as opposed to files), they should end in / (and, at runtime, be appended with the names generated from spring.config.name before being loaded, including profile-specific file names). Files specified in spring.config.location are used as-is, with no support for profile-specific variants, and are overridden by any profile-specific properties.

Config locations are searched in reverse order. By default, the configured locations are classpath:/,classpath:/config/,file:./,file:./config/. The resulting search order is the following:

file:./config/
file:./
classpath:/config/
classpath:/
When custom config locations are configured by using spring.config.location, they replace the default locations. For example, if spring.config.location is configured with the value classpath:/custom-config/,file:./custom-config/, the search order becomes the following:

file:./custom-config/
classpath:custom-config/
Alternatively, when custom config locations are configured by using spring.config.additional-location, they are used in addition to the default locations. Additional locations are searched before the default locations. For example, if additional locations of classpath:/custom-config/,file:./custom-config/ are configured, the search order becomes the following:

file:./custom-config/
classpath:custom-config/
file:./config/
file:./
classpath:/config/
classpath:/
This search ordering lets you specify default values in one configuration file and then selectively override those values in another. You can provide default values for your application in application.properties (or whatever other basename you choose with spring.config.name) in one of the default locations. These default values can then be overridden at runtime with a different file located in one of the custom locations.

[Note]
If you use environment variables rather than system properties, most operating systems disallow period-separated key names, but you can use underscores instead (for example, SPRING_CONFIG_NAME instead of spring.config.name).

[Note]
If your application runs in a container, then JNDI properties (in java:comp/env) or servlet context initialization parameters can be used instead of, or as well as, environment variables or system properties.

24.4 Profile-specific Properties
In addition to application.properties files, profile-specific properties can also be defined by using the following naming convention: application-{profile}.properties. The Environment has a set of default profiles (by default, [default]) that are used if no active profiles are set. In other words, if no profiles are explicitly activated, then properties from application-default.properties are loaded.

Profile-specific properties are loaded from the same locations as standard application.properties, with profile-specific files always overriding the non-specific ones, whether or not the profile-specific files are inside or outside your packaged jar.

If several profiles are specified, a last-wins strategy applies. For example, profiles specified by the spring.profiles.active property are added after those configured through the SpringApplication API and therefore take precedence.

[Note]
If you have specified any files in spring.config.location, profile-specific variants of those files are not considered. Use directories in spring.config.location if you want to also use profile-specific properties.

24.5 Placeholders in Properties
The values in application.properties are filtered through the existing Environment when they are used, so you can refer back to previously defined values (for example, from System properties).

app.name=MyApp
app.description=${app.name} is a Spring Boot application
[Tip]
You can also use this technique to create “short” variants of existing Spring Boot properties. See the Section 74.4, “Use ‘Short’ Command Line Arguments” how-to for details.

24.6 Using YAML Instead of Properties
YAML is a superset of JSON and, as such, is a convenient format for specifying hierarchical configuration data. The SpringApplication class automatically supports YAML as an alternative to properties whenever you have the SnakeYAML library on your classpath.

[Note]
If you use “Starters”, SnakeYAML is automatically provided by spring-boot-starter.

24.6.1 Loading YAML
Spring Framework provides two convenient classes that can be used to load YAML documents. The YamlPropertiesFactoryBean loads YAML as Properties and the YamlMapFactoryBean loads YAML as a Map.

For example, consider the following YAML document:

environments:
	dev:
		url: http://dev.example.com
		name: Developer Setup
	prod:
		url: http://another.example.com
		name: My Cool App
The preceding example would be transformed into the following properties:

environments.dev.url=http://dev.example.com
environments.dev.name=Developer Setup
environments.prod.url=http://another.example.com
environments.prod.name=My Cool App
YAML lists are represented as property keys with [index] dereferencers. For example, consider the following YAML:

my:
servers:
	- dev.example.com
	- another.example.com
The preceding example would be transformed into these properties:

my.servers[0]=dev.example.com
my.servers[1]=another.example.com
To bind to properties like that by using the Spring DataBinder utilities (which is what @ConfigurationProperties does), you need to have a property in the target bean of type java.util.List (or Set) and you either need to provide a setter or initialize it with a mutable value. For example, the following example binds to the properties shown previously:

@ConfigurationProperties(prefix="my")
public class Config {

	private List<String> servers = new ArrayList<String>();

	public List<String> getServers() {
		return this.servers;
	}
}
[Note]
When lists are configured in more than one place, overriding works by replacing the entire list. In the preceding example, when my.servers is defined in several places, the entire list from the PropertySource with higher precedence overrides any other configuration for that list. Both comma-separated lists and YAML lists can be used for completely overriding the contents of the list.

24.6.2 Exposing YAML as Properties in the Spring Environment
The YamlPropertySourceLoader class can be used to expose YAML as a PropertySource in the Spring Environment. Doing so lets you use the @Value annotation with placeholders syntax to access YAML properties.

24.6.3 Multi-profile YAML Documents
You can specify multiple profile-specific YAML documents in a single file by using a spring.profiles key to indicate when the document applies, as shown in the following example:

server:
	address: 192.168.1.100
---
spring:
	profiles: development
server:
	address: 127.0.0.1
---
spring:
	profiles: production
server:
	address: 192.168.1.120
In the preceding example, if the development profile is active, the server.address property is 127.0.0.1. Similarly, if the production profile is active, the server.address property is 192.168.1.120. If the development and production profiles are not enabled, then the value for the property is 192.168.1.100.

If none are explicitly active when the application context starts, the default profiles are activated. So, in the following YAML, we set a value for spring.security.user.password that is available only in the "default" profile:

server:
  port: 8000
---
spring:
  profiles: default
  security:
    user:
      password: weak
Whereas, in the following example, the password is always set because it is not attached to any profile, and it would have to be explicitly reset in all other profiles as necessary:

server:
  port: 8000
spring:
  security:
    user:
      password: weak
Spring profiles designated by using the spring.profiles element may optionally be negated by using the ! character. If both negated and non-negated profiles are specified for a single document, at least one non-negated profile must match, and no negated profiles may match.

24.6.4 YAML Shortcomings
YAML files cannot be loaded by using the @PropertySource annotation. So, in the case that you need to load values that way, you need to use a properties file.

24.6.5 Merging YAML Lists
As we showed earlier, any YAML content is ultimately transformed to properties. That process may be counter-intuitive when overriding “list” properties through a profile.

For example, assume a MyPojo object with name and description attributes that are null by default. The following example exposes a list of MyPojo objects from AcmeProperties:

@ConfigurationProperties("acme")
public class AcmeProperties {

	private final List<MyPojo> list = new ArrayList<>();

	public List<MyPojo> getList() {
		return this.list;
	}

}
Consider the following configuration:

acme:
  list:
    - name: my name
      description: my description
---
spring:
  profiles: dev
acme:
  list:
       - name: my another name
If the dev profile is not active, AcmeProperties.list contains one MyPojo entry, as previously defined. If the dev profile is enabled, however, the list still contains only one entry (with a name of my another name and a description of null). This configuration does not add a second MyPojo instance to the list, and it does not merge the items.

When a collection is specified in multiple profiles, the one with the highest priority (and only that one) is used. Consider the following example:

acme:
  list:
	- name: my name
	  description: my description
	- name: another name
	  description: another description
---
spring:
  profiles: dev
acme:
  list:
	 - name: my another name
In the preceding example, if the dev profile is active, AcmeProperties.list contains one MyPojo entry (with a name of my another name and a description of null).

24.7 Type-safe Configuration Properties
Using the @Value("${property}") annotation to inject configuration properties can sometimes be cumbersome, especially if you are working with multiple properties or your data is hierarchical in nature. Spring Boot provides an alternative method of working with properties that lets strongly typed beans govern and validate the configuration of your application, as shown in the following example:

package com.example;

import java.net.InetAddress;
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

import org.springframework.boot.context.properties.ConfigurationProperties;

@ConfigurationProperties("acme")
public class AcmeProperties {

	private boolean enabled;

	private InetAddress remoteAddress;

	private final Security security = new Security();

	public boolean isEnabled() { ... }

	public void setEnabled(boolean enabled) { ... }

	public InetAddress getRemoteAddress() { ... }

	public void setRemoteAddress(InetAddress remoteAddress) { ... }

	public Security getSecurity() { ... }

	public static class Security {

		private String username;

		private String password;

		private List<String> roles = new ArrayList<>(Collections.singleton("USER"));

		public String getUsername() { ... }

		public void setUsername(String username) { ... }

		public String getPassword() { ... }

		public void setPassword(String password) { ... }

		public List<String> getRoles() { ... }

		public void setRoles(List<String> roles) { ... }

	}
}
The preceding POJO defines the following properties:

acme.enabled, with a value of false by default.
acme.remote-address, with a type that can be coerced from String.
acme.security.username, with a nested "security" object whose name is determined by the name of the property. In particular, the return type is not used at all there and could have been SecurityProperties.
acme.security.password.
acme.security.roles, with a collection of String.
[Note]
Getters and setters are usually mandatory, since binding is through standard Java Beans property descriptors, just like in Spring MVC. A setter may be omitted in the following cases:

Maps, as long as they are initialized, need a getter but not necessarily a setter, since they can be mutated by the binder.
Collections and arrays can be accessed either through an index (typically with YAML) or by using a single comma-separated value (properties). In the latter case, a setter is mandatory. We recommend to always add a setter for such types. If you initialize a collection, make sure it is not immutable (as in the preceding example).
If nested POJO properties are initialized (like the Security field in the preceding example), a setter is not required. If you want the binder to create the instance on the fly by using its default constructor, you need a setter.
Some people use Project Lombok to add getters and setters automatically. Make sure that Lombok does not generate any particular constructor for such a type, as it is used automatically by the container to instantiate the object.

[Tip]
See also the differences between @Value and @ConfigurationProperties.

You also need to list the properties classes to register in the @EnableConfigurationProperties annotation, as shown in the following example:

@Configuration
@EnableConfigurationProperties(AcmeProperties.class)
public class MyConfiguration {
}
[Note]
When the @ConfigurationProperties bean is registered that way, the bean has a conventional name: <prefix>-<fqn>, where <prefix> is the environment key prefix specified in the @ConfigurationProperties annotation and <fqn> is the fully qualified name of the bean. If the annotation does not provide any prefix, only the fully qualified name of the bean is used.

The bean name in the example above is acme-com.example.AcmeProperties.

Even if the preceding configuration creates a regular bean for AcmeProperties, we recommend that @ConfigurationProperties only deal with the environment and, in particular, does not inject other beans from the context. Having said that, the @EnableConfigurationProperties annotation is also automatically applied to your project so that any existing bean annotated with @ConfigurationProperties is configured from the Environment. You could shortcut MyConfiguration by making sure AcmeProperties is already a bean, as shown in the following example:

@Component
@ConfigurationProperties(prefix="acme")
public class AcmeProperties {

	// ... see the preceding example

}
This style of configuration works particularly well with the SpringApplication external YAML configuration, as shown in the following example:

# application.yml

acme:
	remote-address: 192.168.1.1
	security:
		username: admin
		roles:
		  - USER
		  - ADMIN

# additional configuration as required
To work with @ConfigurationProperties beans, you can inject them in the same way as any other bean, as shown in the following example:

@Service
public class MyService {

	private final AcmeProperties properties;

	@Autowired
	public MyService(AcmeProperties properties) {
	    this.properties = properties;
	}

 	//...

	@PostConstruct
	public void openConnection() {
		Server server = new Server(this.properties.getRemoteAddress());
		// ...
	}

}
[Tip]
Using @ConfigurationProperties also lets you generate metadata files that can be used by IDEs to offer auto-completion for your own keys. See the Appendix B, Configuration Metadata appendix for details.

24.7.1 Third-party Configuration
As well as using @ConfigurationProperties to annotate a class, you can also use it on public @Bean methods. Doing so can be particularly useful when you want to bind properties to third-party components that are outside of your control.

To configure a bean from the Environment properties, add @ConfigurationProperties to its bean registration, as shown in the following example:

@ConfigurationProperties(prefix = "another")
@Bean
public AnotherComponent anotherComponent() {
	...
}
Any property defined with the another prefix is mapped onto that AnotherComponent bean in manner similar to the preceding AcmeProperties example.

24.7.2 Relaxed Binding
Spring Boot uses some relaxed rules for binding Environment properties to @ConfigurationProperties beans, so there does not need to be an exact match between the Environment property name and the bean property name. Common examples where this is useful include dash-separated environment properties (for example, context-path binds to contextPath), and capitalized environment properties (for example, PORT binds to port).

For example, consider the following @ConfigurationProperties class:

@ConfigurationProperties(prefix="acme.my-project.person")
public class OwnerProperties {

	private String firstName;

	public String getFirstName() {
		return this.firstName;
	}

	public void setFirstName(String firstName) {
		this.firstName = firstName;
	}

}
In the preceding example, the following properties names can all be used:

Table 24.1. relaxed binding

Property	Note
acme.my-project.person.firstName

Standard camel case syntax.

acme.my-project.person.first-name

Kebab case, which is recommended for use in .properties and .yml files.

acme.my-project.person.first_name

Underscore notation, which is an alternative format for use in .properties and .yml files.

ACME_MYPROJECT_PERSON_FIRSTNAME

Upper case format, which is recommended when using system environment variables.


[Note]
The prefix value for the annotation must be in kebab case (lowercase and separated by -, such as acme.my-project.person).

Table 24.2. relaxed binding rules per property source

Property Source	Simple	List
Properties Files

Camel case, kebab case, or underscore notation

Standard list syntax using [ ] or comma-separated values

YAML Files

Camel case, kebab case, or underscore notation

Standard YAML list syntax or comma-separated values

Environment Variables

Upper case format with underscore as the delimiter. _ should not be used within a property name

Numeric values surrounded by underscores, such as MY_ACME_1_OTHER = my.acme[1].other

System properties

Camel case, kebab case, or underscore notation

Standard list syntax using [ ] or comma-separated values


[Tip]
We recommend that, when possible, properties are stored in lower-case kebab format, such as my.property-name=acme.

24.7.3 Properties Conversion
Spring Boot attempts to coerce the external application properties to the right type when it binds to the @ConfigurationProperties beans. If you need custom type conversion, you can provide a ConversionService bean (with a bean named conversionService) or custom property editors (through a CustomEditorConfigurer bean) or custom Converters (with bean definitions annotated as @ConfigurationPropertiesBinding).

[Note]
As this bean is requested very early during the application lifecycle, make sure to limit the dependencies that your ConversionService is using. Typically, any dependency that you require may not be fully initialized at creation time. You may want to rename your custom ConversionService if it is not required for configuration keys coercion and only rely on custom converters qualified with @ConfigurationPropertiesBinding.

Converting durations
Spring Boot has dedicated support for expressing durations. If you expose a java.time.Duration property, the following formats in application properties are available:

A regular long representation (using milliseconds as the default unit unless a @DefaultUnit has been specified)
The standard ISO-8601 format used by java.util.Duration
A more readable format where the value and the unit are coupled (e.g. 10s means 10 seconds)
Consider the following example:

@ConfigurationProperties("app.system")
public class AppSystemProperties {

	@DurationUnit(ChronoUnit.SECONDS)
	private Duration sessionTimeout = Duration.ofSeconds(30);

	private Duration readTimeout = Duration.ofMillis(1000);

	public Duration getSessionTimeout() {
		return this.sessionTimeout;
	}

	public void setSessionTimeout(Duration sessionTimeout) {
		this.sessionTimeout = sessionTimeout;
	}

	public Duration getReadTimeout() {
		return this.readTimeout;
	}

	public void setReadTimeout(Duration readTimeout) {
		this.readTimeout = readTimeout;
	}

}
To specify a session timeout of 30 seconds, 30, PT30S and 30s are all equivalent. A read timeout of 500ms can be specified in any of the following form: 500, PT0.5S and 500ms.

You can also use any of the supported unit. These are:

ns for nanoseconds
ms for milliseconds
s for seconds
m for minutes
h for hours
d for days
The default unit is milliseconds and can be overridden using @DefaultUnit as illustrated in the sample above.

[Tip]
If you are upgrading from a previous version that is simply using Long to express the duration, make sure to define the unit (using @DefaultUnit) if it isn’t milliseconds alongside the switch to Duration. Doing so gives a transparent upgrade path while supporting a much richer format.

24.7.4 @ConfigurationProperties Validation
Spring Boot attempts to validate @ConfigurationProperties classes whenever they are annotated with Spring’s @Validated annotation. You can use JSR-303 javax.validation constraint annotations directly on your configuration class. To do so, ensure that a compliant JSR-303 implementation is on your classpath and then add constraint annotations to your fields, as shown in the following example:

@ConfigurationProperties(prefix="acme")
@Validated
public class AcmeProperties {

	@NotNull
	private InetAddress remoteAddress;

	// ... getters and setters

}
[Tip]
You can also trigger validation by annotating the @Bean method that creates the configuration properties with @Validated.

Although nested properties will also be validated when bound, it’s good practice to also annotate the associated field as @Valid. This ensure that validation is triggered even if no nested properties are found. The following example builds on the preceding AcmeProperties example:

@ConfigurationProperties(prefix="acme")
@Validated
public class AcmeProperties {

	@NotNull
	private InetAddress remoteAddress;

	@Valid
	private final Security security = new Security();

	// ... getters and setters

	public static class Security {

		@NotEmpty
		public String username;

		// ... getters and setters

	}

}
You can also add a custom Spring Validator by creating a bean definition called configurationPropertiesValidator. The @Bean method should be declared static. The configuration properties validator is created very early in the application’s lifecycle, and declaring the @Bean method as static lets the bean be created without having to instantiate the @Configuration class. Doing so avoids any problems that may be caused by early instantiation. There is a property validation sample that shows how to set things up.

[Tip]
The spring-boot-actuator module includes an endpoint that exposes all @ConfigurationProperties beans. Point your web browser to /actuator/configprops or use the equivalent JMX endpoint. See the "Production ready features" section for details.

24.7.5 @ConfigurationProperties vs. @Value
The @Value annotation is a core container feature, and it does not provide the same features as type-safe configuration properties. The following table summarizes the features that are supported by @ConfigurationProperties and @Value:

Feature	@ConfigurationProperties	@Value
Relaxed binding

Yes

No

Meta-data support

Yes

No

SpEL evaluation

No

Yes

If you define a set of configuration keys for your own components, we recommend you group them in a POJO annotated with @ConfigurationProperties. You should also be aware that, since @Value does not support relaxed binding, it is not a good candidate if you need to provide the value by using environment variables.

Finally, while you can write a SpEL expression in @Value, such expressions are not processed from application property files.

25. Profiles
Spring Profiles provide a way to segregate parts of your application configuration and make it be available only in certain environments. Any @Component or @Configuration can be marked with @Profile to limit when it is loaded, as shown in the following example:

@Configuration
@Profile("production")
public class ProductionConfiguration {

	// ...

}
You can use a spring.profiles.active Environment property to specify which profiles are active. You can specify the property in any of the ways described earlier in this chapter. For example, you could include it in your application.properties, as shown in the following example:

spring.profiles.active=dev,hsqldb
You could also specify it on the command line by using the following switch: --spring.profiles.active=dev,hsqldb.

25.1 Adding Active Profiles
The spring.profiles.active property follows the same ordering rules as other properties: The highest PropertySource wins. This means that you can specify active profiles in application.properties and then replace them by using the command line switch.

Sometimes, it is useful to have profile-specific properties that add to the active profiles rather than replace them. The spring.profiles.include property can be used to unconditionally add active profiles. The SpringApplication entry point also has a Java API for setting additional profiles (that is, on top of those activated by the spring.profiles.active property). See the setAdditionalProfiles() method in SpringApplication.

For example, when an application with the following properties is run by using the switch, --spring.profiles.active=prod, the proddb and prodmq profiles are also activated:

---
my.property: fromyamlfile
---
spring.profiles: prod
spring.profiles.include:
  - proddb
  - prodmq
[Note]
Remember that the spring.profiles property can be defined in a YAML document to determine when this particular document is included in the configuration. See Section 74.7, “Change Configuration Depending on the Environment” for more details.

25.2 Programmatically Setting Profiles
You can programmatically set active profiles by calling SpringApplication.setAdditionalProfiles(…​) before your application runs. It is also possible to activate profiles by using Spring’s ConfigurableEnvironment interface.

25.3 Profile-specific Configuration Files
Profile-specific variants of both application.properties (or application.yml) and files referenced through @ConfigurationProperties are considered as files and loaded. See "Section 24.4, “Profile-specific Properties”" for details.

26. Logging
Spring Boot uses Commons Logging for all internal logging but leaves the underlying log implementation open. Default configurations are provided for Java Util Logging, Log4J2, and Logback. In each case, loggers are pre-configured to use console output with optional file output also available.

By default, if you use the “Starters”, Logback is used for logging. Appropriate Logback routing is also included to ensure that dependent libraries that use Java Util Logging, Commons Logging, Log4J, or SLF4J all work correctly.

[Tip]
There are a lot of logging frameworks available for Java. Do not worry if the above list seems confusing. Generally, you do not need to change your logging dependencies and the Spring Boot defaults work just fine.

26.1 Log Format
The default log output from Spring Boot resembles the following example:

2014-03-05 10:57:51.112  INFO 45469 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet Engine: Apache Tomcat/7.0.52
2014-03-05 10:57:51.253  INFO 45469 --- [ost-startStop-1] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2014-03-05 10:57:51.253  INFO 45469 --- [ost-startStop-1] o.s.web.context.ContextLoader            : Root WebApplicationContext: initialization completed in 1358 ms
2014-03-05 10:57:51.698  INFO 45469 --- [ost-startStop-1] o.s.b.c.e.ServletRegistrationBean        : Mapping servlet: 'dispatcherServlet' to [/]
2014-03-05 10:57:51.702  INFO 45469 --- [ost-startStop-1] o.s.b.c.embedded.FilterRegistrationBean  : Mapping filter: 'hiddenHttpMethodFilter' to: [/*]
The following items are output:

Date and Time: Millisecond precision and easily sortable.
Log Level: ERROR, WARN, INFO, DEBUG, or TRACE.
Process ID.
A --- separator to distinguish the start of actual log messages.
Thread name: Enclosed in square brackets (may be truncated for console output).
Logger name: This is usually the source class name (often abbreviated).
The log message.
[Note]
Logback does not have a FATAL level. It is mapped to ERROR.

26.2 Console Output
The default log configuration echoes messages to the console as they are written. By default, ERROR-level, WARN-level, and INFO-level messages are logged. You can also enable a “debug” mode by starting your application with a --debug flag.

$ java -jar myapp.jar --debug
[Note]
You can also specify debug=true in your application.properties.

When the debug mode is enabled, a selection of core loggers (embedded container, Hibernate, and Spring Boot) are configured to output more information. Enabling the debug mode does not configure your application to log all messages with DEBUG level.

Alternatively, you can enable a “trace” mode by starting your application with a --trace flag (or trace=true in your application.properties). Doing so enables trace logging for a selection of core loggers (embedded container, Hibernate schema generation, and the whole Spring portfolio).

26.2.1 Color-coded Output
If your terminal supports ANSI, color output is used to aid readability. You can set spring.output.ansi.enabled to a supported value to override the auto detection.

Color coding is configured by using the %clr conversion word. In its simplest form, the converter colors the output according to the log level, as shown in the following example:

%clr(%5p)
The following table describes the mapping of log levels to colors:

Level	Color
FATAL

Red

ERROR

Red

WARN

Yellow

INFO

Green

DEBUG

Green

TRACE

Green

Alternatively, you can specify the color or style that should be used by providing it as an option to the conversion. For example, to make the text yellow, use the following setting:

%clr(%d{yyyy-MM-dd HH:mm:ss.SSS}){yellow}
The following colors and styles are supported:

blue
cyan
faint
green
magenta
red
yellow
26.3 File Output
By default, Spring Boot logs only to the console and does not write log files. If you want to write log files in addition to the console output, you need to set a logging.file or logging.path property (for example, in your application.properties).

The following table shows how the logging.* properties can be used together:

Table 26.1. Logging properties

logging.file	logging.path	Example	Description
(none)

(none)

 	
Console only logging.

Specific file

(none)

my.log

Writes to the specified log file. Names can be an exact location or relative to the current directory.

(none)

Specific directory

/var/log

Writes spring.log to the specified directory. Names can be an exact location or relative to the current directory.


Log files rotate when they reach 10 MB and, as with console output, ERROR-level, WARN-level, and INFO-level messages are logged by default. Size limits can be changed using the logging.file.max-size property. Previously rotated files are archived indefinitely unless the logging.file.max-history property has been set.

[Note]
The logging system is initialized early in the application lifecycle. Consequently, logging properties are not found in property files loaded through @PropertySource annotations.

[Tip]
Logging properties are independent of the actual logging infrastructure. As a result, specific configuration keys (such as logback.configurationFile for Logback) are not managed by spring Boot.

26.4 Log Levels
All the supported logging systems can have the logger levels set in the Spring Environment (for example, in application.properties) by using logging.level.<logger-name>=<level> where level is one of TRACE, DEBUG, INFO, WARN, ERROR, FATAL, or OFF. The root logger can be configured by using logging.level.root.

The following example shows potential logging settings in application.properties:

logging.level.root=WARN
logging.level.org.springframework.web=DEBUG
logging.level.org.hibernate=ERROR
26.5 Custom Log Configuration
The various logging systems can be activated by including the appropriate libraries on the classpath and can be further customized by providing a suitable configuration file in the root of the classpath or in a location specified by the following Spring Environment property: logging.config.

You can force Spring Boot to use a particular logging system by using the org.springframework.boot.logging.LoggingSystem system property. The value should be the fully qualified class name of a LoggingSystem implementation. You can also disable Spring Boot’s logging configuration entirely by using a value of none.

[Note]
Since logging is initialized before the ApplicationContext is created, it is not possible to control logging from @PropertySources in Spring @Configuration files. System properties and the conventional Spring Boot external configuration files work fine.)

Depending on your logging system, the following files are loaded:

Logging System	Customization
Logback

logback-spring.xml, logback-spring.groovy, logback.xml, or logback.groovy

Log4j2

log4j2-spring.xml or log4j2.xml

JDK (Java Util Logging)

logging.properties

[Note]
When possible, we recommend that you use the -spring variants for your logging configuration (for example, logback-spring.xml rather than logback.xml). If you use standard configuration locations, Spring cannot completely control log initialization.

[Warning]
There are known classloading issues with Java Util Logging that cause problems when running from an 'executable jar'. We recommend that you avoid it when running from an 'executable jar' if at all possible.

To help with the customization, some other properties are transferred from the Spring Environment to System properties, as described in the following table:

Spring Environment	System Property	Comments
logging.exception-conversion-word

LOG_EXCEPTION_CONVERSION_WORD

The conversion word used when logging exceptions.

logging.file

LOG_FILE

If defined, it is used in the default log configuration.

logging.file.max-size

LOG_FILE_MAX_SIZE

Maximum log file size (if LOG_FILE enabled). (Only supported with the default Logback setup.)

logging.file.max-history

LOG_FILE_MAX_HISTORY

Maximum number of archive log files to keep (if LOG_FILE enabled). (Only supported with the default Logback setup.)

logging.path

LOG_PATH

If defined, it is used in the default log configuration.

logging.pattern.console

CONSOLE_LOG_PATTERN

The log pattern to use on the console (stdout). (Only supported with the default Logback setup.)

logging.pattern.dateformat

LOG_DATEFORMAT_PATTERN

Appender pattern for log date format. (Only supported with the default Logback setup.)

logging.pattern.file

FILE_LOG_PATTERN

The log pattern to use in a file (if LOG_FILE is enabled). (Only supported with the default Logback setup.)

logging.pattern.level

LOG_LEVEL_PATTERN

The format to use when rendering the log level (default %5p). (Only supported with the default Logback setup.)

PID

PID

The current process ID (discovered if possible and when not already defined as an OS environment variable).

All the supported logging systems can consult System properties when parsing their configuration files. See the default configurations in spring-boot.jar for examples:

Logback
Log4j 2
Java Util logging
[Tip]
If you want to use a placeholder in a logging property, you should use Spring Boot’s syntax and not the syntax of the underlying framework. Notably, if you use Logback, you should use : as the delimiter between a property name and its default value and not use :-.

[Tip]
You can add MDC and other ad-hoc content to log lines by overriding only the LOG_LEVEL_PATTERN (or logging.pattern.level with Logback). For example, if you use logging.pattern.level=user:%X{user} %5p, then the default log format contains an MDC entry for "user", if it exists, as shown in the following example.

2015-09-30 12:30:04.031 user:someone INFO 22174 --- [  nio-8080-exec-0] demo.Controller
Handling authenticated request
26.6 Logback Extensions
Spring Boot includes a number of extensions to Logback that can help with advanced configuration. You can use these extensions in your logback-spring.xml configuration file.

[Note]
Because the standard logback.xml configuration file is loaded too early, you cannot use extensions in it. You need to either use logback-spring.xml or define a logging.config property.

[Warning]
The extensions cannot be used with Logback’s configuration scanning. If you attempt to do so, making changes to the configuration file results in an error similar to one of the following being logged:

ERROR in ch.qos.logback.core.joran.spi.Interpreter@4:71 - no applicable action for [springProperty], current ElementPath is [[configuration][springProperty]]
ERROR in ch.qos.logback.core.joran.spi.Interpreter@4:71 - no applicable action for [springProfile], current ElementPath is [[configuration][springProfile]]
26.6.1 Profile-specific Configuration
The <springProfile> tag lets you optionally include or exclude sections of configuration based on the active Spring profiles. Profile sections are supported anywhere within the <configuration> element. Use the name attribute to specify which profile accepts the configuration. Multiple profiles can be specified with a comma-separated list. The following listing shows three sample profiles:

<springProfile name="staging">
	<!-- configuration to be enabled when the "staging" profile is active -->
</springProfile>

<springProfile name="dev, staging">
	<!-- configuration to be enabled when the "dev" or "staging" profiles are active -->
</springProfile>

<springProfile name="!production">
	<!-- configuration to be enabled when the "production" profile is not active -->
</springProfile>
26.6.2 Environment Properties
The <springProperty> tag lets you expose properties from the Spring Environment for use within Logback. Doing so can be useful if you want to access values from your application.properties file in your Logback configuration. The tag works in a similar way to Logback’s standard <property> tag. However, rather than specifying a direct value, you specify the source of the property (from the Environment). If you need to store the property somewhere other than in local scope, you can use the scope attribute. If you need a fallback value (in case the property is not set in the Environment), you can use the defaultValue attribute. The following example shows how to expose properties for use within Logback:

<springProperty scope="context" name="fluentHost" source="myapp.fluentd.host"
		defaultValue="localhost"/>
<appender name="FLUENT" class="ch.qos.logback.more.appenders.DataFluentAppender">
	<remoteHost>${fluentHost}</remoteHost>
	...
</appender>
[Note]
The source must be specified in kebab case (such as my.property-name). However, properties can be added to the Environment by using the relaxed rules.

27. Developing Web Applications
Spring Boot is well suited for web application development. You can create a self-contained HTTP server by using embedded Tomcat, Jetty, Undertow, or Netty. Most web applications use the spring-boot-starter-web module to get up and running quickly. You can also choose to build reactive web applications by using the spring-boot-starter-webflux module.

If you have not yet developed a Spring Boot web application, you can follow the "Hello World!" example in the Getting started section.

27.1 The “Spring Web MVC Framework”
The Spring Web MVC framework (often referred to as simply “Spring MVC”) is a rich “model view controller” web framework. Spring MVC lets you create special @Controller or @RestController beans to handle incoming HTTP requests. Methods in your controller are mapped to HTTP by using @RequestMapping annotations.

The following code shows a typical @RestController that serves JSON data:

@RestController
@RequestMapping(value="/users")
public class MyRestController {

	@RequestMapping(value="/{user}", method=RequestMethod.GET)
	public User getUser(@PathVariable Long user) {
		// ...
	}

	@RequestMapping(value="/{user}/customers", method=RequestMethod.GET)
	List<Customer> getUserCustomers(@PathVariable Long user) {
		// ...
	}

	@RequestMapping(value="/{user}", method=RequestMethod.DELETE)
	public User deleteUser(@PathVariable Long user) {
		// ...
	}

}
Spring MVC is part of the core Spring Framework, and detailed information is available in the reference documentation. There are also several guides that cover Spring MVC available at spring.io/guides.

27.1.1 Spring MVC Auto-configuration
Spring Boot provides auto-configuration for Spring MVC that works well with most applications.

The auto-configuration adds the following features on top of Spring’s defaults:

Inclusion of ContentNegotiatingViewResolver and BeanNameViewResolver beans.
Support for serving static resources, including support for WebJars (covered later in this document)).
Automatic registration of Converter, GenericConverter, and Formatter beans.
Support for HttpMessageConverters (covered later in this document).
Automatic registration of MessageCodesResolver (covered later in this document).
Static index.html support.
Custom Favicon support (covered later in this document).
Automatic use of a ConfigurableWebBindingInitializer bean (covered later in this document).
If you want to keep Spring Boot MVC features and you want to add additional MVC configuration (interceptors, formatters, view controllers, and other features), you can add your own @Configuration class of type WebMvcConfigurer but without @EnableWebMvc. If you wish to provide custom instances of RequestMappingHandlerMapping, RequestMappingHandlerAdapter, or ExceptionHandlerExceptionResolver, you can declare a WebMvcRegistrationsAdapter instance to provide such components.

If you want to take complete control of Spring MVC, you can add your own @Configuration annotated with @EnableWebMvc.

27.1.2 HttpMessageConverters
Spring MVC uses the HttpMessageConverter interface to convert HTTP requests and responses. Sensible defaults are included out of the box. For example, objects can be automatically converted to JSON (by using the Jackson library) or XML (by using the Jackson XML extension, if available, or by using JAXB if the Jackson XML extension is not available). By default, strings are encoded in UTF-8.

If you need to add or customize converters, you can use Spring Boot’s HttpMessageConverters class, as shown in the following listing:

import org.springframework.boot.autoconfigure.web.HttpMessageConverters;
import org.springframework.context.annotation.*;
import org.springframework.http.converter.*;

@Configuration
public class MyConfiguration {

	@Bean
	public HttpMessageConverters customConverters() {
		HttpMessageConverter<?> additional = ...
		HttpMessageConverter<?> another = ...
		return new HttpMessageConverters(additional, another);
	}

}
Any HttpMessageConverter bean that is present in the context is added to the list of converters. You can also override default converters in the same way.

27.1.3 Custom JSON Serializers and Deserializers
If you use Jackson to serialize and deserialize JSON data, you might want to write your own JsonSerializer and JsonDeserializer classes. Custom serializers are usually registered with Jackson through a module, but Spring Boot provides an alternative @JsonComponent annotation that makes it easier to directly register Spring Beans.

You can use the @JsonComponent annotation directly on JsonSerializer or JsonDeserializer implementations. You can also use it on classes that contain serializers/deserializers as inner classes, as shown in the following example:

import java.io.*;
import com.fasterxml.jackson.core.*;
import com.fasterxml.jackson.databind.*;
import org.springframework.boot.jackson.*;

@JsonComponent
public class Example {

	public static class Serializer extends JsonSerializer<SomeObject> {
		// ...
	}

	public static class Deserializer extends JsonDeserializer<SomeObject> {
		// ...
	}

}
All @JsonComponent beans in the ApplicationContext are automatically registered with Jackson. Because @JsonComponent is meta-annotated with @Component, the usual component-scanning rules apply.

Spring Boot also provides JsonObjectSerializer and JsonObjectDeserializer base classes that provide useful alternatives to the standard Jackson versions when serializing objects. See JsonObjectSerializer and JsonObjectDeserializer in the Javadoc for details.

27.1.4 MessageCodesResolver
Spring MVC has a strategy for generating error codes for rendering error messages from binding errors: MessageCodesResolver. If you set the spring.mvc.message-codes-resolver.format property PREFIX_ERROR_CODE or POSTFIX_ERROR_CODE, Spring Boot creates one for you (see the enumeration in DefaultMessageCodesResolver.Format).

27.1.5 Static Content
By default, Spring Boot serves static content from a directory called /static (or /public or /resources or /META-INF/resources) in the classpath or from the root of the ServletContext. It uses the ResourceHttpRequestHandler from Spring MVC so that you can modify that behavior by adding your own WebMvcConfigurer and overriding the addResourceHandlers method.

In a stand-alone web application, the default servlet from the container is also enabled and acts as a fallback, serving content from the root of the ServletContext if Spring decides not to handle it. Most of the time, this does not happen (unless you modify the default MVC configuration), because Spring can always handle requests through the DispatcherServlet.

By default, resources are mapped on /**, but you can tune that with the spring.mvc.static-path-pattern property. For instance, relocating all resources to /resources/** can be achieved as follows:

spring.mvc.static-path-pattern=/resources/**
You can also customize the static resource locations by using the spring.resources.static-locations property (replacing the default values with a list of directory locations). The root Servlet context path, "/", is automatically added as a location as well.

In addition to the “standard” static resource locations mentioned earlier, a special case is made for Webjars content. Any resources with a path in /webjars/** are served from jar files if they are packaged in the Webjars format.

[Tip]
Do not use the src/main/webapp directory if your application is packaged as a jar. Although this directory is a common standard, it works only with war packaging, and it is silently ignored by most build tools if you generate a jar.

Spring Boot also supports the advanced resource handling features provided by Spring MVC, allowing use cases such as cache-busting static resources or using version agnostic URLs for Webjars.

To use version agnostic URLs for Webjars, add the webjars-locator-core dependency. Then declare your Webjar. Using jQuery as an example, adding "/webjars/jquery/dist/jquery.min.js" results in "/webjars/jquery/x.y.z/dist/jquery.min.js". where x.y.z is the Webjar version.

[Note]
If you use JBoss, you need to declare the webjars-locator-jboss-vfs dependency instead of the webjars-locator-core. Otherwise, all Webjars resolve as a 404.

To use cache busting, the following configuration configures a cache busting solution for all static resources, effectively adding a content hash, such as <link href="/css/spring-2a2d595e6ed9a0b24f027f2b63b134d6.css"/>, in URLs:

spring.resources.chain.strategy.content.enabled=true
spring.resources.chain.strategy.content.paths=/**
[Note]
Links to resources are rewritten in templates at runtime, thanks to a ResourceUrlEncodingFilter that is auto-configured for Thymeleaf and FreeMarker. You should manually declare this filter when using JSPs. Other template engines are currently not automatically supported but can be with custom template macros/helpers and the use of the ResourceUrlProvider.

When loading resources dynamically with, for example, a JavaScript module loader, renaming files is not an option. That is why other strategies are also supported and can be combined. A "fixed" strategy adds a static version string in the URL without changing the file name, as shown in the following example:

spring.resources.chain.strategy.content.enabled=true
spring.resources.chain.strategy.content.paths=/**
spring.resources.chain.strategy.fixed.enabled=true
spring.resources.chain.strategy.fixed.paths=/js/lib/
spring.resources.chain.strategy.fixed.version=v12
With this configuration, JavaScript modules located under "/js/lib/" use a fixed versioning strategy ("/v12/js/lib/mymodule.js"), while other resources still use the content one (<link href="/css/spring-2a2d595e6ed9a0b24f027f2b63b134d6.css"/>).

See ResourceProperties for more supported options.

[Tip]
This feature has been thoroughly described in a dedicated blog post and in Spring Framework’s reference documentation.

27.1.6 Welcome Page
Spring Boot supports both static and templated welcome pages. It first looks for an index.html file in the configured static content locations. If one is not found, it then looks for an index template. If either is found, it is automatically used as the welcome page of the application.

27.1.7 Custom Favicon
Spring Boot looks for a favicon.ico in the configured static content locations and the root of the classpath (in that order). If such a file is present, it is automatically used as the favicon of the application.

27.1.8 Path Matching and Content Negotiation
Spring MVC can map incoming HTTP requests to handlers by looking at the request path and matching it to the mappings defined in your application (for example, @GetMapping annotations on Controller methods).

Spring Boot chooses to disable suffix pattern matching by default, which means that requests like "GET /projects/spring-boot.json" won’t be matched to @GetMapping("/projects/spring-boot") mappings. This is considered as a best practice for Spring MVC applications. This feature was mainly useful in the past for HTTP clients which did not send proper "Accept" request headers; we needed to make sure to send the correct Content Type to the client. Nowadays, Content Negotiation is much more reliable.

There are other ways to deal with HTTP clients that don’t consistently send proper "Accept" request headers. Instead of using suffix matching, we can use a query parameter to ensure that requests like "GET /projects/spring-boot?format=json" will be mapped to @GetMapping("/projects/spring-boot"):

spring.mvc.contentnegotiation.favor-parameter=true

# We can change the parameter name, which is "format" by default:
# spring.mvc.contentnegotiation.parameter-name=myparam

# We can also register additional file extensions/media types with:
spring.mvc.contentnegotiation.media-types.markdown=text/markdown
If you understand the caveats and would still like your application to use suffix pattern matching, the following configuration is required:

spring.mvc.contentnegotiation.favor-path-extension=true

# You can also restrict that feature to known extensions only
# spring.mvc.pathmatch.use-registered-suffix-pattern=true

# We can also register additional file extensions/media types with:
# spring.mvc.contentnegotiation.media-types.adoc=text/asciidoc
27.1.9 ConfigurableWebBindingInitializer
Spring MVC uses a WebBindingInitializer to initialize a WebDataBinder for a particular request. If you create your own ConfigurableWebBindingInitializer @Bean, Spring Boot automatically configures Spring MVC to use it.

27.1.10 Template Engines
As well as REST web services, you can also use Spring MVC to serve dynamic HTML content. Spring MVC supports a variety of templating technologies, including Thymeleaf, FreeMarker, and JSPs. Also, many other templating engines include their own Spring MVC integrations.

Spring Boot includes auto-configuration support for the following templating engines:

FreeMarker
Groovy
Thymeleaf
Mustache
[Tip]
If possible, JSPs should be avoided. There are several known limitations when using them with embedded servlet containers.

When you use one of these templating engines with the default configuration, your templates are picked up automatically from src/main/resources/templates.

[Tip]
Depending on how you run your application, IntelliJ IDEA orders the classpath differently. Running your application in the IDE from its main method results in a different ordering than when you run your application by using Maven or Gradle or from its packaged jar. This can cause Spring Boot to fail to find the templates on the classpath. If you have this problem, you can reorder the classpath in the IDE to place the module’s classes and resources first. Alternatively, you can configure the template prefix to search every templates directory on the classpath, as follows: classpath*:/templates/.

27.1.11 Error Handling
By default, Spring Boot provides an /error mapping that handles all errors in a sensible way, and it is registered as a “global” error page in the servlet container. For machine clients, it produces a JSON response with details of the error, the HTTP status, and the exception message. For browser clients, there is a “whitelabel” error view that renders the same data in HTML format (to customize it, add a View that resolves to error). To replace the default behavior completely, you can implement ErrorController and register a bean definition of that type or add a bean of type ErrorAttributes to use the existing mechanism but replace the contents.

[Tip]
The BasicErrorController can be used as a base class for a custom ErrorController. This is particularly useful if you want to add a handler for a new content type (the default is to handle text/html specifically and provide a fallback for everything else). To do so, extend BasicErrorController, add a public method with a @RequestMapping that has a produces attribute, and create a bean of your new type.

You can also define a class annotated with @ControllerAdvice to customize the JSON document to return for a particular controller and/or exception type, as shown in the following example:

@ControllerAdvice(basePackageClasses = AcmeController.class)
public class AcmeControllerAdvice extends ResponseEntityExceptionHandler {

	@ExceptionHandler(YourException.class)
	@ResponseBody
	ResponseEntity<?> handleControllerException(HttpServletRequest request, Throwable ex) {
		HttpStatus status = getStatus(request);
		return new ResponseEntity<>(new CustomErrorType(status.value(), ex.getMessage()), status);
	}

	private HttpStatus getStatus(HttpServletRequest request) {
		Integer statusCode = (Integer) request.getAttribute("javax.servlet.error.status_code");
		if (statusCode == null) {
			return HttpStatus.INTERNAL_SERVER_ERROR;
		}
		return HttpStatus.valueOf(statusCode);
	}

}
In the preceding example, if YourException is thrown by a controller defined in the same package as AcmeController, a JSON representation of the CustomErrorType POJO is used instead of the ErrorAttributes representation.

Custom Error Pages
If you want to display a custom HTML error page for a given status code, you can add a file to an /error folder. Error pages can either be static HTML (that is, added under any of the static resource folders) or be built by using templates. The name of the file should be the exact status code or a series mask.

For example, to map 404 to a static HTML file, your folder structure would be as follows:

src/
 +- main/
     +- java/
     |   + <source code>
     +- resources/
         +- public/
             +- error/
             |   +- 404.html
             +- <other public assets>
To map all 5xx errors by using a FreeMarker template, your folder structure would be as follows:

src/
 +- main/
     +- java/
     |   + <source code>
     +- resources/
         +- templates/
             +- error/
             |   +- 5xx.ftl
             +- <other templates>
For more complex mappings, you can also add beans that implement the ErrorViewResolver interface, as shown in the following example:

public class MyErrorViewResolver implements ErrorViewResolver {

	@Override
	public ModelAndView resolveErrorView(HttpServletRequest request,
			HttpStatus status, Map<String, Object> model) {
		// Use the request or status to optionally return a ModelAndView
		return ...
	}

}
You can also use regular Spring MVC features such as @ExceptionHandler methods and @ControllerAdvice. The ErrorController then picks up any unhandled exceptions.

Mapping Error Pages outside of Spring MVC
For applications that do not use Spring MVC, you can use the ErrorPageRegistrar interface to directly register ErrorPages. This abstraction works directly with the underlying embedded servlet container and works even if you do not have a Spring MVC DispatcherServlet.

@Bean
public ErrorPageRegistrar errorPageRegistrar(){
	return new MyErrorPageRegistrar();
}

// ...

private static class MyErrorPageRegistrar implements ErrorPageRegistrar {

	@Override
	public void registerErrorPages(ErrorPageRegistry registry) {
		registry.addErrorPages(new ErrorPage(HttpStatus.BAD_REQUEST, "/400"));
	}

}
[Note]
If you register an ErrorPage with a path that ends up being handled by a Filter (as is common with some non-Spring web frameworks, like Jersey and Wicket), then the Filter has to be explicitly registered as an ERROR dispatcher, as shown in the following example:

@Bean
public FilterRegistrationBean myFilter() {
	FilterRegistrationBean registration = new FilterRegistrationBean();
	registration.setFilter(new MyFilter());
	...
	registration.setDispatcherTypes(EnumSet.allOf(DispatcherType.class));
	return registration;
}
Note that the default FilterRegistrationBean does not include the ERROR dispatcher type.

CAUTION:When deployed to a servlet container, Spring Boot uses its error page filter to forward a request with an error status to the appropriate error page. The request can only be forwarded to the correct error page if the response has not already been committed. By default, WebSphere Application Server 8.0 and later commits the response upon successful completion of a servlet’s service method. You should disable this behavior by setting com.ibm.ws.webcontainer.invokeFlushAfterService to false.

27.1.12 Spring HATEOAS
If you develop a RESTful API that makes use of hypermedia, Spring Boot provides auto-configuration for Spring HATEOAS that works well with most applications. The auto-configuration replaces the need to use @EnableHypermediaSupport and registers a number of beans to ease building hypermedia-based applications, including a LinkDiscoverers (for client side support) and an ObjectMapper configured to correctly marshal responses into the desired representation. The ObjectMapper is customized by setting the various spring.jackson.* properties or, if one exists, by a Jackson2ObjectMapperBuilder bean.

You can take control of Spring HATEOAS’s configuration by using @EnableHypermediaSupport. Note that doing so disables the ObjectMapper customization described earlier.

27.1.13 CORS Support
Cross-origin resource sharing (CORS) is a W3C specification implemented by most browsers that lets you specify in a flexible way what kind of cross-domain requests are authorized, instead of using some less secure and less powerful approaches such as IFRAME or JSONP.

As of version 4.2, Spring MVC supports CORS. Using controller method CORS configuration with @CrossOrigin annotations in your Spring Boot application does not require any specific configuration. Global CORS configuration can be defined by registering a WebMvcConfigurer bean with a customized addCorsMappings(CorsRegistry) method, as shown in the following example:

@Configuration
public class MyConfiguration {

	@Bean
	public WebMvcConfigurer corsConfigurer() {
		return new WebMvcConfigurer() {
			@Override
			public void addCorsMappings(CorsRegistry registry) {
				registry.addMapping("/api/**");
			}
		};
	}
}
27.2 The “Spring WebFlux Framework”
Spring WebFlux is the new reactive web framework introduced in Spring Framework 5.0. Unlike Spring MVC, it does not require the Servlet API, is fully asynchronous and non-blocking, and implements the Reactive Streams specification through the Reactor project.

Spring WebFlux comes in two flavors: functional and annotation-based. The annotation-based one is quite close to the Spring MVC model, as shown in the following example:

@RestController
@RequestMapping("/users")
public class MyRestController {

	@GetMapping("/{user}")
	public Mono<User> getUser(@PathVariable Long user) {
		// ...
	}

	@GetMapping("/{user}/customers")
	public Flux<Customer> getUserCustomers(@PathVariable Long user) {
		// ...
	}

	@DeleteMapping("/{user}")
	public Mono<User> deleteUser(@PathVariable Long user) {
		// ...
	}

}
“WebFlux.fn”, the functional variant, separates the routing configuration from the actual handling of the requests, as shown in the following example:

@Configuration
public class RoutingConfiguration {

	@Bean
	public RouterFunction<ServerResponse> monoRouterFunction(UserHandler userHandler) {
		return route(GET("/{user}").and(accept(APPLICATION_JSON)), userHandler::getUser)
				.andRoute(GET("/{user}/customers").and(accept(APPLICATION_JSON)), userHandler::getUserCustomers)
				.andRoute(DELETE("/{user}").and(accept(APPLICATION_JSON)), userHandler::deleteUser);
	}

}

@Component
public class UserHandler {

	public Mono<ServerResponse> getUser(ServerRequest request) {
		// ...
	}

	public Mono<ServerResponse> getUserCustomers(ServerRequest request) {
		// ...
	}

	public Mono<ServerResponse> deleteUser(ServerRequest request) {
		// ...
	}
}
WebFlux is part of the Spring Framework and detailed information is available in its reference documentation.

[Tip]
You can define as many RouterFunction beans as you like to modularize the definition of the router. Beans can be ordered if you need to apply a precedence.

To get started, add the spring-boot-starter-webflux module to your application.

[Note]
Adding both spring-boot-starter-web and spring-boot-starter-webflux modules in your application results in Spring Boot auto-configuring Spring MVC, not WebFlux. This behavior has been chosen because many Spring developers add spring-boot-starter-webflux to their Spring MVC application to use the reactive WebClient. You can still enforce your choice by setting the chosen application type to SpringApplication.setWebApplicationType(WebApplicationType.REACTIVE).

27.2.1 Spring WebFlux Auto-configuration
Spring Boot provides auto-configuration for Spring WebFlux that works well with most applications.

The auto-configuration adds the following features on top of Spring’s defaults:

Configuring codecs for HttpMessageReader and HttpMessageWriter instances (described later in this document).
Support for serving static resources, including support for WebJars (described later in this document).
If you want to keep Spring Boot WebFlux features and you want to add additional WebFlux configuration, you can add your own @Configuration class of type WebFluxConfigurer but without @EnableWebFlux.

If you want to take complete control of Spring WebFlux, you can add your own @Configuration annotated with @EnableWebFlux.

27.2.2 HTTP Codecs with HttpMessageReaders and HttpMessageWriters
Spring WebFlux uses the HttpMessageReader and HttpMessageWriter interfaces to convert HTTP requests and responses. They are configured with CodecConfigurer to have sensible defaults by looking at the libraries available in your classpath.

Spring Boot applies further customization by using CodecCustomizer instances. For example, spring.jackson.* configuration keys are applied to the Jackson codec.

If you need to add or customize codecs, you can create a custom CodecCustomizer component, as shown in the following example:

import org.springframework.boot.web.codec.CodecCustomizer;

@Configuration
public class MyConfiguration {

	@Bean
	public CodecCustomizer myCodecCustomizer() {
		return codecConfigurer -> {
			// ...
		}
	}

}
You can also leverage Boot’s custom JSON serializers and deserializers.

27.2.3 Static Content
By default, Spring Boot serves static content from a directory called /static (or /public or /resources or /META-INF/resources) in the classpath. It uses the ResourceWebHandler from Spring WebFlux so that you can modify that behavior by adding your own WebFluxConfigurer and overriding the addResourceHandlers method.

By default, resources are mapped on /**, but you can tune that by setting the spring.webflux.static-path-pattern property. For instance, relocating all resources to /resources/** can be achieved as follows:

spring.webflux.static-path-pattern=/resources/**
You can also customize the static resource locations by using spring.resources.static-locations. Doing so replaces the default values with a list of directory locations. If you do so, the default welcome page detection switches to your custom locations. So, if there is an index.html in any of your locations on startup, it is the home page of the application.

In addition to the “standard” static resource locations listed earlier, a special case is made for Webjars content. Any resources with a path in /webjars/** are served from jar files if they are packaged in the Webjars format.

[Tip]
Spring WebFlux applications do not strictly depend on the Servlet API, so they cannot be deployed as war files and do not use the src/main/webapp directory.

27.2.4 Template Engines
As well as REST web services, you can also use Spring WebFlux to serve dynamic HTML content. Spring WebFlux supports a variety of templating technologies, including Thymeleaf, FreeMarker, and Mustache.

Spring Boot includes auto-configuration support for the following templating engines:

FreeMarker
Thymeleaf
Mustache
When you use one of these templating engines with the default configuration, your templates are picked up automatically from src/main/resources/templates.

27.2.5 Error Handling
Spring Boot provides a WebExceptionHandler that handles all errors in a sensible way. Its position in the processing order is immediately before the handlers provided by WebFlux, which are considered last. For machine clients, it produces a JSON response with details of the error, the HTTP status, and the exception message. For browser clients, there is a “whitelabel” error handler that renders the same data in HTML format. You can also provide your own HTML templates to display errors (see the next section).

The first step to customizing this feature often involves using the existing mechanism but replacing or augmenting the error contents. For that, you can add a bean of type ErrorAttributes.

To change the error handling behavior, you can implement ErrorWebExceptionHandler and register a bean definition of that type. Because a WebExceptionHandler is quite low-level, Spring Boot also provides a convenient AbstractErrorWebExceptionHandler to let you handle errors in a WebFlux functional way, as shown in the following example:

public class CustomErrorWebExceptionHandler extends AbstractErrorWebExceptionHandler {

	// Define constructor here

	@Override
	protected RouterFunction<ServerResponse> getRoutingFunction(ErrorAttributes errorAttributes) {

		return RouterFunctions
				.route(aPredicate, aHandler)
				.andRoute(anotherPredicate, anotherHandler);
	}

}
For a more complete picture, you can also subclass DefaultErrorWebExceptionHandler directly and override specific methods.

Custom Error Pages
If you want to display a custom HTML error page for a given status code, you can add a file to an /error folder. Error pages can either be static HTML (that is, added under any of the static resource folders) or built with templates. The name of the file should be the exact status code or a series mask.

For example, to map 404 to a static HTML file, your folder structure would be as follows:

src/
 +- main/
     +- java/
     |   + <source code>
     +- resources/
         +- public/
             +- error/
             |   +- 404.html
             +- <other public assets>
To map all 5xx errors by using a Mustache template, your folder structure would be as follows:

src/
 +- main/
     +- java/
     |   + <source code>
     +- resources/
         +- templates/
             +- error/
             |   +- 5xx.mustache
             +- <other templates>
27.2.6 Web Filters
Spring WebFlux provides a WebFilter interface that can be implemented to filter HTTP request-response exchanges. WebFilter beans found in the application context will be automatically used to filter each exchange.

Where the order of the filters is important they can implement Ordered or be annotated with @Order. Spring Boot auto-configuration may configure web filters for you. When it does so, the orders shown in the following table will be used:

Web Filter	Order
MetricsWebFilter

Ordered.HIGHEST_PRECEDENCE + 1

WebFilterChainProxy (Spring Security)

-100

HttpTraceWebFilter

Ordered.LOWEST_PRECEDENCE - 10

27.3 JAX-RS and Jersey
If you prefer the JAX-RS programming model for REST endpoints, you can use one of the available implementations instead of Spring MVC. Jersey 1.x and Apache CXF work quite well out of the box if you register their Servlet or Filter as a @Bean in your application context. Jersey 2.x has some native Spring support, so we also provide auto-configuration support for it in Spring Boot, together with a starter.

To get started with Jersey 2.x, include the spring-boot-starter-jersey as a dependency and then you need one @Bean of type ResourceConfig in which you register all the endpoints, as shown in the following example:

@Component
public class JerseyConfig extends ResourceConfig {

	public JerseyConfig() {
		register(Endpoint.class);
	}

}
[Warning]
Jersey’s support for scanning executable archives is rather limited. For example, it cannot scan for endpoints in a package found in WEB-INF/classes when running an executable war file. To avoid this limitation, the packages method should not be used, and endpoints should be registered individually by using the register method, as shown in the preceding example.

For more advanced customizations, you can also register an arbitrary number of beans that implement ResourceConfigCustomizer.

All the registered endpoints should be @Components with HTTP resource annotations (@GET and others), as shown in the following example:

@Component
@Path("/hello")
public class Endpoint {

	@GET
	public String message() {
		return "Hello";
	}

}
Since the Endpoint is a Spring @Component, its lifecycle is managed by Spring and you can use the @Autowired annotation to inject dependencies and use the @Value annotation to inject external configuration. By default, the Jersey servlet is registered and mapped to /*. You can change the mapping by adding @ApplicationPath to your ResourceConfig.

By default, Jersey is set up as a Servlet in a @Bean of type ServletRegistrationBean named jerseyServletRegistration. By default, the servlet is initialized lazily, but you can customize that behavior by setting spring.jersey.servlet.load-on-startup. You can disable or override that bean by creating one of your own with the same name. You can also use a filter instead of a servlet by setting spring.jersey.type=filter (in which case, the @Bean to replace or override is jerseyFilterRegistration). The filter has an @Order, which you can set with spring.jersey.filter.order. Both the servlet and the filter registrations can be given init parameters by using spring.jersey.init.* to specify a map of properties.

There is a Jersey sample so that you can see how to set things up. There is also a Jersey 1.x sample. Note that, in the Jersey 1.x sample, the spring-boot maven plugin has been configured to unpack some Jersey jars so that they can be scanned by the JAX-RS implementation (because the sample asks for them to be scanned in its Filter registration). If any of your JAX-RS resources are packaged as nested jars, you may need to do the same.

27.4 Embedded Servlet Container Support
Spring Boot includes support for embedded Tomcat, Jetty, and Undertow servers. Most developers use the appropriate “Starter” to obtain a fully configured instance. By default, the embedded server listens for HTTP requests on port 8080.

[Warning]
If you choose to use Tomcat on CentOS, be aware that, by default, a temporary directory is used to store compiled JSPs, file uploads, and so on. This directory may be deleted by tmpwatch while your application is running, leading to failures. To avoid this behavior, you may want to customize your tmpwatch configuration such that tomcat.* directories are not deleted or configure server.tomcat.basedir such that embedded Tomcat uses a different location.

27.4.1 Servlets, Filters, and listeners
When using an embedded servlet container, you can register servlets, filters, and all the listeners (such as HttpSessionListener) from the Servlet spec, either by using Spring beans or by scanning for Servlet components.

Registering Servlets, Filters, and Listeners as Spring Beans
Any Servlet, Filter, or servlet *Listener instance that is a Spring bean is registered with the embedded container. This can be particularly convenient if you want to refer to a value from your application.properties during configuration.

By default, if the context contains only a single Servlet, it is mapped to /. In the case of multiple servlet beans, the bean name is used as a path prefix. Filters map to /*.

If convention-based mapping is not flexible enough, you can use the ServletRegistrationBean, FilterRegistrationBean, and ServletListenerRegistrationBean classes for complete control.

Spring Boot ships with many auto-configurations that may define Filter beans. Here are a few examples of Filters and their respective order (lower order value means higher precedence):

Servlet Filter	Order
OrderedCharacterEncodingFilter

Ordered.HIGHEST_PRECEDENCE

WebMvcMetricsFilter

Ordered.HIGHEST_PRECEDENCE + 1

ErrorPageFilter

Ordered.HIGHEST_PRECEDENCE + 1

HttpTraceFilter

Ordered.LOWEST_PRECEDENCE - 10

It is usually safe to leave Filter beans unordered.

If a specific order is required, you should avoid configuring a Filter that reads the request body at Ordered.HIGHEST_PRECEDENCE, since it might go against the character encoding configuration of your application. If a Servlet filter wraps the request, it should be configured with an order that is less than or equal to FilterRegistrationBean.REQUEST_WRAPPER_FILTER_MAX_ORDER.

27.4.2 Servlet Context Initialization
Embedded servlet containers do not directly execute the Servlet 3.0+ javax.servlet.ServletContainerInitializer interface or Spring’s org.springframework.web.WebApplicationInitializer interface. This is an intentional design decision intended to reduce the risk that third party libraries designed to run inside a war may break Spring Boot applications.

If you need to perform servlet context initialization in a Spring Boot application, you should register a bean that implements the org.springframework.boot.web.servlet.ServletContextInitializer interface. The single onStartup method provides access to the ServletContext and, if necessary, can easily be used as an adapter to an existing WebApplicationInitializer.

Scanning for Servlets, Filters, and listeners
When using an embedded container, automatic registration of classes annotated with @WebServlet, @WebFilter, and @WebListener can be enabled by using @ServletComponentScan.

[Tip]
@ServletComponentScan has no effect in a standalone container, where the container’s built-in discovery mechanisms are used instead.

27.4.3 The ServletWebServerApplicationContext
Under the hood, Spring Boot uses a different type of ApplicationContext for embedded servlet container support. The ServletWebServerApplicationContext is a special type of WebApplicationContext that bootstraps itself by searching for a single ServletWebServerFactory bean. Usually a TomcatServletWebServerFactory, JettyServletWebServerFactory, or UndertowServletWebServerFactory has been auto-configured.

[Note]
You usually do not need to be aware of these implementation classes. Most applications are auto-configured, and the appropriate ApplicationContext and ServletWebServerFactory are created on your behalf.

27.4.4 Customizing Embedded Servlet Containers
Common servlet container settings can be configured by using Spring Environment properties. Usually, you would define the properties in your application.properties file.

Common server settings include:

Network settings: Listen port for incoming HTTP requests (server.port), interface address to bind to server.address, and so on.
Session settings: Whether the session is persistent (server.servlet.session.persistence), session timeout (server.servlet.session.timeout), location of session data (server.servlet.session.store-dir), and session-cookie configuration (server.servlet.session.cookie.*).
Error management: Location of the error page (server.error.path) and so on.
SSL
HTTP compression
Spring Boot tries as much as possible to expose common settings, but this is not always possible. For those cases, dedicated namespaces offer server-specific customizations (see server.tomcat and server.undertow). For instance, access logs can be configured with specific features of the embedded servlet container.

[Tip]
See the ServerProperties class for a complete list.

Programmatic Customization
If you need to programmatically configure your embedded servlet container, you can register a Spring bean that implements the WebServerFactoryCustomizer interface. WebServerFactoryCustomizer provides access to the ConfigurableServletWebServerFactory, which includes numerous customization setter methods. Dedicated variants exist for Tomcat, Jetty, and Undertow. The following example shows programmatically setting the port:

import org.springframework.boot.web.server.WebServerFactoryCustomizer;
import org.springframework.boot.web.servlet.server.ConfigurableServletWebServerFactory;
import org.springframework.stereotype.Component;

@Component
public class CustomizationBean implements WebServerFactoryCustomizer<ConfigurableServletWebServerFactory> {

	@Override
	public void customize(ConfigurableServletWebServerFactory server) {
		server.setPort(9000);
	}

}
Customizing ConfigurableServletWebServerFactory Directly
If the preceding customization techniques are too limited, you can register the TomcatServletWebServerFactory, JettyServletWebServerFactory, or UndertowServletWebServerFactory bean yourself.

@Bean
public ConfigurableServletWebServerFactory webServerFactory() {
	TomcatServletWebServerFactory factory = new TomcatServletWebServerFactory();
	factory.setPort(9000);
	factory.setSessionTimeout(10, TimeUnit.MINUTES);
	factory.addErrorPages(new ErrorPage(HttpStatus.NOT_FOUND, "/notfound.html"));
	return factory;
}
Setters are provided for many configuration options. Several protected method “hooks” are also provided should you need to do something more exotic. See the source code documentation for details.

27.4.5 JSP Limitations
When running a Spring Boot application that uses an embedded servlet container (and is packaged as an executable archive), there are some limitations in the JSP support.

With Tomcat, it should work if you use war packaging. That is, an executable war works and is also deployable to a standard container (not limited to, but including Tomcat). An executable jar does not work because of a hard-coded file pattern in Tomcat.
With Jetty, it should work if you use war packaging. That is, an executable war works, and is also deployable to any standard container.
Undertow does not support JSPs.
Creating a custom error.jsp page does not override the default view for error handling. Custom error pages should be used instead.
There is a JSP sample so that you can see how to set things up.

28. Security
If Spring Security is on the classpath, then web applications are secure by default. Spring Boot relies on Spring Security’s content-negotiation strategy to determine whether to use httpBasic or formLogin. To add method-level security to a web application, you can also add @EnableGlobalMethodSecurity with your desired settings. Additional information can be found in the Spring Security Reference Guide.

The default AuthenticationManager has a single user. The user name is user, and the password is random and is printed at INFO level when the application starts, as shown in the following example:

Using generated security password: 78fa095d-3f4c-48b1-ad50-e24c31d5cf35
[Note]
If you fine-tune your logging configuration, ensure that the org.springframework.boot.autoconfigure.security category is set to log INFO-level messages. Otherwise, the default password is not printed.

You can change the username and password by providing a spring.security.user.name and spring.security.user.password.

The basic features you get by default in a web application are:

A UserDetailsService (or ReactiveUserDetailsService in case of a WebFlux application) bean with in-memory store and a single user with a generated password (see SecurityProperties.User for the properties of the user).
Form-based login or HTTP Basic security (depending on Content-Type) for the entire application (including actuator endpoints if actuator is on the classpath).
A DefaultAuthenticationEventPublisher for publishing authentication events.
You can provide a different AuthenticationEventPublisher by adding a bean for it.

28.1 MVC Security
The default security configuration is implemented in SecurityAutoConfiguration and in the classes imported from there (SpringBootWebSecurityConfiguration for web security and AuthenticationManagerConfiguration for authentication configuration, which is also relevant in non-web applications). To switch off the default web application security configuration completely, you can add a bean of type WebSecurityConfigurerAdapter (doing so does not disable the authentication manager configuration or Actuator’s security).

To also switch off the authentication manager configuration, you can add a bean of type UserDetailsService, AuthenticationProvider, or AuthenticationManager. There are several secure applications in the Spring Boot samples to get you started with common use cases.

Access rules can be overridden by adding a custom WebSecurityConfigurerAdapter. Spring Boot provides convenience methods that can be used to override access rules for actuator endpoints and static resources. EndpointRequest can be used to create a RequestMatcher that is based on the management.endpoints.web.base-path property. PathRequest can be used to create a RequestMatcher for resources in commonly used locations.

28.2 WebFlux Security
Similar to Spring MVC applications, you can secure your WebFlux applications by adding the spring-boot-starter-security dependency. The default security configuration is implemented in ReactiveSecurityAutoConfiguration and in the classes imported from there (WebFluxSecurityConfiguration for web security and ReactiveAuthenticationManagerConfiguration for authentication configuration, which is also relevant in non-web applications). To switch off the default web application security configuration completely, you can add a bean of type WebFilterChainProxy (doing so does not disable the authentication manager configuration or Actuator’s security).

To also switch off the authentication manager configuration, you can add a bean of type ReactiveUserDetailsService or ReactiveAuthenticationManager.

Access rules can be configured by adding a custom SecurityWebFilterChain. Spring Boot provides convenience methods that can be used to override access rules for actuator endpoints and static resources. EndpointRequest can be used to create a ServerWebExchangeMatcher that is based on the management.endpoints.web.base-path property.

PathRequest can be used to create a ServerWebExchangeMatcher for resources in commonly used locations.

For example, you can customize your security configuration by adding something like:

@Bean
public SecurityWebFilterChain springSecurityFilterChain(ServerHttpSecurity http) {
	http
		.authorizeExchange()
			.matchers(PathRequest.toStaticResources().atCommonLocations()).permitAll()
			.pathMatchers("/foo", "/bar")
				.authenticated().and()
			.formLogin();
	return http.build();
}
28.3 OAuth2
OAuth2 is a widely used authorization framework that is supported by Spring.

28.3.1 Client
If you have spring-security-oauth2-client on your classpath, you can take advantage of some auto-configuration to make it easy to set up an OAuth2 Client. This configuration makes use of the properties under OAuth2ClientProperties.

You can register multiple OAuth2 clients and providers under the spring.security.oauth2.client prefix, as shown in the following example:

spring.security.oauth2.client.registration.my-client-1.client-id=abcd
spring.security.oauth2.client.registration.my-client-1.client-secret=password
spring.security.oauth2.client.registration.my-client-1.client-name=Client for user scope
spring.security.oauth2.client.registration.my-client-1.provider=my-oauth-provider
spring.security.oauth2.client.registration.my-client-1.scope=user
spring.security.oauth2.client.registration.my-client-1.redirect-uri-template=http://my-redirect-uri.com
spring.security.oauth2.client.registration.my-client-1.client-authentication-method=basic
spring.security.oauth2.client.registration.my-client-1.authorization-grant-type=authorization_code

spring.security.oauth2.client.registration.my-client-2.client-id=abcd
spring.security.oauth2.client.registration.my-client-2.client-secret=password
spring.security.oauth2.client.registration.my-client-2.client-name=Client for email scope
spring.security.oauth2.client.registration.my-client-2.provider=my-oauth-provider
spring.security.oauth2.client.registration.my-client-2.scope=email
spring.security.oauth2.client.registration.my-client-2.redirect-uri-template=http://my-redirect-uri.com
spring.security.oauth2.client.registration.my-client-2.client-authentication-method=basic
spring.security.oauth2.client.registration.my-client-2.authorization-grant-type=authorization_code

spring.security.oauth2.client.provider.my-oauth-provider.authorization-uri=http://my-auth-server/oauth/authorize
spring.security.oauth2.client.provider.my-oauth-provider.token-uri=http://my-auth-server/oauth/token
spring.security.oauth2.client.provider.my-oauth-provider.user-info-uri=http://my-auth-server/userinfo
spring.security.oauth2.client.provider.my-oauth-provider.jwk-set-uri=http://my-auth-server/token_keys
spring.security.oauth2.client.provider.my-oauth-provider.user-name-attribute=name
By default, Spring Security’s OAuth2LoginAuthenticationFilter only processes URLs matching /login/oauth2/code/*. If you want to customize the redirect-uri-template to use a different pattern, you need to provide configuration to process that custom pattern. For example, you can add your own WebSecurityConfigurerAdapter that resembles the following:

public class OAuth2LoginSecurityConfig extends WebSecurityConfigurerAdapter {

	@Override
	protected void configure(HttpSecurity http) throws Exception {
		http
			.authorizeRequests()
				.anyRequest().authenticated()
				.and()
			.oauth2Login()
				.redirectionEndpoint()
					.baseUri("/custom-callback");
	}
}
For common OAuth2 and OpenID providers, including Google, Github, Facebook, and Okta, we provide a set of provider defaults (google, github, facebook, and okta, respectively).

If you do not need to customize these providers, you can set the provider attribute to the one for which you need to infer defaults. Also, if the ID of your client matches the default supported provider, Spring Boot infers that as well.

In other words, the two configurations in the following example use the Google provider:

spring.security.oauth2.client.registration.my-client.client-id=abcd
spring.security.oauth2.client.registration.my-client.client-secret=password
spring.security.oauth2.client.registration.my-client.provider=google

spring.security.oauth2.client.registration.google.client-id=abcd
spring.security.oauth2.client.registration.google.client-secret=password
28.4 Actuator Security
For security purposes, all actuators other than /health and /info are disabled by default. The management.endpoints.web.exposure.include property can be used to enable the actuators.

If Spring Security is on the classpath and no other WebSecurityConfigurerAdapter is present, the actuators are secured by Spring Boot auto-config. If you define a custom WebSecurityConfigurerAdapter, Spring Boot auto-config will back off and you will be in full control of actuator access rules.

[Note]
Before setting the management.endpoints.web.exposure.include, ensure that the exposed actuators do not contain sensitive information and/or are secured by placing them behind a firewall or by something like Spring Security.

28.4.1 Cross Site Request Forgery Protection
Since Spring Boot relies on Spring Security’s defaults, CSRF protection is turned on by default. This means that the actuator endpoints that require a POST (shutdown and loggers endpoints), PUT or DELETE will get a 403 forbidden error when the default security configuration is in use.

[Note]
We recommend disabling CSRF protection completely only if you are creating a service that is used by non-browser clients.

Additional information about CSRF protection can be found in the Spring Security Reference Guide.

29. Working with SQL Databases
The Spring Framework provides extensive support for working with SQL databases, from direct JDBC access using JdbcTemplate to complete “object relational mapping” technologies such as Hibernate. Spring Data provides an additional level of functionality: creating Repository implementations directly from interfaces and using conventions to generate queries from your method names.

29.1 Configure a DataSource
Java’s javax.sql.DataSource interface provides a standard method of working with database connections. Traditionally, a 'DataSource' uses a URL along with some credentials to establish a database connection.

[Tip]
See the “How-to” section for more advanced examples, typically to take full control over the configuration of the DataSource.

29.1.1 Embedded Database Support
It is often convenient to develop applications by using an in-memory embedded database. Obviously, in-memory databases do not provide persistent storage. You need to populate your database when your application starts and be prepared to throw away data when your application ends.

[Tip]
The “How-to” section includes a section on how to initialize a database.

Spring Boot can auto-configure embedded H2, HSQL, and Derby databases. You need not provide any connection URLs. You need only include a build dependency to the embedded database that you want to use.

[Note]
If you are using this feature in your tests, you may notice that the same database is reused by your whole test suite regardless of the number of application contexts that you use. If you want to make sure that each context has a separate embedded database, you should set spring.datasource.generate-unique-name to true.

For example, the typical POM dependencies would be as follows:

<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-data-jpa</artifactId>
</dependency>
<dependency>
	<groupId>org.hsqldb</groupId>
	<artifactId>hsqldb</artifactId>
	<scope>runtime</scope>
</dependency>
[Note]
You need a dependency on spring-jdbc for an embedded database to be auto-configured. In this example, it is pulled in transitively through spring-boot-starter-data-jpa.

[Tip]
If, for whatever reason, you do configure the connection URL for an embedded database, take care to ensure that the database’s automatic shutdown is disabled. If you use H2, you should use DB_CLOSE_ON_EXIT=FALSE to do so. If you use HSQLDB, you should ensure that shutdown=true is not used. Disabling the database’s automatic shutdown lets Spring Boot control when the database is closed, thereby ensuring that it happens once access to the database is no longer needed.

29.1.2 Connection to a Production Database
Production database connections can also be auto-configured by using a pooling DataSource. Spring Boot uses the following algorithm for choosing a specific implementation:

We prefer HikariCP for its performance and concurrency. If HikariCP is available, we always choose it.
Otherwise, if the Tomcat pooling DataSource is available, we use it.
If neither HikariCP nor the Tomcat pooling datasource are available and if Commons DBCP2 is available, we use it.
If you use the spring-boot-starter-jdbc or spring-boot-starter-data-jpa “starters”, you automatically get a dependency to HikariCP.

[Note]
You can bypass that algorithm completely and specify the connection pool to use by setting the spring.datasource.type property. This is especially important if you run your application in a Tomcat container, as tomcat-jdbc is provided by default.

[Tip]
Additional connection pools can always be configured manually. If you define your own DataSource bean, auto-configuration does not occur.

DataSource configuration is controlled by external configuration properties in spring.datasource.*. For example, you might declare the following section in application.properties:

spring.datasource.url=jdbc:mysql://localhost/test
spring.datasource.username=dbuser
spring.datasource.password=dbpass
spring.datasource.driver-class-name=com.mysql.jdbc.Driver
[Note]
You should at least specify the URL by setting the spring.datasource.url property. Otherwise, Spring Boot tries to auto-configure an embedded database.

[Tip]
You often do not need to specify the driver-class-name, since Spring Boot can deduce it for most databases from the url.

[Note]
For a pooling DataSource to be created, we need to be able to verify that a valid Driver class is available, so we check for that before doing anything. In other words, if you set spring.datasource.driver-class-name=com.mysql.jdbc.Driver, then that class has to be loadable.

See DataSourceProperties for more of the supported options. These are the standard options that work regardless of the actual implementation. It is also possible to fine-tune implementation-specific settings by using their respective prefix (spring.datasource.hikari.*, spring.datasource.tomcat.*, and spring.datasource.dbcp2.*). Refer to the documentation of the connection pool implementation you are using for more details.

For instance, if you use the Tomcat connection pool, you could customize many additional settings, as shown in the following example:

# Number of ms to wait before throwing an exception if no connection is available.
spring.datasource.tomcat.max-wait=10000

# Maximum number of active connections that can be allocated from this pool at the same time.
spring.datasource.tomcat.max-active=50

# Validate the connection before borrowing it from the pool.
spring.datasource.tomcat.test-on-borrow=true
29.1.3 Connection to a JNDI DataSource
If you deploy your Spring Boot application to an Application Server, you might want to configure and manage your DataSource by using your Application Server’s built-in features and access it by using JNDI.

The spring.datasource.jndi-name property can be used as an alternative to the spring.datasource.url, spring.datasource.username, and spring.datasource.password properties to access the DataSource from a specific JNDI location. For example, the following section in application.properties shows how you can access a JBoss AS defined DataSource:

spring.datasource.jndi-name=java:jboss/datasources/customers
29.2 Using JdbcTemplate
Spring’s JdbcTemplate and NamedParameterJdbcTemplate classes are auto-configured, and you can @Autowire them directly into your own beans, as shown in the following example:

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.jdbc.core.JdbcTemplate;
import org.springframework.stereotype.Component;

@Component
public class MyBean {

	private final JdbcTemplate jdbcTemplate;

	@Autowired
	public MyBean(JdbcTemplate jdbcTemplate) {
		this.jdbcTemplate = jdbcTemplate;
	}

	// ...

}
You can customize some properties of the template by using the spring.jdbc.template.* properties, as shown in the following example:

spring.jdbc.template.max-rows=500
[Note]
The NamedParameterJdbcTemplate reuses the same JdbcTemplate instance behind the scenes. If more than one JdbcTemplate is defined and no primary candidate exists, the NamedParameterJdbcTemplate is not auto-configured.

29.3 JPA and “Spring Data”
The Java Persistence API is a standard technology that lets you “map” objects to relational databases. The spring-boot-starter-data-jpa POM provides a quick way to get started. It provides the following key dependencies:

Hibernate: One of the most popular JPA implementations.
Spring Data JPA: Makes it easy to implement JPA-based repositories.
Spring ORMs: Core ORM support from the Spring Framework.
[Tip]
We do not go into too many details of JPA or Spring Data here. You can follow the “Accessing Data with JPA” guide from spring.io and read the Spring Data JPA and Hibernate reference documentation.

29.3.1 Entity Classes
Traditionally, JPA “Entity” classes are specified in a persistence.xml file. With Spring Boot, this file is not necessary and “Entity Scanning” is used instead. By default, all packages below your main configuration class (the one annotated with @EnableAutoConfiguration or @SpringBootApplication) are searched.

Any classes annotated with @Entity, @Embeddable, or @MappedSuperclass are considered. A typical entity class resembles the following example:

package com.example.myapp.domain;

import java.io.Serializable;
import javax.persistence.*;

@Entity
public class City implements Serializable {

	@Id
	@GeneratedValue
	private Long id;

	@Column(nullable = false)
	private String name;

	@Column(nullable = false)
	private String state;

	// ... additional members, often include @OneToMany mappings

	protected City() {
		// no-args constructor required by JPA spec
		// this one is protected since it shouldn't be used directly
	}

	public City(String name, String state) {
		this.name = name;
		this.country = country;
	}

	public String getName() {
		return this.name;
	}

	public String getState() {
		return this.state;
	}

	// ... etc

}
[Tip]
You can customize entity scanning locations by using the @EntityScan annotation. See the “Section 79.4, “Separate @Entity Definitions from Spring Configuration”” how-to.

29.3.2 Spring Data JPA Repositories
{http://projects.spring.io/spring-data-jpa/}[Spring Data JPA] repositories are interfaces that you can define to access data. JPA queries are created automatically from your method names. For example, a CityRepository interface might declare a findAllByState(String state) method to find all the cities in a given state.

For more complex queries, you can annotate your method with Spring Data’s Query annotation.

Spring Data repositories usually extend from the Repository or CrudRepository interfaces. If you use auto-configuration, repositories are searched from the package containing your main configuration class (the one annotated with @EnableAutoConfiguration or @SpringBootApplication) down.

The following example shows a typical Spring Data repository interface definition:

package com.example.myapp.domain;

import org.springframework.data.domain.*;
import org.springframework.data.repository.*;

public interface CityRepository extends Repository<City, Long> {

	Page<City> findAll(Pageable pageable);

	City findByNameAndCountryAllIgnoringCase(String name, String country);

}
[Tip]
We have barely scratched the surface of Spring Data JPA. For complete details, see the Spring Data JPA reference documentation.

29.3.3 Creating and Dropping JPA Databases
By default, JPA databases are automatically created only if you use an embedded database (H2, HSQL, or Derby). You can explicitly configure JPA settings by using spring.jpa.* properties. For example, to create and drop tables you can add the following line to your application.properties:

spring.jpa.hibernate.ddl-auto=create-drop
[Note]
Hibernate’s own internal property name for this (if you happen to remember it better) is hibernate.hbm2ddl.auto. You can set it, along with other Hibernate native properties, by using spring.jpa.properties.* (the prefix is stripped before adding them to the entity manager). The following line shows an example of setting JPA properties for Hibernate:

spring.jpa.properties.hibernate.globally_quoted_identifiers=true
The line in the preceding example passes a value of true for the hibernate.globally_quoted_identifiers property to the Hibernate entity manager.

By default, the DDL execution (or validation) is deferred until the ApplicationContext has started. There is also a spring.jpa.generate-ddl flag, but it is not used if Hibernate auto-configuration is active, because the ddl-auto settings are more fine-grained.

29.3.4 Open EntityManager in View
If you are running a web application, Spring Boot by default registers OpenEntityManagerInViewInterceptor to apply the “Open EntityManager in View” pattern, to allow for lazy loading in web views. If you do not want this behavior, you should set spring.jpa.open-in-view to false in your application.properties.

29.4 Using H2’s Web Console
The H2 database provides a browser-based console that Spring Boot can auto-configure for you. The console is auto-configured when the following conditions are met:

You are developing a web application.
com.h2database:h2 is on the classpath.
You are using Spring Boot’s developer tools.
[Tip]
If you are not using Spring Boot’s developer tools but would still like to make use of H2’s console, you can configure the spring.h2.console.enabled property with a value of true.

[Note]
The H2 console is only intended for use during development, so you should take care to ensure that spring.h2.console.enabled is not set to true in production.

29.4.1 Changing the H2 Console’s Path
By default, the console is available at /h2-console. You can customize the console’s path by using the spring.h2.console.path property.

29.5 Using jOOQ
Java Object Oriented Querying (jOOQ) is a popular product from Data Geekery which generates Java code from your database and lets you build type-safe SQL queries through its fluent API. Both the commercial and open source editions can be used with Spring Boot.

29.5.1 Code Generation
In order to use jOOQ type-safe queries, you need to generate Java classes from your database schema. You can follow the instructions in the jOOQ user manual. If you use the jooq-codegen-maven plugin and you also use the spring-boot-starter-parent “parent POM”, you can safely omit the plugin’s <version> tag. You can also use Spring Boot-defined version variables (such as h2.version) to declare the plugin’s database dependency. The following listing shows an example:

<plugin>
	<groupId>org.jooq</groupId>
	<artifactId>jooq-codegen-maven</artifactId>
	<executions>
		...
	</executions>
	<dependencies>
		<dependency>
			<groupId>com.h2database</groupId>
			<artifactId>h2</artifactId>
			<version>${h2.version}</version>
		</dependency>
	</dependencies>
	<configuration>
		<jdbc>
			<driver>org.h2.Driver</driver>
			<url>jdbc:h2:~/yourdatabase</url>
		</jdbc>
		<generator>
			...
		</generator>
	</configuration>
</plugin>
29.5.2 Using DSLContext
The fluent API offered by jOOQ is initiated through the org.jooq.DSLContext interface. Spring Boot auto-configures a DSLContext as a Spring Bean and connects it to your application DataSource. To use the DSLContext, you can @Autowire it, as shown in the following example:

@Component
public class JooqExample implements CommandLineRunner {

	private final DSLContext create;

	@Autowired
	public JooqExample(DSLContext dslContext) {
		this.create = dslContext;
	}

}
[Tip]
The jOOQ manual tends to use a variable named create to hold the DSLContext.

You can then use the DSLContext to construct your queries, as shown in the following example:

public List<GregorianCalendar> authorsBornAfter1980() {
	return this.create.selectFrom(AUTHOR)
		.where(AUTHOR.DATE_OF_BIRTH.greaterThan(new GregorianCalendar(1980, 0, 1)))
		.fetch(AUTHOR.DATE_OF_BIRTH);
}
29.5.3 jOOQ SQL Dialect
Unless the spring.jooq.sql-dialect property has been configured, Spring Boot determines the SQL dialect to use for your datasource. If Spring Boot could not detect the dialect, it uses DEFAULT.

[Note]
Spring Boot can only auto-configure dialects supported by the open source version of jOOQ.

29.5.4 Customizing jOOQ
More advanced customizations can be achieved by defining your own @Bean definitions, which is used when the jOOQ Configuration is created. You can define beans for the following jOOQ Types:

ConnectionProvider
TransactionProvider
RecordMapperProvider
RecordListenerProvider
ExecuteListenerProvider
VisitListenerProvider
You can also create your own org.jooq.Configuration @Bean if you want to take complete control of the jOOQ configuration.

30. Working with NoSQL Technologies
Spring Data provides additional projects that help you access a variety of NoSQL technologies, including: MongoDB, Neo4J, Elasticsearch, Solr, Redis, Gemfire, Cassandra, Couchbase and LDAP. Spring Boot provides auto-configuration for Redis, MongoDB, Neo4j, Elasticsearch, Solr Cassandra, Couchbase, and LDAP. You can make use of the other projects, but you must configure them yourself. Refer to the appropriate reference documentation at projects.spring.io/spring-data.

30.1 Redis
Redis is a cache, message broker, and richly-featured key-value store. Spring Boot offers basic auto-configuration for the Lettuce and Jedis client libraries and the abstractions on top of them provided by Spring Data Redis.

There is a spring-boot-starter-data-redis “Starter” for collecting the dependencies in a convenient way. By default, it uses Lettuce. That starter handles both traditional and reactive applications.

[Tip]
we also provide a spring-boot-starter-data-redis-reactive “Starter” for consistency with the other stores with reactive support.

30.1.1 Connecting to Redis
You can inject an auto-configured RedisConnectionFactory, StringRedisTemplate, or vanilla RedisTemplate instance as you would any other Spring Bean. By default, the instance tries to connect to a Redis server at localhost:6379. The following listing shows an example of such a bean:

@Component
public class MyBean {

	private StringRedisTemplate template;

	@Autowired
	public MyBean(StringRedisTemplate template) {
		this.template = template;
	}

	// ...

}
[Tip]
You can also register an arbitrary number of beans that implement LettuceClientConfigurationBuilderCustomizer for more advanced customizations. If you use Jedis, JedisClientConfigurationBuilderCustomizer is also available.

If you add your own @Bean of any of the auto-configured types, it replaces the default (except in the case of RedisTemplate, when the exclusion is based on the bean name, redisTemplate, not its type). By default, if commons-pool2 is on the classpath, you get a pooled connection factory.

30.2 MongoDB
MongoDB is an open-source NoSQL document database that uses a JSON-like schema instead of traditional table-based relational data. Spring Boot offers several conveniences for working with MongoDB, including the spring-boot-starter-data-mongodb and spring-boot-starter-data-mongodb-reactive “Starters”.

30.2.1 Connecting to a MongoDB Database
To access Mongo databases, you can inject an auto-configured org.springframework.data.mongodb.MongoDbFactory. By default, the instance tries to connect to a MongoDB server at mongodb://localhost/test The following example shows how to connect to a MongoDB database:

import org.springframework.data.mongodb.MongoDbFactory;
import com.mongodb.DB;

@Component
public class MyBean {

	private final MongoDbFactory mongo;

	@Autowired
	public MyBean(MongoDbFactory mongo) {
		this.mongo = mongo;
	}

	// ...

	public void example() {
		DB db = mongo.getDb();
		// ...
	}

}
You can set the spring.data.mongodb.uri property to change the URL and configure additional settings such as the replica set, as shown in the following example:

spring.data.mongodb.uri=mongodb://user:secret@mongo1.example.com:12345,mongo2.example.com:23456/test
Alternatively, as long as you use Mongo 2.x, you can specify a host/port. For example, you might declare the following settings in your application.properties:

spring.data.mongodb.host=mongoserver
spring.data.mongodb.port=27017
[Note]
If you use the Mongo 3.0 Java driver, spring.data.mongodb.host and spring.data.mongodb.port are not supported. In such cases, spring.data.mongodb.uri should be used to provide all of the configuration.

[Tip]
If spring.data.mongodb.port is not specified, the default of 27017 is used. You could delete this line from the example shown earlier.

[Tip]
If you do not use Spring Data Mongo, you can inject com.mongodb.MongoClient beans instead of using MongoDbFactory. If you want to take complete control of establishing the MongoDB connection, you can also declare your own MongoDbFactory or MongoClient bean.

[Note]
If you are using the reactive driver, Netty is required for SSL. The auto-configuration configures this factory automatically if Netty is available and the factory to use hasn’t been customized already.

30.2.2 MongoTemplate
Spring Data MongoDB provides a MongoTemplate class that is very similar in its design to Spring’s JdbcTemplate. As with JdbcTemplate, Spring Boot auto-configures a bean for you to inject the template, as follows:

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.data.mongodb.core.MongoTemplate;
import org.springframework.stereotype.Component;

@Component
public class MyBean {

	private final MongoTemplate mongoTemplate;

	@Autowired
	public MyBean(MongoTemplate mongoTemplate) {
		this.mongoTemplate = mongoTemplate;
	}

	// ...

}
See the MongoOperations Javadoc for complete details.

30.2.3 Spring Data MongoDB Repositories
Spring Data includes repository support for MongoDB. As with the JPA repositories discussed earlier, the basic principle is that queries are constructed automatically, based on method names.

In fact, both Spring Data JPA and Spring Data MongoDB share the same common infrastructure. You could take the JPA example from earlier and, assuming that City is now a Mongo data class rather than a JPA @Entity, it works in the same way, as shown in the following example:

package com.example.myapp.domain;

import org.springframework.data.domain.*;
import org.springframework.data.repository.*;

public interface CityRepository extends Repository<City, Long> {

	Page<City> findAll(Pageable pageable);

	City findByNameAndCountryAllIgnoringCase(String name, String country);

}
[Tip]
You can customize document scanning locations by using the @EntityScan annotation.

[Tip]
For complete details of Spring Data MongoDB, including its rich object mapping technologies, refer to its reference documentation.

30.2.4 Embedded Mongo
Spring Boot offers auto-configuration for Embedded Mongo. To use it in your Spring Boot application, add a dependency on de.flapdoodle.embed:de.flapdoodle.embed.mongo.

The port that Mongo listens on can be configured by setting the spring.data.mongodb.port property. To use a randomly allocated free port, use a value of 0. The MongoClient created by MongoAutoConfiguration is automatically configured to use the randomly allocated port.

[Note]
If you do not configure a custom port, the embedded support uses a random port (rather than 27017) by default.

If you have SLF4J on the classpath, the output produced by Mongo is automatically routed to a logger named org.springframework.boot.autoconfigure.mongo.embedded.EmbeddedMongo.

You can declare your own IMongodConfig and IRuntimeConfig beans to take control of the Mongo instance’s configuration and logging routing.

30.3 Neo4j
Neo4j is an open-source NoSQL graph database that uses a rich data model of nodes related by first class relationships, which is better suited for connected big data than traditional rdbms approaches. Spring Boot offers several conveniences for working with Neo4j, including the spring-boot-starter-data-neo4j “Starter”.

30.3.1 Connecting to a Neo4j Database
You can inject an auto-configured Neo4jSession, Session, or Neo4jOperations instance as you would any other Spring Bean. By default, the instance tries to connect to a Neo4j server at localhost:7474. The following example shows how to inject a Neo4j bean:

@Component
public class MyBean {

	private final Neo4jTemplate neo4jTemplate;

	@Autowired
	public MyBean(Neo4jTemplate neo4jTemplate) {
		this.neo4jTemplate = neo4jTemplate;
	}

	// ...

}
You can take full control of the configuration by adding a org.neo4j.ogm.config.Configuration @Bean of your own. Also, adding a @Bean of type Neo4jOperations disables the auto-configuration.

You can configure the user and credentials to use by setting the spring.data.neo4j.* properties, as shown in the following example:

spring.data.neo4j.uri=http://my-server:7474
spring.data.neo4j.username=neo4j
spring.data.neo4j.password=secret
30.3.2 Using the Embedded Mode
If you add org.neo4j:neo4j-ogm-embedded-driver to the dependencies of your application, Spring Boot automatically configures an in-process embedded instance of Neo4j that does not persist any data when your application shuts down. You can explicitly disable that mode by setting spring.data.neo4j.embedded.enabled=false. You can also enable persistence for the embedded mode by providing a path to a database file, as shown in the following example:

	spring.data.neo4j.uri=file://var/tmp/graph.db
[Note]
The Neo4j OGM embedded driver does not provide the Neo4j kernel. Users are expected to provide this dependency manually. See the documentation for more details.

30.3.3 Neo4jSession
By default, if you are running a web application, the session is bound to the thread for the entire processing of the request (that is, it uses the "Open Session in View" pattern). If you do not want this behavior, add the following line to your application.properties file:

spring.data.neo4j.open-in-view=false
30.3.4 Spring Data Neo4j Repositories
Spring Data includes repository support for Neo4j.

In fact, both Spring Data JPA and Spring Data Neo4j share the same common infrastructure. You could take the JPA example from earlier and, assuming that City is now a Neo4j OGM @NodeEntity rather than a JPA @Entity, it works in the same way.

[Tip]
You can customize entity scanning locations by using the @EntityScan annotation.

To enable repository support (and optionally support for @Transactional), add the following two annotations to your Spring configuration:

@EnableNeo4jRepositories(basePackages = "com.example.myapp.repository")
@EnableTransactionManagement
30.3.5 Repository Example
The following example shows an interface definition for a Neo4j repository:

package com.example.myapp.domain;

import org.springframework.data.domain.*;
import org.springframework.data.repository.*;

public interface CityRepository extends GraphRepository<City> {

	Page<City> findAll(Pageable pageable);

	City findByNameAndCountry(String name, String country);

}
[Tip]
For complete details of Spring Data Neo4j, including its rich object mapping technologies, refer to the reference documentation.

30.4 Gemfire
Spring Data Gemfire provides convenient Spring-friendly tools for accessing the Pivotal Gemfire data management platform. There is a spring-boot-starter-data-gemfire “Starter” for collecting the dependencies in a convenient way. There is currently no auto-configuration support for Gemfire, but you can enable Spring Data Repositories with a single annotation: @EnableGemfireRepositories.

30.5 Solr
Apache Solr is a search engine. Spring Boot offers basic auto-configuration for the Solr 5 client library and the abstractions on top of it provided by Spring Data Solr. There is a spring-boot-starter-data-solr “Starter” for collecting the dependencies in a convenient way.

30.5.1 Connecting to Solr
You can inject an auto-configured SolrClient instance as you would any other Spring bean. By default, the instance tries to connect to a server at localhost:8983/solr. The following example shows how to inject a Solr bean:

@Component
public class MyBean {

	private SolrClient solr;

	@Autowired
	public MyBean(SolrClient solr) {
		this.solr = solr;
	}

	// ...

}
If you add your own @Bean of type SolrClient, it replaces the default.

30.5.2 Spring Data Solr Repositories
Spring Data includes repository support for Apache Solr. As with the JPA repositories discussed earlier, the basic principle is that queries are automatically constructed for \ you based on method names.

In fact, both Spring Data JPA and Spring Data Solr share the same common infrastructure. You could take the JPA example from earlier and, assuming that City is now a @SolrDocument class rather than a JPA @Entity, it works in the same way.

[Tip]
For complete details of Spring Data Solr, refer to the reference documentation.

30.6 Elasticsearch
Elasticsearch is an open source, distributed, real-time search and analytics engine. Spring Boot offers basic auto-configuration for Elasticsearch and the abstractions on top of it provided by Spring Data Elasticsearch. There is a spring-boot-starter-data-elasticsearch “Starter” for collecting the dependencies in a convenient way. Spring Boot also supports Jest.

30.6.1 Connecting to Elasticsearch by Using Jest
If you have Jest on the classpath, you can inject an auto-configured JestClient that by default targets localhost:9200. You can further tune how the client is configured, as shown in the following example:

spring.elasticsearch.jest.uris=http://search.example.com:9200
spring.elasticsearch.jest.read-timeout=10000
spring.elasticsearch.jest.username=user
spring.elasticsearch.jest.password=secret
You can also register an arbitrary number of beans that implement HttpClientConfigBuilderCustomizer for more advanced customizations. The following example tunes additional HTTP settings:

static class HttpSettingsCustomizer implements HttpClientConfigBuilderCustomizer {

	@Override
	public void customize(HttpClientConfig.Builder builder) {
		builder.maxTotalConnection(100).defaultMaxTotalConnectionPerRoute(5);
	}

}
To take full control over the registration, define a JestClient bean.

30.6.2 Connecting to Elasticsearch by Using Spring Data
To connect to Elasticsearch, you must provide the address of one or more cluster nodes. The address can be specified by setting the spring.data.elasticsearch.cluster-nodes property to a comma-separated host:port list. With this configuration in place, an ElasticsearchTemplate or TransportClient can be injected like any other Spring bean, as shown in the following example:

spring.data.elasticsearch.cluster-nodes=localhost:9300
@Component
public class MyBean {

	private final ElasticsearchTemplate template;

	public MyBean(ElasticsearchTemplate template) {
		this.template = template;
	}

	// ...

}
If you add your own ElasticsearchTemplate or TransportClient @Bean, it replaces the default.

30.6.3 Spring Data Elasticsearch Repositories
Spring Data includes repository support for Elasticsearch. As with the JPA repositories discussed earlier, the basic principle is that queries are constructed for you automatically based on method names.

In fact, both Spring Data JPA and Spring Data Elasticsearch share the same common infrastructure. You could take the JPA example from earlier and, assuming that City is now an Elasticsearch @Document class rather than a JPA @Entity, it works in the same way.

[Tip]
For complete details of Spring Data Elasticsearch, refer to the reference documentation.

30.7 Cassandra
Cassandra is an open source, distributed database management system designed to handle large amounts of data across many commodity servers. Spring Boot offers auto-configuration for Cassandra and the abstractions on top of it provided by Spring Data Cassandra. There is a spring-boot-starter-data-cassandra “Starter” for collecting the dependencies in a convenient way.

30.7.1 Connecting to Cassandra
You can inject an auto-configured CassandraTemplate or a Cassandra Session instance as you would with any other Spring Bean. The spring.data.cassandra.* properties can be used to customize the connection. Generally, you provide keyspace-name and contact-points properties, as shown in the following example:

spring.data.cassandra.keyspace-name=mykeyspace
spring.data.cassandra.contact-points=cassandrahost1,cassandrahost2
The following code listing shows how to inject a Cassandra bean:

@Component
public class MyBean {

	private CassandraTemplate template;

	@Autowired
	public MyBean(CassandraTemplate template) {
		this.template = template;
	}

	// ...

}
If you add your own @Bean of type CassandraTemplate, it replaces the default.

30.7.2 Spring Data Cassandra Repositories
Spring Data includes basic repository support for Cassandra. Currently, this is more limited than the JPA repositories discussed earlier and needs to annotate finder methods with @Query.

[Tip]
For complete details of Spring Data Cassandra, refer to the reference documentation.

30.8 Couchbase
Couchbase is an open-source, distributed, multi-model NoSQL document-oriented database that is optimized for interactive applications. Spring Boot offers auto-configuration for Couchbase and the abstractions on top of it provided by Spring Data Couchbase. There are spring-boot-starter-data-couchbase and spring-boot-starter-data-couchbase-reactive “Starters” for collecting the dependencies in a convenient way.

30.8.1 Connecting to Couchbase
You can get a Bucket and Cluster by adding the Couchbase SDK and some configuration. The spring.couchbase.* properties can be used to customize the connection. Generally, you provide the bootstrap hosts, bucket name, and password, as shown in the following example:

spring.couchbase.bootstrap-hosts=my-host-1,192.168.1.123
spring.couchbase.bucket.name=my-bucket
spring.couchbase.bucket.password=secret
[Tip]
You need to provide at least the bootstrap host(s), in which case the bucket name is default and the password is an empty String. Alternatively, you can define your own org.springframework.data.couchbase.config.CouchbaseConfigurer @Bean to take control over the whole configuration.

It is also possible to customize some of the CouchbaseEnvironment settings. For instance, the following configuration changes the timeout to use to open a new Bucket and enables SSL support:

spring.couchbase.env.timeouts.connect=3000
spring.couchbase.env.ssl.key-store=/location/of/keystore.jks
spring.couchbase.env.ssl.key-store-password=secret
Check the spring.couchbase.env.* properties for more details.

30.8.2 Spring Data Couchbase Repositories
Spring Data includes repository support for Couchbase. For complete details of Spring Data Couchbase, refer to the reference documentation.

You can inject an auto-configured CouchbaseTemplate instance as you would with any other Spring Bean, provided a default CouchbaseConfigurer is available (which happens when you enable Couchbase support, as explained earlier).

The following examples shows how to inject a Couchbase bean:

@Component
public class MyBean {

	private final CouchbaseTemplate template;

	@Autowired
	public MyBean(CouchbaseTemplate template) {
		this.template = template;
	}

	// ...

}
There are a few beans that you can define in your own configuration to override those provided by the auto-configuration:

A CouchbaseTemplate @Bean with a name of couchbaseTemplate.
An IndexManager @Bean with a name of couchbaseIndexManager.
A CustomConversions @Bean with a name of couchbaseCustomConversions.
To avoid hard-coding those names in your own config, you can reuse BeanNames provided by Spring Data Couchbase. For instance, you can customize the converters to use, as follows:

@Configuration
public class SomeConfiguration {

	@Bean(BeanNames.COUCHBASE_CUSTOM_CONVERSIONS)
	public CustomConversions myCustomConversions() {
		return new CustomConversions(...);
	}

	// ...

}
[Tip]
If you want to fully bypass the auto-configuration for Spring Data Couchbase, provide your own implementation of org.springframework.data.couchbase.config.AbstractCouchbaseDataConfiguration.

30.9 LDAP
LDAP (Lightweight Directory Access Protocol) is an open, vendor-neutral, industry standard application protocol for accessing and maintaining distributed directory information services over an IP network. Spring Boot offers auto-configuration for any compliant LDAP server as well as support for the embedded in-memory LDAP server from UnboundID.

LDAP abstractions are provided by Spring Data LDAP. There is a spring-boot-starter-data-ldap “Starter” for collecting the dependencies in a convenient way.

30.9.1 Connecting to an LDAP Server
To connect to an LDAP server, make sure you declare a dependency on the spring-boot-starter-data-ldap “Starter” or spring-ldap-core and then declare the URLs of your server in your application.properties, as shown in the following example:

spring.ldap.urls=ldap://myserver:1235
spring.ldap.username=admin
spring.ldap.password=secret
If you need to customize connection settings, you can use the spring.ldap.base and spring.ldap.base-environment properties.

30.9.2 Spring Data LDAP Repositories
Spring Data includes repository support for LDAP. For complete details of Spring Data LDAP, refer to the reference documentation.

You can also inject an auto-configured LdapTemplate instance as you would with any other Spring Bean, as shown in the following example:

@Component
public class MyBean {

	private final LdapTemplate template;

	@Autowired
	public MyBean(LdapTemplate template) {
		this.template = template;
	}

	// ...

}
30.9.3 Embedded In-memory LDAP Server
For testing purposes, Spring Boot supports auto-configuration of an in-memory LDAP server from UnboundID. To configure the server, add a dependency to com.unboundid:unboundid-ldapsdk and declare a base-dn property, as follows:

spring.ldap.embedded.base-dn=dc=spring,dc=io
[Note]
It is possible to define multiple base-dn values, however, since distinguished names usually contain commas, they must be defined using the correct notation.

In yaml files, you can use the yaml list notation:

spring.ldap.embedded.base-dn:
  - dc=spring,dc=io
  - dc=pivotal,dc=io
In properties files, you must include the index as part of the property name:

spring.ldap.embedded.base-dn[0]=dc=spring,dc=io
spring.ldap.embedded.base-dn[1]=dc=pivotal,dc=io
By default, the server starts on a random port and triggers the regular LDAP support. There is no need to specify a spring.ldap.urls property.

If there is a schema.ldif file on your classpath, it is used to initialize the server. If you want to load the initialization script from a different resource, you can also use the spring.ldap.embedded.ldif property.

By default, a standard schema is used to validate LDIF files. You can turn off validation altogether by setting the spring.ldap.embedded.validation.enabled property. If you have custom attributes, you can use spring.ldap.embedded.validation.schema to define your custom attribute types or object classes.

30.10 InfluxDB
InfluxDB is an open-source time series database optimized for fast, high-availability storage and retrieval of time series data in fields such as operations monitoring, application metrics, Internet-of-Things sensor data, and real-time analytics.

30.10.1 Connecting to InfluxDB
Spring Boot auto-configures an InfluxDB instance, provided the influxdb-java client is on the classpath and the URL of the database is set, as shown in the following example:

spring.influx.url=http://172.0.0.1:8086
If the connection to InfluxDB requires a user and password, you can set the spring.influx.user and spring.influx.password properties accordingly.

InfluxDB relies on OkHttp. If you need to tune the http client InfluxDB uses behind the scenes, you can register an OkHttpClient.Builder bean.

31. Caching
The Spring Framework provides support for transparently adding caching to an application. At its core, the abstraction applies caching to methods, thus reducing the number of executions based on the information available in the cache. The caching logic is applied transparently, without any interference to the invoker. Spring Boot auto-configures the cache infrastructure as long as caching support is enabled via the @EnableCaching annotation.

[Note]
Check the relevant section of the Spring Framework reference for more details.

In a nutshell, adding caching to an operation of your service is as easy as adding the relevant annotation to its method, as shown in the following example:

   import org.springframework.cache.annotation.Cacheable
import org.springframework.stereotype.Component;

@Component
public class MathService {

	@Cacheable("piDecimals")
	public int computePiDecimal(int i) {
		// ...
	}

}
This example demonstrates the use of caching on a potentially costly operation. Before invoking computePiDecimal, the abstraction looks for an entry in the piDecimals cache that matches the i argument. If an entry is found, the content in the cache is immediately returned to the caller, and the method is not invoked. Otherwise, the method is invoked, and the cache is updated before returning the value.

[Caution]	Caution
You can also use the standard JSR-107 (JCache) annotations (such as @CacheResult) transparently. However, we strongly advise you to not mix and match the Spring Cache and JCache annotations.

If you do not add any specific cache library, Spring Boot auto-configures a simple provider that uses concurrent maps in memory. When a cache is required (such as piDecimals in the preceding example), this provider creates it for you. The simple provider is not really recommended for production usage, but it is great for getting started and making sure that you understand the features. When you have made up your mind about the cache provider to use, please make sure to read its documentation to figure out how to configure the caches that your application uses. Nearly all providers require you to explicitly configure every cache that you use in the application. Some offer a way to customize the default caches defined by the spring.cache.cache-names property.

[Tip]
It is also possible to transparently update or evict data from the cache.

31.1 Supported Cache Providers
The cache abstraction does not provide an actual store and relies on abstraction materialized by the org.springframework.cache.Cache and org.springframework.cache.CacheManager interfaces.

If you have not defined a bean of type CacheManager or a CacheResolver named cacheResolver (see CachingConfigurer), Spring Boot tries to detect the following providers (in the indicated order):

Generic
JCache (JSR-107) (EhCache 3, Hazelcast, Infinispan, and others)
EhCache 2.x
Hazelcast
Infinispan
Couchbase
Redis
Caffeine
Simple
[Tip]
It is also possible to force a particular cache provider by setting the spring.cache.type property. Use this property if you need to disable caching altogether in certain environment (such as tests).

[Tip]
Use the spring-boot-starter-cache “Starter” to quickly add basic caching dependencies. The starter brings in spring-context-support. If you add dependencies manually, you must include spring-context-support in order to use the JCache, EhCache 2.x, or Guava support.

If the CacheManager is auto-configured by Spring Boot, you can further tune its configuration before it is fully initialized by exposing a bean that implements the CacheManagerCustomizer interface. The following example sets a flag to say that null values should be passed down to the underlying map:

@Bean
public CacheManagerCustomizer<ConcurrentMapCacheManager> cacheManagerCustomizer() {
	return new CacheManagerCustomizer<ConcurrentMapCacheManager>() {
		@Override
		public void customize(ConcurrentMapCacheManager cacheManager) {
			cacheManager.setAllowNullValues(false);
		}
	};
}
[Note]
In the preceding example, an auto-configured ConcurrentMapCacheManager is expected. If that is not the case (either you provided your own config or a different cache provider was auto-configured), the customizer is not invoked at all. You can have as many customizers as you want, and you can also order them by using @Order or Ordered.

31.1.1 Generic
Generic caching is used if the context defines at least one org.springframework.cache.Cache bean. A CacheManager wrapping all beans of that type is created.

31.1.2 JCache (JSR-107)
JCache is bootstrapped through the presence of a javax.cache.spi.CachingProvider on the classpath (that is, a JSR-107 compliant caching library exists on the classpath), and the JCacheCacheManager is provided by the spring-boot-starter-cache “Starter”. Various compliant libraries are available, and Spring Boot provides dependency management for Ehcache 3, Hazelcast, and Infinispan. Any other compliant library can be added as well.

It might happen that more than one provider is present, in which case the provider must be explicitly specified. Even if the JSR-107 standard does not enforce a standardized way to define the location of the configuration file, Spring Boot does its best to accommodate setting a cache with implementation details, as shown in the following example:

   # Only necessary if more than one provider is present
spring.cache.jcache.provider=com.acme.MyCachingProvider
spring.cache.jcache.config=classpath:acme.xml
[Note]
When a cache library offers both a native implementation and JSR-107 support, Spring Boot prefers the JSR-107 support, so that the same features are available if you switch to a different JSR-107 implementation.

[Tip]
Spring Boot has general support for Hazelcast. If a single HazelcastInstance is available, it is automatically reused for the CacheManager as well, unless the spring.cache.jcache.config property is specified.

There are two ways to customize the underlying javax.cache.cacheManager:

Caches can be created on startup by setting the spring.cache.cache-names property. If a custom javax.cache.configuration.Configuration bean is defined, it is used to customize them.
org.springframework.boot.autoconfigure.cache.JCacheManagerCustomizer beans are invoked with the reference of the CacheManager for full customization.
[Tip]
If a standard javax.cache.CacheManager bean is defined, it is wrapped automatically in an org.springframework.cache.CacheManager implementation that the abstraction expects. No further customization is applied to it.

31.1.3 EhCache 2.x
EhCache 2.x is used if a file named ehcache.xml can be found at the root of the classpath. If EhCache 2.x is found, the EhCacheCacheManager provided by the spring-boot-starter-cache “Starter” is used to bootstrap the cache manager. An alternate configuration file can be provided as well, as shown in the following example:

spring.cache.ehcache.config=classpath:config/another-config.xml
31.1.4 Hazelcast
Spring Boot has general support for Hazelcast. If a HazelcastInstance has been auto-configured, it is automatically wrapped in a CacheManager.

31.1.5 Infinispan
Infinispan has no default configuration file location, so it must be specified explicitly. Otherwise, the default bootstrap is used.

spring.cache.infinispan.config=infinispan.xml
Caches can be created on startup by setting the spring.cache.cache-names property. If a custom ConfigurationBuilder bean is defined, it is used to customize the caches.

[Note]
The support of Infinispan in Spring Boot is restricted to the embedded mode and is quite basic. If you want more options, you should use the official Infinispan Spring Boot starter instead. See Infinispan’s documentation for more details.

31.1.6 Couchbase
If the Couchbase Java client and the couchbase-spring-cache implementation are available and Couchbase is configured, a CouchbaseCacheManager is auto-configured. It is also possible to create additional caches on startup by setting the spring.cache.cache-names property. These caches operate on the Bucket that was auto-configured. You can also create additional caches on another Bucket by using the customizer. Assume you need two caches (cache1 and cache2) on the "main" Bucket and one (cache3) cache with a custom time to live of 2 seconds on the “another” Bucket. You can create the first two caches through configuration, as follows:

spring.cache.cache-names=cache1,cache2
Then you can define a @Configuration class to configure the extra Bucket and the cache3 cache, as follows:

@Configuration
public class CouchbaseCacheConfiguration {

	private final Cluster cluster;

	public CouchbaseCacheConfiguration(Cluster cluster) {
		this.cluster = cluster;
	}

	@Bean
	public Bucket anotherBucket() {
		return this.cluster.openBucket("another", "secret");
	}

	@Bean
	public CacheManagerCustomizer<CouchbaseCacheManager> cacheManagerCustomizer() {
		return c -> {
			c.prepareCache("cache3", CacheBuilder.newInstance(anotherBucket())
					.withExpiration(2));
		};
	}

}
This sample configuration reuses the Cluster that was created through auto-configuration.

31.1.7 Redis
If Redis is available and configured, a RedisCacheManager is auto-configured. It is possible to create additional caches on startup by setting the spring.cache.cache-names property and cache defaults can be configured by using spring.cache.redis.* properties. For instance, the following configuration creates cache1 and cache2 caches with a time to live of 10 minutes:

spring.cache.cache-names=cache1,cache2
spring.cache.redis.time-to-live=600000
[Note]
By default, a key prefix is added so that, if two separate caches use the same key, Redis does not have overlapping keys and cannot return invalid values. We strongly recommend keeping this setting enabled if you create your own RedisCacheManager.

[Tip]
You can take full control of the configuration by adding a RedisCacheConfiguration @Bean of your own. This can be useful if you’re looking for customizing the serialization strategy.

31.1.8 Caffeine
Caffeine is a Java 8 rewrite of Guava’s cache that supersedes support for Guava. If Caffeine is present, a CaffeineCacheManager (provided by the spring-boot-starter-cache “Starter”) is auto-configured. Caches can be created on startup by setting the spring.cache.cache-names property and can be customized by one of the following (in the indicated order):

A cache spec defined by spring.cache.caffeine.spec
A com.github.benmanes.caffeine.cache.CaffeineSpec bean is defined
A com.github.benmanes.caffeine.cache.Caffeine bean is defined
For instance, the following configuration creates cache1 and cache2 caches with a maximum size of 500 and a time to live of 10 minutes

spring.cache.cache-names=cache1,cache2
spring.cache.caffeine.spec=maximumSize=500,expireAfterAccess=600s
If a com.github.benmanes.caffeine.cache.CacheLoader bean is defined, it is automatically associated to the CaffeineCacheManager. Since the CacheLoader is going to be associated with all caches managed by the cache manager, it must be defined as CacheLoader<Object, Object>. The auto-configuration ignores any other generic type.

31.1.9 Simple
If none of the other providers can be found, a simple implementation using a ConcurrentHashMap as the cache store is configured. This is the default if no caching library is present in your application. By default, caches are created as needed, but you can restrict the list of available caches by setting the cache-names property. For instance, if you want only cache1 and cache2 caches, set the cache-names property as follows:

spring.cache.cache-names=cache1,cache2
If you do so and your application uses a cache not listed, then it fails at runtime when the cache is needed, but not on startup. This is similar to the way the "real" cache providers behave if you use an undeclared cache.

31.1.10 None
When @EnableCaching is present in your configuration, a suitable cache configuration is expected as well. If you need to disable caching altogether in certain environments, force the cache type to none to use a no-op implementation, as shown in the following example:

spring.cache.type=none
32. Messaging
The Spring Framework provides extensive support for integrating with messaging systems, from simplified use of the JMS API using JmsTemplate to a complete infrastructure to receive messages asynchronously. Spring AMQP provides a similar feature set for the Advanced Message Queuing Protocol. Spring Boot also provides auto-configuration options for RabbitTemplate and RabbitMQ. Spring WebSocket natively includes support for STOMP messaging, and Spring Boot has support for that through starters and a small amount of auto-configuration. Spring Boot also has support for Apache Kafka.

32.1 JMS
The javax.jms.ConnectionFactory interface provides a standard method of creating a javax.jms.Connection for interacting with a JMS broker. Although Spring needs a ConnectionFactory to work with JMS, you generally need not use it directly yourself and can instead rely on higher level messaging abstractions. (See the relevant section of the Spring Framework reference documentation for details.) Spring Boot also auto-configures the necessary infrastructure to send and receive messages.

32.1.1 ActiveMQ Support
When ActiveMQ is available on the classpath, Spring Boot can also configure a ConnectionFactory. If the broker is present, an embedded broker is automatically started and configured (provided no broker URL is specified through configuration).

[Note]
If you use spring-boot-starter-activemq, the necessary dependencies to connect or embed an ActiveMQ instance are provided, as is the Spring infrastructure to integrate with JMS.

ActiveMQ configuration is controlled by external configuration properties in spring.activemq.*. For example, you might declare the following section in application.properties:

spring.activemq.broker-url=tcp://192.168.1.210:9876
spring.activemq.user=admin
spring.activemq.password=secret
You can also pool JMS resources by adding a dependency to org.apache.activemq:activemq-pool and configuring the PooledConnectionFactory accordingly, as shown in the following example:

spring.activemq.pool.enabled=true
spring.activemq.pool.max-connections=50
[Tip]
See ActiveMQProperties for more of the supported options. You can also register an arbitrary number of beans that implement ActiveMQConnectionFactoryCustomizer for more advanced customizations.

By default, ActiveMQ creates a destination if it does not yet exist so that destinations are resolved against their provided names.

32.1.2 Artemis Support
Spring Boot can auto-configure a ConnectionFactory when it detects that Artemis is available on the classpath. If the broker is present, an embedded broker is automatically started and configured (unless the mode property has been explicitly set). The supported modes are embedded (to make explicit that an embedded broker is required and that an error should occur if the broker is not available on the classpath) and native (to connect to a broker using the netty transport protocol). When the latter is configured, Spring Boot configures a ConnectionFactory that connects to a broker running on the local machine with the default settings.

[Note]
If you use spring-boot-starter-artemis, the necessary dependencies to connect to an existing Artemis instance are provided, as well as the Spring infrastructure to integrate with JMS. Adding org.apache.activemq:artemis-jms-server to your application lets you use embedded mode.

Artemis configuration is controlled by external configuration properties in spring.artemis.*. For example, you might declare the following section in application.properties:

spring.artemis.mode=native
spring.artemis.host=192.168.1.210
spring.artemis.port=9876
spring.artemis.user=admin
spring.artemis.password=secret
When embedding the broker, you can choose if you want to enable persistence and list the destinations that should be made available. These can be specified as a comma-separated list to create them with the default options, or you can define bean(s) of type org.apache.activemq.artemis.jms.server.config.JMSQueueConfiguration or org.apache.activemq.artemis.jms.server.config.TopicConfiguration, for advanced queue and topic configurations, respectively.

See ArtemisProperties for more supported options.

No JNDI lookup is involved, and destinations are resolved against their names, using either the name attribute in the Artemis configuration or the names provided through configuration.

32.1.3 Using a JNDI ConnectionFactory
If you are running your application in an application server, Spring Boot tries to locate a JMS ConnectionFactory by using JNDI. By default, the java:/JmsXA and java:/XAConnectionFactory location are checked. You can use the spring.jms.jndi-name property if you need to specify an alternative location, as shown in the following example:

spring.jms.jndi-name=java:/MyConnectionFactory
32.1.4 Sending a Message
Spring’s JmsTemplate is auto-configured, and you can autowire it directly into your own beans, as shown in the following example:

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.jms.core.JmsTemplate;
import org.springframework.stereotype.Component;

@Component
public class MyBean {

	private final JmsTemplate jmsTemplate;

	@Autowired
	public MyBean(JmsTemplate jmsTemplate) {
		this.jmsTemplate = jmsTemplate;
	}

	// ...

}
[Note]
JmsMessagingTemplate can be injected in a similar manner. If a DestinationResolver or a MessageConverter bean is defined, it is associated automatically to the auto-configured JmsTemplate.

32.1.5 Receiving a Message
When the JMS infrastructure is present, any bean can be annotated with @JmsListener to create a listener endpoint. If no JmsListenerContainerFactory has been defined, a default one is configured automatically. If a DestinationResolver or a MessageConverter beans is defined, it is associated automatically to the default factory.

By default, the default factory is transactional. If you run in an infrastructure where a JtaTransactionManager is present, it is associated to the listener container by default. If not, the sessionTransacted flag is enabled. In that latter scenario, you can associate your local data store transaction to the processing of an incoming message by adding @Transactional on your listener method (or a delegate thereof). This ensures that the incoming message is acknowledged, once the local transaction has completed. This also includes sending response messages that have been performed on the same JMS session.

The following component creates a listener endpoint on the someQueue destination:

@Component
public class MyBean {

	@JmsListener(destination = "someQueue")
	public void processMessage(String content) {
		// ...
	}

}
[Tip]
See the Javadoc of @EnableJms for more details.

If you need to create more JmsListenerContainerFactory instances or if you want to override the default, Spring Boot provides a DefaultJmsListenerContainerFactoryConfigurer that you can use to initialize a DefaultJmsListenerContainerFactory with the same settings as the one that is auto-configured.

For instance, the following example exposes another factory that uses a specific MessageConverter:

@Configuration
static class JmsConfiguration {

	@Bean
	public DefaultJmsListenerContainerFactory myFactory(
			DefaultJmsListenerContainerFactoryConfigurer configurer) {
		DefaultJmsListenerContainerFactory factory =
				new DefaultJmsListenerContainerFactory();
		configurer.configure(factory, connectionFactory());
		factory.setMessageConverter(myMessageConverter());
		return factory;
	}

}
Then you can use the factory in any @JmsListener-annotated method as follows:

@Component
public class MyBean {

	@JmsListener(destination = "someQueue", containerFactory="myFactory")
	public void processMessage(String content) {
		// ...
	}

}
32.2 AMQP
The Advanced Message Queuing Protocol (AMQP) is a platform-neutral, wire-level protocol for message-oriented middleware. The Spring AMQP project applies core Spring concepts to the development of AMQP-based messaging solutions. Spring Boot offers several conveniences for working with AMQP through RabbitMQ, including the spring-boot-starter-amqp “Starter”.

32.2.1 RabbitMQ support
RabbitMQ is a lightweight, reliable, scalable, and portable message broker based on the AMQP protocol. Spring uses RabbitMQ to communicate through the AMQP protocol.

RabbitMQ configuration is controlled by external configuration properties in spring.rabbitmq.*. For example, you might declare the following section in application.properties:

spring.rabbitmq.host=localhost
spring.rabbitmq.port=5672
spring.rabbitmq.username=admin
spring.rabbitmq.password=secret
See RabbitProperties for more of the supported options.

[Tip]
See Understanding AMQP, the protocol used by RabbitMQ for more details.

32.2.2 Sending a Message
Spring’s AmqpTemplate and AmqpAdmin are auto-configured, and you can autowire them directly into your own beans, as shown in the following example:

import org.springframework.amqp.core.AmqpAdmin;
import org.springframework.amqp.core.AmqpTemplate;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Component;

@Component
public class MyBean {

	private final AmqpAdmin amqpAdmin;
	private final AmqpTemplate amqpTemplate;

	@Autowired
	public MyBean(AmqpAdmin amqpAdmin, AmqpTemplate amqpTemplate) {
		this.amqpAdmin = amqpAdmin;
		this.amqpTemplate = amqpTemplate;
	}

	// ...

}
[Note]
RabbitMessagingTemplate can be injected in a similar manner. If a MessageConverter bean is defined, it is associated automatically to the auto-configured AmqpTemplate.

If necessary, any org.springframework.amqp.core.Queue that is defined as a bean is automatically used to declare a corresponding queue on the RabbitMQ instance.

To retry operations, you can enable retries on the AmqpTemplate (for example, in the event that the broker connection is lost). Retries are disabled by default.

32.2.3 Receiving a Message
When the Rabbit infrastructure is present, any bean can be annotated with @RabbitListener to create a listener endpoint. If no RabbitListenerContainerFactory has been defined, a default SimpleRabbitListenerContainerFactory is automatically configured and you can switch to a direct container using the spring.rabbitmq.listener.type property. If a MessageConverter or a MessageRecoverer bean is defined, it is automatically associated with the default factory.

The following sample component creates a listener endpoint on the someQueue queue:

@Component
public class MyBean {

	@RabbitListener(queues = "someQueue")
	public void processMessage(String content) {
		// ...
	}

}
[Tip]
See the Javadoc of @EnableRabbit for more details.

If you need to create more RabbitListenerContainerFactory instances or if you want to override the default, Spring Boot provides a SimpleRabbitListenerContainerFactoryConfigurer and a DirectRabbitListenerContainerFactoryConfigurer that you can use to initialize a SimpleRabbitListenerContainerFactory and a DirectRabbitListenerContainerFactory with the same settings as the factories used by the auto-configuration.

[Tip]
It does not matter which container type you chose. Those two beans are exposed by the auto-configuration.

For instance, the following configuration class exposes another factory that uses a specific MessageConverter:

@Configuration
static class RabbitConfiguration {

	@Bean
	public SimpleRabbitListenerContainerFactory myFactory(
			SimpleRabbitListenerContainerFactoryConfigurer configurer) {
		SimpleRabbitListenerContainerFactory factory =
				new SimpleRabbitListenerContainerFactory();
		configurer.configure(factory, connectionFactory);
		factory.setMessageConverter(myMessageConverter());
		return factory;
	}

}
Then you can use the factory in any @RabbitListener-annotated method, as follows:

@Component
public class MyBean {

	@RabbitListener(queues = "someQueue", containerFactory="myFactory")
	public void processMessage(String content) {
		// ...
	}

}
You can enable retries to handle situations where your listener throws an exception. By default, RejectAndDontRequeueRecoverer is used, but you can define a MessageRecoverer of your own. When retries are exhausted, the message is rejected and either dropped or routed to a dead-letter exchange if the broker is configured to do so. By default, retries are disabled.

[Important]	Important
By default, if retries are disabled and the listener throws an exception, the delivery is retried indefinitely. You can modify this behavior in two ways: Set the defaultRequeueRejected property to false so that zero re-deliveries are attempted or throw an AmqpRejectAndDontRequeueException to signal the message should be rejected. The latter is the mechanism used when retries are enabled and the maximum number of delivery attempts is reached.

32.3 Apache Kafka Support
Apache Kafka is supported by providing auto-configuration of the spring-kafka project.

Kafka configuration is controlled by external configuration properties in spring.kafka.*. For example, you might declare the following section in application.properties:

spring.kafka.bootstrap-servers=localhost:9092
spring.kafka.consumer.group-id=myGroup
[Tip]
To create a topic on startup, add a bean of type NewTopic. If the topic already exists, the bean is ignored.

See KafkaProperties for more supported options.

32.3.1 Sending a Message
Spring’s KafkaTemplate is auto-configured, and you can autowire it directly in your own beans, as shown in the following example:

@Component
public class MyBean {

	private final KafkaTemplate kafkaTemplate;

	@Autowired
	public MyBean(KafkaTemplate kafkaTemplate) {
		this.kafkaTemplate = kafkaTemplate;
	}

	// ...

}
[Note]
If a RecordMessageConverter bean is defined, it is automatically associated to the auto-configured KafkaTemplate.

32.3.2 Receiving a Message
When the Apache Kafka infrastructure is present, any bean can be annotated with @KafkaListener to create a listener endpoint. If no KafkaListenerContainerFactory has been defined, a default one is automatically configured with keys defined in spring.kafka.listener.*. Also, if a RecordMessageConverter bean is defined, it is automatically associated to the default factory.

The following component creates a listener endpoint on the someTopic topic:

@Component
public class MyBean {

	@KafkaListener(topics = "someTopic")
	public void processMessage(String content) {
		// ...
	}

}
32.3.3 Additional Kafka Properties
The properties supported by auto configuration are shown in Appendix A, Common application properties. Note that, for the most part, these properties (hyphenated or camelCase) map directly to the Apache Kafka dotted properties. Refer to the Apache Kafka documentation for details.

The first few of these properties apply to both producers and consumers but can be specified at the producer or consumer level if you wish to use different values for each. Apache Kafka designates properties with an importance of HIGH, MEDIUM, or LOW. Spring Boot auto-configuration supports all HIGH importance properties, some selected MEDIUM and LOW properties, and any properties that do not have a default value.

Only a subset of the properties supported by Kafka are available through the KafkaProperties class. If you wish to configure the producer or consumer with additional properties that are not directly supported, use the following properties:

spring.kafka.properties.prop.one=first
spring.kafka.admin.properties.prop.two=second
spring.kafka.consumer.properties.prop.three=third
spring,kafka.producer.properties.prop.four=fourth
This sets the common prop.one Kafka property to first (applies to producers, consumers and admins), the prop.two admin property to second, the prop.three consumer property to third and the prop.four producer property to fourth.

You can also configure the Spring Kafka JsonDeserializer as follows:

spring.kafka.consumer.value-deserializer=org.springframework.kafka.support.serializer.JsonDeseria