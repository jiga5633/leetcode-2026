# #20 Valid Parentheses

> **难度**: 🟢 Easy &nbsp;|&nbsp; **结果**: ✅ 通过 &nbsp;|&nbsp; **用时**: 0分0秒 &nbsp;|&nbsp; **日期**: 2026/5/27

**语言**: Python &nbsp;|&nbsp; **题型**: Array

---

## 解法1: Stack

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

---

*记录于 2026-05-27T12:19:15.250Z*