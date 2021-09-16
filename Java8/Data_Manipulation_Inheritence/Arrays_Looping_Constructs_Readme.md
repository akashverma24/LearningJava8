### Using the args Array in the main Method

- Parameters can be typed on the command line

       > java ArgsTest Hello World!
       args[0]--> Hello
       args[1]--> World!
- Code for retrieving the parameters
  

    public class ArgsTest
        public static void main(String args[]) {
            System.out.println("args[0] is" + args[0]);
            System.out.println("args[1] is" + args[1]);
        }
    }


### Comparing Loop Constructs

 - Use `while` loop to iterate indefinitely through  statements and to perform the statements zero or more times.
 - Use the Standard `for` loop to step through statement a predefined numbers of times.
 - Use `enhanced for` loop to iterate through the element of Array or ArrayList.
 - Use `do/while` loop to iterate indefinitely through statement and to perform the statement one or more times.




