## Classes and Objects


Objects have properties and behaviours
- Properties: Size,Shape,Color
- Behaviour: Play, Stop, Pause, Rewind

We use classes to create objects
- class is a blueprint of object
- describes an object's properties and behaviours
- Is used to create object instances

The Class represents the noun - a person, place or thing
The Fields represents the adjectives - describes the noun
The Methods represent the verbs - action verbs

### Declaring and Instantiating Objects


    public static void main(String args[]) {
    // Create new instances
	    Test testA = new Test();
	    Test testB = new Test();
	// Fields are assessed
		testA.count = 5000;
		testB.smoke = "Smoke Test";
	// methods are accessed
		testA.requestRun();
		testB.requestTrigger();
    }

(.) Dot Operator is used to access the fields and methods

### How to access methods of an object within another object

	testA.runs.report();
	- testA is object reference of Test
	- runs is a object of Test with its own set of properties and behaviour
	- report() is a behaviour of class runs.

### Object Instance and Instantiation Syntax:

`<class name> variable = new <class name>();`
- it looks like that you are calling a method, but in fact you are calling a method (constructor method of the class `variable`)
- variable becomes/stores the reference to that object/ object reference
- `new` keyword creates (instantiates) a new instance


### Two references, one object

    Test testA = new Test();
    Test testB = new Test();
    testA = testB
    //now both the object reference access the same reference
    
    Test testA = new Test();
    Test testB = testA;
    //now both the object reference access the same reference
    testA.count = 15;
    testB.count = 20;
    System.out.println("test counts"+ testA.count)
    Ouput: 20 (since both the object refere same instance)

### Arrays are Objects
Array variable is a object reference, not a primitive data type, so we declare it as an object with new keyword.

	int a[] =  new a[2];
	int a[] = {20, 21};
	
	//complile time error
	int [] a;
	a = {1,2};

Storing Arrays of Object References in Memory

    Test testA = new Test();
    Test[] tests = { new Test(), new Test(), new Test() }
    testA.count = 50;
    tests[0].count = 50;

### Strings
A String is object, immutable object, its value cannot be changed

	String name = "Akash";
	String name = new String("Akash");
	//Second method is not memory efficient, since it creates two string objects,to avoid the unecessary duplication of string objects in memory






### StringBuilder and String Buffer

	// class Geeksforgeeks {
	// Concatenates to String
	public static void concat1(String s1)
	{
		s1 = s1 + "forgeeks";
	}

	// Concatenates to StringBuilder
	public static void concat2(StringBuilder s2)
	{
		s2.append("forgeeks");
	}

	// Concatenates to StringBuffer
	public static void concat3(StringBuffer s3)
	{
		s3.append("forgeeks");
	}

	public static void main(String[] args)
	{
		String s1 = "Geeks";

		// s1 is not changed
		concat1(s1);
		System.out.println("String: " + s1);

		StringBuilder s2 = new StringBuilder("Geeks");

		// s2 is changed
		concat2(s2);
		System.out.println("StringBuilder: " + s2);

		StringBuffer s3 = new StringBuffer("Geeks");

		// s3 is changed
		concat3(s3);
		System.out.println("StringBuffer: " + s3);
	}
	}
	**Output**

	String: Geeks
	StringBuilder: Geeksforgeeks
	StringBuffer: Geeksforgeeks

**Explanation:**

1.  **Concat1**: In this method, we pass a string “Geeks” and perform “s1 = s1 + ”forgeeks”. The string passed from main() is not changed, this is due to the fact that String is  **immutable**. Altering the value of string creates another object and s1 in concat1() stores reference of the new string. References s1 in main() and cocat1() refer to different strings.
2.  **Concat2**: In this method, we pass a string “Geeks” and perform “s2.append(“forgeeks”)” which changes the actual value of the string (in main) to “Geeksforgeeks”. This is due to the simple fact that StringBuilder is  **mutable**  and hence changes its value.
3.  **Concat3**: StringBuffer is similar to StringBuilder except for one difference that StringBuffer is thread-safe, i.e., multiple threads can use it without any issue. The thread-safety brings a penalty of performance.  
    **When to use which one :**

-   If a string is going to remain constant throughout the program, then use the String class object because a String object is immutable.
-   If a string can change (for example: lots of logic and operations in the construction of the string) and will only be accessed from a single thread, using a StringBuilder is good enough.
-   If a string can change and will be accessed from multiple threads, use a StringBuffer because StringBuffer is synchronous, so you have thread-safety.
-   If you don’t want thread-safety than you can also go with StringBuilder class as it is not synchronized.

