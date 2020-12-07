# ARRAYS, CUSTOM TYPES, CODING

## ARRAYS 
### 1) Traverse an 1d array using while loop.  
```java
public class ArrayTraversalUsingWhileLoop {
    public static void main(String[] args) {
        int[] arr = {11,22,33,44,55};
        int i = 0;
        while (i < arr.length)
        {
            System.out.println(arr[i]);
            i++;
        }
    }
}
```

***OutPut***  
11  
22  
33  
44  
55  

### 2) Traverse a 2d array using column major or row major.
```java

```


***OutPut***

### 3) Print a 2d array using toString().  
```java

```

***OutPut***

### 4) For a 2d array of dimesnion 3 * 4. arr.length will give 3 or 4?
```java

```

***OutPut***

### 5) In a 2d array of size 3 * 3. convert a given index say 5 into i,j format. Access the element.  
```java

```


***OutPut***


### 6) use equals method for comparing 2 1d arrays having same or different content.   
```java

```

***OutPut***

### 7) use deepEquals method for comparing 2 2d(or multidimensional) arrays having same or different content.  
```java

```


***OutPut***

### 8)Traverse a 2d array using forEach loop along with for index loop.  
```java

```

***OutPut***

### 9) int[][] arr = new int[3][4]; Try to iterate this 2d array with below data.  
```java
arr[0] = {1,2,3,4,5,6}; // is this valid? 
arr[1] = {1,2,3}; // is this valid? 
arr[2] = {1,2,3,4,5,6, 7}; // is this valid? 
```

***OutPut***

### 10) What is ArrayIndexOutOfBoundsException. Who is the parent class of ArrayIndexOutOfBoundsException.
```java

```


***OutPut**


## CUSTOM TYPES  

### 1) Design a Person class. Where his address is has-a relationship.  

### 2) Display Person & Adrress has-relationshop using toString(). It must display content of object.  

### 3) Assume you have Person (where each person has an address) array. Display Person[] using toString(). It must display content of object.  

### 4) Design a class called Person and Doctor. It must say Doctor is a Person.  

### 5) Does has-a relationship represents composition?  

### 6) How many types of compositions are available.  

## CODING (Write with Junit)

### 1) Given a character array. Reverse it using custom logic.  

### 2) Given a integer sorted array. Search an element in the array. If element not found return -1 and if found then return index of the element.  

### 3) Given below 2 sorted arrays. Transform them.  


```java
input:
int[] arr1 = {2, 10, 12, 14, 16, 18}
int[] arr2 = {13, 17, 21}
output:
arr1 = {2, 10, 12, 13, 14, 16}
arr2 = {17, 18, 21}
```

### 4) Given a sorted matrix of size 3 * 3. Print the position of an element. If not found return -1.  

```java
{ 
  {1, 5, 7},
  {8, 13, 15},
  {17, 19, 21}
}
```

### 5) Without using recursion print the first 10 numbers of fibonaci series.  

### 6) Implment selection sort.

### 7) Given an integer unsorted array. sort it without using any sorting logic. But you are allowed to swap any element with first element of the array.  

### 8) Given an integer almost sorted array which can be sorted exactly with one swap (no bubble sort).  
```java
int[] arr1 = {2, 4, 5, 9, 13, 11, 12, 10, 14, 17}.
```

### 9) Given a string below. Make the initial of each word upper case. custom logic.  

```java
String s = "utkal university odisha"

/**
output: "Utkal University Odisha"
*/
```

### 10) Given a string below. Reverse each word below. custom logic. (dont reverse the complete string).  
```java
String s = "utkal university odisha"

/**
output: "reverse Utkal reverse University reverse odisha"
*/
```

### 11) Given an employee class below. Create Array of employees. Apply sorting by name (comparator). Apply sort by name when age is same (comparator).  
```java
public class Employee
{
   private Integer id;
   private String name;
   private Integer age;

   // getter & setter
}
```

### 12) For above class and array. Apply sort by reverse order of name when age is same (comparable)  

### 13) In an excel spread sheet. A = 1, Z = 26, AA = 27, AB = 28. Implement below methods.  

```java
public static int convertToInt(String shellAsStr) // input can be A, Z, AA, AB
{
  return 0;
}

public static String convertToString(Integer shellAsInt) // input can be any integer
{
  return null;
}
```
