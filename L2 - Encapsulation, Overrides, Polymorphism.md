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
    return self.__firstName #only the method inside the class has access to the hidden attribute

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

## Polymorphism
