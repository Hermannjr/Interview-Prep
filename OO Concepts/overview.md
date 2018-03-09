# List OOP Concepts in Java

The four main OOP concepts are:

* **Abstraction:** The process of only showing those things which are *relevant* and *hiding* the other, unnecessary details of an object from the user. Consider your cell phone, where the user only needs to know which buttons are to be pressed to send a message or make a call. They don't need to know when a button is pressed, how messages are sent, how calls are connected, etc... This information is all *abstracted* away from the user. 

* **Encapsulation:** The process of combining data and functions into a single unit (e.g. java *class*). Through the use of encapsulation, the data is not accessed directly, but rather through the functions present inside the class. This is the basic concept of beans, where fields are kept private and only made accessible through public getter and setter methods. This makes the concept of *data hiding* possible.

* **Inheritance:** Lets a programmer share code through different classes. This way we can build on previous work, without having to reinvent the wheel.
The Advantage of using abstraction is that the user doesn't have to care about implementation details in the background. If the implementing class changes, but the user programs against an interface, then they generally shouldn't have to care about the changes made.

* **Polymorphism:** The concept of letting us use the same word to mean different things in different contexts. The two ways to accomplish this are **method overloading** and **method overriding**.

## Best practices for OOP concepts in Java

* **DRY (Don't Repeat Yourself):** Avoid copy / paste code. Use methods, inheritance, polymorphism to create code which doesn't repeat itself. This avoids errors which could happen when fixing an issue in one place and forgetting to fix it in others.

* **Be restrictive:** Start all fields and methods as private, only opening up scope as it becomes necessary.

* **Single Responsibility:** A class should always have only a single functionality / responsibility. This avoids further coupling of functionality where it shouldn't take place.

* **Open Closed Design:** Make all methods and classes Closed for modification, but Open for extension. That way, tried and tested code can remian static but can be modified to perform new tasks as needed.
