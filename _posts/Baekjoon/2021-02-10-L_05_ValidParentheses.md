---
title           : "<LeetCode>05_20_Valid Parentheses"
layout          : single
date            : 2021-02-10 + T + 22:36 + :00
categories      : "Baekjoon"
---

## 문제

[Valid Parentheses](https://leetcode.com/problems/valid-parentheses/)

## 작성코드

```cs
public class Solution {
    public bool IsValid(string s) {
        Stack<char> stack = new Stack<char>();
         foreach(char a in s)
         {
             switch(a)
            {
                case ')':
                     if (CheckPop(stack) != '(' )
                         return false;
                     break;
                case '}':
                     if (CheckPop(stack) != '{' )
                         return false;
                     break;
                case ']':
                     if (CheckPop(stack) != '[' )
                         return false;
                     break;
                default :
                    stack.Push(a);
                     break;
            }
         }
        
        if (stack.Count == 0)
            return true;
        
        return false;
    }
    
    private char CheckPop(Stack<Char> stack)
    {
        if (stack.Count == 0)
            return '\0';
        return stack.Pop();
    }
}
```

## 배운점
  
+ ASCII 코드에서 Parentheses는 패턴이 완전히 없어 보여도 어느정도는 있는점을 파악하자.
+ Switch에 연연하기보다 이중 If 문의 사용도 고려해보자.
