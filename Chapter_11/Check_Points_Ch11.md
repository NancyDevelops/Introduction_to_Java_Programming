# Checkpoint Answers Chapter 11 #
## 11.1 ##
A subclass is usually not a subset of a superclass. Subclasses will usually add functionality and details that are not present in the superclass thus extending the superclass.  

## 11.2 ##
The keyword extends is used when defining a subclass.  

For example:  
```Java  
public class MountainBike extends Bicycle {
	
	// ...
	// ...
	// ...

}
```  

## 11.3 ##
Single inheritance means that a class may only inherit from one particular class.  

Multiple inheritance is a feature of some object-oriented computer programming languages in which an class can inherit characteristics and features from more than one  parent class.  

Multiple inheritance is not supported by the Java programming language.  

## 11.5 ##
The syntax for calling a superclass constructor that takes no parameters is:  
```Java  
super();  
```  
The syntax with parameters is:  
```Java  
super(parameter list);  
```  
This will cause a call to a constructor with matching parameter list in the superclass.

Invocation of a superclass constructor must be on the first line in the subclass constructor.  

It is possible to omit the explicit call of a superclass constructor. The compiler will in this case insert a call to the no-argument superclass constructor.  

## 11.6 ##
The no-arg constructor of a superclass will not be called if another constructor is called explicitly by the subclass.  

## 11.7 ##
It is not possible to override a method that is declared private in the superclass.  

## 11.8 ##
It is not possible to override a static method defined in a superclass.  

It is still possible to have another static method, with the same name, in a subclass but this method will not override the method in the superclass, it will hide it.  

This is a bit tricky read more [here](http://docs.oracle.com/javase/tutorial/java/IandI/override.html "here").  

## 11.9 ##
The keyword super is used to explicitly invoke the constructor of a superclass.  

## 11.10 ##
The keyword super in combination with the dot operator is used to invoke an overridden superclass method from a subclass.  
´´´Java  
super.method()  
´´´   

## 11.12 ##
Method overloading means making multiple versions of a method based on differences in the signature.  

Method overriding means defining a new version of a method in a subclass of a superclass. Overridden methods have the same signature and return type as the original.  

## 11.13 ##
A corrected version of the code for this checkpoint looks like this:  
```Java  
public class Circle {
	private double radius;

	public Circle(double radius) {
		this.radius = radius;
	}

	public double getRadius() {
		return radius;
	}

	public double getArea() {
		return radius * radius * Math.PI;
	}
}

class B extends Circle {
	private double length;

	B(double radius, double length) {
		super(radius);
		this.length = length;
	}

	@Override
	public double getArea() {
		return super.getArea() * length;
	}
}
```  

