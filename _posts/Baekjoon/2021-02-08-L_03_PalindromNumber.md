---
title           : "<LeetCode>03_09_Palindrome Number"
layout          : single
date            : 2021-02-08 + T + 20:03 + :00
categories      : "Baekjoon"
---

## 문제

Given an integer x, return true if x is palindrome integer.

An integer is a palindrome when it reads the same backward as forward. For example, 121 is palindrome while 123 is not.
  
```
Example 1:

Input: x = 121
Output: true

Example 2:

Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.

Example 3:

Input: x = 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.

Example 4:

Input: x = -101
Output: false
```

## 배운점
  
+ `reverseNumber = reverseNumber * 10 + (x % 10);` 정수역순은 해당 방식을 사용하자.
