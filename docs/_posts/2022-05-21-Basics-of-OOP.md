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
This isn't to say that the capabilities of the tires have nothing to do with the design of a transmission though. What if the engineer mentioned above needs to know what torques the tires can handle in everyday conditions without slipping? She should be able to access that information without needing to understand how it was calculated. In OOP, this idea of putting a veil over irrelevant inner workings is called abstraction.
``` java
import Tire
Tire.torqueLimit()
```
### Encapsulation

### Polymorphism

### Inheritance