# 🌱 Spring Interview Questions

![Spring Logo](https://spring.io/img/spring-2.svg)

<p align="center">
  <img src="https://img.shields.io/badge/Spring-Framework-6DB33F?style=for-the-badge&logo=spring&logoColor=white"/>
  <img src="https://img.shields.io/github/stars/yourusername/spring-interview-questions?style=for-the-badge" />
  <img src="https://img.shields.io/github/forks/yourusername/spring-interview-questions?style=for-the-badge" />
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=for-the-badge" />
</p>

---

Welcome to the **Spring Interview Questions** repository!  
Your go-to resource for preparing for Spring Framework interviews.  
This repo contains a comprehensive collection of questions and answers covering a wide range of topics and difficulty levels.

---

## 📚 Table of Contents

- [Introduction](#introduction)

---

## 📝 Introduction

This repository aims to help you prepare for Spring Framework interviews by providing a curated list of commonly asked questions along with detailed answers.  
Whether you're a **beginner** or an **experienced developer**, this resource will help you enhance your Spring knowledge and be well-prepared for your next interview.

---

## ✨ Features

- ✅ Covers Spring Core, Boot, Data, Security, MVC, and more
- ✅ Questions for all experience levels
- ✅ Regularly updated with new questions
- ✅ Community contributions welcome

---

## 📖 Topics Covered

- Spring Core

---

### Top 50 Spring Core Interview Questions & Answers (SWE 2 Level)

1. **Explain the difference between constructor and setter injection. When would you use each?**  
   Constructor injection ensures all required dependencies are provided at object creation, making the object immutable. Setter injection allows optional dependencies and can be used for circular dependencies. Use constructor injection for mandatory dependencies and setter for optional ones.

2. **How does Spring resolve ambiguity when multiple beans of the same type exist?**  
   By using `@Qualifier` annotation or marking one bean as `@Primary`.

3. **Describe the bean lifecycle in Spring and how you can hook into it.**  
   The lifecycle includes instantiation, dependency injection, post-processing, initialization, use, and destruction. You can hook using `@PostConstruct`, `@PreDestroy`, `InitializingBean`, `DisposableBean`, or custom init/destroy methods.

4. **What is the difference between `@ComponentScan` and `@Import`?**  
   `@ComponentScan` scans packages for annotated components, while `@Import` imports specific configuration classes.

5. **How do you externalize configuration in a Spring application?**  
   By using `.properties` or `.yml` files, environment variables, or command-line arguments, and injecting values with `@Value` or `@ConfigurationProperties`.

6. **What is the purpose of `@ConfigurationProperties` and how is it different from `@Value`?**  
   `@ConfigurationProperties` binds a group of properties to a bean, supporting complex types. `@Value` injects a single property value.

7. **How does Spring handle circular dependencies?**  
   Spring can resolve circular dependencies for setter injection but not for constructor injection. For constructor-based, it throws a `BeanCurrentlyInCreationException`.

8. **What is the difference between `singleton` and `prototype` bean scopes?**  
   Singleton beans are created once per container; prototype beans are created every time they are requested.

9. **How do you inject a prototype bean into a singleton bean?**  
   Use `ObjectFactory`, `Provider`, or `@Lookup` method injection.

10. **What is the use of `@Profile` annotation?**  
    It allows beans to be registered only when a specific profile is active, supporting environment-specific configurations.

11. **How do you create a custom Spring event and listener?**  
    Extend `ApplicationEvent`, publish with `ApplicationEventPublisher`, and listen using `@EventListener` or `ApplicationListener`.

12. **What is the difference between `@Component`, `@Service`, `@Repository`, and `@Controller`?**  
    All are stereotypes for component scanning. `@Service` marks service layer, `@Repository` marks data access layer (adds exception translation), `@Controller` marks web layer, and `@Component` is generic.

13. **How does Spring’s `@Transactional` annotation work?**  
    It creates a proxy around the bean, managing transaction boundaries before and after method execution.

14. **What are the limitations of field injection?**  
    Field injection makes testing and refactoring harder, hides dependencies, and prevents immutability.

15. **How do you define a custom scope in Spring?**  
    Implement `Scope` interface and register it with `ConfigurableBeanFactory`.

16. **What is the use of `@Order` annotation?**  
    It defines the order of execution for beans, such as filters, interceptors, or AOP aspects.

17. **How do you access application context from a bean?**  
    Implement `ApplicationContextAware` or inject `ApplicationContext`.

18. **What is the difference between `BeanFactoryPostProcessor` and `BeanPostProcessor`?**  
    `BeanFactoryPostProcessor` modifies bean definitions before beans are instantiated. `BeanPostProcessor` modifies bean instances after instantiation.

19. **How do you handle exceptions globally in a Spring application?**  
    Use `@ControllerAdvice` with `@ExceptionHandler` for web, or AOP for service layer.

20. **What is the use of `@Conditional` annotation?**  
    It allows beans to be registered conditionally based on custom logic.

21. **How do you inject environment variables into Spring beans?**  
    Use `@Value("${ENV_VAR}")` or inject the `Environment` object.

22. **What is the difference between `@Bean` and `@Component`?**  
    `@Bean` is used in Java config to declare beans, `@Component` is used for classpath scanning.

23. **How do you create a thread-safe singleton bean?**  
    Ensure the bean is stateless or use synchronization for mutable state.

24. **What is the use of `@Lazy` annotation?**  
    It delays bean initialization until it is first requested.

25. **How do you test Spring beans in isolation?**  
    Use `@SpringBootTest`, `@ContextConfiguration`, or mock dependencies with Mockito.

26. **What is the difference between `@Autowired` and `@Inject`?**  
    `@Autowired` is Spring-specific; `@Inject` is JSR-330 standard. Both perform dependency injection.

27. **How do you inject a list or map of beans?**  
    Autowire a `List<T>` or `Map<String, T>`; Spring injects all matching beans.

28. **What is the use of `@Primary` annotation?**  
    It marks a bean as the default candidate for autowiring when multiple beans of the same type exist.

29. **How do you reload properties at runtime in Spring?**  
    Use `@RefreshScope` (Spring Cloud), or implement a custom reload mechanism.

30. **What is the use of `@PostConstruct` and `@PreDestroy`?**  
    Annotate methods to run after dependency injection and before bean destruction.

31. **How do you create a bean only if another bean is missing?**  
    Use `@ConditionalOnMissingBean`.

32. **What is the difference between `@ImportResource` and `@Import`?**  
    `@ImportResource` imports XML configuration, `@Import` imports Java config classes.

33. **How do you inject a value from a nested property in a properties file?**  
    Use `@Value("${parent.child.property}")`.

34. **What is the use of `@DependsOn` annotation?**  
    It specifies that a bean depends on the initialization of another bean.

35. **How do you implement cross-cutting concerns in Spring?**  
    Use AOP with `@Aspect` and advice annotations.

36. **How do you create a prototype bean with request scope in a web application?**  
    Use `@Scope("request")` on the bean.

37. **What is the use of `FactoryBean` interface?**  
    It allows you to create a bean that itself produces other beans.

38. **How do you handle property placeholder resolution in Spring?**  
    Use `PropertySourcesPlaceholderConfigurer` or `@PropertySource`.

39. **What is the difference between `ApplicationContext` and `WebApplicationContext`?**  
    `WebApplicationContext` is a specialized context for web applications, extending `ApplicationContext`.

40. **How do you enable annotation-based configuration in Spring?**  
    Use `@Configuration`, `@ComponentScan`, and `@Enable*` annotations.

41. **How do you inject a bean by name?**  
    Use `@Qualifier("beanName")` with `@Autowired`.

42. **What is the use of `@EnableAspectJAutoProxy`?**  
    It enables support for handling components marked with `@Aspect`.

43. **How do you create a singleton bean that is lazily initialized?**  
    Annotate the bean with `@Lazy`.

44. **How do you access the current active profiles in a bean?**  
    Inject the `Environment` and call `getActiveProfiles()`.

45. **What is the use of `@Resource` annotation?**  
    It injects dependencies by name (JSR-250).

46. **How do you define a bean with a custom initialization method?**  
    Use `@Bean(initMethod = "methodName")` or specify `init-method` in XML.

47. **How do you exclude a bean from component scanning?**  
    Use `@ComponentScan(excludeFilters = ...)` or `@Profile` with inactive profiles.

48. **How do you inject a bean conditionally based on a property value?**  
    Use `@Conditional` or `@Profile` annotations.

49. **How do you access resources (files) in a Spring bean?**  
    Inject `ResourceLoader` or use `@Value("classpath:...")`.

50. **How do you programmatically register a bean at runtime?**  
    Use `ConfigurableApplicationContext#getBeanFactory().registerSingleton()`.

---

## 🌿 Spring Data JPA Interview Questions & Answers

<p align="center">
  <img src="https://img.shields.io/badge/Spring%20Data%20JPA-Interview%20Questions-6DB33F?style=for-the-badge&logo=spring&logoColor=white"/>
</p>

### 🟢 Level: Easy

1. **What is Spring Data JPA?**  
   Spring Data JPA is a Spring project that simplifies data access using JPA by providing repository abstractions and reducing boilerplate code.

2. **What is the purpose of the `@Entity` annotation in JPA?**  
   It marks a class as a JPA entity, mapping it to a database table.

3. **What is an EntityManager in JPA?**  
   The primary interface for interacting with the persistence context and managing entity lifecycle operations.

4. **What is the role of the `@Id` annotation in JPA?**  
   It marks a field as the primary key of the entity.

5. **How do you define a primary key in a JPA entity?**  
   Annotate a field with `@Id` (optionally with `@GeneratedValue`).

6. **What is the difference between `findById` and `getOne` methods in JPA?**  
   `findById` fetches the entity immediately; `getOne` returns a proxy and fetches lazily.

7. **What is the purpose of the `@Table` annotation in JPA?**  
   It specifies the table name and other table-level details for the entity.

8. **Explain the difference between `@Column` and `@JoinColumn`.**  
   `@Column` maps a field to a table column; `@JoinColumn` specifies the foreign key column for associations.

9. **What is the role of the `@GeneratedValue` annotation in JPA?**  
   It defines how the primary key is generated (auto, sequence, identity, table).

10. **What is the default fetch type for `@OneToMany` and `@ManyToOne` relationships in JPA?**  
    `@OneToMany` is LAZY by default; `@ManyToOne` is EAGER by default.

11. **How do you define a one-to-many relationship in JPA?**  
    Use `@OneToMany` on the parent entity and `@ManyToOne` on the child.

12. **What is a repository in Spring Data JPA?**  
    An interface extending `JpaRepository` or `CrudRepository` to provide CRUD operations.

13. **What is the purpose of the `@Repository` annotation in Spring Data JPA?**  
    It marks a class as a repository bean and enables exception translation.

14. **How do you create a custom query in Spring Data JPA?**  
    Use the `@Query` annotation on repository methods.

15. **What is the purpose of the `@Query` annotation in Spring Data JPA?**  
    It allows you to define JPQL or native SQL queries for repository methods.

16. **What is JPQL?**  
    Java Persistence Query Language, an object-oriented query language for JPA entities.

17. **What is the difference between JPQL and SQL?**  
    JPQL operates on entity objects and their properties; SQL operates on database tables and columns.

18. **What is the purpose of the `@Modifying` annotation in Spring Data JPA?**  
    It marks a query method as modifying data (insert, update, delete).

19. **How do you handle transactions in Spring Data JPA?**  
    By using the `@Transactional` annotation at the service or repository layer.

20. **What is the `@Transactional` annotation used for in Spring Data JPA?**  
    It defines the scope of a single database transaction.

21. **How do you paginate results in Spring Data JPA?**  
    By passing a `Pageable` parameter to repository methods.

22. **What is the `Pageable` interface in Spring Data JPA?**  
    It provides pagination information (page number, size, sort).

23. **What is the `Page` interface in Spring Data JPA?**  
    It represents a page of results and provides metadata like total pages and elements.

24. **How do you sort results in Spring Data JPA?**  
    By passing a `Sort` or `Pageable` parameter to repository methods.

25. **What is a derived query method in Spring Data JPA?**  
    A method whose name defines the query (e.g., `findByUsername`).

26. **What is the purpose of the `@NamedQuery` annotation in JPA?**  
    It defines a static, named JPQL query at the entity level.

27. **What is an entity lifecycle in JPA?**  
    The stages an entity goes through: new, managed, detached, removed.

28. **What are the different states of an entity in JPA?**  
    New (transient), Managed (persistent), Detached, Removed.

29. **What is the purpose of the `@PrePersist` annotation in JPA?**  
    Marks a method to be called before an entity is persisted.

30. **What is the purpose of the `@PostPersist` annotation in JPA?**  
    Marks a method to be called after an entity is persisted.

31. **What is the purpose of the `@PreUpdate` annotation in JPA?**  
    Marks a method to be called before an entity is updated.

32. **What is the purpose of the `@PostUpdate` annotation in JPA?**  
    Marks a method to be called after an entity is updated.

33. **What is the purpose of the `@PreRemove` annotation in JPA?**  
    Marks a method to be called before an entity is removed.

34. **What is the purpose of the `@PostRemove` annotation in JPA?**  
    Marks a method to be called after an entity is removed.

35. **What is the purpose of the `@PostLoad` annotation in JPA?**  
    Marks a method to be called after an entity is loaded from the database.

---

### 🟡 Level: Medium

36. **Explain the concept of entity graph in JPA and how it can be used to optimize performance.**  
    Entity graphs allow you to specify which attributes and relationships should be eagerly fetched, reducing the N+1 select problem and optimizing performance.

37. **How do you handle dynamic queries in Spring Data JPA?**  
    By using the `Specification` interface or the JPA Criteria API to build queries programmatically.

38. **What is the role of the Criteria API in JPA?**  
    It enables the creation of type-safe, dynamic queries in a programmatic way.

39. **How do you use the Criteria API to create dynamic queries in JPA?**  
    By building queries using `CriteriaBuilder`, `CriteriaQuery`, and predicates to compose flexible queries at runtime.

40. **What is the purpose of the Specification interface in Spring Data JPA?**  
    It allows you to encapsulate and reuse query logic as composable specifications.

41. **How do you use the Specification interface to create dynamic queries in JPA?**  
    Implement `Specification<T>` and combine multiple specifications using `and()`, `or()`.

42. **What is the purpose of the @Cacheable annotation in JPA?**  
    It marks an entity as eligible for second-level caching for better performance.

43. **How do you configure second-level cache in JPA?**  
    By enabling a cache provider (like Ehcache, Hazelcast) and configuring JPA properties.

44. **What is the difference between first-level and second-level cache in JPA?**  
    First-level cache is per `EntityManager` (transactional); second-level cache is shared across sessions.

45. **Explain the concept of dirty checking in JPA and how it works.**  
    JPA automatically tracks changes to managed entities and synchronizes them with the database during flush/commit.

46. **Explain the concept of cascade types in JPA and how they affect entity relationships.**  
    Cascade types determine how operations (persist, merge, remove, etc.) propagate from parent to child entities.

47. **What are the different cascade types available in JPA and when would you use each?**  
    `PERSIST`, `MERGE`, `REMOVE`, `REFRESH`, `DETACH`, `ALL`—used to control which operations affect related entities.

48. **How do you handle orphan removal in JPA and what is the purpose of the @OneToMany(orphanRemoval = true) annotation?**  
    Orphan removal automatically deletes child entities removed from their parent collection.

49. **What are the different types of entity graphs (attribute node, subgraph) in JPA and how are they used?**  
    Attribute nodes specify fields to fetch; subgraphs allow nested fetches for complex relationships.

50. **How do you optimize performance using Fetch Joins in JPQL?**  
    Use `JOIN FETCH` in JPQL queries to load related entities in a single query and avoid N+1 selects.

51. **What is the N+1 select problem in JPA and how can it be mitigated?**  
    It happens when fetching collections lazily, causing extra queries. Mitigate using fetch joins or batch fetching.

52. **Explain the purpose of the @EntityListeners annotation and how it is used in auditing.**  
    It registers callback listeners for entity lifecycle events, useful for automatic auditing.

53. **How do you handle multi-tenancy in JPA and what are the different strategies available?**  
    Use separate schemas, databases, or discriminator columns to isolate tenant data.

54. **How do you configure and use the @SequenceGenerator and @TableGenerator annotations in JPA?**  
    Use `@SequenceGenerator` for sequence-based keys and `@TableGenerator` for table-based keys by configuring them on the entity.

55. **What is the purpose of the @Converter annotation in JPA and how do you use it to create custom converters?**  
    It marks a class as a converter to map custom Java types to database columns and vice versa.

56. **How do you handle database migrations in a Spring Data JPA application?**  
    By using tools like Flyway or Liquibase to manage schema changes.

57. **What are the key considerations when implementing a custom repository in Spring Data JPA?**  
    Define a custom interface, implement it, and link it to your repository interface for advanced queries.

58. **How do you manage database connection pooling in a Spring Data JPA application?**  
    Configure a connection pool (e.g., HikariCP) in your datasource configuration.

59. **What is the role of the @SecondaryTable annotation in JPA and how do you use it to map an entity to multiple tables?**  
    It allows mapping fields of an entity to columns in a secondary table, enabling normalization.

60. **Explain the concept of Entity Detachment in JPA and how it affects the persistence context.**  
    Detached entities are no longer tracked by the persistence context; changes are not automatically persisted.

61. **How do you implement soft deletes in a Spring Data JPA application?**  
    Add a boolean or status field (e.g., `deleted`) and filter queries to exclude soft-deleted records.

62. **What are the pros and cons of using EntityManager directly versus using Spring Data JPA repositories?**  
    EntityManager offers more flexibility and control; repositories are simpler and less error-prone for standard operations.

63. **How do you handle hierarchical data structures (e.g., trees, graphs) in JPA?**  
    Use self-referencing relationships and recursive queries or custom logic.

64. **Explain the concept of database sharding and how it can be implemented in a Spring Data JPA application.**  
    Sharding splits data across databases; implement with custom routing and multiple datasources.

65. **What are the best practices for managing entity relationships and avoiding circular dependencies in JPA?**  
    Use bidirectional mappings carefully, avoid unnecessary relationships, and use DTOs for complex graphs.

66. **How do you handle large data sets and pagination efficiently in a Spring Data JPA application?**  
    Use pagination (`Pageable`), streaming, and batch processing to reduce memory usage.

67. **Explain the different types of joins (inner, outer, cross) in JPQL and provide examples of when to use each.**  
    INNER JOIN (matching rows), LEFT/RIGHT OUTER JOIN (all from one side), CROSS JOIN (cartesian product).

68. **How do you handle custom exception handling and error codes in a Spring Data JPA application?**  
    Use `@ControllerAdvice` and custom exception classes for consistent error handling.

69. **What are the key differences between Hibernate and other JPA implementations like EclipseLink?**  
    Differences include performance, caching, vendor-specific features, and community support.

70. **How do you integrate Spring Data JPA with other Spring projects like Spring Batch or Spring Integration?**  
    Inject repositories into batch jobs or integration flows for seamless data access.

---

## 🚀 How to Use

1. **Browse Questions:** Go through the list of questions and answers.
2. **Practice:** Try to answer questions yourself before reading the answers.
3. **Contribute:** Add your own questions or improve existing ones!

---

## 🤝 Contributing

I welcome contributions!  
Feel free to fork the repo, create a new branch, and submit a pull request.  

Please see [Contributing.md](Contributing.md) for guidelines.

---

> ⭐️ **Star this repository to keep it on your radar and help others discover it!**
