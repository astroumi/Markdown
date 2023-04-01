# Inheritance

### What is Inheritance?
**When an object or class is based on another class; where its features are from a parent class**
Types:
- Single Inheritance: A subclass inheriting the features of a single superclass / parent class
- Multiple Inheritance: A subclass inheriting the features of a multiple parent classes
- Multilevel Inheritance: A subclass inheriting the features of a multiple parent classes
- Inheritance can have an hierarchy (branching like a tree) and/or be a hybrid: mixing the types of inheritances

### What can you do with Inheritance?
- A child will receive all attributes and methods of the parent
- A child can then enhance itself with new attributes and new methods
- A child can **OVERRIDE** attributes and methods for its own liking/speciality

**If a child class inherits the parent class:**
- The child does not need a new __init__() method UNLESS it **requires new attributes**
- The child does not need to reinstate the parent’s methods UNLESS you override them

```python
class Person: #parent class
  def __init__(self, name):
  	self.__name = name 
  
  def getName(self):
    return self.__name

class Student(Person): #inherited class
  def __init__(self, name, num):
    Person.__init__(self, name)
    self.__sNum = num
  
  def getStudentName(self):
    return('%s: %s' % (self.__sNum,self.getName()))

#testing
p = Person('Umair')
s = Student('Rando', '1234')
print(p.getName()) # Output: 'Umair'
print(s.getStudentName(), “and” , s.getName()) # Output: “1234: Random Child and Random Child”
```

