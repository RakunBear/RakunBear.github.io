---
title           : "<LeetCode>04_13_Roman To Integer"
layout          : single
date            : 2021-02-08 + T + 18:03 + :00
categories      : "Baekjoon"
---

## 문제

[Roman To Integer](https://leetcode.com/problems/roman-to-integer/)

## 작성코드

```cs
public class Solution {
    public int RomanToInt(string s) {
        int answer = 0;
        char pre = '\0';
        foreach(char c in s)
        {
            switch(c)
            {
                case 'I':
                    answer+=1;
                    break;
                case 'V':
                    if (pre == 'I')
                    {
                        answer+=3;
                    }
                    else
                    {
                        answer+=5;
                    }
                    break;
                case 'X':
                    if (pre == 'I')
                    {
                        answer+=8;
                    }
                    else
                    {
                        answer+=10;
                    }
                    break;
                case 'L':
                    if (pre == 'X')
                    {
                        answer+=30;
                    }
                    else
                    {
                        answer+=50;
                    }
                    break;
                case 'C':
                    if (pre == 'X')
                    {
                        answer+=80;
                    }
                    else
                    {
                        answer+=100;
                    }
                    break;
                case 'D':
                    if (pre == 'C')
                    {
                        answer+=300;
                    }
                    else
                    {
                        answer+=500;
                    }
                    break;
                case 'M':
                    if (pre == 'C')
                    {
                        answer+=800;
                    }
                    else
                    {
                        answer+=1000;
                    }
                    break;
            }
            pre = c;
        }
        
        return answer;
    }
}
```

## 배운점
  
+ 이전 자리의 문자를 비교할 때는 `a[i] , a[i+1]` 형태의 방식을 사용하자.
