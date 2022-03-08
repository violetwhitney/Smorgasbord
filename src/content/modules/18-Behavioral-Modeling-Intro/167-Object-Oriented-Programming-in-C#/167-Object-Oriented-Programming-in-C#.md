---
moduleid: 167
title: Object Oriented Programming in C#
published: True
slug: object-oriented-programming-in-c#
---

Behavioral Modeling Intro:
===========================================

# Object Oriented Programming in C#
## Module Summary

In this tutorial you will get:
- a conceptual introduction to object oriented programming 
- Learn about prefabs in Unity
- Get acquainted with C# and how to connect code to behavior in Unity
- Learn how object oriented programming is leveraged in C# and Unity



## Object Oriented Programming
Thus far we’ve learned about functions, loops, and conditionals. Our programs execute as a set of sequential processes.
In Object Oriented Programming, programs are more than a list of procedures, but use collections of interacting “objects.” Objects are like templated typologies with embedded rules.
In a 3d modeling program like Revit, an object might be something like a window. The window object holds data and window-specific functions. Such awindow’s data (or sometimes called “state”) will describe the parameters of the window:
![oop](images/oop-1.jpeg#img-full)
- dimensions (e.g. 3’-0” x 1’-6” x 0’-6”)
- frame material (e.g. metal)
- pane (e.g. frosted glass)


Functions associated with a window might control the height or the dimensions, while another controls the material and how the window renders. You can have functions that compute the area or cost of a window, or control whether it’s “open” or “closed.”
So how does one object differ from another? Let’s look at some other example objects. You could have a class in Revit for a tree with functions to control the amount of foliage or the species.

![oop](images/oop-2.png#img-full)

Tree:
- foliage (heavy)
- species (evergreen)
Or how about the sun in a sunlight study in Revit? A sunlight study’s data might be:
- season (winter)
- time (8:00 am)
- intensity (10)
A function of the sun might control how the sun renders or calculate how bright it is inside a modeled building.

### What is a Class?
An object’s “class” describes the functions and parameters it can take. When an object is created from the class, it’s called an “instance” of the class.
Think of a cookie cutter. A cookie cutter makes cookies, but it is not a cookie itself. The cookie cutter is the class, the cookies are the “instances.”
For example, a Revit model may have 50 windows. How does our model keep track of all of those different windows? Some are small and short; some are large and tall; some are frosted; some are not. Each window may have different values for its parameters, but we can use lists and dictionaries to treat them like a collection.
Using classes, we can also describe all the different objects that go into buildings, such as doors, floors, furniture, etc.


In summary, classes provide a means of bundling data and functionality together. Creating a new class creates a new type of object (cookie cutter), allowing new instances of that type to be made (cookies). Each instance has independent parameters attached to it for maintaining its state. Instances can also have methods (defined by its class) for modifying, computing values from, or drawing geometry based on its state.

### Defining a Class
Classes in Python are written with the word class and then a CamelCase name starting with a capital letter, and then (object).

```class Window(object):```
Next within our class, we may want to define variables or create functions that control our class.

### Initializing a Class
To create a new instance of a class (initialize a class) we use a pre-made function __init__() which will utilize any variables passed into the class during initialization. By convention, these functions always start by referencing themselves using self.

```
class Window(object):
    
    def __init__(self):
```

They can also take multiple parameters such as:
```
class Window(object):
    
    def __init__(self, windowWidth, windowHeight, glazing):
```

These parameters (windowWidth, windowHeight, glazing) are all custom parameters that I created.
You’ll notice this variable self, think of self as the way in which a class references itself.
When we say self.parameter that lets us know that we are talking about a parameter for that particular instance. Within the initialization function we can define new variables using the self.parameter so that we can reference the parameter for a particular instance later on.

