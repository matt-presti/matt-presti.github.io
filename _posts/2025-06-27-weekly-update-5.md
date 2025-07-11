---
layout: post
title: "Weekly Project Post #5"
subtitle: InvestaTrack development updates
date: 2025-06-27
thumbnail-img: /assets/img/IT.png
tags: [project, java, spring-boot, weekly-update]
author: Matthew Presti
---

## Weekly Project Post


### Development Progress

This week I focused on project setup and establishing the development environment. I installed Java 17 and IntelliJ IDEA, then used Spring Initializr to create the Spring Boot project with the necessary dependencies including Spring Web, Spring Data JPA, H2 Database, Spring Security, and Validation.

I organized the project structure with proper package hierarchy for controllers, models, repositories, services, and config. After initializing the Git repository, I confirmed the basic Spring Boot application runs successfully on localhost:8080. The development environment is now configured and ready for authentication implementation.

### Challenges and Next Steps

Setting up the project and configurations has been more conceptually challenging than I anticipated. Understanding how all the Spring Boot components work together and figuring out the proper order for development has been a valuable learning process though time consuming.

Next week I'll begin implementing the authentication system by creating the User entity classes and building the authentication endpoints. I hope that the project foundation is now sufficient to start the actual coding work.
