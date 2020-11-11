---
layout: post
title: 풍선 터트리기
author: ppoox
color: brown
tags: [Algorithm, Programers]
---
    
---
## 프로그래머스 월간 코드챌린지 시즌 1

![풍선터트리기1]({{ "/assets/img/algorithm/bump-balloon-1.PNG" | relative_url }})     
![풍선터트리기2]({{ "/assets/img/algorithm/bump-balloon-2.PNG" | relative_url }})     

---   

**해당 숫자의 좌우로 최솟값 개수를 고려하여 작성**

```java
import java.util.*;

class Solution {
    public int solution(int[] a) {
        int answer = 2;

        int[][] ma = new int[a.length][2];
        int l = a[0], r = a[a.length-1];

        for(int i=1; i<a.length; i++) {
            if(l > a[i]) l = a[i];
            ma[i][0] = l;
        }
        for(int i=a.length-2; i>0; i--) {
            if(r > a[i]) r = a[i];
            ma[i][1] = r;
        }
        for(int i=1; i<a.length-1; i++) {
            if(a[i] <= ma[i][0] || a[i] <= ma[i][1]) answer++;
        }

        return answer;
    }
}
```

---

출처 - [프로그래머스 - 풍선 터트리기](https://programmers.co.kr/learn/courses/30/lessons/68646)
