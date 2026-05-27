# #150 Evaluate Reverse Polish Notation

> **难度**: 🟡 Medium &nbsp;|&nbsp; **结果**: ✅ 通过 &nbsp;|&nbsp; **用时**: 0分0秒 &nbsp;|&nbsp; **日期**: 2026/5/27

**语言**: Python &nbsp;|&nbsp; **题型**: Stack

---

## 解法1: Stack

### Python 代码

```python
class Solution:
    def evalRPN(self, tokens: List[str]) -> int:
        stack =[]
        for token in tokens:
            if token not in ['+','-','*','/']:
                stack.append(int(token))
               
            else:
                b = stack.pop()                 
                a = stack.pop()                 
                if token == '+':
                    stack.append(a + b)
                elif token == '-':
                    stack.append(a - b)
                elif token == '*':
                    stack.append(a * b)
                elif token == '/':
                    stack.append(int(a / b))
        return stack[-1]
```

---

*记录于 2026-05-27T12:41:03.140Z*