# CS 1181 possible final

## 14 points - Early Material
1. Which of the following should be an error and not an exception? - 2
<ul>
    <li> the program is out of memory
    <li> a method attempted to access an index outside of an array
    <li> a method was called on a variable that held `null`
    <li> a zip file had an incorrect password
</ul>
<br><br>
2. Write a class header for a custom exception type `TruckException` - 2
     <li> ___________________
<br><br>
3. What is the problem with the following code? - 2
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
Problems:
         <li> The method header cannot use a generic return type
         <li> The elements ArrayList will also be cleared
         <li> a wildcard should be used for the parameter
         <li> The firstElement will always be `null`
<br><br>
4. Which term refers to the idea that objects can be referred to by their supertypes? - 4
             <ul>
         <li> abstraction
         <li> encapsulation
         <li> concurrency
         <li> polymorphism
             </ul>
<br><br>
5. What are the differences between interfaces and abstract classes? Select 2. - 4
             <ul>
         <li> interfaces support multiple inheritance
         <li> abstract classes can be generic
         <li> interfaces define the natural ordering of a class
         <li> abstract classes can contain concrete methods
             </ul>
## 12 - GUI
6. True/False - Components can be placed in a JFrame directly. - 4
             <ul>
         <li> True
         <li> False
             </ul>
<br><br>
7. What layout arranges components in a grid of flexible size? - 4
             <ul>
         <li> FlowLayout
         <li> BorderLayout
         <li> GridLayout
         <li> GridBagLayout
             </ul>
<br><br>
8. Which is not a way to implement an actionlistener? - 4
             <ul>
         <li> lambda expression
         <li> anonymous inner class
         <li> abstract class
         <li> inner class
             </ul>
<br><br>
## 17 - Generics
9. Where can a generic data type not be used? - 2
             <ul>
         <li> In front of new
         <li> In the class header
         <li> In wildcards
         <li> As a bound for a bounded type
             </ul>
<br><br>
10. What is the problem with the following code? - 2
 ```java
 public static void method() {
     Map<String, int> grades = getGrades();
     String studentName, studentFirstName;
     studentName = studentFirstName = "Clarence";
     String letterGrade = grades.get(studentFirstName);
     System.out.println("Clarence's grade: " + letterGrade);
 }
 ```
Problems:
         <li> `letterGrade` cannot be added to "Clarence's grade" because it is a string
         <li> grades.get() returns an int, but letterGrade is a string
         <li> no implementation was specified for grades
         <li> student name cannot be assigned to "studentFirstName = "Clarence"" because that is code
<br><br>
11. Write a generic class header for a team of players based on the following code (the class should be able to be a team for any type of player): - 4
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
Answer:
         <li> _______________________________
<br><br>
12. Which of the following is the best method header for a method that sorts a numeric list based on whether elements are greater than or less than zero? - 5
             <ul>
         <li> public void sortPositive(List<? super Integer> numbers)
         <li> public void sortPositive(List numbers)
         <li> public void sortPositive(? extends Number list)
         <li> public void sortPositive(List<? extends Number> list)
             </ul>
<br><br>
13. Why would you use a wildcard? - 2
             <ul>
         <li> So that methods can be overridden
         <li> To implement an interface
         <li> To create an instance of an abstract class
         <li> To specify a bounded type for the generic data type of a parameter
             </ul>
<br><br>
14. True/False: Containing an ArrayList instead of extending it is called composition. - 4
<br><br>
## 25 - ADTs
15. True/False: Map takes two type parameters. - 2
<br><br>
16. What is the best description for a set? - 2
             <ul>
         <li> an indexed, unordered collection that does allow duplicates
         <li> an unindexed, unordered collection that does not allow duplicates
         <li> an indexed, ordered collection that does not allow duplicates
         <li> an unindexed, unordered collection that does allow duplicates
             </ul>
<br><br>
17. What does an ADT specify? - 2
             <ul>
         <li> how data can be interacted with
         <li> the internal structure
         <li> the type of data
         <li> the performance of different operations
             </ul>
<br><br>
18. For each scenario, write whether a Stack or Queue would be used. - 10
             <ul>
         <li> to reverse a string
         <li> to store the method calls of a program
         <li> to undo/redo edits in a text editor
         <li> to connect customers to a support agent at a busy hour
         <li> to store timed events in a simulation
         <li> to move forward and backward in a web browser
         <li> to store a list of songs to play on the radio
         <li> to serve print jobs on a printer
         <li> to move up and down in a directory tree
         <li> to store a deck of cards
             </ul>
<br><br>
19. What interface is used to define an additional ordering for a class? - 4
             <ul>
         <li> Collections
         <li> Comparator
         <li> Comparable
         <li> Collection
             </ul>
<br><br>
20. What method must be overwritten in a class that implements Iterable<String>? - 5
    <ul>
         <li> public String next()
         <li> public String hasNext()
         <li> public Collection<String> iterate()
         <li> public Iterator<String> iterator()
             </ul>
<br><br>
## 17 - recursion
21. Why must recursive methods contain a base case? - 4
             <ul>
         <li> The base case makes the recursive call.
         <li> The method will not compile without a base case.
         <li> The base case returns the final value.
         <li> The base case ends the recursion.
             </ul>
<br><br>
22. What does a StackOverflowError usually indicate? - 3
             <ul>
         <li> pop() was called on an empty stack
         <li> a recursive method looped infinitely
         <li> a generic type was generic to itself
         <li> too many interfaces were implemented
             </ul>
<br><br>
23. What is the output of the following method? - 10
             
```java
public String mysteryMethod(String str) {
    if(str.length == 0) {
        return str;
    }
    else {
        char first = str.charAt(0);
        first += 3; // adding to a character advances it 3 letters in the alphabet.
        return first + mysteryMethod(str.substring(1));
    }
}
public static void main(String[]) {
    System.out.println(mysteryMethod("klab"));
}
```
Answer:
    <li> _____
<br><br>
## 16 - threading
24. True/False: A race condition can occur when two threads simultaneously modify the same value. - 4
25. What are two ways to define your own thread? - 4
        <ul>
         <li> extend Exception
         <li> extend Thread
         <li> Create a new Runnable with a lambda expression
         <li> `public thread NewThread`
    </ul>
<br><br>
27. What is a possible result of the following code? - 4
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
Answer:
    <li> _____________________
<br><br>
27. What would the output be if both calls to `start()` were changed to `run()`? - 4
    <li> _____________________
<br><br>
6 - sorts
28. How does quick sort sort a list? - 2
        <ul>
         <li> Finds the minimum value and swaps it to the start of the unsorted area
         <li> Divides the search area in half, then in a quarter, then in an eighth
         <li> Splits the data into two lists based on whether items are greater than or less than a partition
         <li> Swaps adjacent values
         </ul>
<br><br>
29. Which of the following algorithms has the best time complexity? - 2 
             <ul>
         <li> Selection Sort
         <li> Bubble Sort
         <li> Merge Sort
         <li> Insertion Sort
         </ul>
<br><br>
30. What is the time complexity of linear search? - 2
             <ul>
         <li> O(n)
         <li> O(n2)
         <li> O(1)
         <li> O(n log n)
         </ul>
<br><br>
min 70/107
<br>
max - 37 missed
