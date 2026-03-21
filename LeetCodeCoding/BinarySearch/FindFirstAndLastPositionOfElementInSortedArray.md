# [Find First And Last Position Of Element In Sorted Array](#Find-First-And-Last-Position-Of-Element-In-Sorted-Array)

## 🔁 Find First and Last Position of Element in Sorted Array

---

## 1. Problem Understanding

Given a sorted array `nums` and a `target`, return:

* First index of target
* Last index of target

If not found → `[-1, -1]`

---

## 2. Constraints

* Sorted array → enables **binary search**
* Need **O(log n)** → brute force not sufficient

---

## 3. Brute Force Approach (Complete)

### Code (LeetCode Format)

```python
class Solution:
    def searchRange(self, nums, target):
        first, last = -1, -1
        
        for i in range(len(nums)):
            if nums[i] == target:
                if first == -1:
                    first = i
                last = i
        
        return [first, last]
```

---

### Driver Code

```python
def main():
    sol = Solution()
    
    nums = [5,7,7,8,8,10]
    target = 8
    
    result = sol.searchRange(nums, target)
    print("Output:", result)

if __name__ == "__main__":
    main()
```

---

## 4. Optimal Approach (Binary Search)

---

### 💡 Intuition

We run **2 binary searches**:

* One for **first occurrence**
* One for **last occurrence**

---

### Code (LeetCode Format)

```python
class Solution:
    def searchRange(self, nums, target):
        def findFirst(nums, target):
            left, right = 0, len(nums) - 1
            first = -1
            
            while left <= right:
                mid = (left + right) // 2
                
                if nums[mid] == target:
                    first = mid
                    right = mid - 1
                elif nums[mid] < target:
                    left = mid + 1
                else:
                    right = mid - 1
            
            return first
        
        def findLast(nums, target):
            left, right = 0, len(nums) - 1
            last = -1
            
            while left <= right:
                mid = (left + right) // 2
                
                if nums[mid] == target:
                    last = mid
                    left = mid + 1
                elif nums[mid] < target:
                    left = mid + 1
                else:
                    right = mid - 1
            
            return last
        
        return [findFirst(nums, target), findLast(nums, target)]
```

---

### Driver Code

```python
def main():
    sol = Solution()
    
    nums = [5,7,7,8,8,10]
    target = 8
    
    result = sol.searchRange(nums, target)
    print("Output:", result)

if __name__ == "__main__":
    main()
```

---

## 5. Complexity

* Time: **O(log n)**
* Space: **O(1)**

---

## 🔥 Interview Tip

Say this line:

> "This is a classic lower bound and upper bound binary search problem."

---

