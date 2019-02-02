#(Almost) everything is an object 

An object is an instance of its class. 

Classes act as templates that pre-define the state and behaviour of any instance of that particular class of objects. The particular information stored in an objects states may differ but the behaviour/ functionality of objects belonging to the same class will remain constant.

Every time a new object is instantiated from a class, this new object get inherits all of the methods that belong to that class. 

Methods add behaviour that is useful to have for a particular type of object.

Some methods require arguements - additional information so that it can perform a task e.g text.split(" ")

Almost everything in Ruby is an object (Integers, floats, strings, nil etc.)

You can check if something is an object by calling object.class which returns the name of the class that the oject belongs to.

When you object.inspect, this displays a human readable interpretation of the object - in string format. This is different to converting a string. e.g

nil.inspect
> "nil"

nil.to_s
> ""

Every instance of an object has a unique ID.

Small integers have fixed IDs, these follow a pattern. You miltiply the integer by 2, then add 1.

Calling obj.clone creates a copy of an object - this will have a unique ID and will not be equal to the original object