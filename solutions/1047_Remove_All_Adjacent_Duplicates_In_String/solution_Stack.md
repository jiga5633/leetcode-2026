# #1047 Remove All Adjacent Duplicates In String

> **难度**: 🟢 Easy &nbsp;|&nbsp; **结果**: ✅ 通过 &nbsp;|&nbsp; **用时**: 0分0秒 &nbsp;|&nbsp; **日期**: 2026/5/27

**语言**: Python &nbsp;|&nbsp; **题型**: Array

---

## 解法1: Stack

### Python 代码

```python
class Solution:
    def removeDuplicates(self, s: str) -> str:
        stack =[]
        for char in s:
            if not stack:
                stack.append(char)
            else:
                if stack[-1] != char:
                    stack.append(char)
                else:
                    stack.pop()
        return ''.join(stack)
```

---

*记录于 2026-05-27T12:26:11.155Z*