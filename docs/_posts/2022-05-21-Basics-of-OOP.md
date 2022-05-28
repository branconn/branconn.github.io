---
title: "Basics of Object-Oriented Programming"
tag: coding basics
toc: true
---
Object-Oriented Programming, or OOP, is a paradigm for structuring a complex computer program in a way that is scalable and maintainable. OOP expands the concept of modularizing code found in functional programming, the grouping and organizing of commands into callable methods (or functions), to include the modularizing of parameters as well.

There are four concepts that together define what an object-orient approach aims to achieve: abstraction, encapsulation, polymorphism, and inheritance.
### Abstraction
With a sufficiently complex system, it becomes inefficient or even impossible for a user or contributor to need to know the workings of the entire system in full detail. An engineer designing the transmission of a car does not need to understand the rubber compounds and tread pattern of the tires and how they affect grip in various conditions. In fact, as business, you wouldn't want your powertrain engineers to spend a significant amount of time to develop that knowledge base, because ultimately they don't need to know that information to do their job.
``` java
class PowerTrain {...}
class Tire {...}
class BrakingSystem {...}
etc.
```
This isn't to say that the capabilities of the tires have nothing to do with the design of a transmission though. What if the engineer mentioned above needs to know what torques the tires can handle in everyday conditions without slipping? She should be able to access that information without needing to understand how it was calculated. In OOP, this idea of putting a veil over irrelevant inner workings is called ___abstraction___.
``` java
import Tire
Tire.torqueLimit
```
### Encapsulation
You have an application appropriately abstracted into classes. This abstraction lets the parameters and methods particular to a class be separate from others. However, it's important to also protect these parameters and methods from being accessed or changed in ways that could compromise the application. The idea around setting access to variables and methods deliberately is called ___encapsulation___. The basic principle is that from the perspective of classes all variables should be on a need-to-know basis. Using the previous example, not only should the powertrain engineer not need to know the inner workings of tire design (abstraction), but she also shouldn't be able to change some of the properties of the tire herself (encapsulation).

#### Using _private_ and _public_ to enforce encapsulation
A common way of defining access is by the use of ___private___ and ___public___ attributes when declaring a parameter or method. Declaring a public param/method/class means that they can be called from other classes.
``` java
public class PowerTrain {...}
public class Tire {
    \\parameters
    private double treadGap;
    public double torqueLimit;
    ...
    \\methods
    private calculateStoppingDistance() {...}
    public main() {...}
    ...
}
```
Within the Powertrain class you can call the Tire class. Furthermore, you can access torqueLimit within Tire but not treadGap. Access is granted conservatively - making a class public only makes its public constituents accessible.

Consider a class that accesses another class as a ___client___. Methods that are public in a class are collectively called its ___interface___. A client can interact with a class through its ___interface___. Methods that a client would never need to use, but provide functionality to the class should be private and are usually referred to as ___helper methods___.

There's a problem with the example above however. Since torqueLimit is public, not only can it be accessed outside of the Tire class, but it cam be changed as well. There are two solutions to this. If the torqueLimit is a constant, then we can define it as a fixed value by using _final_: `public final double torqueLimit`. If torqueLimit is a variable that changes but we still need to protect it, then we can use _getter_ and _setter_ functions.
#### Using _accessors_ and _mutators_ to control read and write access
Accessors and mutators, also known as ___getters___ and ___setters___ respectively, are public methods that define how certain private parameters can be read or even overwritten. Let's fix the torqueLimit issue by making it private and writing an accessor method.
```java
public class Tire {
    \\parameters
    private double torqueLimit;
    ...
    \\methods
    public double getTorqueLimit() {
        return torqueLimit;
    }
    ...
}
```
Now, within the Powertrain class you can retrieve the torqueLimit variable by simply calling
```java
import Tire
Tire.getTorqueLimit()
```
### Polymorphism

### Inheritance