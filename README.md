# Back End Project

## Overview

Create an application (RESTful Web API) to provide/manipulate food truck information for the Charlotte area. Please find the requirements outlined below. These are just basic guidelines; extra features are always encouraged. Please use your judgement for how to best design and implement this application.

## Requirements

### Language

Choose either Java Spring, .NET Core, or Node.js to build this project. Finish one of the below courses or any other courses you find relevant before attempting the project.

- [Java Spring Course](https://www.udemy.com/spring-hibernate-tutorial/)
- [.NET Course](https://www.udemy.com/aspnet-core-20-e-commerce-web-site-based-on-microservices-and-docker/)
- [Node.js](https://www.udemy.com/course/the-complete-nodejs-developer-course-2/)

### Basics

Create an RESTful API for creating, reading, updating, and deleting food truck information in a persistent data store.

### Code-First Approach

- Use Hibernate as an ORM in conjunction with JPA for if you are building your application in Java Spring.
- Use Entity Framework Core ORM if you are building your application in .NET Core.
- Use Sequelize or Bookshelf ORM if you are building your application in Node.js.

### Authentication

Implement JWT (JSON Web Token) authentication

- Users should be able to register as a user on the application.
- Users should be able to login into the application using their username and password that they set up during registration.
- All the application endpoints should be secure, meaning only users with an auth token should be granted access, otherwise a `401 Unauthorized` code should be returned.

### Users

- Users should have the ability to view all of the users that are registered in the application (Note: This should not display sensitive data like Password).
- Users should have the ability to search any other user by ID and see all of the trucks marked as "favorite" by that user.

### Categories

- Users should have the ability to create a new category of food truck. Categories are global to the application and each food truck can be in one or more categories.
- Users should have the ability to list all the categories of food trucks in the application.

### Trucks

- Users should have the ability to create a new food truck with following properties:
  ```
       ID: non-empty unique alpha-numeric characters
       Name: 1-50 characters
       Price: a choice between `$`, `$$`, `$$$`, `$$$$`
       Rating: from `1.0` to `5.0`
       Total Number of Ratings: integer
       Open hours: an array of daily hours
       Phone number: a string of digits
       Categories: A list of categories. A truck can have many categories.
       Coordinates: latitude and longitude
       Location: an object with street address, city, state, country and zipcode properties
       Created by: The user who created the truck
  ```
- Users should have the ability to view all the trucks in the application.
- Users should have the ability to search a specific food truck by ID.
- Users should have the ability to query all the trucks based on price, rating, and/or category and view the trucks that meet the search criteria.
- Users should have the ability to rate a truck (this should change the rating of the truck).
- Users should have the ability to update a truck (and all its properties) by ID **IF** that truck was created by the user making the update.
- Users should have the ability to delete a food truck from the database **IF** the truck was created by the user deleting the truck.

### Favorites

- Users should have the ability to add a truck to his/her favorites list.
- Users should have the ability to delete a truck from his/her favorites list.
- Users should have the ability to view his/her favorite trucks.

### Database

- Feel free to use any Relational Database. We suggest using Postgres, or MySQL.

### Unit Testing

- There should be an appropriate amount of unit testing using any testing framework that you desire.
  - We suggest NUnit for .Net Core applications; JUnit for Java applications; and Jest for Node.js applications. More links and suggests are found below.
- Tests should test core business logic - no need to test methods that are just making a function call or returning a constant or testing database calls/connections.

### Deployment

- Deploy the application to one of the following platforms - AWS, Azure, or GCP.
- Setup security so that only your IP and Levvel office IPs (we can provide this list when you are ready) can access the website.

## Suggested Readings

- API Design: https://hackernoon.com/restful-api-designing-guidelines-the-best-practices-60e1d954e7c9

#### .NET Core

- JWT Auth: https://jasonwatmore.com/post/2019/10/11/aspnet-core-3-jwt-authentication-tutorial-with-example-api
- Entity Framework Core Relationships: https://www.learnentityframeworkcore.com/configuration/one-to-many-relationship-configuration
- AutoMapper: https://code-maze.com/automapper-net-core/
- Unit Testing: https://docs.microsoft.com/en-us/dotnet/core/testing/

#### Java Spring

- Spring Boot in Action (**highly** recommend the following selections)

  - Chapter 1: Background of Spring, the _why_, and the different kinds of **magical** things that spring does for you
  - Chapter 2: Building your first spring app and understanding **DI (Dependency Injection)**
  - Chapter 3: Explains Spring Configuration - you'll want to pay close attention during the security section to understand how spring will authenticate various routes
  - Chapter 4: Testing - yes you shoud be testing :eyes: It is worth noting that this discusses integration testing _not_ unit testing - The unit testing piece is slightly out of date so use the resource below to learn about JUnit in spring-boot.

  The rest of the book isn't exceptionally helpful for the completion for this project, but still highly recommended

- If you supplement the book with an understanding of unit testing, JWTs/authentication, and spring data-jpa you will have a solid foundation for completing the project. Here are some helpful links for all of those:
  - Unit Testing: https://reflectoring.io/unit-testing-spring-boot/
    - This covers both unit testing and mocking with Mockito
  - JWT Auth: https://medium.com/@xoor/jwt-authentication-service-44658409e12c
  - Data-JPA: https://spring.io/guides/gs/accessing-data-jpa/
- Useful concepts to google when you are stuck
  - **@Component** - basic building block in spring-boot - makes the annotated class discoverable by the spring context and available for dependency injection
  - **Dependency Injection**
  - **@RestController** - (You may see @Controller, but that annotation is for view controllers not REST APIs)
  - **spring data-jpa** - This will make your life a _lot_ easier when setting up your database models
    - **@Entity**
    - **@Repository**

#### Node.js

- In addition to the course listed at the top of this README, here are some suggested readings and resources that could help you develop your Node.js application.
- Using Express.js with Node.js to host web applications:
  - https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/Introduction
  - https://www.tutorialspoint.com/nodejs/nodejs_express_framework.htm
- Unit Testing with Jest:
  - https://medium.com/@bcostabatista/testing-nodejs-applications-with-jest-7ae334daaf55 (Just the section on unit testing, do not need to worry about Integration or End-2-End testing)
  - https://medium.com/@ddevinda/unit-test-for-nodejs-using-jest-e7f52cbb131c
- Node.js ORMs:
  - Sequelize: https://dev.to/nedsoft/getting-started-with-sequelize-and-postgres-emp
  - Bookshelf: https://stackabuse.com/bookshelf-js-a-node-js-orm/
- Feel free to do your own independent research on these topics and more as well!
