---
layout: post
title: 임베딩이란? [Focusing on one-hot encoding]
categories: NLP
tags:
- python
- nlp
date: 2022-02-12 00:15 +0800
last_modified_at: 2022-02-13 17:38 +0800
toc: true
comment: true
---

**Embedding**이란, 사람이 쓰는 자연어를 기계가 이해할 수 있는 숫자형태인 vector로 바꾼 결과 혹은 그 일련의 과정 전체를 의미합니다.
{: .message }

<p align="center">
	<img src="https://images.velog.io/images/ekjh0418/post/76819494-ebe0-40ee-804b-488d94908d40/embedding.png" width="70%">
</p>

최근들어, <strong>사람과 소통할 수 있는 능력을 갖춘 인공지능</strong>이 증가하고 있습니다. 대표적으로 우리 핸드폰에 있는 <strong>Siri</strong> 나 <strong>빅스비</strong> 등을 예로 들 수 있겠군요. 그런데 가끔씩 이러한 인공지능들은 어떻게 사람의 말을 인식하는지 의문이 들곤 합니다. 그래서 이러한 궁금증을 해결하기 위해서 자연어 처리 분야인 임베딩의 기초적인 부분을 이 글을 통해 알아보고자 합니다.


## 🙋 What is Embedding?

<p align="center">
  <img src="https://images.velog.io/images/ekjh0418/post/2d4810ed-06ec-46e7-b394-b014fb4ce66e/computer.jpg" width="95%">
</p>

컴퓨터는 사람들이 일상생활 속에서 사용하는 언어([자연어](https://ko.wikipedia.org/wiki/%EC%9E%90%EC%97%B0%EC%96%B4))를 직접 그 형태로 처리할 수 없습니다. 컴퓨터는 <strong>수치 연산</strong>만 가능하기 때문에 <strong>자연어를 숫자나 벡터 형태로 변환</strong>해야 합니다. 

이러한 과정을 자연어 처리 분야에서는 <strong>임베딩(Embedding)</strong>이라고 부릅니다.
즉, 임베딩(Embedding)은 <mark><ins>단어나 문장을 수치화하여 벡터 공간으로 표현하는 과정</ins></mark>을 의미합니다.

임베딩은 말뭉치(어절)에 따라 벡터화하기 때문에 문법적인 정보가 포함되어 있습니다. 따라서 임베딩 품질이 좋다면, 단순한 인공지능 모델로도 훌륭한 결과를 얻을 수 있습니다.

임베딩은 크게 문장 임베딩과 단어 임베딩으로 나눌 수 있습니다.

<hr>

## 🐣 Sentence Embedding?

<strong>문장 임베딩</strong>은 <mark><ins>전체 문장의 전체 문장의 흐름을 파악해 개별 단어를 벡터로 표현하는 방법</ins></mark>입니다. 따라서 문맥적 의미를 지니다는 장점을 지닙니다. 이런 이유로 밑에서 설명드릴 단어 임베딩 보다 품질이 좋으며, 상용 시스템에 많이 사용됩니다.

하지만, 문장 임베딩하기 위해서 많은 문장 데이터가 필요하며 학습하는데 많은 비용이 들어갑니다.


## 🐤 Word Embedding?

단어 임베딩은 개별 단어를 벡터로 표현하는 방법입니다. 단어 임베딩의 예시를 들어보겠습니다.

```sh
    '학교', '컴퓨터', '집' 3단어만 있고 순서대로 1번, 2번, 3번이라면, 
    단어 임베딩은 학교를 (1,0,0), 컴퓨터를 (0,1,0), 집을 (0,0,1) 로 
    나타냅니다. 이를 one-hot encoding이라고 합니다. 
    단어 문서 행렬의 각 행, 
    즉 문서를 나타내는 벡터는 그 문서를 이루는 단어 벡터들을
    모두 더한 것과 같습니다.
```

단어 임베딩의 경우, 동음이의어에 대한 구분을 하지 않기 때문에 의미가 다르더라도 단어의 형태가 같다면 동일한 벡터 값으로 표현되는 단점이 있습니다. 

하지만, 이러한 단어 임베딩도 문장 임베딩에 비해 학습 방법이 간단해 여전히 실무에서 많이 사용한다는 장점아닌 장점이 있습니다.  

<hr>

## 🐥 What is One-hot Encoding?

<strong>원-핫 인코딩(one-hot encoding)</strong>은 <mark><ins>단어를 숫자 벡터로 변환하는 가장 기본적인 방법</ins></mark>입니다.

이름 자체에서도 알 수 있듯이 요소들 중 단 하나의 값만 1이고 나머지 요솟값은 0인 인코딩을 의미합니다.

원-핫 인코딩으로 나온 결과를 원-핫 벡터라고 부르며, 전체 요소 중 단 하나의 값만 1이기 때문에 희소(sparse) 벡터라고도 합니다.

여러분들은 이미 위의 사례를 통해서 원-핫 인코딩을 접해보았습니다.
아래 이미지를 통해서 쉽게 이해해 봅시다.

<p align="center">
	<img src="https://images.velog.io/images/ekjh0418/post/61ac07c9-1377-4e1c-825e-0db5581f6e48/one-hot-encoding-concept.png" width="85%">
</p>

원-핫 인코딩을 하기 위해서는 <strong>단어 집합</strong>이라 불리는 사전을 먼저 만들어야 합니다. 

여기서 사전은 <mark><ins>말뭉치에서 나오는 서로 다른 단어의 집합</ins></mark>을 의미합니다. 
말뭉치(어절)에 존재하는 모든 단어의 수가 원-핫 벡터의 차원을 결정합니다. 

예를 들어 100개의 단어가 존재한다면, 원-핫 벡터의 크기는 100차원이 됩니다. 
사전 구축이 되었다면 사전 내 단어 순서대로 고유한 인덱스 번호를 부여합니다. 
단어의 인덱스 번호가 원-핫 인코딩에서 1의 값을 가지는 요소의 위치가 됩니다.

<strong>백문이 불여일견</strong>, 파이썬(Python)으로 직접 구현해 보겠습니다.

### 👓 Implementation

우선 KoNLPy 모듈을 설치해줍니다.

#### Window
<code>
 pip install konlpy
</code>

#### Mac
<code>
  $ pip3 install konlpy    # Python 3.x
</code>

#### Ubuntu
<code>
  $ sudo apt-get install python3-dev; pip3 install konlpy
</code>


다음으로 직접 코드를 입력하며 이해해봅시다.

{% highlight python %}

from konlpy.tag import Komoran
import numpy as np

# Komoran 형태소 분석기 객체 생성
# Komoran morphology analysis object creation
komoran = Komoran()
text = "오늘 날씨는 구름이 많아요."

# 명사만 추출
# Extract only nouns
nouns = komoran.nouns(text)
print(nouns)

# 단어 사전 구축 및 단어별 인덱스 부여
# Build word dictionary and give index by word
dics = {}
for word in nouns:
    if word not in dics.keys():
        dics[word] = len(dics)
print(dics)

# One-Hot-Encoding
nb_classes = len(dics)
targets = list(dics.values())
one_hot_targets = np.eye(nb_classes)[targets]
print(one_hot_targets)

{% endhighlight %}

이를 실행한다면, 아래와 같은 결과가 뜸을 알 수 있습니다.

```
['오늘', '날씨', '구름']
{'오늘': 0, '날씨': 1, '구름': 2}
[[1. 0. 0.]
 [0. 1. 0.]
 [0. 0. 1.]]
```

<hr>

## 💣 Finally..

원-핫 인코딩의 영우 간단한 구현 방법에 비해 좋은 성능을 가지기 때문에 많은 사람들에 의해서 사용되고 있습니다.

하지만, 원-핫 벡터의 경우 단순히 단어의 순서에 의한 인덱스 값은 기반으로 인코딩된 값이기 때문에 단어의 의미나 유사한 단어와의 관계를 담고 있지 않습니다.

또한, 단어 사전의 크기가 커짐에 따라 원-핫 벡터의 차원도 커지는데, 이때 메모리 낭비와 계산의 복잡도가 커집니다. 그리고 원-핫 벡터는 대부분 요소가 0의 값을 가지고 있으므로 비효율적입니다.

<hr>

## 💥 Next Post Notice

다른 워드 임베딩의 종류 중 하나인 Word2Vec에 대해 알아볼 것입니다!
