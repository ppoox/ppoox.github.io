---
layout: post
title: 타겟 넘버
author: ppoox
color: brown
tags: [Algorithm, Programers]

---
    
---
## 프로그래머스 코딩테스트 연습 깊이/너비 우선 탐색(DFS/BFS)

![타겟넘버]({{ "/assets/img/algorithm/target-number.PNG" | relative_url }})     

---   

```python
def solution(numbers, target):
    answer = dfs(numbers, target, 0, -1)

    return answer

def dfs(numbers, target, prev, n):
    n += 1

    if(n == len(numbers)):
        return 1 if prev == target else 0

    ans = 0
    ans += dfs(numbers, target, prev + numbers[n], n)
    ans += dfs(numbers, target, prev - numbers[n], n)

    return ans
```

---

출처 - [프로그래머스 - 타겟 넘버](https://programmers.co.kr/learn/courses/30/lessons/43165)
