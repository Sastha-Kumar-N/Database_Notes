When a program runs, the operating system allocates memory in a structured manner to manage data, function calls, and execution flow. The diagrams in the notes mainly illustrate **how memory is organized**, **how functions are executed**, and **how recursion works internally**.

---

## 1. Program Memory Layout

A running program is divided into multiple logical memory regions:

1. **Code (Text) Segment**
    
2. **Stack Memory**
    
3. **Heap Memory**
    
4. **Static / Global Memory**
    

Each region has a specific role in execution.

---

## 2. Stack Memory (Function Execution Area)

The **stack** is used to manage **function calls**.

### Characteristics of Stack:

- Follows **LIFO (Last In, First Out)** principle
    
- Stores:
    
    - Function parameters
        
    - Local variables
        
    - Return addresses
        
- Automatically managed by the system
    

### Stack Frame Concept:

Every time a function is called:

- A **stack frame** is created
    
- It contains:
    
    - Local variables
        
    - Function arguments
        
    - Control information
        

When the function finishes:

- Its stack frame is **destroyed**
    
- Control returns to the calling function
    

This is why stack memory is **fast but limited**.

---

## 3. Heap Memory (Dynamic Allocation Area)

The **heap** is used for **dynamic memory allocation**.

### Characteristics of Heap:

- Memory is allocated at runtime (`malloc`, `new`)
    
- Not automatically freed
    
- Programmer must explicitly release memory
    
- Slower than stack but much larger
    

Heap is commonly used when:

- Data size is unknown at compile time
    
- Objects must persist beyond function calls
    

---

## 4. Function Call Flow (Normal Execution)

When functions are called sequentially:

`main() → functionA() → functionB()`

Execution flow:

1. `main()` stack frame is created
    
2. `functionA()` is called → new stack frame pushed
    
3. `functionB()` is called → another stack frame pushed
    
4. `functionB()` completes → popped from stack
    
5. `functionA()` completes → popped
    
6. Control returns to `main()`
    

This matches the **vertical stack diagrams** in your notes.

---

## 5. Recursion and Stack Growth

Recursion occurs when a function **calls itself**.

Example:

`factorial(n):     if n == 1 return 1     else return n * factorial(n-1)`

### What Happens in Memory:

- Each recursive call creates a **new stack frame**
    
- Values of `n` are stored separately
    
- Stack grows **deeper** with each call
    

### Example Stack Growth:

`factorial(5) factorial(4) factorial(3) factorial(2) factorial(1)`

Once the base condition is reached:

- Stack frames are removed one by one
    
- Results are returned in reverse order
    

This explains the **step-wise downward arrows** in your diagram.

---

## 6. Stack Overflow Concept

If recursion has:

- No proper base condition
    
- Too many nested calls
    

Then:

- Stack memory gets exhausted
    
- Leads to **stack overflow error**
    

This is why recursion must always have:

- A base case
    
- Controlled depth
    

---

## 7. Relationship Between Stack and Heap

|Stack|Heap|
|---|---|
|Stores function calls|Stores dynamic objects|
|Fast access|Slower access|
|Auto managed|Manual management|
|Limited size|Large size|

In many programs:

- Stack variables store **references/pointers**
    
- Actual data lives in the **heap**
    

---

## 8. Real-World Analogy

- **Stack** → Stack of plates  
    (Top plate used first)
    
- **Heap** → Warehouse storage  
    (Items placed and retrieved freely)
    

---

## Conclusion

The notebook diagrams collectively explain how a program executes internally using stack and heap memory. Function calls, recursion, and variable storage are managed using stack frames, while dynamic data is stored in the heap. Understanding this memory flow is crucial for writing efficient programs, avoiding stack overflow, and mastering concepts such as recursion and memory management.