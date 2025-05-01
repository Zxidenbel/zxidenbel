# Final Review Quiz

I love you baby <3  
Don't worry if you don't know something right away, that's why we're studying  
You can do it!  

1. Is this what a question will look like?
    * Why yes it is
    * No, are you crazy?

<details><summary>Answer</summary>
This is what the questions will look like.  
  
#### Explanation:  
This is how I formatted them, silly!
</details>

## Generics and Collections

1. Which mostly-static class in Java provides utility methods to manipulate abstract data types (ADTs)?  
    * `Collection`  
    * `Collections` 
    * `ArrayList`  
    * `DataUtils`  

<details><summary>Answer</summary>
The Collections class.
  
#### Explanation:  
`Collections` provides a series of static methods that are useful for operating on  
lists, sets, and queues, though lists are the focus of the operations. `Collections`  
is called "mostly-static" because almost all of its functionality comes from  
static methods.
</details>
<br>

2. Which of the following are valid methods from the class in question 1? (Select all that apply)
    * `sort(List<T> list)`
    * `add(Object obj)`
    * `shuffle(List<?> list)`
    * `size()`

<details><summary>Answer</summary>

`sort(List<T> list)` and `shuffle(List<?> list)`
  
#### Explanation:  
`sort` and `shuffle` are operations that take in an outside collection and modify it.  
Notice how they each take in a `List`. `Collections` is built to provide these kinds of  
external operations. `add` and `size` each require internal access, and so  
they are instead part of the `Collection` interface.
</details>
<br>

3. What are two benefits of using generics in Java collections? (Select two.)
    * They make the code compile faster.
    * They allow you to store any type of data using a single type.
    * They eliminate the need for import statements.
    * They provide type safety by catching type errors at compile time.

<details><summary>Answer</summary>

They allow you to store any type of data using a single type and they provide type safety by catching type errors.
  
#### Explanation:  
Generics make classes flexible regarding the type that they are used for in the rest of the program.  
When they are used, they also specify what type of object the collection takes and returns. This provides  
"type safety" because if the wrong type is used, Java will be able to detect the problem.

In the following code block, no generics are used and there is an undetected type mismatch.
```java
public static void main(String[] args) {
    Object[] numbers = new Object[2];
    numbers[0] = 11;
    numbers[1] = 1;
    String myString = numbers[1]; // this line will throw an exception when running the program
}
```
<br>

The object at `numbers[1]` is an `int`, but the value was assigned to a `String`. Java is not able
to detect the error before running the program, because `String` also extends `Object`.
<br>

The following code block uses generics, and the type mismatch will be detected.
```java
public static void main(String[] args) {
    ArrayList<Integer> numbers = new ArrayList<>();
    numbers.add(11);
    numbers.add(1);
    String myString = numbers.get(1); // java will detect an error on this line
}
```
<br>

The reason Java can detect the type mismatch when using generics is that generics adapt the method  
signatures of the class they modify. In `ArrayList`, the get method has the header:
```java
public T get(int index)
```
When `ArrayList` is initialized as `ArrayList<Integer>`, the get method will now have the header:
```java
public Integer get(int index)
```
<br>
Because the header was changed, Java now knows that the `get()` method will return an `Integer`,  
which is not compatible with `String`.
</details>
<br>

4. In Java, where can a generic data type (like `<T>`) NOT be used?
    * As a method return type
    * As a class or interface type parameter
    * As a field data type
    * To create an instance of a generic type using `new T()`

<details><summary>Answer</summary>

To create an instance of a generic type using `new T()`
  
#### Explanation:  
`new T()` is used to invoke a constructor in Java. Every class defines its own constructors, sometimes  
with specific parameters, so there is no way for Java to know beforehand what the parameters of the  
generic data type's constructor will be. For this reason, using `new T()` to create a new instance  
of a generic data type is not allowed.
<br>

Method return types are allowed so that the class can adapt its output to the generic data type.
```java
public T poll()
```
<br>

Class or interface type parameters are allowed so that the class can adapt what it implements or extends  
to the generic data type, or the generic data type of objects it takes in.
```java
public class ArrayDeque<T> implements Queue<T>
```
```java
public void addAll(List<? extends T> elements)
```
<br>

Field data types are allowed so that the class can adapt the data type it stores to the generic data type.
```java
private T[] elements;
```
</details>
<br>

5. When should you contain an ArrayList instead of extending it in Java?
    * When you want to add extra functionality to the ArrayList class itself
    * When you want to secure an ArrayList so that outside access is restricted
    * When you want to inherit all of the methods and properties of ArrayList directly
    * When you want to be able to use the methods of ArrayList on a new class

<details><summary>Answer</summary>
When you want to secure an ArrayList.
  
#### Explanation:  
Adding extra functionality, inheriting all methods and properties, and using methods are all benefits  
of extending a class, but when a class is extended, access to the class will be the same.

When a class is contained, the containing class decides how the class can be accessed, allowing it  
to restrict outside access.
</details>
<br>

6. Which of the following is the correct way to declare a generic class in Java?
    * `class Box<T> { }`
    * `class<T> Box { }`
    * `class Box implements T { }`
    * `generic Box<T> { }`

<details><summary>Answer</summary>

`class Box<T>`
  
#### Explanation:  
The carat brackets and generic data type (`<T>`) follow the class name.
</details>
<br>

7. Which is the correct syntax for a generic method that takes an argument of type T?

    * `public <T> void printItem(T item)`
    * `public void <T> printItem(T item)`
    * `public void printItem<T>(T item)`
    * `public printItem<T>(T item)`

<details><summary>Answer</summary>

`public void printItem(T item)`
  
#### Explanation:  
The generic data type can be used as a parameter type by placing it before the identifier.
The carat brackets (<>) are not necessary after public or void.
</details>
<br>

8. Which of the following shows a bounded generic type that accepts any subtype of Number?

    * `<T extends Number>`
    * `<T super Number>`
    * `<T implements Number>`
    * `<T = Number>`

<details><summary>Answer</summary>

`<T extends Number>`
  
#### Explanation: 

Putting the `extends` keyword after the generic data type specifies that it must extend or implement the
following type. In other words, it must be a subtype of that type.
</details>
<br>

9. When would you use a wildcard like `<? extends Number>` in a method parameter?

    * When you want to accept any type of object
    * When you want to restrict a generic to only Integer
    * When you want to read from a collection of unknown subtype of Number
    * When writing elements into the collection

<details><summary>Answer</summary>

When you want to read from a collection of unknown subtype of Number.
  
#### Explanation:  
The `extends` wildcard specifies that the collection can be of any type, as long as that type is a Number.
This is appropriate when reading elements, because any subtype of Number can be read as a Number.
</details>
<br>

10. What does an Abstract Data Type (ADT) not specify?

    * The operations it supports
    * The performance of operations
    * The internal data structure used
    * The logical behavior of the data

<details><summary>Answer</summary>
The internal data structure used.
  
#### Explanation:  
ADTs specify the external behavior of the collection, the internal structure is determined by the implementation.
</details>
<br>

11. Which operation is faster in a LinkedList compared to an ArrayList?

    * Accessing the 10th element
    * Adding an item to the end
    * Removing the first element
    * Sorting the list

<details><summary>Answer</summary>
Removing the first element is faster in a LinkedList.
  
#### Explanation:  
A LinkedList has to follow 9 nodes to reach the 10th element.  
Both an ArrayList and LinkedList can immediately add an item to the end.
An ArrayList has to shift every item towards the start to remove the first element. A LinkedList only has to set the second node as the head of the list.  
The LinkedList has slower swapping and access, so all sorts are slower on a LinkedList.
</details>
<br>

12. What behavior does a Queue model?

    * LIFO – Last In First Out
    * FIFO – First In First Out
    * Random Order
    * Priority-based removal

<details><summary>Answer</summary>
FIFO - First In First Out
  
#### Explanation:  
The first item offered to a queue will be the first item polled.
</details>
<br>

13. Which of the following is true about PriorityQueue in Java?

    * It always keeps its elements sorted internally
    * It removes elements in the order they were added
    * It removes the smallest (or highest priority) element first
    * It is an interface

<details><summary>Answer</summary>
It removes the highest priority element first.
  
#### Explanation:  
</details>
A PriorityQueue does not keep its elements sorted internally. It is a concrete class
that removes the highest priority element first.
<br>

14. Short Answer: Why is a base case required in a recursive method?

<details><summary>Answer</summary>
Without the base case, the method will loop infinitely.

</details>
<br>

15. In recursion, how are local variables handled between recursive calls?

    * They are shared among all recursive calls
    * They are distinct for each call
    * They are declared once and reused
    * They are stored in a global stack

<details><summary>Answer</summary>
They are distinct for each call
  
#### Explanation:  
Every time a method is called, new space is made for its local variables.
When a recursive method calls itself, new space is still made for the new call,
so the variables are distinct.

</details>
<br>

16. What are the two main ways to create threads in Java?

    * Extend Thread or implement Runnable
    * Use ThreadPool or Timer
    * Import java.thread or use Thread.start()
    * Use ForkJoinPool or Future

<details><summary>Answer</summary>
Extend Thread or implement Runnable
  
#### Explanation:  
Extending thread (and overriding `run()`) creates a thread that does something specific when it is started.

The default thread can also run a task defined by implementing Runnable or writing a lambda expression.

</details>
<br>

17. Short Answer: What is a race condition?

<details><summary>Answer</summary>
A race condition is a case where the outcome of code is different based on which piece of code reads/writes a value first.

</details>
<br>

18. What is the time complexity of selection sort?

    * O(n<sup>2</sup>)
    * O(log n)
    * O(n log n)
    * O(1)

<details><summary>Answer</summary>
O(n<sup>2</sup>)
  
#### Explanation:  
When selection sort is used to sort a list of length `n`, it must perform `n` comparisons `n` times.  
The relationship between the time it takes to compute and the length of the list is therefore `t = n * n`, written O(n<sup>2</sup>).

The time complexity of common sorting algorithms:
| Algorithm | Complexity |
|-----------|------------|
| Selection | O(n<sup>2</sup>) |
| Insertion | O(n<sup>2</sup>) |
| Bubble    | O(n<sup>2</sup>) |
| Merge     | O(n * log<sub>2</sub>(n)) |
| Quick     | O(n * log<sub>2</sub>(n)) |
| Bogo      | O(n!) |

The time complexity of common searching algorithms:
| Algorithms | Complexity |
|------------|------------|
| Linear     | O(n)       |
| Binary     | O(log<sub>2</sub>(n)) |

It can be difficult to remember the complexities of different algorithms.  
To remember the complexities, it can be helpful to draw a relationship between patterns in algorithms and their complexity.
| Complexity | Name | Algorithm Patterns | Algorithms    |
|------------|------| -------------------|---------------|
| O(1)       | Constant Time | Algorithms that don't use repeating or branching logic. | Index select |
| O(log<sub>2</sub>(n)) | Logarithmic Time | Algorithms that split data and evaluate. | Binary search |
| O(n)       | Linear Time | Algorithms that must evaluate each value in the data. | Linear search |
| O(nlog<sub>2</sub>(n)) | Loglinear Time | Algorithms that split data and compare. | Merge sort, Quick sort |
| O(n<sup>2</sup>) | Polynomial Time | Algorithms that must compare each value of the data. | Bubble sort, Selection sort, Insertion sort |
| O(2<sup>n</sup>) | Exponential Time | Algorithms that solve very complex problems. | Genetic Algorithm |
| O(n!) | Factorial Time | Algorithms that use random chance to solve problems. | Bogo sort |
</details>
<br>

19. Which sorting algorithm is generally the slowest for large, unsorted datasets?

    * Bubble Sort
    * Insertion Sort
    * Merge Sort
    * Selection Sort

<details><summary>Answer</summary>
Bubble Sort
  
#### Explanation:  
Bubble sort uses significantly more swaps than are necessary to sort the list.  
The other sorting algorithms will complete the task more efficiently.
</details>
<br>

20. Which sorting algorithm is generally the fastest for large, unsorted datasets?

    * Quick Sort
    * Insertion Sort
    * Merge Sort
    * BOGO Sort

<details><summary>Answer</summary>
Merge Sort
  
#### Explanation:  
Merge sort and quick sort both use a divide-and-conquer strategy, but quick sort is  
less efficient for large datasets.
</details>
<br>

21. Can you create an object from an abstract class?

    * Yes
    * No
    * Only if it implements all methods
    * Only using reflection

<details><summary>Answer</summary>
No
  
#### Explanation:  
Classes are marked abstract to specify that they should objects should not  
be made from them. If an object were made from an abstract class, abstract methods  
could be called without a body.
</details>
<br>

22. Can a class implement more than one interface in Java?

    * No
    * Yes
    * Only if the interfaces are related
    * Only if it’s not abstract

<details><summary>Answer</summary>
Yes
  
#### Explanation:  
Classes can implement any number of interfaces. This is what makes interfaces  
a great tool for compatibility in code. For example, the `Comparable` interface makes classes  
compatible with the `sort` method.
</details>
<br>

23. Which of the following is a checked exception?

    * NullPointerException
    * IndexOutOfBoundsException
    * IOException
    * ArithmeticException

<details><summary>Answer</summary>
IOException
  
#### Explanation:  
Null pointers, indices out of bounds, and arithmetic errors are assumed to be prevented
by following good coding practices. IO exceptions signify that a required file could not be read,
which is a possibility that should be acknowledged. This is why it is checked in Java. A checked exception
must be caught with `catch` or declared with `throws` so that it is either handled in the method or when the method is called.
</details>
<br>

24. What is the main purpose of a JFrame in Java Swing?

    * To hold layout settings
    * To represent a window
    * To draw buttons only
    * To run the main method

<details><summary>Answer</summary>
To represent a window
  
#### Explanation:  
The JFrame is a component that creates a window and holds one component.
The responsibility for the other functions falls to other parts of the program.
</details>
<br>

25. Which of the following is not a correct way to create an ActionListener?

    * Use a lambda expression
    * Use an anonymous inner class
    * Use a named class that implements ActionListener
    * Call `addActionListener()` on a JLabel

<details><summary>Answer</summary>

Call `addActionListener()` on a JLabel
  
#### Explanation:  
ActionListener is an interface with only one method, so a lambda expression, anonymous inner class, or named class
are valid ways to create an ActionListener. The `addActionListener()` method instead adds an actionListener that was already
created.
</details>
<br>

## Matching

1. Undoing actions in a text editor	
<details><summary>Answer</summary>Stack</details><br>

2. Print jobs for a printer
<details><summary>Answer</summary>Queue</details><br>	

3. Navigating browser back/forward history	
<details><summary>Answer</summary>Stack</details><br>

4. Call center putting callers on hold	
<details><summary>Answer</summary>Queue</details><br>

5. Reversing a word one character at a time
<details><summary>Answer</summary>Stack</details><br>

<details><summary>Explanations</summary>
Scenarios where a queue should be used require FIFO behavior. Any situation where the first 
item added should be processed first should use a queue. Many queue scenarios involve 
"first-come-first-served" processing for people awaiting a service.  
<br>
Scenarios where a stack should be used require LIFO behavior. Any situation where the most recent
item is the most important should used a stack. Many stack scenarios involve moving backward and forward in time,
adding or removing layers, or reversing something.
</details>

## More Multiple Choice

---

### ✅ **Inheritance**

#### **1. Multiple Choice**  
**Question:**  
Which keyword is used in Java to indicate that one class inherits from another?

**A.** `inherits`  
**B.** `super`  
**C.** `extends`  
**D.** `implements`

<details><summary>Answer</summary>

✅ **Correct Answer:** C

</details>

---

#### **2. Short Answer**  
**Question:**  
What is the purpose of the `super` keyword in an inherited class?

<details><summary>Answer</summary>

✍️ **Sample Answer:**  
It is used to call the constructor or methods of the superclass from the subclass.

</details>

---

### ✅ **Deep vs. Shallow Copies**

#### **3. Multiple Choice**  
**Question:**  
What is the main difference between a **shallow copy** and a **deep copy**?

**A.** A shallow copy includes private fields, while a deep copy does not  
**B.** A shallow copy copies references, while a deep copy copies actual objects  
**C.** A shallow copy duplicates all objects in memory  
**D.** A deep copy only works with primitive types

<details><summary>Answer</summary>

✅ **Correct Answer:** B

</details>

---

#### **4. True or False**  
**Question:**  
A deep copy of a list of objects will result in a new list, where each element is a new object, not just a reference.

<details><summary>Answer</summary>

✅ **Correct Answer:** True

</details>

---

#### **5. Short Answer**  
**Question:**  
Why can a shallow copy be dangerous when working with mutable objects?

<details><summary>Answer</summary>

Because changes made to the copied object's references also affect the original object, since they share the same underlying data.

</details>

---

### ✅ **Polymorphism**

#### **6. Multiple Choice**  
**Question:**  
Which of the following best describes polymorphism?

**A.** A class can have only one method  
**B.** Objects can take many forms and a subclass object can be treated as a parent class object  
**C.** Only abstract classes can use inheritance  
**D.** It prevents method overriding in Java

<details><summary>Answer</summary>

✅ **Correct Answer:** B

</details>

---

#### **7. True or False**  
**Question:**  
A single method name in Java can refer to different implementations depending on the object’s runtime type.

<details><summary>Answer</summary>

✅ **Correct Answer:** True

</details>

---

#### **8. Code-Based Question**  
**Question:**  
What will this code print?

```java
class Animal {
    void speak() {
        System.out.println("Animal speaks");
    }
}

class Dog extends Animal {
    void speak() {
        System.out.println("Dog barks");
    }
}

public class Test {
    public static void main(String[] args) {
        Animal myDog = new Dog();
        myDog.speak();
    }
}
```

<details><summary>Answer</summary>

✅ **Correct Answer:** `Dog barks`  
✅ **Explanation:** This demonstrates runtime polymorphism. The method call is resolved based on the actual object type (`Dog`), not the reference type (`Animal`).

</details>

## Code Question

What is the output of the following code?
```java
public class RecursionExample {
    public static int mystery(int n) {
        if (n <= 1) {
            return 1;
        } else {
            return n * mystery(n - 2);
        }
    }

    public static void main(String[] args) {
        System.out.println(mystery(5));
    }
}
```

<details><summary>Answer</summary>

✅ **Correct Answer:** 15 
✅ **Explanation:** `mystery(5)` returns `5 * mystery(3)`. `mystery(3)` returns `3 * mystery(1)`. `mystery(1)` returns `1`.

</details>
<br>

Which section is the base case in the above question?
1.
```java
mystery(5)
```
2.
```java
if (n <= 1)
    return 1;
```
3.
```java
else {
    return n * mystery(n -2);
```
4.
```java
public static int mystery(int n) {
```

<details><summary>Answer</summary>

✅ **Correct Answer:**
```java
if (n <= 1)
    return 1;
```

✅ **Explanation:** The base case is the case where the input is so simple recursion is not needed.

</details>



