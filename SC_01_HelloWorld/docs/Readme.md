Spring Core
===========

Spring Beans
------------

Central to Spring Core and the Spring philosophy in general are Spring Beans. In contrast to EJB,
the Spring Framework is designed from the core to use POJO's (Plain Old Java Objects), or 'Spring
Beans'. Spring Beans are meant to be simple Java objects.

In practice, Spring Beans are one of the true beauties of the Spring Framework. Spring Beans are
meant to be simple. Thus, you as a developer are discouraged from creating overly complex objects.

Robert C Martin is known for coming up with the " Single Responsibility Principle", which is a
highly accepted fundamental of Object Oriented Programming. Martin argues your classes should have
one, and only one reason to change. Since Spring encourages you to program with simple POJOs you
will find programming with the Spring Framework naturally encourages adhering to the Single
Responsibility Principle.

Dependency Injection(DI)
------------------------

Dependency Injection is a significant strength of the Spring Framework, and was largely absent from
the original EJB specification. The current EJB specification does include Dependency Injection,
which some feel was influenced by the success of Spring. Dependency Injection is a software design
pattern where dependent objects are injected into your class.

A good example of Dependency Injection in action would be when you have a web controller handling a
form post. Following the Single Responsibility Principle, you don't want your controller class
interacting with the database. Instead, you would have some type of service class for that. Thus
your controller code would deal with the form post, and then call a method on the injected class.
The controller doesn't need to care, nor worry about the database connection, connection pooling or
what tables need to be updated. Likewise, the service does not need to know anything about the web
request. The service doesn't need to care that the data came from a form post or a JSON string.

Inversion of Control (IoC)
--------------------------

A core concept of the Spring Framework is Inversion of Control, or also known as IoC. For
application developers, this is the true strength of the Spring Framework. Through the concept of
Inversion of Control, the Spring Framework manages the software components and injection of
components into dependent objects.

Its very easy to get Dependency Injection and Inversion of Control confused. Remember, Dependency
Injection is exactly as it sounds. Dependencies are being injected into your class. Inversion of
Control is the actual injection of the dependencies. This is a subtle, yet important difference.

Dependency Injection and IoC for the Application Developer
----------------------------------------------------------

As an application developer these are two very powerful concepts. You will compose your objects to
be loosely coupled. Each will have a very specific purpose.

For example, a very common design pattern in building web applications is to use a controller for
interacting with the web tier, and inject a service object for interacting with the database tier.
The controller does not need to know anything about the database, and the service object does not
need to know anything about the web tier.

Through the power of Dependency Injection and IoC, when you're testing your controller, you can
inject a mock database service in a test configuration, and the actual database service in the
production configuration.

This concept goes beyond simple testing. This greatly impacts the maintainability of your
application. For example, if a change is needed to the database tier, no changes are required in
the controller object.

Spring Context
--------------

The Spring Context is what brings everything together. It looks at the class files of your source
code, i.e. the Spring Beans, then looks at the configuration of the context and wires up the
environment. Spring will ensure your classes are injected with the specified dependencies.

SpEL - Spring Expression Language
---------------------------------

Also with in the Spring Core is SpEL, or Spring Expression Language. This is a concise language
used to give you a great deal of flexibility when configuring the Spring Framework.
