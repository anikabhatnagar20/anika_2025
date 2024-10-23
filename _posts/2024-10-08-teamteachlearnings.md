---
layout: post
title: Learnings from team teach 
description: These are my learnings and team teaches 
type: issues
comments: True
---

Link each team teach with a button: 

## Unit 1: Primitive Types
Variables: I practiced declaring and using variables like int for numbers, double for decimals, and boolean for true/false values. I also worked on how to initialize and assign values properly.
Errors: The homework taught me to catch common mistakes like using the wrong data type in calculations, which caused errors in my code.
Takeaway: Always double-check data types and remember how to convert between them (e.g., int to double). Fixing these helped me avoid runtime errors.

## Unit 2: Using Objects
- Objects represent real-world entities in programming.
- Methods define object behavior.
- Encapsulation hides data within objects.
- Constructors initialize new object instances.
- Accessors and mutators (getters/setters) manage object data.
Objects: I practiced creating objects and calling methods on them, especially working with strings. Using methods like substring() and charAt() helped me manipulate strings efficiently.
Takeaway: Strings are immutable, so when I used substring or concat, it was important to remember that they return new strings rather than modifying the original. This helped me understand memory management better.

## Unit 3: Boolean Expressions and if Statements
- Boolean expressions evaluate to either true or false.
- Logical operators include AND (&&), OR (||), and NOT (!).
- Used for decision-making (if-else statements).
- Relational operators compare values (==, !=, >, <, >=, <=).
- Critical for loops and flow control in programs.
If-else Logic: I got a lot of practice writing conditional logic using if, else if, and else statements. The exercises helped me understand how to use boolean operators like && (and) and || (or).
Takeaway: Simplifying conditions with boolean operators made my code more readable and efficient. Using De Morgan's Law helped me reduce complex conditions.

## Unit 4: Iteration (Loops)
- Loops allow repeated execution of a block of code.
- Types of loops: for, while, and do-while.
- Loops can iterate over arrays or lists of items.
- Break and continue can control loop execution.
- Used to simplify repetitive tasks in code.
Loops: I worked on both for and while loops to repeat tasks, especially focusing on making sure loops don’t run forever. Debugging infinite loops was a major learning point.
Takeaway: It’s crucial to ensure that loops have a proper exit condition, or they could go on forever. I practiced breaking down problems into smaller steps using loops.

## Unit 5: Writing Classes
- Classes define blueprints for objects.
- Each class contains fields (attributes) and methods.
- Constructors create instances of classes (objects).
- Static methods/fields belong to the class, not instances.
- Inheritance allows creating new classes from existing ones.
Class Design: I learned how to structure a class with fields, constructors, and methods. Using private fields and public methods to control access helped me understand encapsulation better.
Takeaway: Proper use of encapsulation made my classes more secure and easier to maintain. I now use getter and setter methods regularly to control data access.

## Unit 6: Arrays
- Arrays store multiple elements of the same type.
- Elements are accessed using zero-based index numbers.
- Fixed size; cannot change once declared.
- Useful for managing lists or collections of data.
- Common operations: iteration, sorting, and searching.
Array Basics: I practiced creating arrays, accessing elements by index, and performing operations like summing values. I also had to be careful with array bounds to avoid errors.
Takeaway: Arrays start at index 0, and it’s easy to make off-by-one errors, so I practiced double-checking my loop conditions to prevent going out of bounds.

## Unit 7: ArrayList
- ArrayLists are dynamic arrays in Java.
- Unlike arrays, ArrayLists can change size dynamically.
- ArrayLists store objects, not primitive types.
- Useful methods: add(), remove(), get(), size(). 
- ArrayLists offer more flexibility than basic arrays.
Dynamic Lists: I worked with ArrayList and learned how to dynamically add, remove, and access elements. It’s much more flexible than arrays, especially when the size of the list changes frequently.
Takeaway: ArrayList methods like add() and remove() made my code more dynamic and flexible. I prefer ArrayList when I don’t know the exact size of the list beforehand.

## Unit 8: 2D Arrays
- 2D arrays are arrays of arrays (matrix structure).
- Rows and columns are used to access elements.
- Useful for representing grids, tables, and matrices.
- Common operations: iterating over rows and columns.
- Indexed by two values: row index and column index.
2D Arrays: Using nested loops to access elements in a 2D array was key in this unit. I practiced matrix operations like summing rows and columns.
Takeaway: Nested loops are essential for working with 2D arrays. I practiced breaking down complex problems into smaller tasks to handle both rows and columns efficiently.

### Extra Notes 

Unit 1 
* 2 data type: primitive and reference
    * primitive: specifies the size and type of info 
        * simplest typeof variable in Java 
        * store small amounts of data 
        * 3 primitive types: int ( whole number), double (decimal), boolean ( true or false) 
    * reference: stores references to objects rather then the objects directly 
        * Reference types: 
            * classes: data structure that groups variables and methods 
            * Array: collection of same type of variables 
                * int []= array of integers 
                    * without square brackets is for a single integer 
* type: a set of values. 
    * determines how data is stored in memory 
    * determines how a set of operations will work with them
    * ￼
* Variable terms 
    * variable name: often referred as variable identifier
        * follows camel case
    * class name(data type): follows pascals case (PacsalsCase)
* Stack memory: stores temporary variables creates by each function 
* Heap memory: used for storing objects/array
Unit 6 
* Definations 
    * Array : holds groups of object references 
    * element: a single item in a array 
    * element index: the number/location that an element is at in an array. 
    * array length: amount of elements in an array
* Declaring array: need name of array and datatype
    * int[] grades; // Declare an integer array
    * String[] class_list; // Declare a string array
    * boolean[] light_switch; // Declare boolean array
* Creating an Array: needs method, name, and size 
    * String[]class_list = new String[3]; // Create a string array with 3 elements
    * int[]grades = new int[5]; // Create an integer array with 5 elements
    * int[]grades={100,90,100,10,20};
    * boolean[]light_switch={true,false,true,false,true};
* Transversing Arrays: using for/while loops to access each element of an array 
* ￼
incrementing loop control variable: statement that changes the original value after each iteration 

￼
    * Creating the array:
        * int[] list = new int[6]; creates an array called list with 6 slots (index 0 to 5).
    * Generating random numbers:
        * The first for loop fills the array with random numbers using rand.nextInt(4);. 
        * This generates a random number between 0 and 3 
        * since nextInt(4) produces numbers from 0 up to 3.
    * Printing the array:
        * The second for loop prints each element in the array. 
        * That's why you see the values 0, 0, 1, 2, 2, 2
            * those are the random numbers that were generated.
* For each loop: way to go through each item in an array or collection without using an index
    * for(dataType element : array) { }
* Finding max/min in array 
    1.  Initialize a variable to store a maximum value
    2. Iterate through every element in list 
    3. check if the element is greater than the max, if so replace
    4. return element 
Unit 2
￼
* classes= blueprints 
    * class book: book is the class 
* object: different books that use the blueprint 
    * Book book1
    * Book book2 
        * book1 and book2 are objects. 
* method signatures 
* ￼
* Method parameters rules 
    * must be passed in order
    * separated by comma 
    * include datatype and a name
    * be referenced by their names inside the method. 
        * Bad: 
            * public static void funny_method(int funny_number, String funny_string) {
            *     System.out.println(funny_number);
            *     System.out.println(funny_string);
            * }
            * funny_method("cat", 1);
        * Good: 
            * public static void funny_method(int funny_number, String funny_string) {
            *     System.out.println(funny_number);
            *     System.out.println(funny_string);
            * }
            * funny_method(1, "cat");
* Nonvoid: method that has a defined return type. 
* Stopped at string objects
Unit 5 
public class Person {
	String name;
	int age;
	void greet() {
		System.out.println("Hello, my name is " + name);
	   }
	}
* class=person 
* name/age=attributes
* greet()=method

public class Person {
    String name;
    int age;

    // Constructor
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    void greet() {
        System.out.println("Hello, my name is " + name);
    }
}
* person = class and constructer
    * constructer initializes name/age 
* Same name as class
    * The constructor must have the same name as the class.
* No return type
    *  Constructors do not return any value.
* Used to initialize objects
    * They set initial values for object attributes.
Unit 9 
* inheritance allows 1 class to inherit methods from another class. 
    * super class: general class that contains common methods that can be shared by its subclasses 
    * subclass: a class that extends the functionality of a superclass. inherits all of the attributes/methods from the superclass. 
* Key words: 
    * extends: defines subclass
    * super: defines superclass 
        * must be the first statement in the subclass constructor 
    * @overide: subclass can override superclass

