---
layout: post
title: "Weekly Project Post #6"
subtitle: InvestaTrack development updates
date: 2025-07-04
thumbnail-img: /assets/img/IT.png
tags: [project, java, spring-boot, weekly-update]
author: Matthew Presti
---

# Weekly Project Post

### What did you do last week?

This week I made some tangible progress with development. I successfully implemented my first two entities (User and Portfolio) with full CRUD operations and Spring Security authentication. After weeks of setup and learning, I now have working controllers with 11 endpoints total, complete with proper database relationships and JSON serialization.

I built comprehensive User and Portfolio controllers featuring GET, POST, PUT, DELETE operations, implemented JPA relationships with JOIN FETCH queries, and configured Spring Security with HTTP Basic authentication. Tons of time was spent testing the API endpoints and tweaking the implementation, which proved to be a valuable learning opportunity. Figuring out the security configuration and getting the JSON serialization to work properly with entity relationships was particularly challenging but rewarding.

### What do you plan to do this week?

I'm shifting focus to implementing the remaining three entities from my ERD: Stock, Transaction, and Position. These will complete the core investment tracking functionality and demonstrate more complex JPA relationships. 

### Are there any impediments in your way?

The main challenge continues to be the Java and Spring Boot learning curve. While I've made substantial progress, implementing the remaining entities with their complex relationships (Transaction linking Portfolio and Stock, Position tracking current holdings) will require understanding more advanced JPA concepts.

I've also had to acknowledge that my original 12-week timeline was overly ambitious. The time spent on Maven configuration, Spring Boot conventions, and understanding enterprise patterns was much longer than anticipated.

### Reflection on the process you used last week, how can you make the process work better?

Focusing on getting two entities working completely before moving on was the right approach - it gave me confidence and a solid foundation.

Moving forward, I'm prioritizing quality over quantity. Rather than rushing to implement all features, I'll perfect each entity's implementation and ensure proper testing. 

### API Testing Excerpts
```
Command: curl -u admin:password http://localhost:8080/api/users
GET /api/users - List all users (clean JSON with security applied):
[
  {
    "id": 1,
    "username": "alice",
    "firstName": "Alice",
    "lastName": "Smith",
    "createdAt": "2025-07-07T12:33:19.351165",
    "active": true,
    "fullName": "Alice Smith"
  },
  {
    "id": 2,
    "username": "bob",
    "firstName": "Bob",
    "lastName": "Johnson",
    "createdAt": "2025-07-07T12:33:19.371685",
    "active": true,
    "fullName": "Bob Johnson"
  },
...

===========================================
4. TESTING CRUD OPERATIONS
===========================================

Command: curl -X POST http://localhost:8080/api/portfolios -H 'Content-Type: application/json' -d '{...}'
POST /api/portfolios - Creating new portfolio via API:
Creating portfolio for user ID 1...
Verifying the portfolio was created
Command: curl -u admin:password http://localhost:8080/api/portfolios/user/1
Verification - Alice's portfolios after creation attempt:
[
  {
    "portfolioID": 1,
    "name": "Growth Portfolio",
    "description": "Test portfolio for Alice",
    "totalValue": 10000.00,
    "totalCost": 9500.00,
    "createdAt": "2025-07-07T12:33:19.417114",
    "updatedAt": "2025-07-07T12:33:19.41713",
    "user": {
      "id": 1,
      "username": "alice",
      "firstName": "Alice",
      "lastName": "Smith",
      "createdAt": "2025-07-07T12:33:19.351165",
      "active": true,
      "fullName": "Alice Smith"
    },
    "gainLoss": 500.00,
    "gainLossPercentage": 5.2600
  },
  {
    "portfolioID": 4,
    "name": "API Test Portfolio",
    "description": "Portfolio created via REST API for testing",
    "totalValue": 25000.00,
    "totalCost": 23000.00,
    "createdAt": "2025-07-07T12:33:19.98321",
    "updatedAt": "2025-07-07T12:33:19.983228",
    "user": 1,
    "gainLoss": 2000.00,
    "gainLossPercentage": 8.7000
  }
]
```
