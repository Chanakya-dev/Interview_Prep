### 1. What is Spring Boot?
Spring Boot is an extension of the Spring framework that simplifies the process of building production-ready applications. It provides a set of conventions and configurations to quickly set up a Spring application without requiring extensive configuration.

### 2. Can you explain the request handling flow in a Spring Boot application?
The request handling flow begins with the main() method in the application class annotated with @SpringBootApplication, which initializes the Spring context. When a request is received, the dispatcher servlet intercepts it and routes it to the appropriate controller based on the URL mappings defined with annotations like @RequestMapping. The controller processes the request, interacts with the service and repository layers as needed, and then returns a response, which is sent back to the client.

### 3. What are the key annotations used in Spring Boot?
Some key annotations in Spring Boot include:
@SpringBootApplication: Indicates a Spring Boot application.
@RestController: Combines @Controller and @ResponseBody, allowing for RESTful web services.
@RequestMapping: Maps HTTP requests to handler methods.
@Autowired: Automatically injects beans.
@Value: Injects values from application properties.
@Component: Indicates a Spring-managed component.

### 4. What is the purpose of application.properties/application.yml in Spring Boot?
The application.properties or application.yml file is used for externalized configuration in a Spring Boot application. It allows you to define application-specific settings, such as database connection details, server port, logging levels, and custom properties.

### 5. How can you create a RESTful web service using Spring Boot?
- Annotate a class with @RestController.
- Define endpoints using methods annotated with @RequestMapping (or its shortcuts like @GetMapping, @PostMapping, etc.).
- Return data (e.g., objects or collections) as responses, which are automatically serialized to JSON.

### 6. What is the use of Spring Boot Starter?
Spring Boot Starters are a set of convenient dependency descriptors that simplify the inclusion of various Spring and third-party libraries in your project. For example, spring-boot-starter-web includes dependencies for building web applications, including Spring MVC, Tomcat, and JSON handling.

### 7. How can you connect to a database in Spring Boot?
- Add the appropriate database dependency to your pom.xml or build.gradle.
- Configure the connection settings (URL, username, password) in application.properties or application.yml.
- Use Spring Data JPA or JDBC for database operations, and annotate your repository interfaces with @Repository.

### 8. What is Spring Data JPA?
Spring Data JPA is a part of the Spring Data project that simplifies database access by providing an abstraction layer over JPA (Java Persistence API). It allows developers to create repositories using interfaces and automatically generates queries based on method names.

### 9. How can you handle exceptions globally in Spring Boot?
You can handle exceptions globally in Spring Boot by using @ControllerAdvice along with @ExceptionHandler. This allows you to define a centralized exception handling mechanism for all controllers, returning appropriate HTTP status codes and error messages.

### 10. What is the difference between @Component, @Service, and @Repository annotations?
@Component: A generic stereotype for any Spring-managed component.
@Service: Used to indicate that a class provides business logic; it is a specialization of @Component.
@Repository: Indicates a DAO (Data Access Object) class that interacts with the database; it is also a specialization of @Component and provides exception translation.

### 11. What is Spring Boot Actuator?
Spring Boot Actuator is a set of built-in tools that provides production-ready features for monitoring and managing Spring Boot applications. It exposes various endpoints for application health, metrics, environment information, and more, helping developers manage their applications effectively.

### 12. How do you secure a Spring Boot application?
To secure a Spring Boot application, you can use Spring Security, which provides authentication and authorization features. You can configure security settings, define user roles, and protect endpoints using annotations like @PreAuthorize or through XML configuration.

### 13. How can you externalize configuration in Spring Boot?
You can externalize configuration in Spring Boot by using application properties files, YAML files, environment variables, or command-line arguments. Spring Boot will automatically read these configurations and inject them into your beans using the @Value annotation or @ConfigurationProperties.

### 14. What is a Spring Boot profile?
Spring Boot profiles are a way to segregate parts of your application configuration and make it available only in certain environments (e.g., development, testing, production). You can define multiple profiles in your application.properties or application.yml file and activate them using the spring.profiles.active property.

### 15. How can you implement caching in Spring Boot?
You can implement caching in Spring Boot by using the @EnableCaching annotation on a configuration class and then using the @Cacheable, @CachePut, and @CacheEvict annotations on methods to define caching behavior. Spring Boot supports various cache providers, including Ehcache, Hazelcast, and Redis.

### 16. What is the purpose of @SpringBootApplication annotation?
The @SpringBootApplication annotation is a convenience annotation that combines @Configuration, @EnableAutoConfiguration, and @ComponentScan. It marks the main class of a Spring Boot application and enables auto-configuration, allowing Spring Boot to automatically configure beans based on the classpath and other settings.

### 17. How can you customize the embedded Tomcat server in Spring Boot?
You can customize the embedded Tomcat server in Spring Boot by configuring properties in the application.properties or application.yml file, such as setting the server port, context path, and session timeout. Additionally, you can create a TomcatServletWebServerFactory bean for more advanced customizations.

### 18. How can you enable Swagger in a Spring Boot application?
To enable Swagger in a Spring Boot application, you can add the Swagger dependency (e.g., springfox-swagger2 and springfox-swagger-ui) to your project. Then, annotate a configuration class with @EnableSwagger2 and configure Docket beans to customize API documentation.

### 19. What is the purpose of @RequestMapping and its variants?
@RequestMapping is used to map HTTP requests to specific handler methods in a controller. Its variants, such as @GetMapping, @PostMapping, @PutMapping, and @DeleteMapping, provide shortcuts for the respective HTTP methods, making it easier to define RESTful APIs.

### 20. How can you implement pagination and sorting in Spring Boot?
You can implement pagination and sorting in Spring Boot by using the Pageable and Sort interfaces provided by Spring Data JPA. You can define methods in your repository that accept these parameters, and Spring Data will automatically handle the pagination and sorting logic.
