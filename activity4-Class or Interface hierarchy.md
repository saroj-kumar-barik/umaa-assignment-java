## 1) LinkedList (C)
***Extends :*** AbstractSequentialList (AC)  
***Implements :*** List<E> (I), Deque<E> (I), Cloneable (I), java.io.Serializable (I)  

### * AbstractSequentialList: (ac)  
***Extends:*** AbstractList (ac)    

### * AbstrcatList: (ac)
***Extends:*** AbstractCollection (ac)  
***Implemnets:*** List (I)  

### * AbstractCollection (ac)  
***Implements:*** Collection (I)  

### * Collection(I)  
***Extends:*** Iterable(I)  

## Abstract Methods of above abstract classes : 

1. AbstractSequentialList  
   1. listIterator(int index);   
2. AbstrcatList    
   1.  get(int index);  
3. AbstractCollection  
   1. int size();  
   2. Iterator<E> iterator();  

## 2) ArrayList(C)  
***Extends :*** AbstractList (AC)  
***Implements :*** List<E>, RandomAccess, Cloneable, java.io.Serializable  
  
### * AbstractList: (ac)   
***Extends :*** AbstractCollection (AC)  
***Implements :*** List(I)

### * AbstractCollection: (ac)
***Implements :*** Collection(I)

### * Collection(I)  
***Extends:*** Iterable(I) 

## Abstract Methods of above abstract classes : 

1. AbstractList  
   1. get(int index);   
2. AbstractCollection    
   1.  int size();  
   2. Iterator<E> iterator(); 
   
   
## 3) Stackt (C)
***Extends :*** Vector

### * Vector: (C)  
***Extends:*** AbstractList (ac)    
***Implemnets:*** List<E>, RandomAccess, Cloneable, java.io.Serializable  

### * AbstractList: (ac)   
***Extends :*** AbstractCollection (AC)  
***Implements :*** List(I)

### * AbstractCollection: (ac)
***Implements :*** Collection(I)

### * Collection(I)  
***Extends:*** Iterable(I) 

## Abstract Methods of above abstract classes : 
1. AbstractList  
   1. get(int index);   


## 4) ArrayBlockingQueue (C)

***Extends :*** AbstractQueue (ac)  
***Implemnets:*** BlockingQueue<E>, java.io.Serializable  

### * AbstractQueue: (ac)  
***Extends:*** AbstractCollection (ac)    
***Implemnets:*** List

### * AbstractCollection: (ac)   
***Extends :*** AbstractCollection (AC)  
***Implements :*** List(I)

### * AbstractCollection: (ac)
***Implements :*** Collection(I) 

### * Collection(I)  
***Extends:*** Iterable(I) 

## Abstract Methods of above abstract classes : 

1. AbstractQueue  
   1. No abstract methods
2. AbstractCollection  
   1. int size();  
   2. Iterator<E> iterator(); 

## 5) LinkedBlockingQueue (C)  
***Extends :*** AbstractQueue (ac)  
***Implemnets:*** BlockingQueue<E>, java.io.Serializable  

### * AbstractQueue: (ac)  
***Extends:*** AbstractCollection (ac)    
***Implemnets:*** List(I)

### * AbstractCollection: (ac)   
***Extends :*** AbstractCollection (AC)  
***Implements :*** List(I)

### * AbstractCollection: (ac)
***Implements :*** Collection(I) 

### * Collection(I)  
***Extends:*** Iterable(I) 

## Abstract Methods of above abstract classes : 

1. AbstractQueue  
   1. No abstract methods
2. AbstractCollection  
   1. int size();  
   2. Iterator<E> iterator(); 
