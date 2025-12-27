### 1. CLOB (Character Large Object)

### Definition

CLOB is used to store **large amounts of text data**.

### Characteristics

- Stores characters (text)
    
- Used for documents, articles, XML, JSON
    
- Size can be **MBs to GBs**
    

### Example

`Description CLOB`

---

### 2. BLOB (Binary Large Object)

### Definition

BLOB stores **binary data** such as images, audio, or videos.

### Characteristics

- Stores raw binary data
    
- Database does not interpret content
    

### Example

`Photo BLOB`

---

## 5️⃣ LONG and DOUBLE-LONG Data Types

---

### LONG

- Used to store **large character strings**
    
- Older data type
    
- Limited usage in modern databases
    

### DOUBLE-LONG

- Stores **very large numeric values**
    
- Higher precision than LONG
    
- Rarely used today due to better alternatives
    

---

## 6️⃣ Summary Table (Very Exam Friendly)

|Term|Meaning|
|---|---|
|DB Block|Smallest unit of storage|
|512 Bytes|Common DB block size|
|OLTP|Real-time transaction processing|
|Nominal|Category data|
|Ordinal|Ordered data|
|Power|True zero, ratios valid|
|Range|Equal interval, no true zero|
|CLOB|Large text data|
|BLOB|Large binary data|
|LONG|Large character data|
|DOUBLE-LONG|Very large numeric data|

---

## ✅ Exam-Ready Conclusion

Database blocks define how data is physically stored, while OLTP systems focus on fast and reliable transaction handling. Data scales such as nominal and ordinal help in proper data modeling, and large object data types like CLOB and BLOB allow efficient storage of multimedia and large text data.

---

If you want, I can:

- Convert this into **5-mark / 10-mark versions**
    
- Give **diagram-based explanations**
    
- Provide **likely exam questions**
    

Just tell me 👍

pct

Here is a **clear, exam-ready explanation of PCT**, written in **simple words**, exactly how it is expected in DBMS exams.

---

# PCT (Percent Free) in DBMS

## What is PCT?

**PCT (Percent Free)** refers to the **percentage of free space reserved in a database block** for future updates of rows.

It ensures that when a row is updated and grows in size, there is **already free space available in the same block**, avoiding row migration.

---

## Why is PCT Needed?

When data is updated:

- Rows may increase in size
    
- If no free space exists in the block, the row is **moved to another block**
    
- This causes **row migration**, which reduces performance
    

👉 **PCT prevents this problem by reserving space in advance.**

---

## Example: DB Block with PCT

Assume:

- DB block size = **512 bytes**
    
- PCTFREE = **20%**
    

Calculation:

- Free space reserved = 20% of 512 = **102 bytes**
    
- Data allowed initially = **410 bytes**
    

So, only 410 bytes will be filled initially, and 102 bytes are kept free for updates.

---

## Types of PCT (Commonly Asked)

### 1️⃣ PCTFREE

- Percentage of space kept free for updates
    
- Used mainly for tables
    

### 2️⃣ PCTUSED

- Minimum percentage of block usage
    
- If usage falls below this value, block becomes reusable
    

---

## Advantages of Using PCT

- Reduces row migration
    
- Improves performance
    
- Efficient space management
    
- Important for frequently updated tables
    

---

## Where PCT is Used?

- OLTP systems (frequent updates)
    
- Tables with variable-length columns (VARCHAR, CLOB)
    
- Databases with heavy INSERT/UPDATE operations
    

---

## Exam-Ready Definition (Direct Write)

> **PCT (Percent Free)** is a database storage parameter that specifies the percentage of space in a data block reserved for future updates, helping to prevent row migration and improve performance.

---

## Short Notes Version (5 Marks)

- PCT reserves free space in DB blocks
    
- Helps avoid row migration
    
- Improves update performance
    
- Important in OLTP systems
    
- Defined during table creation
    

---

## One-Line Memory Tip

**“PCT keeps space today to avoid problems tomorrow.”**

---

If you want, I can also explain:

- **Row migration vs row chaining**
    
- **PCTFREE vs PCTUSED (with diagram)**
    
- **Numerical problems for exams**