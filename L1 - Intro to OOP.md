# Introduction to Object Oriented Programming

### Classes and Objects
A class is a blueprint for creating objects. In OOP, an object is an instance of a class. The object can be stored in a variable, or other data types.
- The object's data are called **attributes** (variables that belong to the object or class)
- The object's code are called **methods** (functions that the object can call)

```python
class Person: #Class names are capitalized
    def greet(self): #this is a method
        print('Wassup')
    #end of greet
#end of class Person
p = Person() #creating an object, an instance of the class person and storing it in the variable p
p.greet() #calls the greet method of class Person
```

### Object Oriented Programming
- A programming practice to design modular reusable software systems (programs are designed with the creation of objects)
- Focuses on the definition of data rather than input, processing, output logic of procedure oriented programming

### Init method and self parameter
```python
def __init__(self):
```
- The initialization method is executed as soon as an object of the class is instantiated (it lets us initialize object's attributes)
- The `self` parameter is used to denote that the method is applied and accessible for the object itself
- `self` will also treat its own attributes as local
- The double underscore before and after init are key hidden features of Python that allow us to override some Python features and hidden content

```python
class Person:
	def __init__(self, name): #initialization of attributes with class argument of name
		self.name = name #creating the attribute self.name, which is accessible throughout the class or object
	
def greet(self): # the self parameter is always required
		print('Hello, my name is', self.name)
	#end of greet
#end of class Person

p = Person(‘Umair’)
p.greet()
```
