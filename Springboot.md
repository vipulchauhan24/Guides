#Creating Spring boot project 
https://start.spring.io/

#JPA - properties(Postgres)
spring.datasource.url=jdbc:postgresql://localhost:5432/springjpa
spring.datasource.username=root
spring.datasource.password=root
spring.jpa.hibernate.ddl-auto=create-drop
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect
spring.jpa.properties.hibernate.format_sql=true



# what is spring boot?

Spring boot is spring module used to create standalone java application.

# features

## Spring CLI
- allows us to Groovy for writing Spring boot application and avoid boilerplate code.

## Spring Initializer
- This is basically a web application, which can create an internal project structure for you.

## Spring Actuator
- This feature provides help while running Spring Boot applications.

## Starter Dependency
- With the help of this feature, Spring Boot aggregates common dependcies together and eventually improves productivity

## Auto-configration
- this feature of spring boot helps in loading the default configrations according to the project you are working on

## Logging and Security
- This feature of Spring Boot, ensures that all the applications made using Spring Boot are properly secured without any hassle.

# why spring boot?
- Stability
- Based on JVM
- Connectivity
- Cloud-Native
- Flexibility
- Open Source

# spring vs spring boot
- Spring takes time start application
- spring manages life cycle of java while spring boot need not worry about configuring a data source
- dependency injection framework while spring boot has pre-configured set of frameworks/technologies.

# What is MVC?
- It is a Java Framework which is used to build web applications which follows Model-View-Controller design pattern.
- Request -> Dispatcher servlet ->  handler mapping | controller | view resolver | view.

# What is dependency injection?
- ability of an object to supply dependency of another object. 
- uses three types of classes, namely client, injector, and service.
- the injector class creates an object of service class and injects the object to client class.

# what is inversion of control?
- A class should not configure its dependencies statically but should be configured by some other class from outside.
- A class should concentrate on the flow of the application, not creating the object.

# Types of Depedency injection
- Constructor : Dependencies provided through class contructor.
- setter : Injector method injects the dependency to the setter method exposed by the client.
- interface : Injector uses interface to provide the dependency to the client class.

# Benefits of dependency injection
- Enables easy communication between components.
- Application can be easily extended.
- Unit testing made easier.
- Reduction of Boiler plate code.

# component
- @Component is an annotation that allows Spring to automatically detect our custom beans.
- Instantiate them and inject any specified dependencies into them

# Auto Wire
- used to tell class a about existence of class b.
- add @Autowired annotation over the object created in class a referencing class b.

#Important Links

- https://mvnrepository.com/search?q=jasper

# Intallation and Setup

## Spring Boot CLI

- Download and install Apache Maven
- Download Spring boot cli
- set the environment variable

# Change Port
- add server.port = portNumber in application.properties


