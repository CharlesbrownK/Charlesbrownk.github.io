---
layout: post
title: Baekjoon problem 10171
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

```
print("""\    /\
 )  ( ')
(  /  )
 \(__)|""")
```

해당 코드를 실행시키면, 아래의 결과가 나오는 것을 확인할 수 있다.

```
\    / )  ( ')
(  /  )
 \(__)|
```

우리가 [생각하던 출력](#출력)과는 사뭇 다르다.

우선 첫번째로 **```\```** 가 문제다. 파이썬에서 **```\```** 은 어떻게 사용될까?

### \ 출력하기
**```\```** 는 아래의 방법처럼 활용이 가능하다.

  - 줄바꿈 ```print(\n)```
  - 출력될 문자열 내의 따음표 출력 ```print(\"Hello World\")```
  - 커서를 맨앞으로 이동 ```print("Red Apple\rPine")```
  - 백스페이스 ```print("Redd\bApple")```
  - Tab ```print(Red\tApple)```

그렇다면 **```\```** 출력을 어떻게 할까?
우선 아래처럼 입력해보자.
```
print("\")

>>>   File "c:/Users/Desktop/cat.py", line 1
        print("\")
                 ^
    SyntaxError: EOL while scanning string literal
```

위와 같은 오류를 겪을 수 있을 것이다.

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
