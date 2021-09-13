### Access Control 
 - Access control allows you to hide field and methods from the classes
 - Determine how internal data gets changed
 - keep the implementation separate from the public interface.
    - public interface:
   
      setprice(Customer cust)
    - Implementation:
 
      public void setPrice(Customer cust){
        // set the price discount relative to customer
   
        }

Example:
Access from another class

    public class Item{
        private double price = 15.50;
        public void setPrice(Customer cust) {
            if(cust.hasLoyaltyDiscount()) {
                price = price*0.85;
            }
        }
    public class order {
        public static void main(String args[]) {
            Customer cust = new Customer();
            Item item = new Item();
            item.price = 10.00 // this wont compile; private field
            item.setPrice(cust) // can change private field like this.


 - public class  are accessible by anyone
 - private class are accessible only within class

### Encapsulation

- Encapsulation means hiding object fields. It used access control to hide fields.
    - Safe access is provided by `getter` and `setter` methods.
    - In setter methods, use code to ensure that value are valid.
- Encapsulation mandates programming to the interface:
    - A method can change the data type to match the field.
    - A class can be changed as along as interface remains same.
- Encapsulation encourages good Object Oriented (OO) design.

#### Get and Set Methods

    public class Shirts{
        private char colorCode = 'U';

        public char getColorCode() {
            return colorCode;
        }
        public void setColorCode(char newCode) {
            this.colorCode =newCode;
        }
    }

#### Introduction to Overloaded Classes

 - Assuming we have setters of all the private fields of Shirts, you could instantiate and initialize a Shirt object by instantiating it and then setting the various fields through the setter methods.
 - However, java provides a much more convenient way to instantiate and initialize object - by using special method called object.

Example:

    public class Shirt {
        public int shirtID = 0;
        public String description = "--description";
        private char colorCode = 'U';
        public double price = 0.0;
        
        //default Constructor - this constructor is not in the source code.
        //It only exists if no constructor is explicitly defined.
        //public shirt()

        // Constructor with args
        public shirt(char colorCode, String desc, double price) {
            setColorCode(colorCode);
            setDescription(desc);
            setPrice(price);
        }
    }
    
- When you create a constructor with args, the default constructor is no longer created by the compiler.
- this is the reason if we try to use below code it will error


    public static void main(String args[]) {
        Shirt shirt = new Shirt(); //gives error coz default constructor no longer exist, replace by constructor with args
        //Shirt shirt = new Shirt(char colorCode, String desc, double price)
        //correct implementation instead of above line and above implemetation of calling each setter method.


#### OverLoading Constructor

    public class Shirt {
        public Shirt() {
            setColorCode('U');
        }
        public Shirt(char colorCode) {
            setColorCode(colorCode);
        }
        public Shirt(char colorCode, double price){
            this(colorCode); // this will call second constructor
            setPrice(price);
        }
    }
