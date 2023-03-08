---
title: Spring Boot
date: 2022-12-10 20:01:01 +0100
categories: [Spring, Boot]
tags: [Spring Boot]     # TAG names should always be lowercase
mermaid: true
---

# Spring BOOT

![logo](https://miro.medium.com/max/716/1*jMQ9lkY5SBnbcOlJB4aizg.png)

Please sit down and relax, start your IDE and follow this video. It will give you experience in how to use Spring Boot.


{% include embed/youtube.html id='9SGDpanrc8U' %}
_Link to video [Spring(BOOT)](https://www.youtube.com/watch?v=9SGDpanrc8U)_

## What is Spring Boot?

> Spring Boot is an amazing framework for building Java applications. It makes it easy to create stand-alone,
> production-grade Spring based Applications that you can "just run".
{: .prompt-info }
---

> This next video is a little outdated, but many principles still apply. Just watch the video, you don't have to do the
> exercise unless you really want to, it might be difficult. The video does show the progress of Spring compared to 
> video we just did.
{: .prompt-danger }

{% include embed/youtube.html id='vtPkZShrvXQ' %}
[link to  video](https://www.youtube.com/watch?v=vtPkZShrvXQ)


## Breakdown:

- Bootstrap your application
- Spring Boot is a tool to create Spring Based applications
- It's stand-alone
- Production-grade, it is NOT "Hello Wolrd"
- Just Run: it makes it very easy, and you can skip a lot of configuration

## A Flow Chart to show where you start with Spring Boot.

```mermaid
graph TD;
    A(Spring Boot)-->B{Create};
		B-->C[Production Grade];
    B-->D[Stand Alone];
    D-->E{Application};
    C-->E;
	  E-->F((Run));
```

As we can see Spring BOOT makes it very easy to build applications
[Bootstrap your project](https://start.spring.io/)

Here is an example in a very wide overview how Spring Boot helps in development:

We usually make a Service Layer, more on this topic in abstraction layers later on, for now lets see what a service
layer does:

```mermaid
graph TD;
A[Service layer]-->B(responsible to handle all the business logic) 
```
Lets say we use a database,and want to use Spring to build CRUD functions, lets see:


> Using a datbase for CRUD operations:
> SpringBoot depedency injection = switching databases is changing one line of code.
{: .prompt-info }

What you need to know:
```php
spring(boot) = "al lot of flexibility with dependencies"
```

This graph tries to  show you why, it tells us that it is just 1 line of code to change the behavior of a Spring Boot
application, and also just 1 line of code to tell the application what type of database we use:

```mermaid
graph TD
   A(Spring Boot) --> B{Application has <br>Database?}
   B -->|No| H(run)
   B -->|Yes| C{Dependency injection} -->|PostgreSQL| G(1 line of code)
   C -->|MySQL| D[1 line of code] 
```

***
> Start daily exercises [in the Code Gym](https://codegym.cc/)
{: .prompt-tip }

# [Start with: Start your journey to become a Java Developer]({% link _posts/2022-12-01-start.md %})

# [Continue with: Spring]({% link _posts/2022-12-08-spring.md %})
