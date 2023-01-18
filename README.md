# SpringNotes


- Spring’in IOC tarafından yönetilen objelere **********Bean********** denir.
- A bean is an object that is instantiated, assembled, and otherwise managed by a Spring loC container.
- Bir uygulama içerisinde üretilen tüm bean’lerin spring tarafından yönetilmesine ihtiyac yoktur.
- Java bean, default constractur olan tüm fieldları private olan getter setter methodları olan kastedilir. Ama spring beande default constructor olmasına gerek yoktur.

## Spring IOC

Spring IOC (Inversion of Control) is a technique used in software development to manage the dependencies between objects. It allows objects to be designed and built independently of each other, and then have their dependencies injected at runtime. This means that the objects do not need to know how to create or locate the objects they depend on, and can instead focus on their own specific functionality.

IOC container is responsible for managing these object dependencies, creating objects and injecting them into other objects as needed. This makes the code more modular, reusable, and easier to test and maintain.

## Bean

In the Java Spring Framework, a "bean" is a Java object that is managed by the Spring Framework. The Spring Framework uses a concept called Inversion of Control (IoC) to manage these beans and their dependencies. This means that rather than a bean having to look up its dependencies and manage them on its own, the Spring Framework will handle creating and managing the dependencies for the bean.

Beans are defined in Spring configuration files, which specify how the beans should be created and configured. The configuration files can be written in XML or in Java. Once the beans are defined, the Spring Framework can be used to retrieve the beans and use them in the application.

In simple terms, beans in Spring Framework are just Java objects that are managed by the framework, these beans are created and initialized with their dependencies by the spring framework, you can use these beans in your application.

## Dependencies

In the context of the Spring Framework, "dependencies" refers to the other objects that a bean needs in order to function properly. These dependencies can include other beans, external services, or resources such as a database.

For example, imagine that you have a bean that represents a user service in your application. This bean might have a dependency on a bean that represents a user repository, which is responsible for storing and retrieving user data from a database. The user service bean would need the user repository bean in order to function properly, so the user repository bean would be considered a dependency of the user service bean.

Dependencies can also be defined as setter or constructor injection, which means that when the bean is created, it's dependency is passed in constructor or setter method.

In summary, dependencies are the objects that a bean needs to function properly, they can be other beans, external services or resources, and they can be passed in the constructor or setter method.

## BeanFactory and ApplicationContext

- Resource’u yükleme kabiliyeti vardır.

BeanFactory and ApplicationContext are both implementations of the Spring IoC container. The BeanFactory is the most basic implementation and provides the basic functionality of an IoC container. It is responsible for instantiating, configuring, and managing the lifecycle of beans, which are objects defined in the configuration.

ApplicationContext is an extension of the BeanFactory, providing additional functionality such as the ability to resolve messages from resource bundles, and support for internationalization. It also provides event propagation, making it easier for beans to communicate with each other. Additionally, it offers support for annotation-based configuration and aspect-oriented programming.

In simple terms, BeanFactory is a lightweight container and ApplicationContext is a more advanced and feature-rich container. BeanFactory is typically used in simple and small-scale applications, while ApplicationContext is better suited for more complex and large-scale applications.

- ClassPathXMLApplicationContext takes the context definition files in classpath using packageName/resource. xm1 style.
- SystemFilePathXMLApplicationContext takes the context definition files in file system using absolute path with file: prefix or relative path when used without any prefix.

ApplicationContext context = new ClassPathXmlApplicationContext("org/javaturk/spring/beans.xml");

ApplicationContext context = new FileSystemXmApplicationContext("file: /Users/akin/beans. xml");

- XML-based configuration metadata configures beans as <bean/> elements inside a top-level <beans/> element.
- @Component and other annotations are used to designate beans.
- Java configuration typically uses @Bean-annotated methods within a
@Configuration class.
- And Spring container represents bean definitions by
org.springframework.beans.factory.config. BeanDefinition objects.
