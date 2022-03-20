---
layout: post
title: Baekjoon problem 1000
categories: BAEKJOON
tags:
- BAEKJOON
- Algorithm
- Python
date: 2022-03-19 15:17 +0800
last_modified_at: 2022-03-20 14:31 +0800
toc: true
comment: true
---

This article is a solution to the Baekjun problem.
{: .message }

# 백준 1000번 문제 해결법

## 백준 1000번 문제

### 문제

```
두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오.
```

### 입력

```
첫째 줄에 A와 B가 주어진다. (0 < A, B < 10)
```

example input:
```
1 2
```

### 출력

```
첫째 줄에 A+B를 출력한다.
```

example print:
```
3
```

## 접근법
우선 문제에서 0보다 크고 10보다 작은 정수를 입력받으라 하였기 때문에 ```map(function, iterable)```함수를 이용해 접근할 수 있다. 정수형이라는 조건이 있기에 ```function```자리에 ```int```함수를 넣어줄 수 있다.

그리고 입력이 ```1 2```로 들어가므로 ```input().split()```을 이용해서 입력 값을 공백을 기준으로 나누어 저장할 수 있을 것이다.

## code
```py
A, B = map(int, input().split())
print(A + B)
```
