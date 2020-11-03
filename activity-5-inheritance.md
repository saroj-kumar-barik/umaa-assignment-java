### 1) Code example of inheritance. Reuse static/non-static method(s) & static/non-static variable(s).  
```java
public  class Test1 {

    public static void main(String[] args) {
        Parent p1 = new Child();

        System.out.println(p1.var1); // parent
        p1.m1();  // child
        Parent.m2(); // parent
        Child.m2(); // child

        Child c1 = new Child();
        System.out.println(c1.var1); // child
        c1.m1(); // child
    }

    public static class Parent {
        int var1 = getVar1();
        static int var2 = getVar2();

        public void m1() {
            System.out.println("methods inside parent, m1()");
        }

        public static void m2() {
            // static methods are inherited, but not overridden
            System.out.println("static method inside parent, m2()");
        }

        public  int getVar1(){
            System.out.println("non-static variable ");
            return 100;
        }

        public static int getVar2(){
            System.out.println("non-static variable ");
            return 1000;
        }

    }

    public static class Child extends Parent {
        // variable hiding
        int var1 =  getVar2();
        static int var2 = getVar2();

        public void m1() {
            // m1() is overridden in child class
            System.out.println("method inside child, m1()");
        }

        public static void m2() {
            // hiding parent class static method m2()
            System.out.println("static method inside child, m2()");
        }

        public  int getVar1(){
            System.out.println("non-static variable ");
            return 200;
        }

        public static int getVar2(){
            System.out.println("non-static variable ");
            return 2000;
        }

    }
}

```
### 2) Code example of instance of operator using classes as BaseParent->Parent->Child.   
```java
// Multiple inheritance
public class Test2 {
    public static void main(String[] args) {
        BaseParent baseParent = new Child("India","Odisha","Kendrapara");
        // instance of operator compare an instanceVariable with Class/Subclass/interface
        System.out.println(baseParent instanceof BaseParent);
        System.out.println(baseParent instanceof Parent);
        System.out.println(baseParent instanceof Child);

        System.out.println(baseParent.getCountryName());
        baseParent = new Parent("India","Odisha");
        System.out.println(baseParent instanceof BaseParent);
        System.out.println(baseParent instanceof Parent);
        System.out.println(baseParent instanceof Child);

        Child child = new Child("India","Odisha","Kendrapara");
        System.out.println(child.getCountryName());
        System.out.println(child.getStateName());
        System.out.println(child.getDistrictName());

    }

    public static class BaseParent{
        public String countryName;

        public BaseParent(String countryName) {
            this.countryName = countryName;
        }

        public String getCountryName() {
            return countryName;
        }
    }

    public static class Parent extends BaseParent{
        public String stateName;

        public Parent(String countryName, String stateName) {
            super(countryName);
            this.stateName = stateName;
        }

        public String getStateName() {
            return stateName;
        }
    }

    public static class Child extends Parent{
        public String districtName;

        public Child(String countryName, String stateName, String districtName) {
            super(countryName, stateName);
            this.districtName = districtName;
        }

        public String getDistrictName() {
            return districtName;
        }
    }
}

```

### 3) Code example of super constructor.   
```java
public class Test3 {
    private static void main(String[] args) {
        Parent p = new Child();
    }

    private static class Parent{
        public Parent() {
            System.out.println("constructor parent..");

        }
    }

    private static class Child extends Parent{
        public Child() {
//            super(); // this call is made automatically
            System.out.println("constructor child..");
        }
    }
}

```

### 4) Does multiple object created in inheritance hierarchy.   

* No, Multiple objects are not created in inheritance from Child to parent.  
* A single object is created throug out.  

### 5) Does super constructor invocation creates one more object.   
* No, when super() calls the parent constructor, smae object is used. No new  object is created.

### 6) Code example of method hiding.  
```java
public class Test4 {
    public static void main(String[] args) {
        Parent p = new Child();
        p.m1();
        Child c = new Child();
        c.m1();
    }

    private static class Parent{
        public static void m1(){
            System.out.println("static method : parent,m1()");
        }
    }

    private static class Child extends Parent{
        // method hiding
        public static void m1(){
            System.out.println("static method : child,m1()");
        }
    }
}
```

### 7) Code example of variable hiding.  
```java
public class Test5 {
    public static void main(String[] args) {
        Parent p = new Child();
        System.out.println(p.i); // access parent 
        
        Child c = new Child();
        System.out.println(c.i); // access child
    }
    public static class Parent{
        public  int i= 10 ;
    }

    public static class Child extends Parent{
        
        // the variable "i" is hidden in child class
        public int i = 100;
    }
}
```

### 8) Does static methods overridden.  
* No, static method does not override, it's inherited. 

### 9) Deos private methods overriden. 
* No

### 10) By default any class extends which class.  
* Object

### 11) List down the public/protected (inherited) methods present in java.lag.Object class.   

***protected methods:***  
*  Object clone()  
*  void finalize() 


***public methods:***  


* boolean equals(Object obj)
* native Class<?> getClass();
* int hashCode();
* void notify();
* native void notifyAll();
* String toString()
* void wait()
* void wait(long)
* void wait(long,int)

### 12) Find the output:  
```java
class A
{
  public int i = 10;
  public int j = 20;
}
class B extends A
{
   public int i = 100;
   public int sumValue(int x)
   {
      return x + this.i + this.j +  super.i + super.j;
   }
}

class Test
{
  public static void main(String[] args)
  {
    A a = new B();
    int result = a.sumValue(a.i);
    System.out.println(result);
  }

}
```
* Compilation Error : a.sumValue(a.i) is not present in A   

***FIX-1***  

// Adding sumValue() to class A  
// in this case the sumValue() will be overriden  
// a.sumValue() will give the output of child class overridden method  
```java
class A {
    public int i = 10;
    public int j = 20;

    public int sumValue(int x) {
        return x + this.i + this.j;
    }

}

class B extends A {
    public int i = 100;

    public int sumValue(int x) {
        return x + this.i + this.j+ super.i + super.j;
    }
}

class Test {
    public static void main(String[] args) {
        A a = new B();
        int result = a.sumValue(a.i);
        System.out.println(result);
    }
}
```
***Output***    

* 160    

***FIX-2***  


```java
// typecasting a.sumValue() to ((B) a)).sumValue
public class Test6 {
    static class A {
        public int i = 10;
        public int j = 20;
    }

    static class B extends A {
        public int i = 100;

        public int sumValue(int x) {
            return x + this.i + this.j + super.i + super.j;
        }
    }

    static class Test {
        public static void main(String[] args) {
            A a = new B();
            int result = ((B) a).sumValue(a.i);
            System.out.println(result);
        }
    }
}
```
***Output***  

* 160  


### 13) Fix the code with all the approaches you know.    
```java
class A
{
  private int i;
  public A(int i)
  {
     this.i = i;
  }
}

class B extends A
{
   public B()
   {
   
   }
}
```
* Compilation Error : there is no default constructor in parent class A  
***FIX-1***    
```java
// adding default constructor to A  
class A
{
    private int i;
    public A(int i)
    {
        this.i = i;
    }

    public A() {
    }
}

class B extends A
{
    public B()
    {

    }
}
```

***FIX-2***  


```java
// passing a value inside super() of the type integer
class A
{
    private int i;
    public A(int i)
    {
        this.i = i;
    }

//    public A() {
//    }
}

class B extends A
{
    public B()
    {
        super(10);
    }
}
```



