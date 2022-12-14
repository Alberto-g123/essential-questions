# Java
1. Scopes in Java?
   1. variable scopes
      - where code can be accessed

      1. class scope
         - where everything is written 
         - static variables must be declared inside a class, accessible to all objects of that class

      2. Instance/object scope
         - inside of class scope 
         - variable is non-static and is accessible anywhere

      3. method scope
         - variables made in a method can only be accessed in the method

      4. block scope
         - code usually in if-statements/for-loops
         - if variables made in block scopes, can only be accessed in it


2. 4 pillars of OOP?
   1. Abstraction
   2. Polymorphism
   3. Inheritence
   4. Encapsulation

3. Explain each pillar and be able to provide examples as well as analogies
   1. Abstraction
      - ability to hide implentations
        - abstract classes and interfaces, methods is also a form of abstraction
        - ### example: 
          - turning your car on, you know that you use your keys and turn the ignition to start the car but you dont know the internal process of turning the ignition that makes the car run.
   2. Polymorphism
      - many forms, ability to treat the same object differently
        - Static polymorphism
          - Overloading
            - method with same name but different parameters
              - ### example:
              - two methods with the same name "add" one that takes in two arguments and one that takes in three
               ```Java
                 double add(double num1, double num2){
                    return num1 + num2;
                 }
                 double add(double num1, double num2, double num3){
                    return num1 + num2 + num3;
                 }
               ```
        - Dynamic Polymorphism
          - Overriding
            - same method signature but child class has different implentation
   3. Inheritence
      - DRY code (Dont Repeat Yourself), usually use extends to derive code from another class
        - Uses Overriding to modify parent code
        - ### example:
          - Bird as parent class has a sound method that prints out tweet
          - Hawk as a child class that extends the parent class bird, overrides the sound method with its own that prints out screech
            ```Java
            class Bird{
                void sound(){
                    System.out.println("tweet");
                }
            }

            class Hawk extends Bird{
                @Override
                void sound(){
                    System.out.println("screech")
                }
            }
            ``` 
   4. Encapsulation
      - Prevents data and methods from being misused elsewhere in the code
      - means wrapping or binding data and methods and code together into a single unit
      - sub process in data hiding(data hiding can only have data as private)
        - Access Modifiers private is used alot to show off Encapsulation
        - ### example: 
          - school bag that has stuff inside like pencils, notebooks. and in order to get any of the stuff you would have to open that bag
          ```Java
          class Bag{
            private String pencil;
            private String notebooks;

            public String getPencil(){return pencil;}
            public String getNotebooks(){return notebooks;}
          }
          ``` 

4. What is the Collections Framework?
   - network of classes and interfaces that are objects designed to hold other objects


5. What is a List?
   - a child interface of collection
     - duplicates of a value can be stored here
     - maintains order of insertion

6. What are some implementations of a list?
   - ArrayList
   - LinkedList
   - Stack
   - Vector
     - Syntax:
     ```Java
     List<Obj> arrayList = new ArrayList<Obj>();
     LinkedList linkedList = new LinkedList();
     Stack stack = new Stack();
     Vector<Obj> vector = new Vector<Obj>();
     ``` 

7. What is a Set?
   - a child interface of collection
     - No duplicates
     - *Does not* maintain order of insertion
  
8. what are some implementations of a Set?
   - HashSet
   - TreeSet
   - LinkedHashSet
     - Syntax:
     ```Java
     HashSet<obj> hashSet = new HashSet();
     TreeSet treeSet = new TreeSet();
     LinkedHashSet<Obj> linkedHashSet = new LinkedHashSet<Obj>();
     ```    

9.  What is a queue
    - a child interface of collection
      - follows FIFO(First In First Out)

10. what are some implementations of a Queue?
    - PriorityQueue
    - LinkedList
    - PriorityBlockingQueue
      - Syntax:
      ```Java
      Queue<Obj> priorityQueue = new PriorityQueue<Obj>();
      Queue<Obj> linedListQueue = new LikedList<Obj>();
      Queue<Obj> priorityBlockingQueue = new PriorityBlockingQueue<Obj>();
      ```   

11. What is a Map?
    - **Not** a subtype of Collection Interface
    - Represents a mapping between a key and a value
    - **Can not** contain duplicate keys
    - each key can map to at most one value


12. what are some implementations of a Map?
    - HashMap (Class that implents Map)
    - LinkedHashMap (extends HashMap class)
    - SortedMap (Interface that extends Map)
    - TreeMap (class that implements SortedMap Interface)
      - Syntax:
        ```Java
        Map<String, Integer> map = new HashMap<>();
        Map<String, Integer> map = new LinkedHashMap<>();
        Map<String, Integer> map = new TreeMap<>();
        ``` 

13. Difference between a List and a Set?
    - List is a type of **ordered** collection that maintains insertion order
    - Set is a type of **unordered** collection that are not maintained in any order
    - List **allows** duplicates, Set **DOES NOT** allow duplicates. if you were to try to insert a duplicate value in a Set it would replace the existing value
    - 


14. Is a Map a collection?
    - Technically not a collection because it does **NOT** implement the collection interface


15. What is the root class of collection hierarchy?
    - Collection Interface


16. Collection interface vs Collections class
    1. Collection interface:
       1. an interface in Java Collection Framework
       2. Used to store list of objects in a single object
       3. Set, List, and Queue are subinterfaces
       4. Map is not part of this interface
    2. Collections Class:
       1. a utility class in Collection framework
       2. used to operate on collection
       3. Map interface is part of the collections framework
       4. contains only static methods like sort(), min(), max(), fill(), copy(), reverse()


17. Access Modifiers
    1. Default
       - only visible within the package
    2. private
       - only visible in the class
    3. public
       - visible everywhere
    4. protected
       - visible within the package or subclasses


18. What is the entry point of a Java program?
    - Main Method 


19. What is the method signature of the main method?
    ```Java
    public static void Main(String[] args){

    }
    ```

20. What does the static keyword do?
    1. Variables declared static:
       - shared among all objects of a class
         - (since the variable itself essentially belongs to the class itself)
    2. Methods and Variables declared static:
       - can be accessed via the class name (insted of the usual object reference)
        ```Java
        MyClass.staticMethod();
        ``` 


21. Can you tell me keywords that are not access modifiers?
    1.  static
        - The member belongs to the class
        - not to objects of that class 
    2.  final
        - Variable values **Can't** be changedonce assigned
        - methods cant be overriden
        - classes **Can't** be inherited
    3.  abstract
        - if applied to a method, has to be implemented in a subclass
        - if applied to a class, contains abstract methods
    4.  synchronized
        - Controls thread access to a block/method
    5.  volatile
        - Variable value is always read from the main memory
        - not from a specific thread's memory
    6.  transient
        - The member is skipped when serializing an object
        - when a variale is marked transient, it is not serialized
          - serialization is the process of converting an object into a byte stream


22. What is a constructor and how do I make one?
    - Special methods that create an object from a class
    - Must be named the same as the class
    - do not have a return type
    - can be overloaded, **Can Not** be overridden
    - if no constructor is defined than Java provided a default no args constructor
    ```Java
    class Example{
        int num;
        String name;
        // no args Constructor
        Example(){
        }

        // Constructor that takes 2 arguments
        Example(int num, String name){

        }
    }
    ``` 


23. Errors vs Exceptions?
    1. Errors
       - Catastrophic failures that you should not catch
    2. Exceptions 
       - problem that can be handled


24. Checked vs Unchecked Exceptions?
    1. Checked Exception
       - compile time exception
       - handled by a try catch block
    2. Unchecked Exception
       - runtime exception

25. How do I do error handling in Java?
    - Try catch block to handle errors or exceptions 


26. JDK vs JRE vs JVM?
    1. JDK (Java Developement Kit)
       - software develpment environment used for developing Java applications and applets
       - Example:
         - Oracle JDK
         - Amazon Corretto
         - OpenJDK
       - includes two things
         - developement tools (provide an environment to develop java programs)
         - JRE (to execute the java program)


    2. JRE (Java Runtime Environment)
       - an installation package that provides an environment to **only run(not develop)** the java program
       
    3. JVM (Java Virtual Machine)
       - responsible for executing the java program line by line
       - known as an **Interpreter**


27. Tell me about Java?
    - Strongly typed
      - no restrictions between conversions between data types
    - Statically typed
      - all variables must have there data types defined
    - High level language
      - No pointers
      - read and written easily by humans
    - Compiled
      - You write human readable .java files
      - Java Compiler reads the .java files and create .class versions
      - which are computer readable files


28. What is an algorithm?
    - static methods that can be used to perform various operations on collections
    - Example:
    ```Java
    Collections.sort('name of list');
    Collections.shuffle('name of list');
    Collections.min('name of list');
    Collections.max('name of list')
    ``` 


29. Abstract classes vs interfaces?
    - Interfaces:
      1. Interface can have only abstract methods
      2. variables are by default final
      3. only has static and final variables
      4. cannot provide the implentation of an abstract class
      5. supports multiple inheritance
    - Abstract:
      1. can have both abstract and non-abstract methods
      2. can contain non-final variables.
      3. can have final, non-final, static and non-static variables
      4. can provide the implementation of the interface
      5. does not support multiple inheritance


30. How do I make a lambda in Java?
    1. have a functional interface (interface with one method)
    2. paraenthesized set of parameters
    3. an arrow pointing to right
    4. A body, which can be a block of code or a single expression
       1. syntax of a lambda
        ```Java
        (parameters) ->{body};
        ``` 


31. Give me an example of where you used lambdas?
    1. where you would have an interface that had one method
    ```Java
        @FunctionalInterface//It is optional but best practice to add annotation 
        interface Drawable{  
            public void draw();  
        }         
        public class LambdaExpressionExample2 {  
            public static void main(String[] args) {  
                int width=10;  
                // Lambda 
                Drawable d2=()-> System.out.println("Drawing "+width);//since its one line of code, body does not need curly brackets 
                d2.draw();  
        }  
    }  
    ```

32. What is a thread?
    - line of execution within a program
    - All java programs have at least one thread, main thread, created at the start of the program, main method is invoked with the main thread


33. How do I make a thread?
    1. class extends thread
    2. declare a class that implements the runnable interface


34. What is deadlock?
    1.  where two or more threads are blocked forever


35. What is a Java Bean?
    1. classes that encapsulate many objects into a single object(the bean)
    2. should follow these conventions:
       1. must implement serilizable
       2. should have a public no-args constructor
       3. all properties in java bean must be private with public getters and setter methods


36. What is a singleton?
    1. a class that can have only one object(an instance of the class) at a time



## SQL
1. What is SQL?
   - (Structured Query Language)
   - SQL is a Domain Specific Language(DSL)
   - programming language for relational databases

2. How can I join a table on a column?
   1. you can use different kinds of joins
   2. left join, right join, inner join, full join
   3. one table would have to reference the second table
   ```SQL
    select * from left join table1 on table1.t_id = table2.table_id;
   ```
3. What are the sublanguages of SQL?
   1. DDL(Data Definition Language)
      1. commands for creating the schema
      2. CREATE, DROP, ALTER
   2. DML(Data Manipulation Language)
      1. commands for editing the data
      2. DELETE, UPDATE, INSERT
   3. DQL(Data Query Language)
      1. SELECT
   4. DCL(Data Control Language)
      1. Commands for editing permissions 
      2. GRANT, REVOKE
   5. TCL(Transaction Control Language)
      1. commands for making transactions
      2. COMMIT, ROLLBACK
   
4. What is normalization?
   1. process of removing redundancy from a database/table


5. When is a table in 1NF?
   1. each record is uniquely identifiable
   2. data is atomic, cannot be broken down into more meaningful columns


6. When is a table in 2NF?
   1. take previous normalized form
   2. column cannot be calculated using values in another column


7. When is a table in 3NF?
   1. take previous normalized form adds....
   2. column cannot be found in another table


8. Tell me SQL constraints.
   1. Restrictions we can add to columns on a table
      1. example:
         1. unique
         2. not null
         3. check
         4. default


9.  What is a primary key?
    1. combination of two keys unique and not null

10. How do I make a Foreign key?
    1. you would need a unique column on the parent table
    2. on the child table you would need a column that would **reference** the unique column in the parent table


11. What is a scalar function?
    1. a function that are based on user input
    2. these return single value
12. Examples?
    1.  UCASE()
    2.  LCASE()
    ```SQL
    select ucase(column_name) from table_name;
    select lcase(colum_name) from table_name;
    ``` 

13. What is an aggreate function?
    1. used to do operations from the values of the column
    2. return a single value
14. Examples?
    1.  AVG()
    2.  Count()
    ```SQL
    select avg(column_name) from table_name;
    select count(column_name) from table_name;
    ```  
15. How would you create your own function?
     ```SQL
     CREATE FUNCTION [database_name.]function_name (parameters)
    RETURNS data_type AS
    BEGIN
        SQL statements
        RETURN value
    END;

     ```


16. What is a transaction?
    1. Discrete update units for Relational Database
    2. consists of 1 to many SQL statments
17. What are the ACID properties of transatcions?
    1. Atomic
       1. All or none of the statements persist in the transaction
    2. Consistent
       1. constraints must be maintained so that the database is consistent before and after the transaction
    3. Isolated
       1. transactions occur independently without interference
       2. trasactions can run in parallel and serial
          1. parallel
             1. multiple computations at the same time
          2. serial
             1. one at a time
    4. Durable
       1. failures in a transaction do not cause data corruption

## Spring
1. What is Spring?
2. What is a Framework?
   1. A framework, or software framework, is a platform that provides a foundation for developing software applications.

3. What is Depenedency Injection?
4. Type of dependency injection?
5. What is a framework?
6. Tell me about Inversion of Control
7. What is the IoC containers?
8. What is the ApplicationContext/BeanFactory
9.  What is a Spring bean?
10. What are the scopes of a bean?
11. What are stereotypes?
12. How do you configure Spring?
13. Spring vs Spring Boot.
14. Spring dispatcher servlet?
15. What is the Spring Bean Lifecycle.
16. Know all your annotations!
17. Cloud/DevOps
18. What DevOps have you done?
19. What is your expeience with the cloud?
20. What cloud services have you used?
21. What is Maven?
22. How have you used Maven in your project?
23. What experience do you have with CI?
24. How did you set up Continous Integration/Delivery?