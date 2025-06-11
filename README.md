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
- [Features](#features)
- [Topics Covered](#topics-covered)
- [How to Use](#how-to-use)
- [Contributing](#contributing)
- [License](#license)

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

## 🚀 How to Use

1. **Browse Questions:** Go through the list of questions and answers.
2. **Practice:** Try to answer questions yourself before reading the answers.
3. **Contribute:** Add your own questions or improve existing ones!

---

## 🤝 Contributing

I welcome contributions!  
Feel free to fork the repo, create a new branch, and submit a pull request.  

Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

> ⭐️ **Star this repository to keep it on your radar and help others discover it!**
