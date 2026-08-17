#  Reverse-Start Alphabet Triangle

A Python pattern-printing program that builds an alphabet triangle by changing the **starting character of each row**.

Unlike a standard alphabet triangle, this pattern works backward from the final character while still printing the letters in ascending order within each row.

---

##  Pattern Preview

For `N = 5`:

```text
E
D E
C D E
B C D E
A B C D E
```

---

##  Pattern Logic

The pattern is controlled by the starting character of each row.

For every row:

```text
Row 1 → E
Row 2 → D E
Row 3 → C D E
Row 4 → B C D E
Row 5 → A B C D E
```

The starting character moves backward through the alphabet, while the ending character remains `E`.

---

##  Core Logic

The starting ASCII value is calculated using:

```python
ord('A') + N - 1 - i
```

For `N = 5`:

```text
i = 0 → E
i = 1 → D
i = 2 → C
i = 3 → B
i = 4 → A
```

The inner loop then continues from that starting character up to:

```python
ord('A') + N
```

---

##  Implementation

```python
class Solution:
    def pattern18(self, N):
        for i in range(N):
            for ch in range(
                ord('A') + N - 1 - i,
                ord('A') + N
            ):
                print(chr(ch), end=" ")
            print()


if __name__ == "__main__":
    sol = Solution()
    N = 5
    sol.pattern18(N)
```

---

##  Example Walkthrough

For `N = 4`:

```text
D
C D
B C D
A B C D
```

Each new row introduces one additional letter from the beginning of the alphabet.

---

##  Complexity Analysis

| Metric | Complexity |
|---|---|
| **Time Complexity** | **O(N²)** |
| **Auxiliary Space** | **O(1)** |

The total number of characters printed is:

```text
1 + 2 + 3 + ... + N
```

Therefore, the algorithm takes **O(N²)** time and uses **O(1)** auxiliary space.

---

##  Concepts Practiced

- Nested `for` loops
- `ord()` function
- `chr()` function
- ASCII character values
- Reverse starting positions
- Alphabet sequence generation
- Pattern construction

---

##  Key Idea

The interesting part of this pattern is that the **starting letter moves backward**, while the sequence itself always moves forward:

```text
E
D → E
C → D → E
B → C → D → E
A → B → C → D → E
```

This makes it a useful exercise for understanding how loop boundaries can control both the starting and ending characters.
