	
# SpringCore Annotations:

### For example in .properties file we have

	student.name = vijay
	student.hobby = cricket

If we want we can provide default values for properties then use below code:
	 
	Example:
	@value("testing")
	private String name;


# @PropertySource:

It is basically used for reading properties file and specify on top of class.

```java
@PropertySource("classpath:test.properties")
```

# @value:

@value("${student.name}") 
private String name;

# @required:
	
It is basically used for restricting user for not providing values for object.

	Example:
	@required
	private String name;


# @Component:

It is used for creating object in IOC container


# Below Line Of Code

Creates object of exam and stores in IOC container and Object referenceName will be exam.

```java
<bean id="exam" class="com.express.java"></bean>
```

# Below Line Of Code
Also does same job as above code

```java
@Component("exam") Public class Exam{
	}

```

![Hello World](SpringCoreWithXMLApproach-2.PNG)

## In XML file write below code:

```java
	<?xml version="1.0" encoding="UTF-8"?>

	<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xmlns:context="http://www.springframework.org/schema/context" xsi:schemaLocation="http://www.springframework.org/schema/beans
	https://www.springframework.org/schema/beans/spring-beans.xsd http://www.springframework.org/schema/context
	https://www.springframework.org/schema/context/spring-context.xsd">

	<context:component-scan base-package="com.express.college"></context:component-scan>
	
	</beans>

	<context:component-scan base-package="com.express.college">
	</context:component-scan>
	```
	