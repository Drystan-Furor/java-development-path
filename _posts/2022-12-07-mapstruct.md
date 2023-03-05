---
title: Mapstruct
date: 2022-12-07 20:01:01 +0100
categories: [Tools, mapstruct]
tags: [mapping data]     # TAG names should always be lowercase
---
> ### Start daily exercises [in the Code Gym](https://codegym.cc/)
{: .prompt-tip }

# MapStruct

![logo](https://mapstruct.org/images/mapstruct.png)
## A Java compiler plugin (IDE independent)

---

> MapStruct is a new way of mapping data that generates Java code at compilation time. It's easy to debug, has no run time
dependencies, is type safe and doesn't use reflection.
{: .prompt-info }

---

- [Documentation](https://mapstruct.org/documentation/stable/reference/html/)
- [Map me if you can! Painless bean mappings with MapStruct](https://www.youtube.com/watch?v=nvjqtWQ5zj8)
{% include embed/youtube.html id='nvjqtWQ5zj8' %}

The mapping between different data models is a common but unpleasant task for developers, e.g. when propagating data
from an internal domain model to the elements of a REST facade, UI layer or external web service.

Writing conversion code by hand is tedious and error-prone, while reflection-based solutions suffer from poor
performance and the lack of type-safety. MapStruct takes a fresh look at the issue and generates mapping code at compile
time, based on Java interface definitions. The resulting code is type-safe and super-fast, has no dependencies and is
easy to understand (and debug, if ever needed). Providing many type conversions out of the box, MapStruct also allows
you to customize and amend mappings as needed.

[Get smart with MapStruct by Filip Hrisafov](https://www.youtube.com/watch?v=ICl9gJ4o7Ec)
{% include embed/youtube.html id='ICl9gJ4o7Ec' %}
---
### MapStruct = mapping between models
> Implement mappings = boilerplate
> MapStruct generates & configure implementation

## MapStruct auto generates DTO's
Remeber what a DTO is, this is the moment that it comes together...

Mapstruct, like Lombok, provides code generation for us in compile time, (you can compile with Maven)


> Advantages of code generation:
> - Type safe
> - Quick feedback loop
> - Easy to debug
> - Plain Method Calls -> very fast
> - No runtime dependencies
> - Works on CLI or IDE
{: .prompt-info }

***

# [Start with: Start your journey to become a Java Developer]({% link _posts/2022-12-01-start.md %})

# [Continue with: What is Maven]({% link _posts/2022-12-05-day2.md %})
