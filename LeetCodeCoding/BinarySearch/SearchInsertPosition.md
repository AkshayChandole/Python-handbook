
# [Search Insert Position](#Search-Insert-Position)
 

## 1. Problem Understanding

You are given:

* A **sorted array** `nums`
* A `target` value

👉 Return:

* If target exists → its index
* If not → the index where it **should be inserted** to maintain sorted order

---

#### Example:

```text id="3rj9gi"
nums = [1,3,5,6], target = 5 → Output = 2
nums = [1,3,5,6], target = 2 → Output = 1
nums = [1,3,5,6], target = 7 → Output = 4
```

---

## 2. Constraints

* `1 <= n <= 10^4`
* Array is **sorted (ascending)**
* No duplicates (usually assumed)

---

#### Impact:

* Sorted array → Binary Search applicable
* Need **O(log n)** → brute force not optimal

---

## 3. Examples

#### Example 1

```text id="lfqkcr"
nums = [1,3,5,6], target = 5
```

👉 Output: `2`

---

#### Example 2

```text id="hij5u8"
nums = [1,3,5,6], target = 2
```

👉 Output: `1`

---

#### Example 3

```text id="r9p5l7"
nums = [1,3,5,6], target = 7
```

👉 Output: `4`

---

## 4. Brute Force Approach (FULL + COMPLEXITY) 🔥

### 💡 Intuition

* Traverse array
* Find first element ≥ target
* That index is answer

---

### 📋 Algorithm Steps

1. Loop through array:

   * If `nums[i] >= target` → return `i`
2. If not found → return `len(nums)`

---

### ✅ Code (LeetCode Format)

```python
class Solution:
    def searchInsert(self, nums, target):
        for i in range(len(nums)):
            if nums[i] >= target:
                return i
        return len(nums)
```

---

### ▶ Driver Code

```python
def main():
    sol = Solution()
    
    nums = [1,3,5,6]
    target = 2
    
    print(sol.searchInsert(nums, target))

if __name__ == "__main__":
    main()
```

---

### 🔍 Dry Run

```text
nums = [1,3,5,6], target = 2
```

| i | nums[i] | Condition (>=2) | Action   |
| - | ------- | --------------- | -------- |
| 0 | 1       | No              | continue |
| 1 | 3       | Yes             | return 1 |

---

### ⏱ Complexity Analysis (Brute Force)

#### Time Complexity: **O(n)**

* Worst case:

  * Target at end OR larger than all elements
  * Traverse entire array

---

#### Space Complexity: **O(1)**

* No extra space used

---

### ⚠️ Limitation

* Doesn’t use sorted property
* Not optimal for large inputs

---

## 5. Optimal Approach (Binary Search) 🚀

---

### 💡 Intuition (VERY IMPORTANT)

We are essentially finding:
👉 **Lower Bound of target**

Meaning:

* First index where `nums[i] >= target`

---

### 🧠 Key Idea

Binary search helps us:

* Narrow down insertion position efficiently
* Even if target not found → left pointer gives answer

---

### 📋 Algorithm

1. Initialize:

   ```python
   left = 0
   right = len(nums) - 1
   ```

2. While `left <= right`:

   * Compute mid
   * If `nums[mid] == target` → return mid
   * If `nums[mid] < target` → search right
   * Else → search left

3. Return `left`

---

### ✅ Code (LeetCode Format)

```python
class Solution:
    def searchInsert(self, nums, target):
        left, right = 0, len(nums) - 1
        
        while left <= right:
            mid = (left + right) // 2
            
            if nums[mid] == target:
                return mid
            elif nums[mid] < target:
                left = mid + 1
            else:
                right = mid - 1
        
        return left
```

---

### ▶ Driver Code

```python
def main():
    sol = Solution()
    
    nums = [1,3,5,6]
    target = 2
    
    print(sol.searchInsert(nums, target))

if __name__ == "__main__":
    main()
```

---

### 🔍 Dry Run

```text
nums = [1,3,5,6], target = 2
```

| left | mid | right | nums[mid] | Action          |
| ---- | --- | ----- | --------- | --------------- |
| 0    | 1   | 3     | 3         | move left side  |
| 0    | 0   | 0     | 1         | move right side |

👉 Final `left = 1`

✅ Answer = `1`

---

## 6. Complexity Analysis (Optimal)

#### Time Complexity: **O(log n)**

* Each iteration halves search space

---

#### Space Complexity: **O(1)**

* No extra space used

---

## 7. Edge Cases

* Target smaller than all → return 0
* Target larger than all → return n
* Single element
* Target equals first/last
* Empty array (rare but possible)

---

## 8. Interview Tips 🎯

#### What to say:

> "This is a classic lower bound binary search problem."

---

#### Follow-ups:

1. Implement **upper bound**
2. Count occurrences using bounds
3. Insert into array

---

## 🔥 Pattern Recognition

If you see:

* Sorted array
* Insert position / first ≥ target

👉 Think:
✅ **Lower Bound (Binary Search)**

---

