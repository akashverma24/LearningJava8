### Constructor

A constructor method is a special method that is invoked when you create an object instance.
- Its purpose is to instantiate an object of the class and store the reference in a reference variable.
- Test testA = new Test();

       <modifier> Classname();

### Static Variable and Methods

- Belongs to the class and shared by all objects of the class.
- Since objects have unique properties and behaviours, static is not unique as it is shared inside every object and class.

        e.g. Test testA = new Test();  
Test testB = new Test(); testA and testB will have unique properties and behaviour testA.count = 50; testB.count = 20; static int run; testA.run is equal to testB.run
- Can be accessed without instantiating the class.
- An instance variable is unique to an individual object.

- To access static variable or method:
   - from another class
     `Test.count` ,  `Test.runTest()`
     - from same class
     ` count` , `runTest()`
 - Static methods and variables include the keyword static before their name in the header or declaration. They can be public or private.

 - Static variables belong to the class, with all objects of a class sharing a single static variable.

 - Static methods are associated with the class, not objects of the class.

 - Static variables are used with the class name and the dot operator, since they are associated with a class, not objects of a class.

 - Static methods cannot access or change the values of instance variables, but they can access or change the values of static variables.

 - Static methods cannot call non-static methods.