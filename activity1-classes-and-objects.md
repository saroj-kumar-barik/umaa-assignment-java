 ### 1) Example with code to show state and behaviour of an object where behaviour depends upon the state of object?
 
 * Below is a code in java that explains the state and behaviour of an object
 ```java
 package org.activitypractice;

public class StateAndBehavior {
    // explaining the fields of a laptop
    private String model;
    private String nameOfOS;
    private double rating;

    // constructor to initialise the fields
    public StateAndBehavior(String model, String nameOfOS, double rating) {
        this.model = model;
        this.nameOfOS = nameOfOS;
        this.rating = rating;
    }

    //crating methods of the class
    public String getDetails(){
        return "The name of the laptop is "+this.model+" OS used : "+this.nameOfOS
                +" with a costumer rating "+this.rating;
    }

    @Override
    public String toString() {
        return "StateAndBehavior{" +
                "model='" + model + '\'' +
                ", nameOfOS='" + nameOfOS + '\'' +
                ", rating=" + rating +
                '}';
    }

    public static void main(String[] args) {
        StateAndBehavior stb = new StateAndBehavior("ASUS ROG STRIX G","Windows",4.6);// states of objects
        System.out.println(stb.getDetails()); // behaviour of Object
        System.out.println(stb.toString());

    }
}
```
* In the above code the the states of the objects are : model - "ASUS ROG STRIX G, nameOfOS - Windows & rating - 4.6
* Here ***getDetails()*** & ***toString()*** are the behaviour of the object
* We have accesed the behavior of the states of the objects in the behaviour part


### 2) What is the definition of hashcode as per java 8 document?
* It Returns a hash code value for the object. This method is supported for the benefit of hash tables such as those provided by HashMap.
* Whenever it is invoked on the same object more than once during an execution of a Java application, the hashCode method must consistently return the same integer, provided no information used in equals comparisons on the object is modified. This integer need not remain consistent from one execution of an application to another execution of the same application.
* If two objects are equal according to the equals(Object) method, then calling the hashCode method on each of the two objects must produce the same integer result.
* It is not required that if two objects are unequal according to the equals(java.lang.Object) method, then calling the hashCode method on each of the two objects must produce distinct integer results. However, the programmer should be aware that producing distinct integer results for unequal objects may improve the performance of hash tables.

### 3) What is the fully qualified name of Object class in java ?
* The fully qualifued class name of Object Class in java is : java.lang.Object

### 4) Object class is in which package ?
* It is present in java.lang package.

* ## Find the Output : ##
---------------------------

### 1) Find the output?
```java
public class Test
{
    public static void main(String[] args)
    {
        Object obj1 = new Object();
        Object obj2 = new Object();
        System.out.println(obj1.hashCode() == obj2.hashCode());
        System.out.println(obj1.getClass());
        System.out.println(obj1 == obj2);
    }
} 
```
### Ans :  O/P of the Program is : 
* False
* class Test
* False  
*  ***Explanation***
* Two different objects obj1 and obj2 has two different hashCodes
* So obj1.hashCode() == obj2.hashCode() will not be same hence O/P comes False
* The getClass() methods returns the class name of the Object hence O/P comes to be : class Test

### 2) Find the output?
```java
public class Test {
    int x;
    public Test(int x){
        this.x = x;
    }
    public static void main(String[] args) {
        Test t = new Test(10);
        System.out.println(t.x);
    }
}
```
### Ans : O/P of the program is 
* 10(as new Test(10) will invoke the constructor and updates the field value to 10 and t.x will give the O/P as 10 )

### 3) Why below code will not compile? What is the fix we have to do so that the code will compile.  
```java
public class Test {
    int x;
    public Test(int x){
        this.x = x;
    }
    public static void main(String[] args) {
        Test t = new Test();
        System.out.println(t.x);
    }
}
```
### Ans :
* The above code will give compile time error as the user defind constructor has one argument where as, we have not pass one value of type int in the constructor calling part.
* A fix to the program would be, to pass an int value as the constructor parameter in the constructor invoking part.

### 4) Will below code will compile?
```java
public class Test {
    int x;
    public Test(int x){
        this.x = x;
    }
    public Test()
    {
        
    }
    public static void main(String[] args) {
        Test t = new Test();
        System.out.println(t.x);
    }
}
```
* The above code will compile fine because we have defind a no argument constructor for the call : new Test() and hence t.x will give a O/P as 0(Default value)

### 5) Find the output?
```java
public class Test {
    int x;
    String y;
    public static void main(String[] args) {
        Test t = new Test();
        System.out.println(t.x);
        System.out.println(t.y);
    }
}
```
### Ans :
* The O/P of the above code is 0 and null because the default values for int and String is 0 and null respectively

### 6) Find the output?
```java
public class Test {
    int x;
    String y;

    public Test(int x, String y) {
        this.x = x;
        this.y = y;
        Test tVar = this;
        System.out.println(tVar.hashCode() == this.hashCode());
    }

    public static void main(String[] args) {
        Test t = new Test(10,"john");
        System.out.println(t.x);
        System.out.println(t.y);
    }
}
```
### Ans :
* The O/P of the above programs are 
* true 
* 10 
* John
* The statement : Test tVar = this; , tVar will be assigned the same memory location as of t as "this" refers to the current object.

### 7) Find the output?
```java
public class Test {
    int x;
    String y;

    public Test(int x, String y) {
        this.x = x;
        this.y = y;
        m1(this);
    }

    public static void main(String[] args) {
        Test t = new Test(10,"john");
        System.out.println(t.x);
        System.out.println(t.y);
    }
    
    public void m1(Test t1)
    {
        t1.x = 100;
        t1.y = "Doe";
    }
}
```
### Ans :
* The O/P is :
* 100
* Joe
* because m1(this) will invoke m1 method where the fields are updated to 100 and Joe

### 8) Find the output?
```java
public class Test {
    int x;
    String y;

    public Test(int x, String y) {
        this.x = x;
        this.y = y;
        this.m1(this);
    }

    public static void main(String[] args) {
        Test t = new Test(10,"john");
        System.out.println(t.x == 10);
        System.out.println(t.y == "john");
    }

    public void m1(Test t1)
    {
        t1.x = 100;
        t1.y = "Doe";
    }
}
```
### Ans :
* The O/P will be 
* false
* false
* because the this.m1(this) method call will update the filed values and hence the above sout statemets will give false

### 9) Find the output?
```java
public class Test {
    int x;
    String y;

    public Test(int x, String y) {
        x = x;
        y = y;
        this.m1(this);
    }

    public static void main(String[] args) {
        Test t = new Test(10,"john");
        System.out.println(t.x);
        System.out.println(t.y);
    }

    public void m1(Test t1)
    {
        t1.x = 100;
        t1.y = "Doe";
    }
}
```

### Ans :
* O/P will be : 
* 100
* Doe 
* here x = x and y= y will not update the value to the field but the field values will be updated in the m1() and give the above output

### 10) Find the output?
```java
public class Test {
    int x;
    String y;

    public Test(int x, String y) {
        x = x;
        y = y;
    }

    public static void main(String[] args) {
        Test t = new Test(10,"john");
        System.out.println(t.x);
        System.out.println(t.y);
    }

    public void m1(Test t1)
    {
        t1.x = 100;
        t1.y = "Doe";
    }
}
```
### Ans :
* O/P
* 0
* null
* as explained above the x and y will not update the value hence the value of fields will be default

### 11) Find the output?
```java
public class Test {
    int x;
    String y;

    public Test(int x, String y) {
        x = x;
        y = y;
    }

    public static void main(String[] args) {
        Test t = new Test(10,"john");
        Test t1 = t;
        System.out.println(t1 == t);
        t1.x = 300;
        t1.y = "alex";
        System.out.println(t.x);
        System.out.println(t.y);
    }
}
```
### Ans :
* O/P will be
* true
* 300
* alex

### 12) Identify State & Behaviour. Find where the state is used. Does behavour depends on the state?
```java
public class Calculator
{
   private int i;
   private int j;
   
   public Calculator(int i, int j)
   {
     this.i = i;
     this.j = j;
   }
   
   public int sum()
   {
     return i + j;
   }
}
```
### Ans :
* States of the object are i and j
* behavior : int sum() where state is used and returniing the sum of i and j
* but the returning value are not used
* Yes behaviour depends on the state

### 13) Find the output? Identify the static method & variables.
```java
public class Test
{
  static int x;
  int y;
  static{
    x = 10;
  }
  
  static{
    x = x + 20;
  }
  
  {
    y = 100;
  }
  
  {
    y = y + 20;
  }
  
  public static void main(String[] args)
  {
    Test t = null;
    t.x = t.x + 40;
    x = x + 50;
    
    t = new Test();
    t.y = t.y + 200;
    
    Test t1 = new Test();
    System.out.println(t.x)
    System.out.println(t1.x)
    System.out.println(Test.x)
    
    System.out.println(t.y)
    System.out.println(t1.y)
   
   System.out.println(t.getX());
   System.out.println(t1.getX());
   System.out.println(Test.getX());
   
   System.out.println(t.getSum());
   System.out.println(t1.getSum());
   
  }
  
  public static int getX()
  {
    return x;
  }
  
  public int getSum()
  {
    return  x + y;
  }
}
```
### Ans : 
* The O/P of the above program is as follows
* 120
* 120
* 120
* 320
* 120
* 120
* 120
* 120
* 440(x = 120 + y = 320) - for object t
* 240(x = 120 + y = 120) - for object t1
* ***Explanation***
* If a field is static then any change to the field value will update the value to the last modified value. As static does not depend on the instance of the class so for any       object the value will be the same 


### Write some code to create Null Pointer Exception 
* If we want to access a non static method with an instance of the class which is assigned to null, it will creat NullPointerException
* Below is the code that creat nullPointerException
```java
public class Test
{
      public void m1()
      {
            System.out.println("Method m1()")
      }
      public static void main(String[] args)
      {
            Test t = null;
            t.m1(); // this line creat nullPointerException
      }
}
```
