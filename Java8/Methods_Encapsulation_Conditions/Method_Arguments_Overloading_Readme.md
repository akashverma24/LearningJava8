### Passing an Object Reference
An Object reference is similar to a house address. When it is passed to a method:
 - The Object itself is not passed
 - The method can access the object using the reference.
 - The method can act upon the object.
 
        House myHouse = new House();
        PainterMan.pain(myHouse);

Example

            public class ShoppingCart {
                public static void main(String args[]) {
                    Shirt myShirt = new Shirt();
                    System.out.println("Shirt color: "+ myShirt.colorCode);
                    changeShirtColor(myShirt, 'B');
                    System.out.println("Shirt color: "+ myShirt.colorCode);
                }
                public static void changeShirtColor(Shirt theShirt, char color) {
                    theShirt.colorCode = color;
                }
            }

Output: 

    Shirt color: U
    Shirt color: B

Now, if a new object is created in method changeShirtColor
    
    public class ShoppingCart {
        public static void main(String args[]) {
            Shirt myShirt = new Shirt();
            System.out.println("Shirt color: "+ myShirt.colorCode);
            changeShirtColor(myShirt, 'B');
            System.out.println("Shirt color: "+ myShirt.colorCode);
        }
    public static void changeShirtColor(Shirt theShirt, char color) {
        theShirt = new Shirt();
        theShirt.colorCode = color;
    }
Output:

        Shirt color: U
        Shirt color: U
The reference value passed into the method `changeShirtColor` is assigned to a new Shirt.
Note that the reference now points to a new reference Object Shirt() than myShirt reference does.



### Method Overloading

 - Overloaded Methods have same name
 - Have different signatures
    - The number of parameters
    - the types of parameters
    - the order of parameters
 - may have different functionality or same functionality.
 - Are widely used in the foundation class.

Example:

    public class Calc {
        public static int sum(int a, int b) {
            System.out.println("Method 1");
            return a+b;
        }
        public static float sum(float a, float b) {
            System.out.println("Method 2");
            return a+b;
        }
        public static float sum(int a, float b) {
            System.out.println("Method 3");
            return a+b;
        }