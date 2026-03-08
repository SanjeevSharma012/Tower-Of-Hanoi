# Tower of Hanoi

## Problem Statement

You are given **n disks** placed on a starting rod (**from**), arranged from smallest at the top to largest at the bottom. There are three rods:

* **from** → Starting rod
* **to** → Target rod
* **aux** → Auxiliary rod

The goal is to move all disks from the **starting rod** to the **target rod** following these rules:

1. Only **one disk** can be moved at a time.
2. A disk can only be placed on **top of a larger disk** or on an **empty rod**.

Return the **minimum number of moves** required to transfer all disks.

---

## Approach

The problem follows a **recursive pattern**:

1. Move **n-1 disks** from the source rod to the auxiliary rod.
2. Move the **largest disk** from the source rod to the destination rod.
3. Move the **n-1 disks** from the auxiliary rod to the destination rod.

---

## Algorithm

1. If `n == 0`, return `0`.
2. Recursively move `n-1` disks from **from → aux**.
3. Count the move of the largest disk.
4. Recursively move `n-1` disks from **aux → to**.
5. Return the total moves.

---

## Java Implementation

```java
class Solution {
    public int towerOfHanoi(int n, int from, int to, int aux) {

        if (n == 0) return 0;

        int moves = 0;

        moves += towerOfHanoi(n - 1, from, aux, to);

        moves++;

        moves += towerOfHanoi(n - 1, aux, to, from);

        return moves;
    }
}
```

---

## Example

Input

```
n = 2
```

Output

```
3
```

Explanation

Minimum moves required:

```
1 → 2
1 → 3
2 → 3
```

Total moves = **3**

---

## Formula

The minimum number of moves required is:

```
Moves = 2^n - 1
```

Example:

| n | Moves |
| - | ----- |
| 1 | 1     |
| 2 | 3     |
| 3 | 7     |
| 4 | 15    |

---

## Complexity Analysis

**Time Complexity:**

```
O(2^n)
```

**Space Complexity:**

```
O(n)  (Recursion stack)
```

---

## Key Concepts

* Recursion
* Divide and Conquer
* Mathematical pattern `2^n - 1`

---

⭐ If you like this solution, consider giving the repository a **star**.


Author
👤 Sanjeev Sharma
DSA & Full Stack Developer..
