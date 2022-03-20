---
layout: post
title: Baekjoon problem 10171
categories: BAEKJOON
tags:
- BAEKJOON
- Algorithm
- Python
date: 2022-03-20 09:35 +0800
last_modified_at: 2022-03-20 11:49 +0800
toc: true
comment: true
---

This article is a solution to the Baekjun problem.
{: .message }

# 백준 10171번 문제 해결법

## 백준 10171번 문제

### 문제

<mark>아래 예제와 같이 고양이를 출력하시오.</mark>

### 출력

example print:
```
\    /\
 )  ( ')
(  /  )
 \(__)|
```

## 접근법
우선 바로 고양이 형태를 **```print()```** 해주자.

```
print("\    /\
\    /\
 )  ( ')
(  /  )
 \(__)|")
```

 그런데 실행 시 오류가 발생한다.
``` 
 >>>   File "c:/Users/Desktop/cat.py", line 3
      )  ( ')
            ^
    SyntaxError: EOL while scanning string literal
```
EOL 에러는 흔히 오타오류이다. 그런데 저 기호는 오타가 아니라 고양이 모양인데..
파이썬을 처음 해본 것이라면, 여기서 막힐 수 있다.
 
보통 이런 문자열에서 다양한 방법이 이겠지만, 나같은 경우는 **```print(""" """)```** 으로 사용한다.
 
그럼 **```print(""" """)```** 이렇게 출력해보자.

{% highlight python linenos %}
print("""\    /\
 )  ( ')
(  /  )
 \(__)|""")
{% endhighlight %}

해당 코드를 실행시키면, 아래의 결과가 나오는 것을 확인할 수 있다.

{% highlight python linenos %}
\    / )  ( ')
(  /  )
 \(__)|
{% endhighlight %}

우리가 [생각하던 출력](#출력)과는 사뭇 다르다.

우선 첫번째로 **```\```** 가 문제다. 파이썬에서 **```\```** 은 어떻게 사용될까?

## code

{% highlight python linenos %}
print("""\\    /\\\n )  ( ')\n(  /  )\n \\(__)|""")
{% endhighlight %}

{% highlight python linenos %}
print("\\    /\\")
print(" )  ( ')")
print("(  /  )")
print(" \\(__)|")
{% endhighlight %}
