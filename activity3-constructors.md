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
