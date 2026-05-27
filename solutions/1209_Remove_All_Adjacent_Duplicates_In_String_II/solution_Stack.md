# #1209 Remove All Adjacent Duplicates In String II

> **难度**: 🟡 Medium &nbsp;|&nbsp; **结果**: ✅ 通过 &nbsp;|&nbsp; **用时**: 0分0秒 &nbsp;|&nbsp; **日期**: 2026/5/27

**语言**: Python &nbsp;|&nbsp; **题型**: Stack

---

## 解法1: Stack

### Python 代码

```python
class Solution:
    def removeDuplicates(self, s: str, k: int) -> str:
        stack =[]
        for char in s:
            if not stack:
                stack.append((char,1))
                
            else:
                if stack and stack[-1][0]== char:
                    stack[-1] = (char,stack[-1][1]+1)
                    if stack[-1][1] == k:
                        stack.pop()
                else:
                    stack.append((char,1))
        return ''.join(char * count for char, count in stack)
```

---

*记录于 2026-05-27T12:36:22.890Z*