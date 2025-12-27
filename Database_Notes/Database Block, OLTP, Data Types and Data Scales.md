### What is a Database Block?

A **database block** is the **smallest unit of data storage and I/O** in a database.  
Whenever a database reads or writes data to disk, it does so **block by block**, not row by row.

### DB Block Size – 512 Bytes

- A **DB block of 512 bytes** means:
    
    - Data is stored and transferred in chunks of **512 bytes**
        
    - Smaller block size → more blocks → more I/O operations
        
- Typical block sizes can be 512 bytes, 1 KB, 2 KB, 4 KB, etc.
    

### Why DB Block is Important?

- Determines **storage efficiency**
    
- Affects **performance**
    
- Indexes and tables are stored using blocks
    

### Example

If a table row is 200 bytes, multiple rows can fit into one 512-byte block.

## Types of Data Scales (Measurement Levels)

These describe **how data values are measured and compared**.

---

### 1. Nominal Scale

- Data is **named categories**
    
- No order or ranking
    

#### Examples:

- Gender: Male, Female
    
- Blood group: A, B, AB, O
    
- Department names
    

👉 Only equality (=, ≠) comparisons possible

---

### 2. Ordinal Scale

- Data has **order or ranking**
    
- Differences between values are **not measurable**
    

#### Examples:

- Grades: A, B, C
    
- Satisfaction: Low, Medium, High
    
- Rank: 1st, 2nd, 3rd
    

👉 Order matters, but not the exact difference

---

### 3. Power (Ratio) Scale

- Has **order + exact difference + true zero**
    
- All mathematical operations possible
    

#### Examples:

- Salary
    
- Age
    
- Weight
    

👉 Zero means absence of quantity

---

### 4. Range (Interval) Scale

- Ordered values with equal intervals
    
- **No true zero**
    

#### Examples:

- Temperature (°C, °F)
    
- Calendar dates
    

👉 Difference meaningful, ratio not meaningful