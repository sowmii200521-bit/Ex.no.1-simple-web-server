## Ex 01 -Simple Web Server using Spring Boot

## AIM:

To develop a Simple Web Server using Spring Boot that can handle basic HTTP requests and return appropriate responses through RESTful endpoints.

## ALGORITHM:

Start a New Spring Boot Project:

Use Spring Initializr (https://start.spring.io/)

Select dependencies: Spring Web

Create the Main Application Class:

This class contains the main() method with @SpringBootApplication annotation to bootstrap the application.

Create a Controller Class:

Create a class annotated with @RestController.

Define one or more HTTP request handler methods using @GetMapping, @PostMapping, etc.

Write Endpoint Methods:

Inside the controller, define a simple method for handling GET requests (e.g., return “Hello World” when /hello is accessed).

Run the Application:

Run the application using your IDE or via the command line (mvn spring-boot:run or ./mvnw spring-boot:run).

Test the Endpoint:

Open a web browser or use Postman to visit:
http://localhost:8080/hello

You should see the output (e.g., "Hello World").

Stop the Server.

Stop the Spring Boot server once testing is complete.

## Program

```
simple-web-server/
├── src/
│ └── main/
│ ├── java/
│ │ └── com.example.simple_web_server/
│ │ ├── SimpleWebServerApplication.java
│ │ └── HelloController.java
│ └── resources/
│ └── application.properties
├── pom.xml
```

### pom.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>4.0.6</version>
		<relativePath/> <!-- lookup parent from repository -->
	</parent>
	<groupId>com.example</groupId>
	<artifactId>simple-web-server</artifactId>
	<version>0.0.1-SNAPSHOT</version>
	<name>simple-web-server</name>
	<description/>
	<url/>
	<licenses>
		<license/>
	</licenses>
	<developers>
		<developer/>
	</developers>
	<scm>
		<connection/>
		<developerConnection/>
		<tag/>
		<url/>
	</scm>
	<properties>
		<java.version>21</java.version>
	</properties>
	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-webmvc</artifactId>
		</dependency>

		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-webmvc-test</artifactId>
			<scope>test</scope>
		</dependency>
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
		</plugins>
	</build>

</project>
```

### SimpleWebServerApplication.java

```java
package com.example.simple_web_server;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class SimpleWebServerApplication {

	public static void main(String[] args) {
		SpringApplication.run(SimpleWebServerApplication.class, args);
	}

}
```

### HelloController.java

```java
package com.example.simple_web_server;

import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class HelloController {

    @GetMapping("/hello")
    public String hello() {
        return "Hello, Spring Boot!";
    }
}
```

### application.properties:

```properties
spring.application.name=simple-web-server
```

### Output:

<img width="1046" height="552" alt="image" src="https://github.com/user-attachments/assets/b3ccaf37-a594-4193-8776-fcf0b964faf4" />
