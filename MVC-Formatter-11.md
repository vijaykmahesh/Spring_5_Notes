
# Formatter

- Formatter Basically is used for types like PhoneNumber, CreditCard etc...

- Formatter interface extends Printer,Parser

- Parser is a interface which has method parse() which  converts string type to object type.

- Printer interface has only 1 method called print()
	
## If we want to use a formatter follow below steps i,e For Phone Object
	
### Below Example
Define a class that implements Formatter
	
```java
	class PhoneNumberFormatter implements Formatter<Phone> 
	{
	
	@Override
	public String print(Phone object, Locale locale) 
	{
		// Convert Object to String and show it to end-user in field.
		return null;
	}

	@Override
	public Phone parse(String text, Locale locale) throws ParseException 
	{
		
		System.out.println("Parse is executing");
		//convert String to Phone Object
		
		return null;
	}
	
	}
```
	
- Inorder to execute this class we have to tel spring i,e 	
- Inside SpringConfig class i,e SpringConfig should Implement WebMvcConfigurer 
- so that now spring will know we have written our own formatter 
- we have to overide a mathod call addFormatters()
	
```java
	@Override
	public void addFormatters(FormatterRegistry registry) 
	{
		
		registry.addFormatter(new PhoneNumberFormatter());
	}
```
	
- Whenever DispatcherServlet is intialized it is reading  SpringConfig and it is executing addFormatter() where PhoneNumberFormatter is getting registered with DispatcherServlet.
	
- Once we click on register button directly it is going into Formatter Class and executing parse() instead of controller class and before DataBinding happens.
	
- Once is succesfully executed then it goes to the controller and execute particular method.
	
- Locale is used for internalization and helps us to do translation.
	
- Whenever we load Registration Page (in our case) It directly comes to Formatter Class and executes print() to convert object to string.
	
# Note 
		
- Whenever their is a need then only formatter comes into picture or else it won't execute
	
- For Example: If we don't spsecify phone and click on register button formatter class will not be executed.
