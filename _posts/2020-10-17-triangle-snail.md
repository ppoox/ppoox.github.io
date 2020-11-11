---
layout: post
title: 삼각 달팽이
author: ppoox
color: brown
tags: [Algorithm, Programers]

# feature-img: "assets/img/pexels/circuit.jpeg"
# thumbnail: "assets/thumbnails/pexels/circuit.jpeg"
# excerpt_separator: <!--more-->
---
    
---
## 프로그래머스 월간 코드챌린지 시즌 1

![삼각달팽이1]({{ "/assets/img/algorithm/tri-snail-1.PNG" | relative_url }})     
![삼각달팽이2]({{ "/assets/img/algorithm/tri-snail-2.PNG" | relative_url }})     

---   

**수직 이등변 삼각형으로 생각하고 달팽이 코드 작성**

```java
import java.util.*;
class Solution {
    public int[] solution(int n) {
        int[][] snail = new int[n][n];
        int x = -1, y = 0, num = 1;

        for(int i=0; i<n; i++) {
            for(int j=i; j<n; j++) {
                if(i%3 == 0) {
                    x++;
                } else if(i%3 == 1) {
                    y++;
                } else if(i%3 == 2) {
                    x--;
                    y--;
                }
                snail[x][y] = num;

                num++;
            }
        }

        int[] result = new int[n*(n+1)/2];
        int ri = 0;
        for(int[] s : snail) {
            for(int ss : s) {
                if(ss == 0) break;
                result[ri++] = ss;
            }
        }

        return result;
    }
}
```

---

출처 - [프로그래머스 - 삼각 달팽이](https://programmers.co.kr/learn/courses/30/lessons/68645)
