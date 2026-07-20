# Longest Valid Parentheses Substring (Java)

## 📌 Problem Statement
Given a string containing just the characters `'('` and `')'`, this program finds the length of the longest valid (well-formed) parentheses substring.

### Constraints
- $0 \le \text{s.length} \le 3 \times 10^4$
- `s[i]` is either `'('` or `')'`

---

## 💡 Approach & Algorithm

This solution uses a **Stack-based Index Tracking** approach (`java.util.ArrayDeque`):

1. **Base Boundary Initialization:** Push `-1` onto the stack. This serves as a reference point for calculating valid lengths starting from index `0`.
2. **Iterate Through String:**
   - **For `'('`:** Push its index onto the stack.
   - **For `')'`:** Pop the top of the stack.
     - **If Stack becomes empty:** Push current index as the new base boundary marker.
     - **If Stack is not empty:** Calculate length as `currentIndex - stack.peek()` and update `maxLength`.

---

## ⏱️ Complexity Analysis

- **Time Complexity:** $\mathcal{O}(N)$ — Performs a single linear scan through the string of length $N$.
- **Space Complexity:** $\mathcal{O}(N)$ — In the worst-case scenario (e.g., `"((((("`), the stack stores up to $N$ indices.

---

## 🛠️ How to Compile & Run

```bash
# 1. Compile the Java code
javac Solution.java

# 2. Run the application
java Solution
