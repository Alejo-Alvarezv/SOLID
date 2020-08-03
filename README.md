
![Logo](https://github.com/Alejo-Alvarezv/SOLID/blob/master/images/image1.jpg)

**SOLID** is an acronym that represents five principles very important when we develop with the **OOP** paradigm, in addition it is an essential knowledge that every developer must know.
Understanding and applying these principles will allow you to write better quality code and the therefore be a better develop

The SOLID principles were defined in the early 2000s by Robert C Martin (Uncle Bob). Uncle Bob elaborated some of these and identified others already existing and said that these principles should be used to get a good management of dependencies in our code

However, in the begining these principle were not yet known as SOLID until Michael Feathers observed that the initials of these principles fit perfectly under the acronym SOLID and that it was also a very representative name for iths definition

These principles help us to obtain the following benefits:
	• Ease to maintain
	• Ease to extend
	• Robust code

But before we see what each SOLID principle means, we need to remember two relevant concepts in the development of any software, The **COUPLING** and the **COHESION**

##### COUPLING:
We can define it as the degree to wich a class, method or any other software entity, is directly linked to another. This degree of coupling can also be seen as a degree of dependence.

##### COHESION
Is the measuare in which two or more partes of a sustem work together to obtain better results than each part individually

* **S** - Single Responsability Principle
* **O** - Open Closed Principle
* **L** - Lisko Substitucion Principle
** *I** - Interface Segregation Principle
* **D** - Dependency Inversion Principle

## Single Responsability Principle (SRP)
A class should have a single function.

A class should be responsible for only one thing. The moment it acquires more responsibility it becomes docked, something that is not desirable if you want to ensure the maintenance of the application. This is because changing one of your responsibilities may affect the other and vice versa.

```ssh

class Vehicle {

    String brand;

    Vehicle(String brand){
        this.brand = brand;
    }

     String getVehicleIdentifier() { 
        return brand;
     }

     void saveVehicle(Vehicle vehicle) {
        //Implementation for save into database...
      }     
}
```

This class violates SRP. Why? The single responsibility principle states that each class should have a single function. However, the class **Vehicle** handles both properties ( getVehicleIdentifier) and database storage ( saveVehicle). This means that if, for example, a change occurs in the storage system of our application, it is likely to affect the way in which the properties are managed, forcing us to change the class Vehicleas well as the classes that are using it.

In other words, the SRP establishes a high degree of stiffness , so that there is no domino effect every time a change occurs.

One way to solve the previous example would be the following:

```ssh

class Vehicle {
    String brand;

    Vehicle(String brand){
        this.brand = brand;
    }
    String getVehicleIdentifier() { 
        return brand
    }
}

class VehicleDB {
    saveVehicle(Vehicle vehicle) { 
        //Implementation for save into database
    } 
    getVehicle(int idVehicle) {
        return idVehicle;
     }
}
```

## Open-Closed Principle

Classes should be open to extension but closed to modification.

The software Establishes that the entities (classes, modules and functions) are open for extension, but closed for modification.

Let's continue with our class **Vehicle**:

IMAGE

If we wanted to iterate through a list of cars and print their marks on the screen:

IMAGE




