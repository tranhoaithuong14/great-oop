### **Entity Abstractions and the Contract Model**

#### **Entity Abstractions**
Entity abstractions are the **foundation of object-oriented design** because they mirror the vocabulary and concepts of the problem domain. By focusing on these abstractions, developers can create software systems that are intuitive and closely aligned with the real-world entities they represent.

---

### **Key Concepts**

1. **Client-Server Relationship**:
   - A **client** is any object that uses the resources or services of another object, called the **server**.
   - Example:
     - A `Customer` object (client) interacts with a `BankAccount` object (server) to perform operations like `deposit()` or `withdraw()`.

2. **Contract Model of Programming**:
   - Introduced by **Meyer**, the **contract model** formalizes the interaction between objects by defining a **contract** that specifies:
     1. The **services** an object provides (its responsibilities).
     2. The **expectations** it has for other objects.
   - The contract is the **public interface** of the server object and is made up of:
     - **Operations**: Methods the client can invoke.
     - **Preconditions**: Assumptions that must be satisfied before an operation is called.
     - **Postconditions**: Guarantees provided after the operation is executed.

   - **Violating the Contract**:
     - If a **precondition** is violated, the client is at fault (e.g., attempting to withdraw more money than the account balance allows).
     - If a **postcondition** is violated, the server is at fault (e.g., the balance does not update correctly after a deposit).

3. **Protocol**:
   - The **protocol** of an object includes all the operations the client can invoke and the sequence in which they may be called.
   - **Example**:
     - For a `Printer` object:
       - The protocol may specify that you must call `loadPaper()` before `printDocument()`.

4. **Invariants**:
   - **Invariants** are conditions that must always hold true for an object to maintain its integrity.
   - Example:
     - For a `BankAccount`, the balance must always be greater than or equal to zero.
   - **Preconditions**:
     - Define what must be true before an operation is called.
   - **Postconditions**:
     - Define what must be true after an operation is executed.

5. **Exceptions**:
   - Exceptions occur when an invariant cannot be maintained. For example:
     - A `BankAccount` might throw an exception if `withdraw(amount)` is called with an amount greater than the balance.
   - Languages like Java and Python allow exceptions to be thrown and caught to handle such issues gracefully.

---

### **Static vs. Dynamic Properties**

1. **Static Properties**:
   - Characteristics of an object that define its identity and structure.
   - Example:
     - A `File` object has static properties like:
       - Name
       - Size
       - Location on disk

2. **Dynamic Properties**:
   - Attributes that change over time during the object’s lifetime.
   - Example:
     - The size and contents of a `File` object may grow or shrink, and its name might change.

---

### **Behavior of Objects**

1. **Object-Oriented Programming (OOP)**:
   - In OOP, behavior is defined by the **operations** an object can perform and its **reactions** to those operations.
   - Example:
     - Sending a message to a `Car` object like `startEngine()` triggers a reaction (engine starts).

2. **Comparing Styles**:
   - **Procedure-Oriented**: Changes occur when subprograms (functions) are executed.
   - **Rule-Oriented**: Changes occur when rules are triggered by events.
   - **Object-Oriented**: Changes occur when messages (method calls) are sent to objects.

---

### **Example: Bank Account Contract**

1. **Contract**:
   - **Services** provided:
     - `deposit(amount)`
     - `withdraw(amount)`
     - `checkBalance()`
   - **Preconditions**:
     - `deposit(amount)`: `amount > 0`
     - `withdraw(amount)`: `amount > 0` and `amount <= balance`
   - **Postconditions**:
     - `deposit(amount)`: Balance increases by `amount`.
     - `withdraw(amount)`: Balance decreases by `amount`.

2. **Invariant**:
   - `balance >= 0` (a bank account cannot have a negative balance).

3. **Exception Handling**:
   - If `withdraw(amount)` is called with an amount greater than the balance, an exception is thrown (e.g., `InsufficientFundsException`).

---

### **Summary**

- **Entity Abstractions** represent real-world entities and form the backbone of object-oriented design.
- The **contract model** formalizes object interactions by defining:
  - The services an object provides.
  - The expectations it has from other objects.
- **Invariants**, **preconditions**, and **postconditions** ensure the integrity of an object and its interactions.
- The behavior of an object is defined by the operations it supports and its responses to those operations.

By adhering to these principles, object-oriented systems become predictable, robust, and maintainable.