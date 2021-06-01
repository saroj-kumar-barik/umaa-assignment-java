@rkpatra201 solutions to the above : 
* CREATE ITEM TABLE WITH COLUMNS AS ID,NAME,UNIT_PRICE,PRODUCT_SKU_ID, CATEGORY,BRAND. ID IS PRIMARY KEY WITH AUTO INCREMENT, PRODUCT_SKU_ID IS UNIQUE KEY.
```sql
CREATE TABLE ITEM_TBL(
ID INT PRIMARY KEY AUTO_INCREMENT,
NAME VARCHAR(30) NOT NULL,
UNIT_PRICE DOUBLE NOT NULL,
PRODUCT_SKU_ID VARCHAR(30) NOT NULL UNIQUE,
CATEGORY VARCHAR(20) NOT NULL,
BRAND VARCHAR(20) NOT NULL
);
```

* INSERT SOME DATA TO ABOVE TABLE. CATEGORY CAN BE SHOES, JEANS, TOPS. BRANDS CAN BE PUMA, LEVIS, ADIDAS.
```sql
INSERT INTO ITEM_TBL VALUE
(1,'iid-1',29.30,'sku-id-1','shoe','nike'),
(2,'iid-2',29.31,'sku-id-2','jeans','being-human'),
(3,'iid-3',29.31,'sku-id-3','tops','w');
```
* CREATE USER TABLE WITH ID, USER_EMAIL, FIRST_NAME, MOBILE. ID IS PRIMARY KEY WITH AUTO INCREMENT, USER_EMAIL IS UNIQUE.
```sql
CREATE TABLE USER_TBL(
ID INT PRIMARY KEY AUTO_INCREMENT,
USER_EMAIL VARCHAR(30) NOT NULL UNIQUE,
FIRST_NAME VARCHAR(20) NOT NULL,
MOBILE NUMERIC(10) NOT NULL
);
```
* INSERT SOME DATA TO ABOVE TABLE.
```sql
INSERT INTO USER_TBL VALUE
(1,'abc@mail.com','bablu',8249550714),
(3,'abcd@mail.com','bablu1',8249550114),
(2,'abcf@mail.com','bablu2',8249950114),
(4,'abce@mail.com','bablu3',8149540114);
```


* CREATE CART TABLE WITH ID OF USER TABLE AS USER_ID, ID OF ITEM TABLE AS ITEM_ID, QUANTITY. THE USER_ID COLUMN OF CART TABLE IS A FOREIGN_KEY TOWARDS USER TABLE. THE ITEM_ID OF CART TABLE IS A FOREIGN KEY TO ITEM TABLE.


```sql
CREATE TABLE CART_TBL(
USER_ID INT NOT NULL,
FOREIGN KEY(USER_ID) REFERENCES  USER_TBL(ID),
ITEM_ID INT NOT NULL,
FOREIGN KEY(ITEM_ID) REFERENCES  ITEM_TBL(ID),
QUANTITY INT NOT NULL
);
```
* INSERT SOME DATA TO ABOVE TABLE. 
```sql
INSERT INTO CART_TBL VALUE
(1,1,10),
(3,2,5),
(4,3,3),
(4,3,3),
(2,3,4),
(4,3,7)
(4,2,7),
(1,1,10),
(1,3,10),
(1,2,10),
(3,2,5),
(4,3,3),
(2,3,4),
(4,2,7);
```



# SQL QUERIES:  
* DISPLAY ITEMS BY BRAND.
 ```sql
SELECT CATEGORY,BRAND FROM ITEM_TBL;
 ```
* FIND THE ITEMS ADDED TO THE CART FOR A GIVEN USER BY EMAIL.
 ```sql
SELECT * FROM ITEM_TBL WHERE ID IN
(SELECT ITEM_ID FROM CART_TBL WHERE USER_ID =
(SELECT ID FROM USER_TBL WHERE USER_EMAIL= 'abcf@mail.com'));
 ```
* DISPLAY THE TOTAL PRICE OF CART FOR A GIVEN USER.
 ```sql
SELECT (CART_TBL.QUANTITY * ITEM_TBL.UNIT_PRICE)
FROM CART_TBL INNER JOIN ITEM_TBL
ON CART_TBL.ITEM_ID = ITEM_TBL.ID
WHERE USER_ID IN
(SELECT USER_ID FROM CART_TBL WHERE USER_ID =
(SELECT ID FROM USER_TBL WHERE USER_EMAIL= 'abcf@mail.com'));
 ```
* DESIGN ER DIAGRAM FOR ABOVE USE CASE.
