# CS 1181 possible final

## 14 points - Early Material
	- Which of the following should be an error and not an exception? - 2
     - the program is out of memory
     - a method attempted to access an index outside of an array
     - a method was called on a variable that held `null`
     - a zip file had an incorrect password
	- Write a class header for a custom exception type `TruckException` - 2
     - ___________________
	- What is the problem with the following code? - 2
 ```java
 // returns an ArrayList containing only the first element
 public static ArrayList<T> firstElementOnly(ArrayList<T> elements) {
    ArrayList<T> firstOnly = elements;
    T firstElement = firstOnly.getFirst();
    firstOnly.clear();
    firstOnly.add(firstElement);
    return firstOnly;
 }
 ```
         - The method header cannot use a generic return type
         - The elements ArrayList will also be cleared
         - a wildcard should be used for the parameter
         - The firstElement will always be `null`
	Which term refers to the idea that objects can be referred to by their supertypes? - 4
         - abstraction
         - encapsulation
         - concurrency
         - polymorphism
	What are the differences between interfaces and abstract classes? Select 2. - 4
         - interfaces support multiple inheritance
         - abstract classes can be generic
         - interfaces define the natural ordering of a class
         - abstract classes can contain concrete methods
12 - GUI
	True/False - Components can be placed in a JFrame directly. - 4
         - True
         - False
	What layout arranges components in a grid of flexible size? - 4
         - FlowLayout
         - BorderLayout
         - GridLayout
         - GridBagLayout
	Which is not a way to implement an actionlistener? - 4
         - lambda expression
         - anonymous inner class
         - abstract class
         - inner class
17 - Generics
	Where can a generic data type not be used? - 2
         - In front of new
         - In the class header
         - In wildcards
         - As a bound for a bounded type
	What is the problem with the following code? - 2
 ```java
 public static void method() {
     Map<String, int> grades = getGrades();
     String studentName, studentFirstName;
     studentName = studentFirstName = "Clarence";
     String letterGrade = grades.get(studentFirstName);
     System.out.println("Clarence's grade: " + letterGrade);
 }
 ```
         - `letterGrade` cannot be added to "Clarence's grade" because it is a string
         - grades.get() returns an int, but letterGrade is a string
         - no implementation was specified for grades
         - student name cannot be assigned to "studentFirstName = "Clarence"" because that is code
	Write a generic class header for a team of players based on the following code (the class should be able to be a team for any type of player): - 4
 ```java
 public class Player {
     ...
 }
 public class FootballPlayer extends Player {
     ...
 }
 public class BaseballPlayer extends Player {
     ...
 }
 ```
         - _______________________________
	Which of the following is the best method header for a method that sorts a numeric list based on whether elements are greater than or less than zero? - 5
         - public void sortPositive(List<? super Integer> numbers)
         - public void sortPositive(List numbers)
         - public void sortPositive(? extends Number list)
         - public void sortPositive(List<? extends Number> list)
	Why would you use a wildcard? - 2
         - So that methods can be overridden
         - To implement an interface
         - To create an instance of an abstract class
         - To specify a bounded type for the generic data type of a parameter
	True/False: Containing an ArrayList instead of extending it is called composition. - 4
25 - ADTs
	True/False: Map takes two type parameters. - 2
	What is a set? - 2
         - an indexed, unordered collection that does allow duplicates
         - an unindexed, unordered collection that does not allow duplicates
         - an indexed, ordered collection that does not allow duplicates
         - an unindexed, unordered collection that does allow duplicates
	What does an ADT specify? - 2
         - how data can be interacted with
         - the internal structure
         - the type of data
         - the performance of different operations
	For each scenario, write whether a Stack or Queue would be used. - 10
         - to reverse a string
         - to store the method calls of a program
         - to undo/redo edits in a text editor
         - to connect customers to a support agent at a busy hour
         - to store timed events in a simulation
         - to move forward and backward in a web browser
         - to store a list of songs to play on the radio
         - to serve print jobs on a printer
         - to move up and down in a directory tree
         - to store a deck of cards
	What interface is used to define an additional ordering for a class? - 4
         - Collections
         - Comparator
         - Comparable
         - Collection
	What method must be overwritten in a class that implements Iterable<String>?
         - public String next()
         - public String hasNext()
         - public Collection<String> iterate()
         - public Iterator<String> iterator()
17 - recursion
	Why must recursive methods contain a base case? - 4
         - The base case makes the recursive call.
         - The method will not compile without a base case.
         - The base case returns the final value.
         - The base case ends the recursion.
	What does a StackOverflowError usually indicate? -3
         - pop() was called on an empty stack
         - a recursive method looped infinitely
         - a generic type was generic to itself
         - too many interfaces were implemented
	What is the output of the following method? - 10
```java
public String mysteryMethod(String str) {
    if(str.length == 0) {
        return str;
    }
    else {
        char first = str.charAt(0);
        first += 3;
        return first + mysteryMethod(str.substring(1));
    }
}
public static void main(String[]) {
    System.out.println(mysteryMethod("zlab"));
}
```
    - _____
16 - threading
	True/False: A race condition can occur when two threads simultaneously modify the same value. - 4
	What are two ways to define your own thread? - 4
         - extend Exception
         - extend Thread
         - Create a new Runnable with a lambda expression
         - `public thread NewThread`
	What is a possible result of the following code? - 4
```java
public static void main(String[] args) {
    Thread t1 = new Thread(() -> {
        for(int i = 1; i <= 4; i++) {
            System.out.println(i);
        }
    }
    Thread t2 = new Thread(() -> {
        for(int j = 1; j <= 3; j++) {
            System.out.println(j);
        }
    }
    t1.start();
    t2.start();
}
```
    - _____________________
	What would the output be if both calls to `start()` were changed to `run()`? - 4
    - _____________________
6 - sorts
	How does quick sort sort a list? - 2
         - Finds the minimum value and swaps it to the start of the unsorted area
         - Divides the search area in half, then in a quarter, then in an eighth
         - Splits the data into two lists based on whether items are greater than or less than a partition
         - Swaps adjacent values
	Which of the following algorithms has the best time complexity? - 2 
         - Selection Sort
         - Bubble Sort
         - Merge Sort
         - Insertion Sort
    What is the time complexity of linear search? - 2
         - O(n)
         - O(n2)
         - O(1)
         - O(n log n)

min 70/107

max - 37 missed
