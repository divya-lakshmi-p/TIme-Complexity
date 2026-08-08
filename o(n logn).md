# O(n log n) — Linearithmic Time

## Definition

O(n log n) means **linearithmic time**.

It usually occurs when we perform **O(log n) work for each of n elements**.

In simple terms:

```text
O(n) × O(log n)
        ↓
   O(n log n)




Basic Idea
n elements
   ↓
For each element
   ↓
Perform log n work
   ↓
O(n log n)

Another way to think about it:

O(n log n) = n × log n




Example 1 — Nested Loop
for (int i = 0; i < n; i++) {

    for (int j = 1; j < n; j *= 2) {
        System.out.println(i + " " + j);
    }
}
Outer Loop
for (int i = 0; i < n; i++)

The outer loop runs n times.

Therefore:

O(n)
Inner Loop
for (int j = 1; j < n; j *= 2)

The values are:

1 → 2 → 4 → 8 → 16 → ... → n

The value doubles every time.

Therefore:

O(log n)
Combined Complexity

The loops are nested, so multiply:

O(n) × O(log n)

Therefore:

O(n log n)






Example 2 — Outer O(log n), Inner O(n)
for (int i = 1; i < n; i *= 2) {

    for (int j = 0; j < n; j++) {
        System.out.println(i + " " + j);
    }
}

Outer loop:

O(log n)

Inner loop:

O(n)

Nested loops:

O(log n) × O(n)

Therefore:

O(n log n)

The order does not matter:

O(log n × n)
=
O(n log n)




Common Algorithms With O(n log n)

Some important algorithms have O(n log n) complexity:

Merge Sort
→ O(n log n)

Heap Sort
→ O(n log n)

Quick Sort
→ O(n log n) average case
→ O(n²) worst case


