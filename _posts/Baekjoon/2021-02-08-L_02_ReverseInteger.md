---
title           : "<LeetCode>02_07_ReverseInteger"
layout          : single
date            : 2021-02-08 + T + 19:03 + :00
categories      : "Baekjoon"
---

## 문제

Given a signed 32-bit integer x, return x with its digits reversed. If reversing x causes the value to go outside the signed 32-bit integer range [-2^31, 2^31 - 1], then return 0.

Assume the environment does not allow you to store 64-bit integers (signed or unsigned).
  
```
Example 1:

Input: x = 123
Output: 321

Example 2:

Input: x = -123
Output: -321

Example 3:

Input: x = 120
Output: 21

Example 4:

Input: x = 0
Output: 0
```

## 배운점
  
+ `string`으로 변환해 반복문 절반 줄이는 것보다 `%`를 이용한 반복이 훨씬 효율적.  
+ `int32`에서 벗어난 수는 `* -1`이 통하지 않아서, `-1l`로 써야한다.
