# Full Subtractor Circuit

A **Full Subtractor** is a combinational logic circuit used in digital electronics to perform subtraction of three bits: the minuend, the subtrahend, and a "borrow-in" from a previous stage.

---

## 1. Inputs and Outputs
The circuit consists of three inputs and two outputs:

| Signal | Type | Description |
| :--- | :--- | :--- |
| **A** | Input | Minuend (The bit being subtracted from) |
| **B** | Input | Subtrahend (The bit to be subtracted) |
| **B<sub>in</sub>** | Input | Borrow-in from the previous lower-significant bit |
| **D** | Output | **Difference**: The result of the subtraction |
| **B<sub>out</sub>** | Output | **Borrow-out**: Indicates if a '1' was borrowed from the next stage |

---

## 2. Truth Table
The logic follows binary subtraction rules (0 - 1 = 1 with a borrow of 1).

| A | B | B<sub>in</sub> | Difference (D) | Borrow-out (B<sub>out</sub>) |
|:---:|:---:|:---:|:---:|:---:|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 1 |
| 0 | 1 | 0 | 1 | 1 |
| 0 | 1 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 0 |
| 1 | 1 | 0 | 0 | 0 |
| 1 | 1 | 1 | 1 | 1 |

---

## 3. Logical Expressions
The Boolean expressions for the outputs are:

### Difference (D)
$$D = A \oplus B \oplus B_{in}$$

### Borrow-out (B<sub>out</sub>)
$$B_{out} = \bar{A}B + \bar{A}B_{in} + BB_{in}$$

---

## 4. Implementation
In digital logic design, a Full Subtractor is typically implemented using **two Half Subtractors** connected by an **OR gate** to combine the borrow signals. This modular approach is highly efficient for complex VLSI layouts.


### 5 Key Applications
1. **ALUs:** For processing arithmetic operations in CPUs.
2. **Multi-bit Arithmetic:** Cascaded for large binary operations.
3. **DSP:** Used for signal filtering and error detection.
4. **Calculators:** Basic subtraction and decrementing logic in counters.
5. **Comparators:** Determining relative magnitude between binary numbers.
