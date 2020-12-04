### 1) Write a simple example of a Product class where it uses this constructor with paremeterized constructor.
***Solution***
```java
public class Product{
    private String carModel;
    private int gear;
    private int topSpeed;

    public Product(String carModel, int gear, int topSpeed) {// parameterized constructor
        this(carModel); // invoking constructor using this.
        this.gear = gear;
        this.topSpeed = topSpeed;
    }

    public Product(String carModel) { // one param constructor
        this.carModel = carModel;
    }

    @Override
    public String toString() {
        return "Product{" +
                "carModel='" + carModel + '\'' +
                ", gear=" + gear +
                ", topSpeed=" + topSpeed +
                '}';
    }

    public static void main(String[] args) {
        Product product = new product("mercedise Benz 330d",6,300);
        System.out.println("after initializing the fields...");
        String result = product.toString();
        System.out.println(result);
    }
}
```

### 2) Does toString() method present in java.lang.Object class? If yes what the implementaion for toString() method given by java.lang.Object class.
***Ans***
* Yes, the toString() is present in java.lang.Object class
* The toString() method returns the string representation of the object
* By overriding toString(), we can get the desired output, such as states of an object.
* By applying toString() on an object of a class, it will retuen the fully qualified class name and hexadecimal representation of hashCode separated by a @ symbol of the object.

### 3) Override toString() method in the class A (as given below) such that it will print the value of i, j, k.
```java
public class Test {
    public static void main(String[] args) {
        A a = new A(10, 20);
        a.setK(400);
        System.out.println(a);
    }
}

class A {
    private int i;
    private int j;
    private int k;

    public A(int i, int j) {
        this.i = i;
        this.j = j;
    }

    public int getI() {
        return i;
    }

    public void setI(int i) {
        this.i = i;
    }

    public int getJ() {
        return j;
    }

    public void setJ(int j) {
        this.j = j;
    }

    public int getK() {
        return k;
    }

    public void setK(int k) {
        this.k = k;
    }
}
```

***Solution***
* Below is the code that shows the use of toString() so that it will print the values of i, j, k.
```java
public class Test {
    public static void main(String[] args) {
        A a = new A(10, 20);
        a.setK(400);
        System.out.println(a);
    }
}

class A {
    private int i;
    private int j;
    private int k;

    public A(int i, int j) {
        this.i = i;
        this.j = j;
    }

    public int getI() {
        return i;
    }

    public void setI(int i) {
        this.i = i;
    }

    public int getJ() {
        return j;
    }

    public void setJ(int j) {
        this.j = j;
    }

    public int getK() {
        return k;
    }

    public void setK(int k) {
        this.k = k;
    }

    @Override
    public String toString() {
        return "A{" +
                "i=" + i +
                ", j=" + j +
                ", k=" + k +
                '}';
    }
}
```

### 4) What is StackOverflowError. When it occurs. It comes under which package in java library.
***Solution***
* StackOverflowError id a run time error in java.
* It arrises due to recursive function call, that finally leads to an infinity loop and finally JVM goes out of memory for the program.
* This usually happens if we do not put a terminating code to the recursive funtion call.
* It comes under the library : java.lang.StackOverflowError

### 5) Will the below code compile? Find the output of the below code.
```java
public class Test {
    public static void main(String[] args) {
        A a = new A();
    }
}

class A
{
    private int x =11;
    public A()
    {
        new A(10);
    }

    public A(int x)
    {
        this();
        this.x = x;
    }
}
```

***Ans***
* Yes, the above code will compile fine.
* But it will throw RunTime error : java.lang.StackOverflowError
* It happens because of the statement new A(10); calls the parameterized constructor and again the this(); inside parameterized constructor will invoke again the no argument constructor, and hence finally fall in a recursive infinity loop.

### 6) Will the below code compile. If not why?
```java
class A
{
    private int x =11;
    public A()
    {
        this(10);
    }

    public A(int x)
    {
        this();
        this.x = x;
    }
}
```

***Ans***
* No, this time the code will not compile, it will show compile time error of Recursive Constructor Invokation
* Here a compile time error occurs as we are invokinng constructor using this(), which will refer to the same object & same object calling to the constructor, but in case of the above case the new keyword would creat new object each time for invoking the constructor, so that program will go out of memory of JVM where as this program will throe compile time error.

### 7) Find the output with explanation.
```java
public class Test {
    public static void main(String[] args) {
        A a = new A();
    }
}

class A
{
    private int x =11;
    public A()
    {
        this(10);
        if(x % 2 == 0)
        {
            System.out.println("even");
        }
        else
        {
            System.out.println("odd");
        }
    }
    
    public A(int x)
    {
        this.x = x;
    }
}
```
***Output***
even  
#### Explanation :
* The statement this(10); will invoke the parameterized constructore and inside that the value of x will be updated to 10 and 10%2 will be equal to zero, giving output as even.

### 8) Will the below code compile?
```java
class A
{
    public A()
    {
        new A();
    }
}
```
***Ans***
* On callinng the constructor, yes the code will compile but creat the error : StackOverflowError(Already explained above)

### 9) Why the below code won't compile?
```java
class A
{
    public A()
    {
        this();
    }
}
```
***Ans***
* This code will show compile time error : recurrsive contructor invokation

### 10) ind the output with explanation?
```java
public class Test {
    public static void main(String[] args) {
        A a = new A();
        System.out.println(a.hashValue == a.hashCode());
    }
}

class A
{
    public int i;
    public int hashValue;
    public A()
    {
        new A(10);
    }

    public A(int x)
    {
        this.i = x;
        this.hashValue = this.hashCode();
    }
}
```
***Output***
false  
#### Explanation  
* inside class Test, we have created an object and assigned to an instance "a". So the call to constructor with no param will be happen.
* But inside the no param constructor we have invoked the one param constructor using new keyword not by this. So inside one param constructor the this will refer to the newly created object not the "a" instance and hence value of hashvalue will be updated for the new object only.
* So, the a.hasvalue gives the default integer value as 0 and a.hashCode() will produce the memory location whill will never be 0. Hence output is commming as false.

### 11) Find the output with explanation?
```java
public class Test {
    public static void main(String[] args) {
        A a = new A();
        System.out.println(a.hashValue == a.hashCode());
    }
}

class A
{
    public int i;
    public int hashValue;
    public A()
    {
        this(10);
    }
    
    public A(int x)
    {
        this.i = x;
        this.hashValue = this.hashCode();
    }
}
```
***Output***
true  
#### Explanation  
* As already explained above, invoking one param constructor will also update the value for object "a" hence the value of hashvalue and hashCode() will be same.

### 12) Access Modifiers & Packages. Find the compilation errors & why? Find the output also by fixing them.
```java
package com.pkg1;

class A
{
  private int i = 10;
  public int j = 100;
  int k = 50;
}

package com.pkg1;
class B
{
  public static void main(String[] args)
  {
    A a = new A();
	System.out.println(a.i);
	System.out.println(a.j);
	System.out.println(a.k); // why this is accessible?
  }
}

package com.pkg2;
class B
{
  public static void main(String[] args)
  {
    A a = new A();
	System.out.println(a.i);
	System.out.println(a.j);
	System.out.println(a.k); // why this is not accessible?
  }
}
```
#### Errors :  

***Inside same package (com.pkg1)  
inside same class :***
private, public, protected, default acces modiferes are accessible  
***Inside same package (com.pkg1)  
different class:***
 public, protected, default acces modiferes are asscesable but private not accessible.  
 
 
 ***Different package (com.pkg1)***
 Only public access modifier is accesable  
 
 Hence for com.pkg1 : inside class B the public and default field is accesible but the private one is not accessible.
 #### Solution to the error
 * We can define a getter for the private field and access the value using the instance of class A. the `code()` is given below  
 ```java
 package com.pkg1;

public class B {
    public static void main(String[] args) {
        A a = new A();
//        System.out.println(a.i); // private access so not accessible
        System.out.println(a.getI()); // definig a public getter
        System.out.println(a.j);
        System.out.println(a.l);
        System.out.println(a.k); // why this is accessible?
    }
}
```

***Errors for com.pkg2 :***
* Only sout(a.j); is accessible  
* Other two have private and default access so these can't be accessible  
#### Solution to the error  
* We have to import the package com.pkg1; and also need getters inside  class A of pkg1 to access the field. The code is as follows
```java
package org.com.pkg2;
import org.com.pkg1.*; // importing pacjage
public class B {
    public static void main(String[] args) {
        A a = new A();
        System.out.println(a.i);
        System.out.println(a.getI()); // using getters
        System.out.println(a.getK()); // using getters
        System.out.println(a.j);
//        System.out.println(a.k); // default modifiers not accessible
    }
}
```
### 13) Why we use getters and setters for a class. Give an example.

***Ans***  
* Getters are used to get the field values.  
* Setters are used to set/initialize the field values.  
***Example***
```java
import java.util.Scanner;
class Student {
    private String name;
    private int age;
    public int getAge() {
        return age;
    }
    public void setAge(int age) {
        this.age = age;
    }
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    public void display() {
        System.out.println("name: "+getName());
        System.out.println("age: "+getAge());
    }
}
public class Test{
    public static void main(String args[]) {
        //Reading values from user
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the name of the student: ");
        String name = sc.nextLine();
        System.out.println("Enter the age of the student: ");
        int age = sc.nextInt();
        //Calling the setter and getter methods
        Student obj = new Student();
        obj.setName(name);
        obj.setAge(age);
        obj.display();
    }
}
```

### 14) Why it is good to have private fields with public getters & setters?

***Ans***
* The priate fields are not accessible to a different class. 
* To solve the above problem we need a public method inside the same class to set the value to that private field and return the value.
* So inorder to set and return the value we need getters and setters.
* A field with priveate access modifiers is always recomended.





