---
layout: post
title: Baekjoon problem 8393
categories: BAEKJOON
tags:
- BAEKJOON
- Algorithm
- Python
date: 2022-03-20 15:35 +0800
last_modified_at: 2022-03-20 16:49 +0800
toc: true
comment: true
---

This article is a solution to the Baekjun problem.
{: .message }

# 백준 8393번 문제 해결법
<hr />
## 백준 8393번 문제
<hr />
### 문제

<mark>n이 주어졌을 때, 1부터 n까지 합을 구하는 프로그램을 작성하시오.</mark>

### 입력

```
첫째 줄에 n (1 ≤ n ≤ 10,000)이 주어진다.
```

example input:
```
3
```
  
### 출력

example print:
```
6
```

<hr />

## 접근법
우선 **```1 ~ n```** 까지 전부 더해야 하는 것이 문제이다. 간단하게 코딩을 해보겠다.

{% highlight python linenos %}
n = int(input())
total = 0

for i in range(1, n+1):
    total = total + i

print(total)
{% endhighlight %}

흔히 이 방법으로 푸는 것이 일반적일 것이다. 그런데 이 문제는 사실 for문을 쓸 필요가 없다.
흔히 중학교 수학에서 다루는 간단한 개념을 이용하면 **2줄로** 간단하게 끝낼 수 있다.

### 가우식

$$
sum _{1} ^{n} n`=` {n(n+1)} over {2}
$$

흔히 중학교에서 배우는 식이기는 하지만 사실 고등학교 과정에서 더 자주 쓰는 식 중 하나이다. 이 식은 수학적 귀납법을 통해서 증명이 가능하다.

$$
1. f(n) = {n(n+1)} over {2}
2. f(1) = 1
3. f(k+1) = {(k+1){(k+2) + 1}} over {2}
$$

그럼 이 가우스 식을 코딩해보자!

## code

{% highlight python linenos %}
n = int(input())
print(int(n*(n+1)/2))
{% endhighlight %}
