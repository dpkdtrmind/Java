## JAVA SE { }


### Types of Data:
> Primitives have only data whereas objects have data and behaviors
### Primitive (8 types)
* byte: Integers (default value is 0)
* short: Integers (default value is 0)
* int: Integers (default value is 0)
* long: Integers (default value is 0)
* float: Decimal of 32bit (default value is 0.0)
* double: Decimal of 64 bit (default value is 0.0)
* boolean: True/False (default value is False)
* char: 1 character in ‘colons’ (default value as NULL character; \u0000)
# Objects
* String (Strings are Objects as they are immutable; can’t be changed once assigned): “Text"; Strings are always in “Quotations” 
* Point

# Variable Assignment: 
int X;   <- int is the reference type of X
X = Y;  <- # reference type for a variable will be once. By seeing no reference type we can get a hint that its already referenced some where else before.
* Here Value Y is assigned/referenced in to Variable X
* X <- Y; before assigning value Y into X, we should define what kind of X is that
Objects
* String (Strings are Objects as they are immutable; can’t be changed once assigned): “Text"; Strings are always in “Quotations” 
* Point

Variable Assignment: 
int X;   <- int is the reference type of X
X = Y;  <- reference type for a variable will be once. By seeing no reference type we can get a hint that its already referenced some where else before.
* Here Value Y is assigned/referenced in to Variable X
* X <- Y; before assigning value Y into X, we should define what kind of X is that

Object: 
* Anything which has data and behaviors
* Objects are also called Instances

Class: 
* Class is a data type, tells about the blueprint of objects/ type of object behaviors
* Class is always at the highest level
* Public Class is stored in a file with the name <classname>.java
* If there are multiple classes in a java file; only one class should be Public (as the file name should be one class)
public class <classname> { 
public static void main(String[] args) { 
int A; -> Variable
String B;
public void set(); -> Method
System.out.println(“Hello World”);
}
}
class <helperclass> {
}
public static void main(String[] args) { } -> String with S Capital and [ ]-> Array
* The String type is capitalized because it is an Object, not a primitive type like boolean or int 
* "Return Type" is just to the left of the method like void or return
* Parameters are the ones in the Method brackets
* String[] -> List of Strings; args -> variable name in which Strings are stored

static
* static is a method/Variable modifier that makes method/Variable to be "assigned to class itself" rather to an object 
* calling a static variable is by using (<classname>.<static_variable/method> = X)
* static variables are also called as class variables
* static method can be accessed using class as well as object associated with that class
* static methods don’t have access to instance methods/variables
* { …} -> initialization block; static{ … } -> static initialization block
* initialization block executes every time a new object is created in the class but static initialization block is executed only once with the class
* static initialization block/method can only access static variables/methods (because we cannot make a static reference/assignment to any non-static field or vice versa, as static refers to class and non-static refers to an Object)
* static blocks/methods/variables are executed right away when the class is loaded/executed

Modifiers 
* Public is meant to be accessed from ‘anywhere’ 
* Private is meant to be accessed from within the Class
* (Its good to have private variables and public methods)
* Protected: 

Get Vs Set
Getter Gets the Private variables to Public, when printed
Seter Sets the Private Variable to another variable, when equated

Methods: 
* Something which a class can do; (Similar to Functions( ) of C)
* main Method (with small m) is the most important and a necessary method in all java programs
* we can say, behavior of an object is a Method
* Calling a method is by using dot notation: Obj_Var.method(type a, type b)
* Overloading Methods: Adding new Method Parameters; Method (New Values) 
* accessing static members with a null Class reference will not throw a NullPointerException (<class> C = Null; int D = <class>.method( ) will run)

public class <classname {   
String X; <- (String X = Null)
void <method> ( ) {
String Y; <- (No default value is assigned for Method Variables/ Local Variables)
…..
}
}

Five Rules of java
Rule1. Modifiers of main method should be public static 
(anyone should access to main, so public and main is assigned directly to class)
Rule2. Modifiers should be to the left of return type
Rule3. Return type of main method must be void
(because we don’t need return for main; as we don’t refer that method to anywhere)
Rule4. String[], String [] and String args[] are legal.
Rule5. args is a variable name; can be anything

Constructor: 
* Special Method called automatically when a new Object is created/instantiated 
* Object Creation->    <classname> Obj_Var = new  <classname>(x, y);    <-Object
* The new keyword here generates new objects in the constructor class, dot keyword is for regular methods
* Constructor don’t have a return statement or void, as its purpose is just to initialize an object
* We can instantiate the same Object many times with different parameters
* Constructor is executed only after running all the Object variables and Initialization blocks
* Object variables and Initialization blocks are executed from top to bottom
* If Multiple Constructors are defined with different parameters and a particular parameter constructor is called, it checks with the number of parameters given and call the respective Constructor with same number of parameters

public class <classname> { <- Constructor Class
String A;       <- Instance Variable/ Object Variable
String B;
{
String C;        <- Initialization block
}
<classname>( String x, String y) {    <- Constructor
A = x;
B = y;
}
<classname>( )     <- Constructor Overloading
...
}
Initialization blocks always executed before each constructor is executed 
(as it is a part of every constructor in common)

DRY -> Don’t repeat yourself; If String A is common in <classname>( String x, String y) and <classname>( ); write only once in common.

Stack & Heap: Memory management in java
* Instance/Reference Variables are stored in Stack (Small memory) 
* variables in Stack are defined within Scope {curly braces} -> Code block
* Objects and Classes are stored in Heap (Large memory)
* Stack Variables points towards -> Heap Objects (in the Memory) but in the code, Objects are referenced to the Variable
* (We require Pen and Paper to write down for stack and heap problems)
* Most of the things in java starts with zero index
* Object’s variable assignment: Obj_Var.X = Y (here Y value is assigned to X Variable within the Heap, as the assigning taking place within Object. 
* Only Object Variables and Static Variables have default values as Null
* Method Variables and Constructor Variables don’t have default values; they should be initialized before using them
* Local Variables are generally Method/Constructor “Parameters" which are stored in Stack as the method/Constructor is called by an object. 
* Method/Constructor Parameters stores in the stack as frames until it is executed
* Local variables can be declared in any loop statements or can be return type also

Garbage Collector: A special run time memory management by JVM
* Unassigned/Unreferenced Objects are destroyed here
* Runs periodically on its own
* Benefit of reducing memory leaks and space wastage
* Local variables are sent into Garbage collector once the Method/Constructor execution is complete
* System.gc( ) is the suggestion we give for garbage collector to execute and it runs only if JVM thinks there is sufficient wastage of space happening
* Objects which are no longer referenced after execution are also removed fro the heap, as the frame with Local variables is temporary and Object is no longer linked
* When a Local variable in frame is linked with another object or null, the first object is automatically sent to garbage collector

this Object
# If Instance/Object Variables and Method/Constructor Parameters are same, we refer (this dot/this object) to all Object variables inside Method/Constructor and referenced to this object by making to this.Object_Variables (this differentiate Object Variables and Method/Constructor Parameters)
“this” is a part of inheritance which means the object class itself
(There are three types of Variables: Class or static, Instance or Object and Local Variables)

this Constructor: It is used for Nested or Chain Constructors
* Constructor inside Constructor is allowed only by using this, but it should be called/invoke on the first lines of code within the Constructor (before the local variables)
* this cannot be used inside methods

Execution of Variables:
1. Firstly when Object calls a Method, it gives values to its Parameters
2. Local variables in Method are adjusted as per the Parameter assignment; if there is discrepancy, local variables check for the object class weather it has the variables to get the values from. (Variables see the Most Local way of resolving the issues: Method -> Object)

OOP Concepts - Object Oriented Programming 
(Assembling Code into Modules so that it mimics some useful real world behavior)
Benefits of OOP:
1. Code is Assembled
2. Extendable, by adding features to our Objects from existing Class/Objects
3. Code reusability using Libraries and Packages

1.Abstraction: Simplify the code by Hiding the relevant data/functionality of the Objects and Methods. This is to reduce the code complexity

2.Encapsulation: Brings together all Variables and Methods into single unit of a Class is called Encapsulation

3.Inheritance: Used for Code Reusability. If we already defined Objects and Attributes. We can make use of again and expand upon them using Inheritance.
this.


4.Polymorphism: 
* Polymorphism means having Many Forms. 
* Two types of Polymorphism: Static and Dynamic binding.
* Static Binding: Checking is done at Compilation time (E.g., Function Overloading)
* Dynamic Binding: Checking is done at Run time
* (“AB” + “BC” = “ABBC”) => + is a Concatenation operator for Strings as well as for Integers

Packages: Package is like a Folder
* Packages are used to organizes the Classes
* To avoid Naming Conflicts
* Multiple classes can exist in one package, but name of the class should be Unique
* dot is the folder to folder transition reference in package
package <package_name>;   <- Reads/creates a new package
public class <classname>{ …}    <- Reads/creates class from the above package

#Generally reverse of the Domain name is the starting point for creating Packages like com.<company_name>.<package_name> format



API
https://docs.oracle.com/javase/8/docs/api/
java.util.*
java.lang.(math, …..)


Interfaces


Enumerations







Frequent Methods:
substring(start,stop): returns the sub-string from start index till stop index -1 
trim( ): removes initial and trial spaces from string
toUpperCase( ): returns the string in uppercase
charAt( index): gives a character of string which is positioned at index

Exception Handling



