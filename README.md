# LEETCODE-Recursion-2698
1. It squares each number \( i \) from \( 1 \) to \( n \).
2. It checks if the square of \( i \) can be split into parts such that the sum of those parts equals \( i \).

---

### **Understanding the `check` function:**
- `num`: The number being checked (initially the square of \( i \)).
- `cs`: The cumulative sum of extracted parts.
- `t`: The target sum (which should match \( i \) if valid).

The function recursively:
1. Extracts digits (1-digit, 2-digits, ..., 4-digits at a time).
2. Checks if the sum of extracted parts equals \( i \).

---

### **Dry Run for `punishmentNumber(10)`**
Let's check \( n = 10 \):

1. \( i = 1 \), \( \text{sq} = 1 \)
   - `check(1, 0, 1)` → \( 1 == 1 \) ✅ → Add \( 1 \) to `pm`

2. \( i = 2 \), \( \text{sq} = 4 \)
   - `check(4, 0, 2)` → No valid split ❌

3. \( i = 3 \), \( \text{sq} = 9 \)
   - `check(9, 0, 3)` → No valid split ❌

4. \( i = 4 \), \( \text{sq} = 16 \)
   - `check(16, 0, 4)` → No valid split ❌

5. \( i = 5 \), \( \text{sq} = 25 \)
   - `check(25, 0, 5)` → No valid split ❌

6. \( i = 6 \), \( \text{sq} = 36 \)
   - `check(36, 0, 6)` → No valid split ❌

7. \( i = 7 \), \( \text{sq} = 49 \)
   - `check(49, 0, 7)` → No valid split ❌

8. \( i = 8 \), \( \text{sq} = 64 \)
   - `check(64, 0, 8)` → No valid split ❌

9. \( i = 9 \), \( \text{sq} = 81 \)
   - `check(81, 0, 9)` → ✅ Split `81 → 8 + 1 = 9` → Add \( 81 \)

10. \( i = 10 \), \( \text{sq} = 100 \)
   - `check(100, 0, 10)` → ✅ Split `100 → 10 + 0 = 10` → Add \( 100 \)

---

### **Final Sum:**
\( 1 + 81 + 100 = 182 \)

Thus, `punishmentNumber(10)` returns **182**.

---

### **Complexity Analysis:**
- Outer loop runs \( O(n) \).
- `check` recursively explores partitioning \( O(\log M) \) times (where \( M \) is \( i^2 \)).
- Approximate complexity: **\( O(n \log n) \)**.
