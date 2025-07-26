---
layout: post
title: "Weekly Project Post #7"
subtitle: InvestaTrack development updates
date: 2025-07-11
thumbnail-img: /assets/img/IT.png
tags: [project, java, spring-boot, weekly-update]
author: Matthew Presti
---
### What did you do last week?

I have been working on implementing the remaining core entities from my ERD. I’ve been deep in coding mode, working on the Stock and Transaction entities with their corresponding controllers and service layers. This has involved setting up the more complex JPA relationships, particularly getting the Transaction entity to properly link Portfolios and Stocks, and implementing the Position tracking logic for current holdings.

There continues to be a decent learning curve creating entity classes with proper annotations, building out the service layer methods, and getting the controller endpoints structured correctly.

### What do you plan to do this week?

I’m continuing with the implementation of the Stock and Transaction entities, aiming to complete both by the end of this week. Once these are finished, I’ll have all the core entities in place and can shift focus to comprehensive API testing across all endpoints.

### Are there any impediments in your way?

The complex JPA relationships between Transaction, Portfolio, and Stock entities are proving challenging as expected. Working through the proper mapping annotations and ensuring data integrity across these relationships requires careful attention to detail.

### Reflection on the process you used last week, how can you make the process work better?

Staying focused on one entity at a time continues to work well. The concentrated coding approach is helping me maintain momentum and build familiarity with the Spring Boot patterns I established earlier.
