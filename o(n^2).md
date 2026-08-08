# O(n²) — Quadratic Time

## 1. Definition

**O(n²)** means the amount of work grows approximately as:

```text
n × n = n²
```

It is called **quadratic time**.

If `n` doubles:

```text
n → 2n
```

then the work becomes:

```text
(2n)² = 4n²
```

So the work becomes approximately **4 times larger**.

---

## 2. Most Common Pattern

Two `O(n)` loops nested together:

```java
for (int i = 0; i < n; i++) {

    for (int j = 0; j < n; j++) {

        System.out.println(i + " " + j);
    }
}
```

Outer loop:

```text
O(n)
```

Inner loop:

```text
O(n)
```

Nested loops → multiply:

```text
O(n) × O(n)
= O(n²)
```

---

## 3. Why O(n²)?

If:

```text
n = 5
```

Outer loop runs:

```text
5 times
```

For every outer iteration, inner loop runs:

```text
5 times
```

Total:

```text
5 × 5 = 25
```

For general `n`:

```text
n × n
= n²
```

Therefore:

```text
O(n²)
```

---

## 4. Another Example

```java
for (int i = 0; i < n; i++) {

    for (int j = 0; j < i; j++) {
        System.out.println(j);
    }
}
```

The inner loop runs approximately:

```text
0 + 1 + 2 + 3 + ... + n
```

This sum is:

```text
n(n - 1) / 2
```

Which becomes:

```text
(n² - n) / 2
```

Ignore constants and lower-order terms:

```text
O(n²)
```

---

## 5. Nested Loops Do Not Always Mean O(n²)

Example:

```java
for (int i = 0; i < n; i++) {

    for (int j = 0; j < 10; j++) {
    }
}
```

Outer:

```text
O(n)
```

Inner:

```text
O(10)
= O(1)
```

Therefore:

```text
O(n) × O(1)
= O(n)
```

So this is **O(n)**, not O(n²).

---

## 6. O(n²) With Constant Work

```java
for (int i = 0; i < n; i++) {

    for (int j = 0; j < n; j++) {

        int x = 10;
    }
}
```

Outer:

```text
O(n)
```

Inner:

```text
O(n)
```

Work inside:

```text
O(1)
```

Therefore:

```text
O(n) × O(n) × O(1)
= O(n²)
```

---

## 7. Sequential Loops

```java
for (int i = 0; i < n; i++) {
}

for (int j = 0; j < n; j++) {
}
```

These loops are sequential, so:

```text
O(n) + O(n)
= O(2n)
= O(n)
```

This is **NOT O(n²)**.

---

## 8. Nested vs Sequential

### Sequential → ADD

```text
O(n) + O(n)
= O(n)
```

### Nested → MULTIPLY

```text
O(n) × O(n)
= O(n²)
```

This is one of the most important rules in time-complexity analysis.

---

## 9. O(n²) With Different Inner Complexity

### O(n) × O(log n)

```text
O(n log n)
```

### O(n) × O(n)

```text
O(n²)
```

### O(n) × O(1)

```text
O(n)
```

So always analyze **how each loop changes** before deciding the final complexity.

---

## 10. Common Applications

`O(n²)` commonly appears in:

* Comparing every pair of elements
* Simple sorting algorithms
* Nested array/matrix traversal
* Brute-force pair checking

Examples:

```text
Bubble Sort       → O(n²) worst case
Selection Sort    → O(n²)
Insertion Sort    → O(n²) worst case
```

---

## 11. Comparing Growth

For large `n`:

```text
O(n)
    ↓
O(n log n)
    ↓
O(n²)
```

Generally:

```text
O(n) < O(n log n) < O(n²)
```

So `O(n²)` grows faster than both `O(n)` and `O(n log n)`.

---

## 12. Important Example

```java
for (int i = 0; i < n; i++) {

    for (int j = i + 1; j < n; j++) {

        System.out.println(i + " " + j);
    }
}
```

The inner loop does not run exactly `n` times for every iteration.

But the total number of operations is approximately:

```text
n(n - 1) / 2
```

Therefore:

```text
O(n²)
```

This pattern is common when checking **every pair of elements**.

---

## 13. How to Identify O(n²)

Ask:

> **Am I doing O(n) work for each of n elements?**

If yes:

```text
O(n) × O(n)
↓
O(n²)
```

---

## 14. Common Mistakes

### Mistake 1

Thinking:

```text
Two loops = O(n²)
```

Not always.

You must check the loop complexity.

```java
for (...) {              // O(n)

    for (...) {          // O(log n)
    }
}
```

This is:

```text
O(n log n)
```

---

### Mistake 2

Thinking sequential loops multiply:

```text
O(n) + O(n)
```

Correct:

```text
O(n)
```

Only nested loops multiply:

```text
O(n) × O(n)
= O(n²)
```

---

### Mistake 3

Confusing `O(2n)` with `O(2ⁿ)`:

```text
O(2n)
→ O(n)
```

But:

```text
O(2ⁿ)
→ Exponential
```

They are completely different.

---

# Quick Identification

```text
One O(n) loop
        ↓
      O(n)

Two O(n) loops sequentially
        ↓
O(n) + O(n)
        ↓
      O(n)

Two O(n) loops nested
        ↓
O(n) × O(n)
        ↓
      O(n²)
```

---

# Complexity Comparison

```text
O(1)        → Constant
O(log n)    → Logarithmic
O(n)        → Linear
O(n log n)  → Linearithmic
O(n²)       → Quadratic
O(2ⁿ)       → Exponential
O(n!)       → Factorial
```

---

# One-Line Summary

> **O(n²) = O(n) work performed for each of n elements, most commonly caused by two nested loops that each depend linearly on n.**

### Memory Trick

```text
Sequential → ADD

Nested → MULTIPLY

O(n) + O(n)
→ O(n)

O(n) × O(n)
→ O(n²)
```
