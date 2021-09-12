### Constructor

A constructor method is a special method that is invoked when you create an object instance.
- Its purpose is to instantiate an object of the class and store the reference in a reference variable.
- Test testA = new Test();

      <modifier> Classname();  

### Static Variable and Methods

- Belongs to the class and shared by all objects of the class.
- Since objects have unique properties and behaviours, static is not unique as it is shared inside every object and class.

e.g. Test testA = new Test(); Test testB = new Test(); testA and testB will have unique properties and behaviour testA.count = 50; testB.count = 20; static int run; testA.run is equal to testB.run
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

### this Keyword

- Within an instance method or a constructor, this is a reference to the current object — the object whose method or constructor is being called. You can refer to any member of the current object from within an instance method or a constructor by using this.
- From within a constructor, you can also use the `this` keyword to call another constructor in the same class. Doing so is called an explicit constructor invocation. Here's another Rectangle class, with a different implementation from the one in the Objects section.

Usage of this keyword 
- The most common use of the `this` keyword is to eliminate the confusion between class attributes and parameters with the same name (because a class attribute is shadowed by a method or constructor parameter).
- `this`  can also be used to
    - Invoke current class constructor
    -   Invoke current class method
    -   Return the current class object
    -   Pass an argument in the method call
    -   Pass an argument in the constructor call

Usage 1:`this` keyword can also be used to invoke current class instance variable

    public class Main { 
		int x; 
	// Constructor with a parameter
	public Main(int x) { 
	    this.x = x; 
	    } 
	// Call the constructor
	public static void main(String[] args)  { 
	    Main myObj = new Main(5);
	    System.out.println("Value of x = " + myObj.x);
	    } 
	  }

If you omit `this` keyword in the example above, the output would be "0" instead of "5".

Usage 2: `this` keyword can be used to invoke current class method (implicitly)

    public class Customer {
      void setValue() {

        System.out.println("hello");
      }
      void show(){
        setValue();
        //this.setValue(); complier will add this implicitly
      }

    public static void main(String args[]){

        Customer customer = new Customer();
        customer.show();
      }
    }
In above example output will be "hello", here `this` is implicitly called by the compiler to invoke current class method.

Usage 3: `this` keyword can be used to invoke current class constructor

    public class Customer {
      Customer() {
       // this("Akash"); call parameterized method
        System.out.println("no argument constructor");
      }
      Customer(String display){
        // this(); calls no parameter constructor
        System.out.println("parameterized constructor "+ display);
      }

      public static void main(String args[]){

        Customer customer = new Customer();
      }
    }

- if the user calls ``Customer customer = new Customer();`` no argument constructor will be called
- if the user calls ``Customer customer = new Customer("Akash");`` parameterised constructor will be called
- if user wants to invoke no argument constructor can use this() keyword
- if user wants to invoke parameterized constructor can use this(string) keyword
- refer comments in example