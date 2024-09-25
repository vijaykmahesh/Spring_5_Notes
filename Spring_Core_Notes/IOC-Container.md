# Spring Overview:

Spring framework creates and manages object inside IOC container.
	Spring has IOC container which reads the config file i,e beans.xml and creates object.
	Spring Bean is nothing but the object which is created inside IOC container.


	## We can use IOC container in 2 ways

	1. 	BeanFactoy (I)
	2.	ApplicationContext (I)


	But ApplicationContext has more methods then BeanFactoy so it is best to use. ApplicationContext is called as FactoryDesignPattern.

	ClassPathXmlApplicationContext implements ApplicationContext.

    Dependency Injection is defined as injecting dependencies required for class.

## 2 Types we can inject values:

1. Constructor Injection
2. Setter Injection

# Constructor Injection

we must define constructor inside specific class

```java

<bean id = "vijay" class = "com.express.di.Student">
	<constructor-arg name="studentName" value="Vijay K"> </constructor-arg>
	<constructor-arg name="studentId" value="1"></constructor-arg>
</bean>
```

# Setter Injection

```java
<bean id = "vijay" class = "com.express.di.Student">
	<property name="studentName" value="Vijay K" />
	<property name="studentId" value="1" />
</bean>
```

## Dependency Injection for object type:

```java
<bean id = "studentObject" class = "com.express.di.Student">
	<property name="id" value="1"></property>
	<property name="mathCheat" >
	<bean class="com.express.di.MathCheat"></bean>
	</property>
</bean>

```


	If we have same dependency object for 2 or more classes above approach not holds good. For example:
	Student and AnotherStudent class has dependency on MathCheat Object


```java
<bean id = "mathCheat" class="com.express.di.MathCheat"><bean>
	<bean id = "studentObject" class = "com.express.di.Student">
	<property name="id" value="1"></property>
	<property name="mathCheat" ref="mathCheat" >
	</property>
</bean>
	 

<bean id = "anotherStudentObject" class = "com.express.di.AnotherStudent">
	<property name="matCheat" ref="mathCheat">
	</property>
</bean>
```




