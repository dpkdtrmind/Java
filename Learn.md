JAVA Terminology
Variable Assignment: 
int X;   <- int is the reference type of X
X = Y;  <- reference type for a variable will be once. By seeing no reference type we can get a hint that its already referenced some where else before.
* Here Value Y is assigned/referenced in to Variable X
* X <- Y; before assigning value Y into X, we should define what kind of X is that
* In Java, checking for Equal to is: ==

Object: 
* Anything which has data and behaviors
* Objects are also called Instances
* E.g., String (Strings are Objects as they are immutable; can’t be changed once assigned): “Text"; Strings are always in “Quotations” 

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
* Generally null dot something will not execute (as null is not an object)

public class <classname {   
String X; <- (String X = Null)
<public/private> <void/primitive> <method> ( ) {  
String Y; <- (No default value is assigned for Method Variables/ Local Variables)
…..
}
}
* If there is a void before method, there is no need for return and if there is a return in method, there is no need of void type; there should be at least one
* Primitive is used for return type when there is no void for the method
* <public/private> <void/primitive> <method> ( ) { …} where public/private, void and primitive are optional types


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

Packages: Package is like a Folder
* Packages are used to organizes the Classes
* To avoid Naming Conflicts
* Multiple classes can exist in one package, but name of the class should be Unique
* dot is the folder to folder transition reference in package
* import statements reduces the pain to type the class location every time
package <package_name>;   <- Reads/creates a new package
public class <classname>{ …}    <- Reads/creates class from the above package

Generally reverse of the Domain name is the starting point for creating Packages like com.<company_name>.<package_name> format

import com.<company>.<package_name>.*; 
* (*) Star =>All classes in the package are imported import statements in java doesn’t make our bite-code larger, like C++ but compilation time maybe longer because of extra import 
* Java assumes <classname> is more accurate than general star (*)
* If import is not given, by default you are referenced to the package you are currently in; so no need to import if our class is in the package 
* We can use Classpath instead of import by telling the location of classes through command line: javac -classpath c:/temp/classes; . <class>.java
* If our package directory is wrong, we can still add a correct classpath and change it

JAR: 
* Java Archive (bundle of Classes and other related files in a single file); Similar to Zip file
* JAR is for security, as we can give passwords to it
* JAR makes file compressed and makes easier to download
jar cf jar-file input-file(s) -> creates JAR files (jar cf jar-file: jar create file jar-file)
classpath = c:/java/lib/* -> imports all JARs in library
classpath = c:/java/lib -> imports all Classes in library 
classpath = c:/java/lib/*; c:/java/lib -> Both JARs and Classes are imported

Case Conventions(Optional):
Package names: lowercase
Class names: UpperCamelCase
Methods&Var names: lowerCamelCase

Name/Identifier Convention Rules:
* Only Letters, Numbers, _ and $ in a name
* Don’t start Name with a Number
* Name cannot be same as a Java Keywords
* All Keywords: 
abstract
continue
for
new
switch
assert***
default
goto*
package
synchronized
boolean
do
if
private
this
break
double
implements
protected
throw
byte
else
import
public
throws
case
enum****
instanceof
return
transient
catch
extends
int
short
try
char
final
interface
static
void
class
finally
long
strictfp**
volatile
const*
float
native
super
while

Comment: // -> Line Comment; /* multi-line Comment */ (No Nested Comments)
Java doc Comment: //** Documentation Comment */

JAVA Data Types
Types of Data:
> Primitives have only data whereas objects have data and behaviors
Primitive (8 types)
* byte: 
    1. Integers of 8bit (default value is 0; when value is not yet assigned)
    2. Range(byte): -2^7 to 2^7 - 1 (-1 because 0 is counted as positive)
* short: 
    1. Integers of 16bits (default value is 0)
    2. Range(short): -2^15 to 2^15 - 1 (-1 because 0 is counted as positive)
* int: 
    1. Integers of 32bits (default value is 0)
    2. Range(int): -2^31 to 2^31 - 1 (-1 because 0 is counted as positive)
    3. Any integer is an int by default
    4. Binary int: putting a ‘0b’ in front of number (Binary 0b101 = 5) [b or B]
    5. Octal Int: putting a ‘0' in front of number makes it octal (Octal 070 = 56)
    6. Hex Int: putting ‘0x’ in front of Hexadecimal (Hex 0x7E = 126) 
* long: 
    1. Integers of 64bits (default value is 0)
    2. Range(long): -2^63 to 2^63 - 1 (-1 because 0 is counted as positive)
    3. Representation: 2L or 2l -> L is for long (Capital L is preferred, after the integer)
* float: 
    1. Decimal of 32bits (default value is 0.0)
    2. Representation: 2.2F or 2f -> F is for Float
* double: 
    1. Decimal of 64 bits (default value is 0.0)
    2. Any decimal is a double by default (d or D for representation is optional)
* boolean: 
    1. True/False of 1 bit (default value is False); if(b) => if( b == True)
* char: 
    1. character in ‘colons’ (default value as NULL character; \u0000)
    2. ‘/n’-> New Line char; ‘/t’ -> New Tab char; ‘//‘ -> backslash char; 
    3. Hex notation can be used, to represent chars ‘\uHHHH’; 4 H-> Hexadecimal
    4. We can use number as a character
Underscore for differentating Thousands: 1_234_567.123_456_789

Primitive Conversion: 
* Widening and Casting are the only way of primitive conversion when they are equated (E.g, byte b = 4; so int x = b does the widening of b to x)
* Widening works every time but lack in accuracy (e.g, converting large int to float)
* Shortening works by Casting every time (int x = 5; byte b = (byte) x;) <- Casting
* Overflow or Underflow happens when Shortening happens with Casting larger numbers 
(int x = 200; byte b = (byte) x) => result: byte b = -56 (case of Overflow)
What it does when Shortened large number, it flips the maximum possible shortened bits and adds the difference (between larger number and maximum possible shortened bits)

Operators
postfix 
expr++ expr--
unary 
++expr --expr +expr -expr ~ !
multiplicative 
* / % (P E M D A S)
additive 
+ -
shift 
<< (left shift signed) >> (right shift signed) >>> (right shift unsigned)
relational 
< > <= >= instanceof
equality 
== !=
bitwise AND 
& 
bitwise exclusive OR 
^
bitwise inclusive OR 
|
logical AND 
&&
logical OR 
||
ternary 
? :
assignment 
= += -= *= /= %= &= ^= |= <<= >>= >>>=

Post and Pre Increment/decrement (exp++/-- and ++/—exp):
* X++ -> Increment by one & then Returns Old Value
* ++X -> Increment by one & then Returns New Value
* X ; Returns New Value

Unsigned Shift and Signed Shift: 
* Signed Shift replaces New Vacant Values with 0 for Positive and 1 for Negative whereas Unsigned Shift replaces New Vacant Values with 0 for both Positive and Negative (because Unsigned removes Sign if negative)
* Vacant Values get occurred on the left side when the shift happens
* 32bit positive int has all zeros as binary before number whereas 32bit negative int has all ones as binary before number
int x = 4 =>(28zeros 0100); x >> 1 => (28zeros 0010); x >>> 1 => (28zeros 0010)
int y = -4 => (28ones 1100); y >> 1 => (28ones 1110) [-2]; y >>> 1 => (zero 27ones 1110) 
[2147483646]

Bitwise Operations (&, |, ^, ~): using AND - &, OR - |, XOR - ^, Complement - ~
int 8 & int 10 = 8 (because 28zeros 1000 & 28zeros 1010 = 28zeros 1000)
int 8 | int 10 = 10 (because 28zeros 1000 or 28zeros 1010 = 28zeros 1010)
int 8 ^ int 10 = 2 (because 28zeros 1000 xor 28zeros 0010 = 28zeros 0010)[0xor1=1;else 0]
int ~8 = 28ones 0111 (Complement Flips all the bits from 0 to 1 and from 1 to 0)

Short Circuiting (&&, ||):
Left && Right: 
* && and || operator checks the Left to it and neglects right if it can answer with left
* And And / Or Or operator doesn’t care about right syntax, if Left is good; it short circuit the Right side’s compilation

Ternary Operator (= ? : )
* [  = -> If(  ] ;  [  ? -> ) ];   [  : -> else  ]
* String = “”; if (X) {Condition1} else {Condition2} => String = X ? C1 else C2

JAVA Loops
If Else Loop: if (<boolean>) {…} else if {…} else{…} 
* If no condition is kept in if, then it takes by boolean as true by default
* else if and else are optional for if loop
* Curly braces for if statement are optional, only one statement is attached if and else if and else if no curly braces. All other statements don’t attach to them and run

Switch Statement: switch(<Variable>) { case 1: … break; case 2: … break; default: … }
* Here <Variable> with a value matches with the case value
* Once the matching occurs then the following case break occurs
* Multiple cases can run, if we forget to apply a break for each case
* <Variable> can be int, short, byte and char
* case <known>: -> case is to be known value (number or String) at the compile time; cannot be a Variable or method
* Rule: Variables cannot be declared between switch and case statements



























API
https://docs.oracle.com/javase/8/docs/api/
java.lang.*; -> Default package, no need to import (Eg, System, String)
java.lang.math (BigInteger, BigDecimal): Using these we can exceed the Primitive number limitations
java.util.*

java.io


Interfaces


Enumerations










Frequent Methods:
substring(start,stop): returns the sub-string from start index till stop index -1 
trim( ): removes initial and trial spaces from string
toUpperCase( ): returns the string in uppercase
charAt( index): gives a character of string which is positioned at index

Exception Handling



