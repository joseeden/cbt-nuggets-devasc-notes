
# 2 - Design Patterns #
____________________________________________________________

<!--  2021-01-04 04:48:04 -->

## DESIGN PATTERNS ##
<br>
<p align=center>
    <img src="../Images/design-pattern.jpg">
</p>
<br>
A pattern or a series of plot points that you're program will go through. By doing so, you can be sure you can arrive at the expected outcome.

A design pattern is **NOT A CODE**.

It is a set of rules on how you can write code - this means it can be applied to any programming language.

There's 2 design patterns discussed here:

    1.  Singleton Design Pattern
    2.  Observer Design Pattern 

_________________________________________________________

## SINGLETON DESIGN PATTERN ##

A pattern that restricts classes to only being instantiated once during the entire execution of the program.
Useful for: 

- database connection strings
- configuration values
- constants/static variables

As an example, here we have created a class ConfigValues

```python
class ConfigValues:

    # When class variable is preceeded with '__', it is a private variable.
    # This means it can't be accessed from outside the class.
    __instance = None

    # The decorator '@static_method' means the getInstance() method can be executed
    # even before instantiated an object of this class.
    @static_method
    def getInstance():

        # if __instance is blank, create a new instance.
        # The __instance will be blank on the first run.
        # On the second run, the __instance variable will not be empty,
        # thus this If-statement will not be executed.
        if ConfigValues.__instance == None:
            ConfigValues()
        return  ConfigValues.__instance

    # Initialize the object.
    # Note that this constructor prevents you from instantiating a new value 
    # for the instantiated object
    def __init__(self):
        """Virtually private constructor"""

        if ConfigValues.__instance != None:
            raise Exception("This class is a singleton")
        else:
            ConfigValues.__instance = self


# Creating the object
s = ConfigValues()                         
print(s)

# This can run without creating the object first.
s = ConfigValues.getInstance()              
print(s)                                      

# Same here, this will create version 3 of s 
s = ConfigValues.getInstance()              
print(s)

# This will raise an exception "This class is a singleton" 
# This is because this will create a 2nd instance of the class.
s = ConfigValues()                          
print(s)                                      

# Test the code by running      
python 3-Singleton.py
```
______________________________________________________

## OBSERVER DESIGN PATTERN ##

Allows multiple different things ("observers") to receive updates when a single source ("subject") changes.

This is where dependent objects are updated or notifed by one or more subject objects. The dependent object/s is the objserver/s

Used with event-driven systems, this pattern is popular in UI systems.

There are two classes defined by observer pattern

**SUBJECT**
Maintains a list of observers and includes methods for attaching, detaching, and notifying observers.

**OBSERVERS**
Has a method to receive updates from the subject.

As an example,

```python
class Observer():
    
    # This is the function called whenever the subject updates.
    def update(self, subject):
        print("Observer: My subject just updated and told me about it.")
        print("Observer: It's states is now - " + str(subject.__state))

class Subject():
    
    _state = 0
    _observers = []         
    # this listwill contain all the observer objects
    
    # Add observer to the list
    def attach(self, observer):
        self._observers.append(observer)
    
    # Remove observer from the list.
    def detach(self, observer):
        self._observers.remove(observer)
    
    # goes thru the list and update
    def notify(self):
        
        print("Subject: I'm notifying my observers ...")
        
        for observer in self._observers:
            observer.update(self)
    
    # Updates state, which changes the _state to variable n.
    # This also calls the notify() function.
    def updateState(self, n):
        
        print("Subject: I have received a state update!")
        self._state = n
        
        self.notify()
        

# Creating the objects
s = Subject()

obj1 = Observer()
obj2 = Observer()
obj3 = Observer()

# Attach the observer objects to the single Subject object.
s.attach(obj1)
s.attach(obj2)
s.attach(obj3)

s.updateState(s)


