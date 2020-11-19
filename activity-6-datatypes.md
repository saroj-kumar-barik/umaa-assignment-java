### 1) 1's complement?
***Ans***  
* To get 1’s complement of a binary number, simply invert the given number. For example, 1’s complement of binary number 0011 is 1100.  
* It's mainly used for getting the values of signed numbers in binary.  
* The Drawback of 1's complement form is we have to representations for Zero i.e +ve Zero and -ve Zero.  
* 0 = 0000 (+ve number)  
* 0 = 1111 (-ve number) which is not true  

### 2) 2's complement?
***Ans***  
* To get 2's Complement of a binary number we need the 1s compplement and then adding one to the LSB . For example, 2’s complement of binary number 0011 is (1100) + 1 = 1101.    
* It is used for signed Binary number representation and various arithmetic operations for Binary numbers.  
* The advantage of this system is that 0 has only one representation for -0 and +0. Zero (0) is considered as always positive (sign bit is 0) in 2’s complement representation. Therefore, it is unique or unambiguous representation.  
### 3) Represent whole numbers (+ve / -ve ) or float point numbers (+ve / -ve) in binary format.  
***Ans)***  
### Positive Whole Number to Binary :     
* Decimal to the Binary Conversion formula.  
* In general, decimal to any number system conversion procedure will be,  

    * 1. Take the number modulo base i.e. number % base  
    * 2. Write down the result. i.e. remainder  
    * 3. Divide the number by base i.e. number / base  
    * 4. repeat the process untill the number greater than 0. (number > 0)  

Finally, rewrite all remainders in reverse order.  

![alt image](https://circuitglobe.com/wp-content/uploads/2016/09/decimal-to-binary-conversion-example-1.jpg)

* Below is the code in java 
```java
public class Conversion {    
    public static void main(String[] args) {
        Integer a = 328;
        System.out.println(Integer.toBinaryString(a)); // 101001000  
    }
}
```

* So (25)<sub>10</sub> in binary is 11001
### Negative Whole Number to Binary :  
* The simplest way to convert a negetive number to binary is :  
    * Fisrt find the binary no of the given number in positive.
    * Then take 1's complement as discussed above
    * then add 1 to it.
![alt image](https://media.geeksforgeeks.org/wp-content/uploads/20200421181357/R-o.png)   
* Below is the code in java 
```java
public class Conversion {    
    public static void main(String[] args) {
    // java represents negetive number to binary the numbers in 32 bit format.  
        Integer a = -328;
        System.out.println(Integer.toBinaryString(a)); // 11111111111111111111111010111000  
    }
}
```
 
 ### Floating Number to Binary :  
 * A floating point number has two parts one is integral part and another one is decimal part
 * The Conversion of integral part will be the same as discussed above.
 * To convert the decimal part follow these steps :
    * To convert the fractional part to binary, multiply fractional part with 2 and take the one bit which appears before the decimal point.  
    * Follow the same procedure until it becomes 1.0.
 ![alt image](https://i.ytimg.com/vi/kWLv0xnNd60/maxresdefault.jpg)    
 * So the binary of 40.15625 is 10100.00101  
 * there is no direct conversion method in java to convert a float number to binary number. 
 
 ### 4) Convert between primtiive type and wrapper types.  
 ***Ans***  
Primitive Types  | Wrapper Types
-----------------|---------------
int              |    Integer
char             |    Character  
float            |    Float
double           |    Double
short            |    Short
long             |    Long
boolean          |    Boolean
byte             |    Byte
 
* Wrapper{data types} provide more flexibility as these are the classes, so that these classes have inbuilt methods which provides more grip over the normal data types
#### CONVERSION
```java
public class autoboxingAndUnboxing {    
    public static void main(String[] args) {
        // auto-boxing
        // conversion of primitive to wrapper types
        char a = 'a';
        Character c = a;
        System.out.println(c); // output - a
        
        // un-boxing
        // conversion of wrapper type to primitive types
        char c1 = c.charValue();
        System.out.println(c1); // output - a
    }
}
```

### 5) convert string (decimal value) to long, int, short, byte.  
***Sol***
```java
public class Conversion {    
    public static void main(String[] args) {
         String str = "100";

        long l = Long.parseLong(str);
        System.out.println(Long.parseLong(str));

        int i = Integer.parseInt(str);
        System.out.println(Integer.parseInt(str));

        short s = Short.parseShort(str);
        System.out.println(Short.parseShort(str));

        byte b = Byte.parseByte(str);
        System.out.println(Byte.parseByte(str));
    }
}
```

### 6) Understand the wrapper class hierachy. Explain the wrapper child classes for Number class.
* Except Short and Boolean Wrapper class all other Wrapper classes Extends the Number Class which is an abstract class and implements Comparable<>  
* The Character Wrapper class implements java.io.Serializable, Comparable<Character>   
* The Boolean Wrapper class implements java.io.Serializable,Comparable<Boolean>   
* The wrapper child classes of Number abstarct class are : Byte, Short, Integer, Double, Float, Long  
* except this there are 4 other classes namely : "BigDecimal" and "BigInteger" are used for high-precision calculations. "AtomicInteger" and "AtomicLong" are used for multi-threaded applications.   
 ![alt image](https://docs.oracle.com/javase/tutorial/figures/java/objects-numberHierarchy.gif)     

 ### 7) Define auto boxing & auto unboxing with example.  
 ***Ans***
 ```java
public class autoboxingAndUnboxing {    
    public static void main(String[] args) {
        // auto-boxing
        // conversion of primitive to wrapper types
        char a = 'a';
        Character c = a;
        System.out.println(c); // output - a
        
        // un-boxing
        // conversion of wrapper type to primitive types
        char c1 = c.charValue();
        System.out.println(c1); // output - a
    }
}
```
### 8) Convert a string ("105") to integer. and print the doubleValue(), longValue(), byteValue(), floatValue(), shortValue(), toString() 
 ***Ans***
 ```java
public class NumberClassDemo {    
    public static void main(String[] args) {
       String str = "105";
        // to use  doubleValue(), longValue(), byteValue(), floatValue(), shortValue(), toString() methods
        // we need Number class.
        
        Number n = Integer.parseInt(str);

        System.out.println(n.toString());     // 105
        System.out.println(n.doubleValue());  // 105.0
        System.out.println(n.longValue());    // 105
        System.out.println(n.shortValue());   // 105
        System.out.println(n.byteValue());    // 105
        System.out.println(n.floatValue());   // 105.0
        System.out.println(n.intValue());     // 105

    }
}
``` 

### 9) Mention the fully qualified name of each wrapper class.
***Ans*** 
* for Numbers : java.lang.Number  
* for CHaracter : java.lang.Character  
* for Booleand : java .lang.Boolean  

### 10) Write the class definition for all wrapper class types. Find out the abstract methods peresent in the implemented interface. (Ex: public final class Float extends Number implements Comparable, Comparable: public int compareTo(T o); ).
***Ans***
#### Class Definition : 
* Byte : public final class Byte extends Number implements Comparable<Byte>, Constable, ConstantDesc  
* Short : public final class Short extends Number implements Comparable<Short>, Constable, ConstantDesc  
* Integer : public final class Integer extends Number implements Comparable<Integer>, Constable, ConstantDesc  
* Long : public final class Long extends Number implements Comparable<Long>, Constable, ConstantDesc  
* Float : public final class Float extends Number implements Comparable<Float>, Constable, ConstantDesc  
* Double : public final class Double extends Number implements Comparable<Double>, Constable, ConstantDesc  
* Character : public final class Character implements java.io.Serializable, Comparable<Character>  
* Boolean : public final class Boolean implements java.io.Serializable,Comparable<Boolean>  
 
