# #239 Sliding Window Maximum

> **难度**: 🔴 Hard &nbsp;|&nbsp; **结果**: ❌ 未通过 &nbsp;|&nbsp; **用时**: 0分0秒 &nbsp;|&nbsp; **日期**: 2026/5/27

**语言**: Python &nbsp;|&nbsp; **题型**: Linked List

---

## 解法1: deque

| 复杂度 | 值 |
|--------|-----|
| 空间复杂度 | `O(n*k)` |

### Python 代码

```python
from collections import deque
class Solution:
    def maxSlidingWindow(self, nums: List[int], k: int) -> List[int]:
        queue =deque()
        result =[]

        for i in range(len(nums)):
            queue.append(nums[i])

            if len(queue) == k:
                result.append(max(queue))
                queue.popleft()
        return result
```

---

*记录于 2026-05-27T13:28:54.505Z*