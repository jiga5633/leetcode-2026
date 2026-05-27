# #239 Sliding Window Maximum

> **难度**: 🔴 Hard &nbsp;|&nbsp; **结果**: ✅ 通过 &nbsp;|&nbsp; **用时**: 0分0秒 &nbsp;|&nbsp; **日期**: 2026/5/27

**语言**: Python &nbsp;|&nbsp; **题型**: Linked List

---

## 解法2: Deque

| 复杂度 | 值 |
|--------|-----|
| 时间复杂度 | `187` |

### Python 代码

```python
from collections import deque

class Solution:
    def maxSlidingWindow(self, nums: List[int], k: int) -> List[int]:
        dq = deque()     # 存 index，不存值
        result = []

        for i in range(len(nums)):
            # 1. 移除超出窗口的队头
            if dq and dq[0] < i - k + 1:
                dq.popleft()

            # 2. 移除队尾比当前小的元素
            while dq and nums[dq[-1]] < nums[i]:
                dq.pop()

            # 3. 当前index加入队尾
            dq.append(i)

            # 4. 窗口够k个了，记录队头=最大值
            if i >= k - 1:
                result.append(nums[dq[0]])

        return result
```

---

*记录于 2026-05-27T13:29:57.458Z*