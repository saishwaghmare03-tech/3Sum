# 3Sum (LeetCode 15)

![Java](https://img.shields.io/badge/Language-Java-orange.svg)
![Difficulty](https://img.shields.io/badge/Difficulty-Medium-yellow.svg)
![Status](https://img.shields.io/badge/Status-Solved-success.svg)

An optimal and clean **Java** solution for the classic [LeetCode 15: 3Sum](https://leetcode.com/problems/3sum/) problem using the **Sorting and Two Pointers** approach.

---

## 📋 Problem Description

Given an integer array `nums`, return all the triplets `[nums[i], nums[j], nums[k]]` such that `i != j`, `i != k`, and `j != k`, and `nums[i] + nums[j] + nums[k] == 0`.

> **Notice:** The solution set must not contain duplicate triplets.

### Examples

* **Example 1:**
  * **Input:** `nums = [-1, 0, 1, 2, -1, -4]`
  * **Output:** `[[-1, -1, 2], [-1, 0, 1]]`
  * **Explanation:** The distinct triplets that sum up to `0` are `[-1, 0, 1]` and `[-1, -1, 2]`.

* **Example 2:**
  * **Input:** `nums = [0, 1, 1]`
  * **Output:** `[]`
  * **Explanation:** No possible triplet sums up to `0`.

* **Example 3:**
  * **Input:** `nums = [0, 0, 0]`
  * **Output:** `[[0, 0, 0]]`

---

## 💡 Approach & Algorithm

1. **Sorting:** Sort the array in ascending order. This allows us to efficiently find pairs using two pointers and makes skipping duplicates straightforward.
2. **Fixed Pointer (`i`) & Early Exit:** Iterate through the array fixing one element at a time. If the current element is greater than `0`, we can break early since all subsequent numbers will also be positive and can never sum to `0`.
3. **Two-Pointers (`left` & `right`)**: For each fixed element, use a `left` pointer starting at `i + 1` and a `right` pointer starting at the end of the array.
   * If `sum == 0`, record the triplet and skip adjacent duplicate elements for both pointers.
   * If `sum < 0`, increment `left` to increase the sum.
   * If `sum > 0`, decrement `right` to decrease the sum.

---

## ⏱️ Complexity Analysis

* **Time Complexity:** **$O(n^2)$**
  * Sorting the array takes $O(n \log n)$.
  * The outer loop runs $n$ times, and the inner two-pointer scan takes linear time $O(n)$, dominating the runtime.
* **Space Complexity:** **$O(1)$** or **$O(n)$** auxiliary space (depending on the internal sorting implementation of Java's `Arrays.sort()`), excluding the space required for the output list.

---

## 🚀 Getting Started

### Prerequisites
* Java Development Kit (JDK) installed on your machine.

### Running the Code
1. Clone the repository or copy the `Solution.java` file.
2. Compile the code:
   ```bash
   javac Solution.java
