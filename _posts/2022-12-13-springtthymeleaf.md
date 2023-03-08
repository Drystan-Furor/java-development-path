---
title: Spring Thymeleaf
date: 2022-12-13 20:01:01 +0100
categories: [Spring, Thymeleaf]
tags: [server-side Java template engine]     # TAG names should always be lowercase
mermaid: true
---
# What is Thymeleaf?
![logo](https://raw.githubusercontent.com/thymeleaf/thymeleaf-org/main/artwork/thymeleaf%202016/thymeleaf_logo_white.png)
_Thymeleaf logo_

# [ThymeLeaf](https://www.youtube.com/watch?v=hoVUmn8ZCOo "TUTORIAL")

{% include embed/youtube.html id='hoVUmn8ZCOo' %}



> * Thymeleaf is a server-side Java template engine for both web and standalone environments, capable of processing HTML, XML, JavaScript, CSS and plain text (RAW).
> * It is commonly used to generate HTML views for web apps.
{: .prompt-info }

```mermaid
graph TD
   Z(Java)--> |Templates|A
   A(Thymeleaf) --> |Engine|B{SERVER}
   B --> H(Web)
   B -->C[Standalone] 
   C --> D
   H --> D
   K(HTML)
   L(XML)
   M(JavaScript)
   N(CSS)
   O(RAW)
   D((Processing)) --> K
   D --> L
   D --> M
   D --> N
   D --> O
```
---
## What is a Thymeleaf template?
- HTML with Thymeleaf expressions
- Dynamic content from Thymeleaf expressions
```mermaid
graph TD
   Z(Java)--> A
   A(Thymeleaf)
   Y((Can access:<br> Java Code, objects,<br> Spring Beans))--- A
```

The Thymeleaf engine will parse a Thymeleaf Template.
It uses Java model data to replace the positions marked on the Thymeleaf Template to create a new text in the HTML Page.

---
# Model + Inclusion statement + view = result

## MODEL
```java
public class Person {
    private String firstName;
    private String lastName;
}
```

## INCLUSION STATEMENT
```html
<div th:replace="fragments/header :: header">...</div>
```

## VIEW(Thymeleaf Template)
```html
<!DOCTYPE html>
<html>
<head>
    ...
</head>
<body>
...
<div th:replace="fragments/header :: header">
    <!-- ============================================================================ -->
    <!-- This content is only used for static prototyping purposes (natural templates)-->
    <!-- and is therefore entirely optional, as this markup fragment will be included -->
    <!-- from "fragments/header.html" at runtime.                                     -->
    <!-- ============================================================================ -->
    <div class="navbar navbar-inverse navbar-fixed-top">
        <div class="container">
            <div class="navbar-header">
                <a class="navbar-brand" href="#">Static header</a>
            </div>
            <div class="navbar-collapse collapse">
                <ul class="nav navbar-nav">
                    <li class="active"><a href="#">Home</a></li>
                </ul>
            </div>
        </div>
    </div>
</div>
<div class="container">
    <div class="hero-unit">
        <h1>Thymeleaf Template</h1>
        <div>
            <table>
                <tr>
                    <th>First Name</th>
                    <th>Last Name</th>
                </tr>
                <tr th:each="person:#(persons)">
                    <td th:utext="@(person.firstName)">...</td>
                    <td th:utext="@(person.lasstName)">...</td>
                </tr>
            </table>
        </div>
        <p>
            <a href="/signup" th:href="@{/signup}" class="btn btn-large btn-success">Sign up</a>
        </p>
    </div>
    <div th:replace="fragments/footer :: footer">&copy; 2016 The Static Templates</div>
</div>
</body>
</html>
```

> Inspect Me with developer Tools.
> Right Click - > Inspect.
> Look at the HTML vs what you see
{: .prompt-tip }

<!DOCTYPE html>
<html>
  <head>
    ...
  </head>
  <body>
    ...
    <div th:replace="fragments/header :: header">
      <!-- ============================================================================ -->
      <!-- This content is only used for static prototyping purposes (natural templates)-->
      <!-- and is therefore entirely optional, as this markup fragment will be included -->
      <!-- from "fragments/header.html" at runtime.                                     -->
      <!-- ============================================================================ -->
      <div class="navbar navbar-inverse navbar-fixed-top">
        <div class="container">
          <div class="navbar-header">
            <a class="navbar-brand" href="#">Static header</a>
          </div>
          <div class="navbar-collapse collapse">
            <ul class="nav navbar-nav">
              <li class="active"><a href="#">Home</a></li>
            </ul>
          </div>
        </div>
      </div>
    </div>
    <div class="container">
      <div class="hero-unit">
        <h1>Thymeleaf Template</h1>
						<div>
							<table>
								<tr>
									<th>First Name</th>
									<th>Last Name</th>
								</tr>
<!--=====================Thymeleaf injected table==================== -->
								<tr th:each ="person:#(persons)">
									<td th:utext="@(person.firstName)">...</td>
									<td th:utext="@(person.lasstName)">...</td>
<!--=========================================================== -->
								</tr>
							</table>
		  </div>
        <p>
          <a href="{% link _posts/2022-12-01-start.md %}" th:href="@{/signup}" class="btn btn-large btn-success">Sign up</a>
        </p>
      </div>
      <div th:replace="fragments/footer :: footer">&copy; 2016 The Static Templates</div>
    </div>
    ...
  </body>
</html>

---
## RESULT
<div>
							<table>
								<tr>
									<th>First Name</th>
									<th>Last Name</th>
								</tr>
								<tr>
									<td>Bill</td>
									<td>Gates</td>
								</tr>
								<tr>
									<td>Steve</td>
									<td>Jobs</td>
								</tr>
							</table>
		  </div>
		  
---

## How is it processed?

```mermaid
graph TD
   Z(MODEL java Class)--> B
   A(Thymeleaf Template) --> B
   B[Template engine] --> C{VIEW HTML}
```

---
## Where is Thymeleaf template processed?
* In a web app, Thymeleaf is processedo n the server.
* Results are included in the HTML and returned to the browser

```mermaid
graph TD
   1{Thymeleaf<br>SERVER <br>Processing}
   1 --> 2(HTML)
   2 --> 3[Client]
   3 --> 4
   4((Request)) --> 1
   
A[Client]
B[employeee controller]
C[Employee Service]
D[employee Repository]
E[Database]
F(employees list <br>VIEW<br>HTML<br>Table)

A-->|request|B
B-->C
C-->B
C-->D
D-->C
D-->E
E-->D

B-->|HTML|F
F-->A

```

---
# Where to start?
[Templates First](https://www.youtube.com/watch?v=1PHTH1uRtlk)
{% include embed/youtube.html id='1PHTH1uRtlk' %}

1. Start with the template so you can prototype
2. Prototype to determine requirements early

***
> Start daily exercises [in the Code Gym](https://codegym.cc/)
{: .prompt-tip }

# [Start with: Start your journey to become a Java Developer]({% link _posts/2022-12-01-start.md %})
# [Continue with: Spring]({% link _posts/2022-12-08-spring.md %})
