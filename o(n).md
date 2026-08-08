O(n) = Linear Time

Input increases → Work increases proportionally.

<aside>
📦

Common patterns:

i++
i += 2
i += constant
i -= constant

</aside>

Examples:

for (i = 0; i < n; i++)
→ O(n)

for (i = 0; i < n; i += 2)
→ O(n)

for (i = 0; i < n; i += 100)
→ O(n)

Array traversal
→ O(n)

Sequential:
O(n) + O(n)
→ O(n)

Nested:
O(n) × O(n)
→ O(n²)
