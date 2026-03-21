# [Find Minimum in Rotated Sorted Array](#Find-Minimum-in-Rotated-Sorted-Array)


## 1. Problem Understanding

You are given:

* A **sorted array** that has been **rotated** at some pivot

👉 Your task:
Return the **minimum element** in the array.

---

#### 🔍 What is a rotated array?

Original sorted:

```text
[1, 2, 3, 4, 5, 6, 7]
```

Rotated:

```text
[4, 5, 6, 7, 1, 2, 3]
```

👉 Notice:

* Array is still partially sorted
* The **smallest element is the pivot point**

---

## 2. Constraints

Typical constraints:

* `1 <= nums.length <= 10^5`
* `-10^5 <= nums[i] <= 10^5`
* All elements are **unique**

---

#### Impact:

* O(n) works but not optimal
* We should aim for **O(log n)** → Binary Search

---

## 3. Examples

#### Example 1

```text
nums = [3, 4, 5, 1, 2]
```

👉 Minimum = **1**

---

#### Example 2

```text
nums = [4, 5, 6, 7, 0, 1, 2]
```

👉 Minimum = **0**

---

#### Example 3 (No rotation)

```text
nums = [1, 2, 3, 4]
```

👉 Minimum = **1**

---

## 4. Brute Force Approach

### Idea:

Scan entire array and track minimum

### Code:

```python
def findMin(nums):
    return min(nums)
```

### Complexity:

* Time: **O(n)**
* Space: **O(1)**

---

## 5. Better Approach

We want faster than O(n) → use **Binary Search**

---

## 6. Optimal Approach (Binary Search)

### 💡 Intuition (VERY IMPORTANT)

Key observation:

* One half of array is always **sorted**
* Minimum lies in the **unsorted half**

---

#### Core Idea:

Compare **mid element with rightmost element**

```text
nums[mid] vs nums[right]
```

---

#### Cases:

1. **nums[mid] > nums[right]**
   👉 Minimum is in **right half**

2. **nums[mid] <= nums[right]**
   👉 Minimum is in **left half (including mid)**

---

### Algorithm:

1. Initialize:

   ```python
   left = 0
   right = len(nums) - 1
   ```

2. While `left < right`:

   * Find mid
   * Compare `nums[mid]` with `nums[right]`
   * Adjust search space

3. Return `nums[left]`

---

### Code:

```python
def findMin(nums):
    left, right = 0, len(nums) - 1
    
    while left < right:
        mid = (left + right) // 2
        
        if nums[mid] > nums[right]:
            ## Minimum is in right half
            left = mid + 1
        else:
            ## Minimum is in left half (including mid)
            right = mid
    
    return nums[left]
```

---

### 🔎 Dry Run

```text
nums = [4, 5, 6, 7, 0, 1, 2]
```

| left | mid | right | nums[mid] | nums[right] | Action       |
| ---- | --- | ----- | --------- | ----------- | ------------ |
| 0    | 3   | 6     | 7         | 2           | left = mid+1 |
| 4    | 5   | 6     | 1         | 2           | right = mid  |
| 4    | 4   | 5     | 0         | 1           | right = mid  |

👉 Stop when `left == right`

✅ Answer = `nums[4] = 0`

---

## 7. Complexity Analysis

#### Time Complexity:

* Each step halves the search space

👉 **O(log n)**

---

#### Space Complexity:

* No extra space used

👉 **O(1)**

---

## 8. Edge Cases

* Single element → `[1]`
* No rotation → `[1,2,3,4]`
* Two elements → `[2,1]`
* Large input
* Minimum at last index

---

## 9. Interview Tips 🎯

#### How to explain:

* Say: *"This is a modified binary search problem"*
* Emphasize:
  👉 "One half is always sorted"
  👉 "We discard the sorted half intelligently"

---

#### Common Follow-ups:

1. **What if duplicates exist?**
   → Harder version → need:

   ```python
   if nums[mid] == nums[right]:
       right -= 1
   ```

2. **Find rotation index?**
   → Same logic

3. **Search element in rotated array?**
   → Extension of this problem

---

### 🔥 Pattern Recognition

Whenever you see:

* Sorted + Rotated
* Need O(log n)

👉 Think:
✅ **Binary Search with conditions**

---
