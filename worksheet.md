# Worksheet 2: Memory, Classes & Generics


Collaborators:


## Review
1. In your own words, explain what a stack is, and what kind of data goes on the stack.

2. In your own words, explain what a heap is, and what kind of data goes on the heap.

3. For each of the following datatypes, say whether a variable of that type would go on the stack or the heap:    
a. `bool`  
b. `int`  
c. `float`  
d. `Car`  
e. `Engine`   
f. `String`

4. In your own words, explain what a data structure is.

5. What must be considered when selecting a data structure for a task?



## Exploration
1. Draw the stack and heap at the indicated place in the code. You can use [Java Tutor](http://pythontutor.com/java.html) to check your answer. Upload your drawing to your github repo and put a link in your markdown worksheet file so the drawing displays here.

    ```java
    public class Worksheet {

        public static int twice(int n) {
            int result = 2 * n;
            // DRAW MEMORY HERE
            return result;
        }

        public static int thrice(int n) {
            int result = 3 * n;
            return result;
        }

        public static int sixce(int n) {
            return twice(thrice(n));
        }

        public static void main(String [] args) {
            int n = 7;
            System.out.println(sixce(n));
        }

    }
    ```
2. `null` is a special value in Java for reference variables that do not currently refer to anything. In the code below,  which line(s) would a variable be set to `null`?

    ```java
    public class MemoryModel {

        static class Engine {
            String name = "Turbo";
        }

        static class Car {

            int id;
            int hp;
            Engine myEngine;

            public Car(int id) {
                this.id = id;
            }
        }

        public static void doMore() {
            System.out.println("doing more stuff...");
        }

        public static void doWork() {
            double weight = 120.30;
            doMore();
        }

        public static void main(String[] args) {
            int age;
            age = 12;
            age = 15;
            String name = "";

            Car myCar;
            myCar = new Car(1);
            myCar = new Car(2);

            Car my2Car = new Car(3);
            my2Car.hp = 120;

            Car my3Car = new Car(4);
            my3Car.hp = 1000;

            Engine bigEngine = new Engine();
            my3Car.myEngine = bigEngine;
        }

    }
    ```
3. Arrays are also reference variables. In the code below, we create an array of three elements, then set the 0th element to 37 and the 1st element to 42. Using [Java Tutor](http://pythontutor.com/java.html) to check your answer, draw out memory at the indicated place in the code. Make sure you select "render all objects on the heap" and "draw pointers as arrows". Do the same for this drawing, upload image and link in your worksheet.

    ```java
    public class Worksheet {
        public static void main(String[] args) {
            int[] array = new int[3];
            array[0] = 37;
            array[1] = 42;
            // DRAW MEMORY HERE
        }
    }
    ```
4. Draw out memory at the indicated place in the code. Upload your drawing to your github branch. Explain why that is the result.

    ```java
    public class Worksheet {
        public static void main(String[] args) {
            String[] array = new String[3];
            array[1] = "hello";
            // DRAW MEMORY HERE
        }
    }
    ```
5. Consider the following two (equivalent) diagrams of memory below. Change the code marked `FIXME` so that memory will be as depicted at the indicated place in the code.

    ![Exploration Q5](images/exploration-q5-tutor.png)

    ![Exploration Q5](images/exploration-q5.png)

    ```java
    public class Worksheet {

        static class Element {
            private String my_name;

            public Element(String name) {
                this.my_name = name;
            }

        }

        public static void main(String[] args) {
            Element[] elements = new Element[3];
            // FIXME

            // MEMORY DRAW HERE
        }

    }
   ```
6. Suppose you were given the following class definition:

    ```
    public class Bucket<T>{

       private T item;

       public Bucket<T> (T item){
          this.item = item;
          }
    }
    ```

    a. How would you instantiate a `Bucket` object that holds integers?
    b. How would you instantiate a `Bucket` object that holds strings?  
    c. How would you instantiate a `Bucket` object that holds Car objects?  
    d. Write a method `getItem()` that returns the `item` held by a `Bucket`.


## Challenge


1. Java has two ways of testing if two objects are the same - `==` and `.equals()`. You might have been told to always use `.equals()`, but there *are* cases where `==` is useful. Read some of the search results from Google on how these are different, then in your own words, explain what `==` does and why you would want to use `.equals()` most of the time.
2. What are the benefits of writing generic classes? When might it be better to _not_ use generics?
