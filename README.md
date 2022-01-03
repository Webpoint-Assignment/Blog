# OOP and Its Usecase:
__Object Oriented Programming(OOP)__ is a programming language model in which object are use rather than method and data than logic.OOP is not programming language like C,C++,Java,Python it is method or rule to write the code. In OOP class,object,data etc are use. In oop we see the each problem like in real world probelms and try to solve it. OOP tries to map code instructions with real world making the code short and easier to understand. It is Solving Problem by creating the objects.

OOP conccept also uses the DRY concepts that is Donot Repeat Yourself. For example:In software there is different page like profile page,home Page,About page etc.Suppose we have to show same navigation bar to all page. In this case we donot write same code in different place.We write the re-use code in oneplace from from that we pull that code into different  place.From that work load in changing and deleting will  reduce as well as space.

OOP used to solve the real world problem using the concept of Class and object.

__Class__ :  Class is defined as the blue print of object.Class is the group of attribute and methods.Class is define by using keyword __class__ .Class define the nature of objects.Instance is the specific object which is created form class.Class are used to creat the object and support inheritance.

Class is a way of organizing information about type of data so programmer can reuse elements when making multiple instance of data type.Class is the blue print of object because without create an object we cannot all methods of class.For example:

Blueprint of house is class. In Blueprint we cannot access Door,window etc. To acces the door,window etc we have to make objects.Which is real house.

Class are derived from base class.Creating Class in JS.
```javascript
   class House{
     constructor(Window,Door){
       this.Window=window
       this.Door=Door
     }
   }

```



Inside Class Constructor is self-calling function which used to create the instances of class.When instance is created constructor is automatically called.Constructor is used to initiallize the instant variable.Instant Variable are those varibale which is decleared inside the constructor.For eg: In above code Door and Window are instance variable.





__Object__: Object are instance of the class.Object in OOP is self conatined component which consist of methods and properties to make a particular type of data useful. An object in OOPs can include a data structure,a variable,or a function. It has a memory location allocated.Object are often used to model real-world objects you find in everyday life.Creating object in JavaScript:

1. Object.create()

   Syntax:

   const Object_name=Object.create(Class_name);

   Example:

   ```javascript
    class User{
      constructor(firstname,lastname,address){
        this.firstname=firstname
        this.lastname=lastname
        this.address=address
      }
      fullname(){
        let fullname= '${this.firstname} ${this.lastname} is my fullname';

      }
    }
    const user= new User("Rupesh","Bhujel","Kathmandu")
    console.log(user.fullname())

   
   ```
   As already mentioned that class is blueprint. To access all method,variable object comes to use.


 
2. Custom and Null object:

A new object created from a completely custom object(especially one created from __null__ object,which is basically a custom object with NO members)can behave in unexpected ways.This is especially true when debbugging,since common object-property converting/detecting utility function may generate errors or lose information

For example:
```javascript
 const user1=Object.create({})
 const user2=Object.create(null)

```
__Object Oriented Programming(OOP)__ stands upon four pillar and they are given belows:

1. Abstraction:

Abstraction in OOP is a process of hiding the real implementation of the method by only showing a method signature. For example:

```python
from abc import abstractmethod, ABC

class Vehicle(ABC):
    def __init__(self, speed, year):
        self.speed = speed
        self.year = year

    def start(self):
        print("Starting engine")

    def stop(self):
        print("Stopping engine")

    @abstractmethod
    def drive(self):
        pass


class Car(Vehicle):
    def __init__(self, canClimbMountains, speed, year):
        Vehicle.__init__(self, speed, year)
        self.canClimbMountains = canClimbMountains

    def drive(self):
        print("Car is in drive mode")

```
Here in this exaple Vehicle is inherited from base class ABC.It has abstract method named as drive and car is inherited from vechile.so it has to implement the drive method which shows the abstraction property


2. Polymerphism

The word polymorphism means having many forms. In programming, polymorphism means the same function name (but different signatures) being used for different types.For Example:
```python
class Webpoint():
	def Location(self):
		print("Sanepa")

	def type(self):
		print("Software company")

	
class Sagarmatha():
	def Location(self):
		print("Sanepa")

	def type(self):
		print("BSC.CSIT College")

	
obj_webpoint = Webpoint()
obj_sagarmatha = Sagarmatha()
for aa in (obj_webpoint, obj_sagarmatha):
	 aa.type()
   aa.Location()

```
The above code shows  use two different class types, in the same way. creating a for loop that iterates through a tuple of objects. Then call the methods without being concerned about which class type each object is. Assuming that these methods actually exist in each class. 



3. Inheritance

The mechanism of deriving a new class from an old class such that new class inherit all the members of old class is called inheritance.

For example:

```python
 class Father():
   def __init__(self,property,cast):
     self.property=property
     self.cast=cast

   def show(self):
     print(self.property,self.cast)  

  class Son(Father):
    def  __init__(self ,education):
      self.education=education

  S=Son("BSC.CSIT)    

```
In above code child class Son inheritate all method  from father.But Father Cannot inherit Son class method and property.Types Of Inheritance are given below:

a. Single class Inheritance:

If child class is derived from one base class then it is called as single class Inheritance.
For example:

```python
class Car():
   def __init__(self,Wheel,Door):
     self.Wheel=Wheel
     self.Door=Door

   def show(self):
     print(self.Wheel,self.Door)  

  class BMW(Car):
    def  __init__(self ,Price):
      self.price=price

  B=BMW(20000000)    

```
Here BMW is inheriting property from one base class that is Car

b. Multilevel Inheritance:

 Multilevel inheritance is one type of inheritance being used to inherit both base class and derived class features to the newly derived class when we inherit a derived class from a base class and another derived class from the previous derived. For example:

 ```python
 class Grandfather:
 
    def __init__(self, grandfathername):
        self.grandfathername = grandfathername
 

class Father(Grandfather):
    def __init__(self, fathername, grandfathername):
        self.fathername = fathername
 
        
        Grandfather.__init__(self, grandfathername)
 

class Son(Father):
    def __init__(self,sonname, fathername, grandfathername):
        self.sonname = sonname
 
        
        Father.__init__(self, fathername, grandfathername)
 
    def print_name(self):
        print('Grandfather name :', self.grandfathername)
        print("Father name :", self.fathername)
        print("Son name :", self.sonname)
 

s1 = Son('AAA', 'BBB', 'CCC')
print(s1.grandfathername)
s1.print_name()
 
 ```





c.Hierarchical Inheritance:

 When more than one derived classes are created from a single base this type of inheritance is called hierarchical inheritance. In this program, we have a parent (base) class and two child (derived) classes.For example:

 ```python
 class Dad:
      def func1(self):
          print("This function is in parent class.")
 

class Son(Dad):
      def func2(self):
          print("This function is in Son.")
 
# Derivied class2
class Daughter(Dad):
      def func3(self):
          print("This function is in Daughter.")
  
# Driver's code
object1 = Son()
object2 = Daughter()
object1.func1()
object1.func2()
object2.func1()
object2.func3()

 ```


d.Multiple Inheritance:

 When a class can be derived from more than one base class this type of inheritance is called multiple inheritance. In multiple inheritance, all the features of the base classes are inherited into the derived class.For example:

 ```python
class Mother:
     
    def __init__(self,mothername):
        self.mothername=mothername
 
# Base class2
class Father:
    def __init__(self,fathername):
      self.fathername=fathername 
    
# Derived class
class Son(Mother, Father):
    def parents(self):
        print("Father :", self.fathername)
        print("Mother :", self.mothername)
 
# Driver's code
s1 = Son()
s1.fathername = "RAM"
s1.mothername = "SITA"
s1.parents()

   
 ``` 

4. Encapsulation:

Encapsulation is one of the fundamental concepts in object-oriented programming (OOP). It describes the idea of wrapping data and the methods that work on data within one unit. This puts restrictions on accessing variables and methods directly and can prevent the accidental modification of data. To prevent accidental change, an object’s variable can only be changed by an object’s method. Those types of variables are known as private variable. For example:

```python
class Base:
	def __init__(self):
		
		
		self._a = 2

class Derived(Base):
	def __init__(self):
		
		Base.__init__(self)
		print("Calling protected member of base class: ")
		print(self._a)

obj1 = Derived()
		
obj2 = Base()

print(obj2.a)

```



 











