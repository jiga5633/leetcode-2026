# #20 Valid Parentheses

> **难度**: 🟢 Easy &nbsp;|&nbsp; **结果**: ✅ 通过 &nbsp;|&nbsp; **用时**: 0分0秒 &nbsp;|&nbsp; **日期**: 2026/5/27

**语言**: Python &nbsp;|&nbsp; **题型**: Stack

---

## 解法3: Stack

### Python 代码

```python
class Solution:
    def isValid(self, s: str) -> bool:
        stack =[]
        pairs = {')':'(','}':'{',']':'['}

        for char in s:
            if char in '({[':
                stack.append(char)
            else:
                if not stack:
                    return False
                if stack.pop() != pairs[char]:
                    return False
                  
        return len(stack) == 0 
```

### Java 代码

```java
import java.util.HashMap;

public class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer,Integer> map = new HashMap<>();
        for(int i=0;i<nums.length;i++){
            int diff = target - nums[i];
            if(map.containsKey(diff)) return new int[]{map.get(diff),i};
            map.put(nums[i],i);
        }
        return new int[]{};
    }
}
```

---

*记录于 2026-05-27T12:12:11.318Z*