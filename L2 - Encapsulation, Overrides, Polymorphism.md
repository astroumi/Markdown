# Encapsulation, Overrides, Polymorphism

## Encapsulation

### What is Encapsulation?
- Encapsulation restricts access to certain attributes and methods of the class/object
- It is useful for data protection and restricting certtain methods from being callable
- Technically, encapsulation is not possible in python so we use a special system
- Hidden attributes and methods are denoted by a double underscore `__` prefix

```python
class Student:
  def __init__(self,nameF, nameL, num):
    self.firstName = nameF #normal attribute
    self.lastName = nameL
    self.__studentNumber = num #hidden attribute
  
  def __getStudentNumber(self): #hidden method (can be called by object)
    return self.__studentNumber #only the method inside the class has access to the hidden attribute

  def actuallyGetStudentNumber(self): #hidden method (can be called by object)
    return self.__studentNumber #only the method inside the class has access to the hidden attribute

#end of Student
s1 = Student("Mr.", "Park", 10)
print(s1.__getStudentNumber()) # Will cause an error
print(s1.__studentNumber) #Wil also cause an error
print(s1.firstName) #Will run fine
print(s1.actuallyGetStudentNumber()) #Will also run just fine
```
### Imoprtance of Encapsulation and Common Practices
- Disallows people or other code from being able to see, edit, or call attrbutes or methods of a class/object
- When handling important information, this is critical
- A common practice is to have all attributes hidden and create **set and get functions**

```python
class Student:
  def __init__(self,nameF, nameL, num):
    self.__firstName = nameF
    self.__lastName = nameL
    self.__studentNumber = num
  
  def setFirstName(self, newName):
    self.__firstName = newName
    
  def getFirstName(self):
    return self.__firstName
```

## Overrides
### Overloading
**Two methods in one class that have the same method name, but different parameters**
```python
class Name:
  def name():
    pass #give random name
  def name(startswith):
    pass #give random name starting with that letter
```
_there is **no overloading** in Python 3_

### Overriding
**Two methods with the same method name and parameters**
- One method is in the **parent class**
- One method is in the **child class**
- Overriding allows the child class to provide specific implementation for a method that **exists in the parent class**
- You can also override built-in magic methods or base functions
  - Can complete mathematical operations on custom Objects
  - Can compare equality between custom Objects

```python
class Dog:
	def __init__(self, name): #overriding init function
		self.__name = name
	def __str__(self): #overriding str function
		return 'Woof, I’m %s.' % self.__name
  def __repr__(self): #use repr and str together
    return self.__str__()

corgi = Dog('Tobasco')
print(corgi) # 'Woof, I’m Tobasco.'
```

## Polymorphism
**A method that can be used across different classes and objects that is dependent on the parameters**
- Different classes (non inherited) can have the same named methods
- Within a set of inherited classes you can have the same methods
- Overloading is a type of Polymorphism but illegal in Python 3
- Overriding is also a type of Polyporphism

```python
class Bear:
    def sound(self):
        print("Groarrr")
 
class Dog:
    def sound(self):
        print("Woof woof!")
 
def makeSound(animalType):
    animalType.sound()
bearObj = Bear()
dogObj = Dog()
 
makeSound(bearObj)
makeSound(dogObj)
```
In summary, we can have:
- Two different classes have a same attributes and methods
- A child of a parent have an overrided method where the child would utilize the method differently.
