
# [Search In A Rotated Sorted Array](#Search-In-A-Rotated-Sorted-Array)

## 1. Problem Understanding

You are given:

* A **sorted array** that is **rotated**
* A `target` value

👉 Return:

* Index of target if found
* Else return `-1`

---

#### Example:

```text
nums = [4,5,6,7,0,1,2], target = 0
Output = 4
```

---

## 2. Constraints

* `1 <= n <= 10^4`
* All elements are **unique**
* Must solve in **O(log n)**

---

#### Impact:

* Linear scan works but not optimal
* Sorted + rotated → **Modified Binary Search**

---

## 3. Examples

#### Example 1

```text
nums = [4,5,6,7,0,1,2], target = 0
```

👉 Output: `4`

---

#### Example 2

```text
nums = [4,5,6,7,0,1,2], target = 3
```

👉 Output: `-1`

---

#### Example 3

```text
nums = [1], target = 0
```

👉 Output: `-1`

---

## 4. Brute Force Approach (FULL + COMPLEXITY) 🔥

### 💡 Intuition

* Just scan entire array
* Return index when found

---

### ✅ Code (LeetCode Format)

```python
class Solution:
    def search(self, nums, target):
        for i in range(len(nums)):
            if nums[i] == target:
                return i
        return -1
```

---

### ▶ Driver Code

```python
def main():
    sol = Solution()
    
    nums = [4,5,6,7,0,1,2]
    target = 0
    
    print(sol.search(nums, target))

if __name__ == "__main__":
    main()
```

---

### ⏱ Complexity Analysis (Brute Force)

#### Time Complexity: **O(n)**

* We check every element
* Worst case → target at end or not present

---

#### Space Complexity: **O(1)**

* No extra space used

---

### ⚠️ Limitation

* Doesn’t use sorted + rotated property
* Fails required O(log n)

---

## 5. Optimal Approach (Modified Binary Search) 🚀

---

### 💡 Intuition (VERY IMPORTANT)

👉 Key observation:
At any point:

* **One half of the array is always sorted**

---

### 🧠 Core Idea

At each step:

1. Find `mid`
2. Check which half is sorted:

   * Left sorted OR Right sorted
3. Decide where target lies

---

### 🔍 Cases

#### Case 1: Left Half is Sorted

```text
nums[left] <= nums[mid]
```

👉 If target lies between:

```text
nums[left] <= target < nums[mid]
```

→ Search LEFT

Else → Search RIGHT

---

#### Case 2: Right Half is Sorted

👉 If:

```text
nums[mid] < target <= nums[right]
```

→ Search RIGHT

Else → Search LEFT

---

### ✅ Code (LeetCode Format)

```python
class Solution:
    def search(self, nums, target):
        left, right = 0, len(nums) - 1
        
        while left <= right:
            mid = (left + right) // 2
            
            if nums[mid] == target:
                return mid
            
            ## Left half is sorted
            if nums[left] <= nums[mid]:
                if nums[left] <= target < nums[mid]:
                    right = mid - 1
                else:
                    left = mid + 1
            
            ## Right half is sorted
            else:
                if nums[mid] < target <= nums[right]:
                    left = mid + 1
                else:
                    right = mid - 1
        
        return -1
```

---

### ▶ Driver Code

```python
def main():
    sol = Solution()
    
    nums = [4,5,6,7,0,1,2]
    target = 0
    
    print(sol.search(nums, target))

if __name__ == "__main__":
    main()
```

---

### 🔍 Dry Run

```text
nums = [4,5,6,7,0,1,2], target = 0
```

| left | mid | right | nums[mid] | Decision               |
| ---- | --- | ----- | --------- | ---------------------- |
| 0    | 3   | 6     | 7         | left sorted → go right |
| 4    | 5   | 6     | 1         | right sorted → go left |
| 4    | 4   | 4     | 0         | found ✅                |

---

## 6. Complexity Analysis (Optimal)

#### Time Complexity: **O(log n)**

* Each step halves the search space

---

#### Space Complexity: **O(1)**

* No extra memory used

---

## 7. Edge Cases

* Single element
* Target not present
* No rotation
* Rotation at index 0
* Target at boundaries

---

## 8. Interview Tips 🎯

#### What to say:

> "Since the array is rotated, one half is always sorted.
> We can use this property with binary search to eliminate half the space."

---

#### Common Follow-ups:

1. **With duplicates?**
   → Harder:

   ```python
   if nums[left] == nums[mid] == nums[right]:
       left += 1
       right -= 1
   ```

2. **Find minimum instead?**
   → Related problem

3. **Find rotation index?**

---

## 🔥 Pattern Recognition

If you see:

* Sorted + Rotated
* Search element

👉 Think:
✅ **Modified Binary Search (identify sorted half)**

---

