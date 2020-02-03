This application about my learning spring boot in documentation.
https://docs.spring.io/spring-boot/docs/2.2.4.RELEASE/reference/html/index.html

First all we include in pom:

<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>

In documentation teache instaling spring CLI, but i dont want that. I will do in future to test.


Main points in this first section is:

The annotaion @RestController and @RequestMapping is Spring MVC annotations (they are not specific to Spring Boot).

We can use line command "mvn package" to create a file jar it will create file into target and this jar you can use
command line to start with "java -jar target/myproject-0.0.1-SNAPSHOT.jar"

So in this point we version our application using

git init
git add .
git commit -m "Example Commit Message"
git remote add origin https://github.com/user/repo.git
git push -u origin master

A good point about spring dependencies is sicronyze all version if you change the dependencie of spring boot.
	"In practice, you do not need to provide a version for any of these dependencies in your build configuration, as Spring Boot manages that for you."
	
And the most importante:
	"Each release of Spring Boot is associated with a base version of the Spring Framework. We highly recommend that you not specify its version."
	
It's here a explanation about packages in java if you dont know what conventions is.

https://docs.oracle.com/javase/tutorial/java/package/namingpkgs.html

Put in your class main @EnableAutoConfiguration or @SpringBootApplication to able auto-configuration the spring boot in your project. Never use together this annotations.

To configure our project spring the form sample, the docs of spring sugest include in our main class @ComponentScan without any arguments, that it will register 
all (@Component, @Service, @Repository, @Controller etc.) as Spring Beans.

reference at website: https://docs.spring.io/spring-boot/docs/2.2.4.RELEASE/reference/html/using-spring-boot.html#using-boot

```java

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

```