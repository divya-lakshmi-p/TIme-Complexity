# O(log n) — Logarithmic Time

## Definition

O(log n) means **logarithmic time**.

The number of operations grows logarithmically as the input size `n` increases.

It usually occurs when the problem size is repeatedly **divided or multiplied by a constant factor**.

---

## Basic Idea

```text
Problem size
     ↓
Repeatedly divide/multiply by a constant
     ↓
Number of steps grows slowly
     ↓
O(log n)



1.int i = n;

while (i > 1) {
    i = i / 2;
}
Pattern
n → n/2 → n/4 → n/8 → ... → 1

The value is divided by 2 every iteration.

Therefore:

Time Complexity: O(log n)



2.for (int i = 1; i < n; i *= 2) {
    System.out.println(i);
}
Pattern
1 → 2 → 4 → 8 → 16 → 32 → ... → n

The value doubles every iteration.

Therefore:

Time Complexity: O(log n)



3.int i = n;

while (i > 1) {
    i = i / 3;
}
Pattern
n → n/3 → n/9 → n/27 → ... → 1

Therefore:

O(log₃ n)

In Big O notation, the base of the logarithm is ignored:

O(log₃ n) → O(log n)


4.for (int i = 1; i < n; i *= 5) {
    System.out.println(i);
}
Pattern
1 → 5 → 25 → 125 → 625 → ... → n

Therefore:

O(log₅ n) → O(log n)





One-Line Summary

O(log n) = The number of operations grows slowly because the problem size is repeatedly multiplied or divided by a constant factor.


### ⭐ Memory Trick

```text
+ / -  constant amount
       ↓
     O(n)

× / ÷  constant factor
       ↓
   O(log n)
