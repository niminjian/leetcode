# [219. Contains Duplicate II](https://leetcode.com/problems/contains-duplicate-ii)

[中文文档](/solution/0200-0299/0219.Contains%20Duplicate%20II/README.md)

## Description

<p>Given an integer array <code>nums</code> and an integer <code>k</code>, return <code>true</code> if there are two <strong>distinct indices</strong> <code>i</code> and <code>j</code> in the array such that <code>nums[i] == nums[j]</code> and <code>abs(i - j) &lt;= k</code>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> nums = [1,2,3,1], k = 3
<strong>Output:</strong> true
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> nums = [1,0,1,1], k = 1
<strong>Output:</strong> true
</pre>

<p><strong>Example 3:</strong></p>

<pre>
<strong>Input:</strong> nums = [1,2,3,1,2,3], k = 2
<strong>Output:</strong> false
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= nums.length &lt;= 10<sup>5</sup></code></li>
	<li><code>-10<sup>9</sup> &lt;= nums[i] &lt;= 10<sup>9</sup></code></li>
	<li><code>0 &lt;= k &lt;= 10<sup>5</sup></code></li>
</ul>

## Solutions

<!-- tabs:start -->

### **Python3**

```python
class Solution:
    def containsNearbyDuplicate(self, nums: List[int], k: int) -> bool:
        helper = {}
        for i, v in enumerate(nums):
            if v in helper and i - helper[v] <= k:
                return True
            helper[v] = i
        return False
```

### **Java**

```java
class Solution {
    public boolean containsNearbyDuplicate(int[] nums, int k) {
        Map<Integer, Integer> helper = new HashMap<>();
        for (int i = 0, n = nums.length; i < n; ++i) {
            if (helper.containsKey(nums[i])) {
                int j = helper.get(nums[i]);
                if (i - j <= k) {
                    return true;
                }
            }
            helper.put(nums[i], i);
        }
        return false;
    }
}
```

### **...**

```

```

<!-- tabs:end -->
