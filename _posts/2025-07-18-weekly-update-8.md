---
layout: post
title: "Weekly Project Post #8"
subtitle: InvestaTrack development updates
date: 2025-07-18
thumbnail-img: /assets/img/IT.png
tags: [project, java, spring-boot, weekly-update]
author: Matthew Presti
---

### What did you do last week?

I successfully completed the implementation of all remaining core entities (Stock, Transaction, and Position) along with their initial controller endpoints. All six entities from my original ERD are now in place with basic CRUD operations defined. However, integrating these entities together has revealed significant challenges with the relationships I designed.

The majority of my time was spent debugging issues with entity relationships and JSON serialization. I'm encountering circular reference problems when Jackson tries to serialize entities with bidirectional relationships, particularly between Portfolio-Transaction-Stock entities and the Position tracking logic. Even with @JsonIgnore and @JsonManagedReference/@JsonBackReference annotations, I'm getting inconsistent serialization behavior that breaks API responses.

I've also run into cascade operation issues where creating a new Transaction sometimes fails to properly link to existing Portfolio and Stock entities, throwing constraint violation exceptions. 

Basic API testing with Postman has been challenging. GET requests work for individual entities, but endpoints involving entity relationships either return malformed JSON or throw serialization errors.

### What do you plan to do this week?

My priority is debugging these relationship and serialization issues. I need to review my JPA annotations  and potentially restructure some of the relationships. Since my ERD focuses on one-to-many relationships rather than complex many-to-many mappings, I expected this to be doable.  I'm also considering implementing DTOs (Data Transfer Objects) to avoid the JSON serialization problems entirely.

Once I resolve these fundamental issues, I can move forward with robust API testing across all endpoints to demonstrate a fully functional backend.

### Are there any impediments in your way?

The main impediment for me is being relatively new to Spring Boot and Java. I am learning the hard way that the actual implementation and testing takes time and experience to become familiar with and to achieve competency. That said, it has provided invaluable learning experience even if frustrating at times. 

### Reflection on the process you used last week, how can you make the process work better?

The iterative development approach I've been using has proven to be highly valuable. Building and testing each entity incrementally has made debugging much more manageable than if I had tried to implement everything at once. Being able to isolate issues to specific entity relationships rather than debugging a completely integrated system has saved significant time.


### My ERD: 
![InvestaTrack Entity Relationship Diagram](/assets/img/erd.png)
