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
print(s.getStudentName(), “and” , s.getName()) # Output: “1234: Rando and Rando
```

### What is super()?
**super() is a built-in method for classes to refer their parent class**
- This prevents us from doing ParentClass.method(self)
- The self with self gets confusing…
- In the code you would just do `super().__init__()` instead of `ClassName.__init__(self)`

### Multiple Inheritance
**1. Multi-Generational**

Grandparent → Parent → Child

**2. Multi-Parent (Not limited to two)**

Two parents with children. Each child inherits from multiple parents.

**3. Mixture of 1 and 2**

## Polymorphism
- Polymorphism applies to inheritance because different inherited classes can have the same named methods as their parent classes.
- This would be an example of overriding, the child's method would override the parent's method with the same name