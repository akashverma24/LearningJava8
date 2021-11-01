### Inheritance

 - parent class is the super class
 - child class is the subclass
 - subclass may have unique fields and methods not found in the super class


    public class Shirts extends Clothing {
        public int neckSize;
        public int getNeckSize() {
            return neckSize;
        }
        public void setNeckSize(int nSize) {
            this.neckSize = nSize;
        }
- Inheritance can help reduce code duplication, e.g we have two class `Shirts` and `Trousers` both have getID, getPrice, getSize methods, then it can be declared in a super class called `Clothing`, and Shirts can have only unique methods like getNeckSize.
- Also, if we want to scale our function, we can add class `Socks` without adding duplicate code.
- 
