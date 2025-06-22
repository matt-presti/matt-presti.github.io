---
layout: post
title: "Weekly Project Post #4"
subtitle: InvestaTrack development updates
date: 2025-06-20
thumbnail-img: /assets/img/IT.png
tags: [project, java, spring-boot, weekly-update]
author: Matthew Presti
---




**What did you do last week?**

This week I focused on Spring Boot architecture research and made a crucial design decision that will improve my implementation process. I continued familiarizing myself with the controller-service-repository pattern and began building my backend code repository.

The most valuable part was consulting with a professional Spring Boot developer, who reviewed my design. Based on his feedback, I switched from JWT token-based authentication to a simpler database-driven approach using User and UserRoleJoin tables with Spring Security's session management. Considering my goals, this is better than JWT because it's easier to implement correctly and integrates seamlessly with Spring Security without the complexity of token refresh logic.

Due to this authentication change, I redesigned my API endpoints and updated my database schema documentation.

**What do you plan to do this week?**

I'm transitioning to development by implementing the authentication code. I'll create the User and UserRoleJoin entity classes with JPA annotations, build the UserController with registration/login endpoints using BCrypt password hashing, and set up the corresponding repository and service layers.

I'll also configure the H2 database and test the authentication flow before moving to portfolio functionality.

**Are there any impediments in your way?**

The main challenge remains the Java and Spring Boot learning curve. Implementing Spring Security correctly requires understanding new concepts like UserDetails and authentication providers. Enterprise Java also has more boilerplate than the Python frameworks I'm used to.

**Reflection on the process you used last week, how can you make the process work better?**

Consulting with an experienced developer was incredibly valuable and should have been done earlier. The focus on architecture before coding continues to pay off—having a more simplistic authentication design will hopefully make implementation more straightforward.
