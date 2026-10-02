# 데이터분석 5주차 정규과제

📌데이터분석 정규과제는 매주 정해진 분량의 『*혼자 공부하는 데이터 분석 with 파이썬*』 을 읽고 학습하는 것입니다. 이번 주는 아래의 **DataAnalysis_5th_TIL**에 나열된 분량을 읽고 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 제시된 강의를 참고하여 보완하는 것이 좋습니다.

<!-- 강의 링크는 아래와 같습니다.
https://www.youtube.com/watch?v=ho0LZ6GWhtc&list=PLVsNizTWUw7FGzSRCkQrPEEe-ljVXgS7k&index=10
https://www.youtube.com/watch?v=deYY4xHsI0o&list=PLVsNizTWUw7FGzSRCkQrPEEe-ljVXgS7k&index=11
-->


## DataAnalysis_5th_TIL

### 5장 데이터 시각화하기
#### 01. 맷플롯립 기본 요소 알아보기
#### 02. 선 그래프와 막대 그래프 그리기


## Study Schedule

| 주차  | 공부 범위     | 완료 여부 |
| ----- | ------------- | --------- |
| 1주차 | p.24~81    | ✅         |
| 2주차 | p.84~151   | ✅         |
| 3주차 | p.154~219  | ✅         |
| 4주차 | p.222~279 | ✅         |
| 5주차 | p.282~325 | ✅         |
| 6주차 | p.328~379 | 🍽️         |
| 7주차 | p.382~430 | 🍽️         |

<br>

<!-- 여기까진 그대로 둬 주세요-->
<img width="2376" height="1594" alt="데이터분석학습로드맵" src="https://github.com/user-attachments/assets/cbad8bf7-71a6-452a-bb45-d9f6976e9226" />


# 1️⃣ 개념 정리 

## 01. 맷플롯립 기본 요소 알아보기

# 데이터분석 6주차 정규과제

📌 데이터분석 정규과제는 매주 정해진 분량의 『혼자 공부하는 데이터 분석 with 파이썬』을 읽고 학습하는 것입니다.  
이번 주는 아래의 DataAnalysis_6th_TIL에 나열된 분량을 읽고 공부합니다.

---

## DataAnalysis_6th_TIL

### 6장 복잡한 데이터 표현하기

#### 01. 객체지향 API로 그래프 꾸미기

#### 02. 맷플롯립의 고급 기능 배우기

---

## Study Schedule

주차 | 공부 범위 | 완료 여부
--- | --- | ---
1주차 | p.24~81 | ✅
2주차 | p.84~151 | ✅
3주차 | p.154~219 | ✅
4주차 | p.222~279 | ✅
5주차 | p.282~325 | 🍽️
6주차 | p.328~379 | 🍽️
7주차 | p.382~430 | 🍽️

---

# 1️⃣ 개념 정리

# 01. 객체지향 API로 그래프 꾸미기

---

핵심 키워드: `객체지향 API` `rcParams` `산점도` `컬러맵` `컬러 막대`

### 목차

- [가. pyplot 방식과 객체지향 API 방식](#가-pyplot-방식과-객체지향-api-방식)
- [나. 그래프에 한글 출력하기](#나-그래프에-한글-출력하기)
- [다. rcParams와 rc() 함수](#다-rcparams와-rc-함수)
- [라. 출판사별 데이터 추출하기](#라-출판사별-데이터-추출하기)
- [마. 객체지향 API로 산점도 그리기](#마-객체지향-api로-산점도-그리기)
- [바. 산점도의 마커 꾸미기](#바-산점도의-마커-꾸미기)
- [사. 컬러맵과 컬러 막대](#사-컬러맵과-컬러-막대)
- [★ 핵심 함수와 메서드](#-01-핵심-함수와-메서드)

---

## 가. pyplot 방식과 객체지향 API 방식

맷플롯립(Matplotlib)에서 그래프를 그리는 방법은 크게 두 가지로 나눌 수 있다.

| 방식 | 특징 | 적합한 경우 |
| --- | --- | --- |
| `pyplot` 방식 | `plt.plot()`, `plt.title()`과 같은 함수를 바로 사용 | 간단한 그래프 |
| 객체지향 API 방식 | `Figure`, `Axes` 객체를 직접 만든 뒤 메서드를 사용 | 복잡한 그래프, 여러 개의 서브플롯 |

> 하나의 그래프를 간단하게 그릴 때는 `pyplot` 방식이 편리하지만,  
> 여러 개의 그래프를 배치하거나 세부적으로 꾸밀 때는 객체지향 API 방식이 유리하다.

---

### 1. 그래프 DPI 설정

```python
import matplotlib.pyplot as plt

plt.rcParams['figure.dpi'] = 100
```

- `figure.dpi` : 그래프의 해상도를 설정
- DPI가 높을수록 그래프가 더 선명하게 출력

---

### 2. pyplot 방식

```python
plt.plot([1, 4, 9, 16])
plt.title('simple line graph')
plt.show()
```

`plot()`에 하나의 리스트만 전달하면 리스트의 값은 `y축`의 값으로 사용된다.

따라서

```python
[1, 4, 9, 16]
```

을 입력하면

| x | y |
| ---: | ---: |
| 0 | 1 |
| 1 | 4 |
| 2 | 9 |
| 3 | 16 |

과 같이 리스트의 인덱스가 자동으로 x축의 값이 된다.

---

### 3. 객체지향 API 방식

```python
fig, ax = plt.subplots()

ax.plot([1, 4, 9, 16])
ax.set_title('simple line graph')

fig.show()
```

구조는 다음과 같이 이해할 수 있다.

```text
Figure
└── Axes
    └── 실제 그래프
```

- `Figure` : 전체 그림을 담는 큰 도화지
- `Axes` : Figure 안에서 실제 그래프가 그려지는 영역
- `ax.plot()` : 해당 Axes에 그래프 출력
- `ax.set_title()` : 해당 Axes의 제목 설정

> 쉽게 생각하면  
> `fig` = 큰 도화지  
> `ax` = 도화지 위에 놓인 그래프 칸

---

### 4. pyplot과 객체지향 API 비교

pyplot | 객체지향 API
--- | ---
`plt.plot()` | `ax.plot()`
`plt.title()` | `ax.set_title()`
`plt.xlabel()` | `ax.set_xlabel()`
`plt.ylabel()` | `ax.set_ylabel()`
`plt.xlim()` | `ax.set_xlim()`
`plt.ylim()` | `ax.set_ylim()`
`plt.legend()` | `ax.legend()`

---

## 나. 그래프에 한글 출력하기

맷플롯립의 기본 폰트는 한글을 지원하지 않기 때문에 별도로 한글 폰트를 설정해야 한다.

### 1. Google Colab에서 나눔 폰트 설치

```python
import sys

if 'google.colab' in sys.modules:
    !echo 'debconf debconf/frontend select Noninteractive' | debconf-set-selections
    !sudo apt-get -qq -y install fonts-nanum
```

설치된 나눔 폰트를 맷플롯립에 등록한다.

```python
import matplotlib.font_manager as fm

font_files = fm.findSystemFonts(
    fontpaths=['/usr/share/fonts/truetype/nanum']
)

for fpath in font_files:
    fm.fontManager.addfont(fpath)
```

---

### 2. 맷플롯립 다시 불러오기

```python
import matplotlib.pyplot as plt

plt.rcParams['figure.dpi'] = 100
```

---

## 다. rcParams와 rc() 함수

### 1. rcParams

`rcParams`는 맷플롯립 그래프의 기본 설정값을 관리하는 객체이다.

현재 기본 폰트를 확인한다.

```python
plt.rcParams['font.family']
```

폰트를 `NanumGothic`으로 변경한다.

```python
plt.rcParams['font.family'] = 'NanumGothic'
```

---

### 2. rc() 함수

`rc()` 함수를 이용해서도 맷플롯립의 기본 설정을 변경할 수 있다.

```python
plt.rc('font', family='NanumBarunGothic')
```

폰트 종류와 크기를 동시에 설정할 수도 있다.

```python
plt.rc(
    'font',
    family='NanumBarunGothic',
    size=11
)
```

설정값을 확인한다.

```python
print(
    plt.rcParams['font.family'],
    plt.rcParams['font.size']
)
```

---

### 3. 한글 제목 출력

```python
plt.plot([1, 4, 9, 16])
plt.title('간단한 그래프')
plt.show()
```

폰트 크기를 다시 기본값으로 변경한다.

```python
plt.rc('font', size=10)
```

---

### ※ rcParams와 rc()의 차이

```python
plt.rcParams['font.family'] = 'NanumGothic'
```

처럼 속성을 직접 변경할 수도 있고,

```python
plt.rc('font', family='NanumGothic')
```

처럼 `rc()` 함수를 사용할 수도 있다.

둘 다 맷플롯립의 기본 설정값을 변경한다는 점은 동일하다.

---

## 라. 출판사별 데이터 추출하기

### 1. 데이터 불러오기

```python
import gdown

gdown.download(
    'https://bit.ly/3pK7iuu',
    'ns_book7.csv',
    quiet=False
)
```

```python
import pandas as pd

ns_book7 = pd.read_csv(
    'ns_book7.csv',
    low_memory=False
)

ns_book7.head()
```

---

### 2. 발행 도서가 많은 상위 30개 출판사 구하기

```python
top30_pubs = ns_book7['출판사'].value_counts()[:30]

top30_pubs
```

`value_counts()`는 각 값이 몇 번 등장하는지 계산하고 기본적으로 개수가 많은 순서대로 정렬한다.

따라서

```python
[:30]
```

을 사용하면 발행 도서 수가 많은 상위 30개 출판사를 추출할 수 있다.

---

### 3. isin()으로 상위 출판사 찾기

```python
top30_pubs_idx = ns_book7['출판사'].isin(
    top30_pubs.index
)

top30_pubs_idx
```

`isin()`은 각 데이터가 주어진 목록에 포함되는지를 검사한다.

```text
포함됨     → True
포함 안 됨 → False
```

즉, 데이터프레임 전체 길이와 동일한 불리언 배열을 생성한다.

---

### 4. True의 개수 구하기

```python
top30_pubs_idx.sum()
```

파이썬에서는

```text
True  = 1
False = 0
```

처럼 처리할 수 있으므로 불리언 배열에 `sum()`을 적용하면 `True`의 개수를 셀 수 있다.

---

### 5. sample()로 무작위 데이터 추출

데이터 전체가 너무 많으면 산점도가 지나치게 복잡해질 수 있다.

따라서 상위 30개 출판사의 데이터 중 1,000개만 무작위로 선택한다.

```python
ns_book8 = ns_book7[top30_pubs_idx].sample(
    1000,
    random_state=42
)

ns_book8.head()
```

- `1000` : 추출할 행의 개수
- `random_state=42` : 항상 동일한 무작위 결과를 얻도록 설정

> `random_state`는 난수 결과를 고정하는 역할을 한다.

---

## 마. 객체지향 API로 산점도 그리기

```python
fig, ax = plt.subplots(figsize=(10, 8))

ax.scatter(
    ns_book8['발행년도'],
    ns_book8['출판사']
)

ax.set_title('출판사별 발행 도서')

fig.show()
```

산점도의 구조는 다음과 같다.

항목 | 데이터
--- | ---
x축 | `발행년도`
y축 | `출판사`
점 하나 | 하나의 도서 데이터

---

## 바. 산점도의 마커 꾸미기

산점도에서는 각 점을 `마커(marker)`라고 한다.

마커의 크기·색상·투명도 등을 변경하면 하나의 그래프에 더 많은 정보를 표현할 수 있다.

---

### 1. 마커 크기 변경 : `s`

```python
fig, ax = plt.subplots(figsize=(10, 8))

ax.scatter(
    ns_book8['발행년도'],
    ns_book8['출판사'],
    s=ns_book8['대출건수']
)

ax.set_title('출판사별 발행 도서')

fig.show()
```

`s` 매개변수에 데이터와 동일한 길이의 배열을 넣으면 값에 따라 마커의 크기가 달라진다.

```text
대출건수 ↑
   ↓
마커 크기 ↑
```

---

### 2. alpha : 투명도

```python
alpha=0.3
```

범위는 일반적으로 다음과 같다.

```text
0 ←────────────→ 1
투명            불투명
```

데이터가 많이 겹치는 산점도에서는 작은 `alpha` 값을 사용하면 데이터 밀도를 확인하기 쉽다.

---

### 3. edgecolors : 마커 테두리 색상

```python
edgecolors='k'
```

`k`는 검은색을 의미한다.

마커가 서로 겹칠 때 경계를 구분하기 쉬워진다.

---

### 4. linewidths : 테두리 두께

```python
linewidths=0.5
```

마커 테두리의 두께를 설정한다.

---

### 5. c : 데이터에 따라 색상 변경

```python
c=ns_book8['대출건수']
```

각 데이터의 값에 따라 서로 다른 색상을 부여한다.

---

### 6. 여러 옵션을 동시에 적용

```python
fig, ax = plt.subplots(figsize=(10, 8))

ax.scatter(
    ns_book8['발행년도'],
    ns_book8['출판사'],
    linewidths=0.5,
    edgecolors='k',
    alpha=0.3,
    s=ns_book8['대출건수'] * 2,
    c=ns_book8['대출건수']
)

ax.set_title('출판사별 발행 도서')

fig.show()
```

### 주요 매개변수 정리

매개변수 | 의미
--- | ---
`s` | 마커 크기
`c` | 마커 색상에 대응할 값
`alpha` | 투명도
`edgecolors` | 마커 테두리 색상
`linewidths` | 마커 테두리 두께
`cmap` | 사용할 컬러맵

---

## 사. 컬러맵과 컬러 막대

### 1. 컬러맵(Color Map)

컬러맵은 수치에 따라 서로 다른 색을 연결한 색상표이다.

맷플롯립의 기본 산점도 컬러맵은 `viridis`이다.

```text
낮은 값 ───────────── 높은 값
진한 색                밝은 색
```

대표적인 컬러맵 가운데 하나인 `jet`은 대략 다음과 같이 변한다.

```text
낮은 값                         높은 값
파랑 → 초록 → 노랑 → 주황 → 빨강
```

---

### 2. cmap 사용하기

```python
fig, ax = plt.subplots(figsize=(10, 8))

sc = ax.scatter(
    ns_book8['발행년도'],
    ns_book8['출판사'],
    linewidths=0.5,
    edgecolors='k',
    alpha=0.3,
    s=ns_book8['대출건수'] ** 1.3,
    c=ns_book8['대출건수'],
    cmap='jet'
)

ax.set_title('출판사별 발행 도서')

fig.show()
```

---

### 3. 컬러 막대 추가하기

```python
fig.colorbar(sc)
```

전체 코드는 다음과 같다.

```python
fig, ax = plt.subplots(figsize=(10, 8))

sc = ax.scatter(
    ns_book8['발행년도'],
    ns_book8['출판사'],
    linewidths=0.5,
    edgecolors='k',
    alpha=0.3,
    s=ns_book8['대출건수'] ** 1.3,
    c=ns_book8['대출건수'],
    cmap='jet'
)

ax.set_title('출판사별 발행 도서')

fig.colorbar(sc)

fig.show()
```

`colorbar()`는 그래프에서 각각의 색상이 어떤 실제 수치에 대응하는지 확인할 수 있도록 해준다.

---

### ※ 마커 크기 사용 시 주의점

마커 크기는 데이터의 차이를 시각적으로 크게 보이게 만들 수 있다.

예를 들어

```python
s=ns_book8['대출건수'] ** 1.3
```

처럼 제곱을 사용하면 큰 값일수록 마커의 차이가 더 크게 나타난다.

따라서 마커 크기를 변환해서 표현했다면 어떤 방식으로 크기를 조절했는지 함께 밝혀주는 것이 좋다.

---

## ★ 01. 핵심 함수와 메서드

함수 / 메서드 | 기능
--- | ---
`plt.subplots()` | Figure와 Axes 객체 생성
`plt.rcParams` | 맷플롯립의 기본 설정값 관리
`plt.rc()` | rcParams의 설정값 변경
`Series.value_counts()` | 고유값별 데이터 개수 계산
`Series.isin()` | 값이 특정 목록에 포함되는지 검사
`DataFrame.sample()` | 데이터프레임에서 무작위 행 추출
`Axes.scatter()` | 산점도 출력
`Axes.set_title()` | 그래프 제목 지정
`Figure.colorbar()` | 컬러 막대 추가

---

---

# 02. 맷플롯립의 고급 기능 배우기

---

핵심 키워드: `범례` `피벗 테이블` `스택 영역 그래프` `스택 막대 그래프` `원 그래프` `서브플롯`

### 목차

- [가. 실습 데이터 준비](#가-실습-데이터-준비)
- [나. 하나의 피겨에 여러 개의 선 그래프 그리기](#나-하나의-피겨에-여러-개의-선-그래프-그리기)
- [다. 범례와 그래프 범위 설정](#다-범례와-그래프-범위-설정)
- [라. 피벗 테이블](#라-피벗-테이블)
- [마. 스택 영역 그래프](#마-스택-영역-그래프)
- [바. 여러 개의 막대 그래프](#바-여러-개의-막대-그래프)
- [사. 스택 막대 그래프](#사-스택-막대-그래프)
- [아. 원 그래프](#아-원-그래프)
- [자. 여러 그래프를 하나의 Figure에 배치](#자-여러-그래프를-하나의-figure에-배치)
- [차. 판다스로 여러 개의 그래프 그리기](#차-판다스로-여러-개의-그래프-그리기)
- [★ 핵심 함수와 메서드](#-02-핵심-함수와-메서드)

---

## 가. 실습 데이터 준비

```python
import matplotlib.pyplot as plt

plt.rc(
    'font',
    family='NanumBarunGothic'
)

plt.rcParams['figure.dpi'] = 100
```

```python
import gdown

gdown.download(
    'https://bit.ly/3pK7iuu',
    'ns_book7.csv',
    quiet=False
)
```

```python
import pandas as pd

ns_book7 = pd.read_csv(
    'ns_book7.csv',
    low_memory=False
)

ns_book7.head()
```

---

## 나. 하나의 피겨에 여러 개의 선 그래프 그리기

### 1. 상위 30개 출판사 추출

```python
top30_pubs = ns_book7['출판사'].value_counts()[:30]

top30_pubs_idx = ns_book7['출판사'].isin(
    top30_pubs.index
)
```

---

### 2. 필요한 열만 추출

```python
ns_book9 = ns_book7[top30_pubs_idx][
    ['출판사', '발행년도', '대출건수']
]
```

---

### 3. 출판사와 발행년도로 그룹화

```python
ns_book9 = ns_book9.groupby(
    by=['출판사', '발행년도']
).sum()
```

같은 출판사에서 같은 연도에 발생한 대출건수를 하나로 합친다.

구조는 다음과 같다.

```text
출판사 + 발행년도
        ↓
   같은 그룹끼리 묶기
        ↓
   대출건수 합계 계산
```

---

### 4. 인덱스 초기화

```python
ns_book9 = ns_book9.reset_index()
```

`groupby()`를 사용하면 그룹 기준 열이 인덱스로 이동하기 때문에 `reset_index()`로 일반 열로 되돌린다.

---

### 5. 출판사 2개의 데이터 만들기

```python
line1 = ns_book9[
    ns_book9['출판사'] == '황금가지'
]

line2 = ns_book9[
    ns_book9['출판사'] == '비룡소'
]
```

---

### 6. 선 그래프 2개 그리기

```python
fig, ax = plt.subplots(figsize=(8, 6))

ax.plot(
    line1['발행년도'],
    line1['대출건수']
)

ax.plot(
    line2['발행년도'],
    line2['대출건수']
)

ax.set_title('연도별 대출건수')

fig.show()
```

`plot()`을 여러 번 호출하면 하나의 Axes 안에 여러 개의 선을 겹쳐서 그릴 수 있다.

---

## 다. 범례와 그래프 범위 설정

### 1. label 지정

```python
fig, ax = plt.subplots(figsize=(8, 6))

ax.plot(
    line1['발행년도'],
    line1['대출건수'],
    label='황금가지'
)

ax.plot(
    line2['발행년도'],
    line2['대출건수'],
    label='비룡소'
)

ax.set_title('연도별 대출건수')

ax.legend()

fig.show()
```

---

### 범례(Legend)

범례는 그래프에 그려진 데이터의 이름과 색상을 알려주는 표이다.

```text
파란 선 → 황금가지
주황 선 → 비룡소
```

`plot()`의 `label`에 이름을 설정한 뒤

```python
ax.legend()
```

를 호출한다.

---

### 2. 상위 5개 출판사를 반복문으로 그리기

```python
fig, ax = plt.subplots(figsize=(8, 6))

for pub in top30_pubs.index[:5]:

    line = ns_book9[
        ns_book9['출판사'] == pub
    ]

    ax.plot(
        line['발행년도'],
        line['대출건수'],
        label=pub
    )

ax.set_title('연도별 대출건수')

ax.legend()

ax.set_xlim(1985, 2025)

fig.show()
```

반복문을 사용하면 출판사마다 코드를 직접 작성하지 않아도 된다.

---

### 3. 그래프 범위 설정

x축의 범위 설정

```python
ax.set_xlim(1985, 2025)
```

y축의 범위 설정

```python
ax.set_ylim(0, 13000)
```

pyplot 방식에서는

```python
plt.xlim(1985, 2025)
plt.ylim(0, 13000)
```

을 사용한다.

---

### 4. axis() 사용

x축과 y축의 범위를 한 번에 설정할 수도 있다.

```python
plt.axis([
    1985,
    2025,
    0,
    13000
])
```

순서는 다음과 같다.

```text
[
    x 최소,
    x 최대,
    y 최소,
    y 최대
]
```

객체지향 API에서도

```python
ax.axis([
    1985,
    2025,
    0,
    13000
])
```

처럼 사용한다.

---

## 라. 피벗 테이블

### 1. 피벗 테이블(Pivot Table)

피벗 테이블은 데이터를 원하는 기준에 따라 행과 열로 재배치하여 요약하는 방법이다.

예를 들어 원래 데이터가

출판사 | 발행년도 | 대출건수
--- | ---: | ---:
A출판사 | 2020 | 10
B출판사 | 2021 | 20
A출판사 | 2021 | 30

형태라면 피벗 테이블로

출판사 | 2020 | 2021
--- | ---: | ---:
A출판사 | 10 | 30
B출판사 | NaN | 20

형태로 바꿀 수 있다.

---

### 2. pivot_table()

```python
ns_book10 = ns_book9.pivot_table(
    index='출판사',
    columns='발행년도'
)

ns_book10.head()
```

- `index='출판사'` : 행에 출판사 배치
- `columns='발행년도'` : 열에 발행년도 배치

---

### 3. MultiIndex

위와 같이 `values`를 따로 지정하지 않으면 열 이름이 여러 단계로 구성될 수 있다.

```python
ns_book10.columns
```

예를 들면 다음과 같다.

```text
대출건수 / 2000
대출건수 / 2001
대출건수 / 2002
...
```

이러한 구조를 다단 인덱스 또는 `MultiIndex`라고 한다.

---

### 4. get_level_values()

발행년도만 가져온다.

```python
year_cols = ns_book10.columns.get_level_values(1)
```

상위 10개 출판사를 선택한다.

```python
top10_pubs = top30_pubs.index[:10]
```

---

## 마. 스택 영역 그래프

### 1. 스택 영역 그래프

스택 영역 그래프(Stacked Area Graph)는 여러 개의 그래프를 y축 방향으로 차례대로 쌓은 그래프이다.

```text
출판사 C  █████████████
출판사 B  ██████████
출판사 A  ██████
          ────────────
              연도
```

각 영역의 두께가 해당 데이터의 값을 의미한다.

---

### 2. stackplot()

```python
fig, ax = plt.subplots(figsize=(8, 6))

ax.stackplot(
    year_cols,
    ns_book10.loc[top10_pubs].fillna(0),
    labels=top10_pubs
)

ax.set_title('연도별 대출건수')

ax.legend(loc='upper left')

ax.set_xlim(1985, 2025)

fig.show()
```

---

### 3. fillna(0)를 사용하는 이유

맷플롯립은 누락된 값 `NaN`이 있을 경우 그래프를 제대로 표현하지 못하는 경우가 있다.

따라서

```python
.fillna(0)
```

을 사용하여 결측값을 0으로 바꾼다.

피벗 테이블을 만들 때 바로 처리할 수도 있다.

```python
pivot_table(
    ...,
    fill_value=0
)
```

---

## 바. 여러 개의 막대 그래프

### 1. 막대 그래프 2개 겹쳐 그리기

```python
fig, ax = plt.subplots(figsize=(8, 6))

ax.bar(
    line1['발행년도'],
    line1['대출건수'],
    label='황금가지'
)

ax.bar(
    line2['발행년도'],
    line2['대출건수'],
    label='비룡소'
)

ax.set_title('연도별 대출건수')
ax.legend()

fig.show()
```

막대 그래프는 선 그래프와 달리 내부가 채워져 있기 때문에 같은 위치에 그리면 뒤에 그린 막대가 앞의 막대를 가리게 된다.

---

### 2. 막대를 옆으로 나란히 배치

기본 막대 너비를 줄이고 x축 위치를 조금 이동시킨다.

```python
fig, ax = plt.subplots(figsize=(8, 6))

ax.bar(
    line1['발행년도'] - 0.2,
    line1['대출건수'],
    width=0.4,
    label='황금가지'
)

ax.bar(
    line2['발행년도'] + 0.2,
    line2['대출건수'],
    width=0.4,
    label='비룡소'
)

ax.set_title('연도별 대출건수')

ax.legend()

fig.show()
```

핵심은 다음과 같다.

```text
첫 번째 막대 : 원래 위치 - 0.2
두 번째 막대 : 원래 위치 + 0.2

막대 폭      : 0.4
```

---

## 사. 스택 막대 그래프

### 1. 스택 막대 그래프

여러 막대를 옆으로 놓는 대신 위로 쌓아서 표현하는 그래프이다.

```text
│     ███ C
│     ███
│     ███ B
│     ███
│     ███ A
└────────────
```

---

### 2. bottom 매개변수

맷플롯립의 `bar()`에는 스택 막대 그래프 전용 함수가 따로 없기 때문에 `bottom` 매개변수를 활용한다.

```python
height1 = [5, 4, 7, 9, 8]
height2 = [3, 2, 4, 1, 2]
```

첫 번째 막대

```python
plt.bar(
    range(5),
    height1,
    width=0.5
)
```

두 번째 막대를 첫 번째 막대 위에 배치

```python
plt.bar(
    range(5),
    height2,
    bottom=height1,
    width=0.5
)

plt.show()
```

즉,

```python
bottom=height1
```

은 두 번째 막대가 `height1`이 끝난 위치에서 시작하도록 만든다.

---

### 3. zip()으로 값 더하기

```python
height3 = [
    a + b
    for a, b in zip(height1, height2)
]
```

`zip()`은 여러 리스트의 같은 위치에 있는 값을 하나씩 묶는다.

```text
height1 : 5  4  7  9  8
height2 : 3  2  4  1  2
           ↓  ↓  ↓  ↓  ↓
height3 : 8  6 11 10 10
```

---

### 4. cumsum()

데이터가 많을 경우 값을 직접 더하는 대신 판다스의 `cumsum()`을 사용한다.

```python
ns_book12 = ns_book10.loc[top10_pubs].cumsum()
```

`cumsum()`은 누적 합을 계산한다.

예를 들어

```text
A : 10
B : 20
C : 30
```

이라면

```text
A : 10
B : 30
C : 60
```

으로 계산된다.

---

### 5. 누적값으로 스택 막대 그래프 그리기

```python
fig, ax = plt.subplots(figsize=(8, 6))

for i in reversed(range(len(ns_book12))):

    bar = ns_book12.iloc[i]
    label = ns_book12.index[i]

    ax.bar(
        year_cols,
        bar,
        label=label
    )

ax.set_title('연도별 대출건수')

ax.legend(loc='upper left')

ax.set_xlim(1985, 2025)

fig.show()
```

---

### ※ reversed()를 사용하는 이유

누적값이 가장 큰 막대를 먼저 그려야 한다.

작은 막대를 먼저 그린 뒤 큰 막대를 그리면 큰 막대가 앞의 막대를 덮어버리기 때문이다.

```python
reversed(range(len(ns_book12)))
```

을 이용하여 가장 큰 누적값부터 차례대로 그린다.

---

## 아. 원 그래프

### 1. 데이터 준비

상위 10개 출판사의 발행 도서 수를 사용한다.

```python
data = top30_pubs[:10]

labels = top30_pubs.index[:10]
```

---

### 2. pie()

```python
fig, ax = plt.subplots(figsize=(8, 6))

ax.pie(
    data,
    labels=labels
)

ax.set_title('출판사 도서 비율')

fig.show()
```

원 그래프(Pie Chart)는 전체 데이터에 대한 비율을 부채꼴 모양으로 표현한다.

---

### 3. startangle

원 그래프가 시작되는 위치를 조절한다.

```python
plt.pie(
    [10, 9],
    labels=['A제품', 'B제품'],
    startangle=90
)

plt.title('제품의 매출 비율')

plt.show()
```

```python
startangle=90
```

으로 설정하면 12시 방향에서 그래프가 시작된다.

---

### 4. autopct

부채꼴 위에 실제 비율을 표시한다.

```python
autopct='%.1f%%'
```

뜻은 다음과 같다.

```text
%.1f → 소수점 첫째 자리까지 표시
%%   → % 문자 출력
```

---

### 5. explode

특정 부채꼴을 원에서 떨어뜨려 강조한다.

```python
explode=[0.1] + [0] * 9
```

첫 번째 데이터만 원 중심에서 약간 떨어뜨린다.

---

### 6. 완성된 원 그래프

```python
fig, ax = plt.subplots(figsize=(8, 6))

ax.pie(
    data,
    labels=labels,
    startangle=90,
    autopct='%.1f%%',
    explode=[0.1] + [0] * 9
)

ax.set_title('출판사 도서 비율')

fig.show()
```

---

### ※ 원 그래프 사용 시 주의

원 그래프는 각 부채꼴의 크기가 비슷한 경우 데이터 사이의 차이를 정확하게 비교하기 어렵다.

따라서 가능한 경우

```python
autopct='%.1f%%'
```

처럼 실제 비율을 함께 표시하는 것이 좋다.

---

## 자. 여러 그래프를 하나의 Figure에 배치

### 1. 2 × 2 서브플롯

```python
fig, axes = plt.subplots(
    2,
    2,
    figsize=(20, 16)
)
```

생성되는 구조는 다음과 같다.

```text
axes[0, 0]    axes[0, 1]

axes[1, 0]    axes[1, 1]
```

---

### 2. 산점도

```python
ns_book8 = ns_book7[
    top30_pubs_idx
].sample(
    1000,
    random_state=42
)

sc = axes[0, 0].scatter(
    ns_book8['발행년도'],
    ns_book8['출판사'],
    linewidths=0.5,
    edgecolors='k',
    alpha=0.3,
    s=ns_book8['대출건수'],
    c=ns_book8['대출건수'],
    cmap='jet'
)

axes[0, 0].set_title(
    '출판사별 발행 도서'
)

fig.colorbar(
    sc,
    ax=axes[0, 0]
)
```

서브플롯 안에 컬러 막대를 넣을 때는

```python
ax=axes[0, 0]
```

처럼 컬러 막대를 연결할 Axes를 지정한다.

---

### 3. 스택 영역 그래프

```python
axes[0, 1].stackplot(
    year_cols,
    ns_book10.loc[top10_pubs].fillna(0),
    labels=top10_pubs
)

axes[0, 1].set_title(
    '연도별 대출건수'
)

axes[0, 1].legend(
    loc='upper left'
)

axes[0, 1].set_xlim(
    1985,
    2025
)
```

---

### 4. 스택 막대 그래프

```python
for i in reversed(
    range(len(ns_book12))
):

    bar = ns_book12.iloc[i]
    label = ns_book12.index[i]

    axes[1, 0].bar(
        year_cols,
        bar,
        label=label
    )

axes[1, 0].set_title(
    '연도별 대출건수'
)

axes[1, 0].legend(
    loc='upper left'
)

axes[1, 0].set_xlim(
    1985,
    2025
)
```

---

### 5. 원 그래프

```python
axes[1, 1].pie(
    data,
    labels=labels,
    startangle=90,
    autopct='%.1f%%',
    explode=[0.1] + [0] * 9
)

axes[1, 1].set_title(
    '출판사 도서 비율'
)
```

---

### 6. 그래프 이미지 저장

```python
fig.savefig(
    'all_in_one.png'
)

fig.show()
```

`savefig()`는 완성한 Figure 전체를 이미지 파일로 저장한다.

---

## 차. 판다스로 여러 개의 그래프 그리기

판다스 데이터프레임도 내부적으로 맷플롯립을 활용하여 그래프를 그릴 수 있다.

단순한 그래프는 판다스를 이용하면 코드가 훨씬 짧아진다.

다만 세밀한 설정이 필요하면 맷플롯립을 직접 사용하는 것이 좋다.

---

### 1. pivot_table() 다시 구성하기

이번에는

```text
행    → 발행년도
열    → 출판사
값    → 대출건수
```

형태로 피벗 테이블을 만든다.

```python
ns_book11 = ns_book9.pivot_table(
    index='발행년도',
    columns='출판사',
    values='대출건수'
)
```

```python
ns_book11.loc[2000:2005]
```

---

### 2. values를 사용하는 이유

```python
values='대출건수'
```

를 지정하면 피벗 테이블이 어떤 데이터를 실제 값으로 사용할지 명확하게 정할 수 있다.

따라서 앞에서처럼 열 이름이

```text
대출건수 / 2000
대출건수 / 2001
```

형태의 MultiIndex로 생성되는 것을 피할 수 있다.

---

### 3. groupby()와 pivot_table() 비교

| 메서드 | 특징 |
| --- | --- |
| `groupby()` | 그룹 기준 열들이 인덱스로 구성 |
| `pivot_table()` | 그룹 기준을 행과 열로 나누어 배치 |

둘 다 데이터를 특정 기준으로 묶어 집계한다는 점은 비슷하다.

---

### 4. aggfunc

원본 데이터에서 바로 피벗 테이블을 만들 경우 같은 출판사·같은 연도의 데이터가 여러 개 있을 수 있다.

따라서 값을 어떻게 합칠 것인지 지정해야 한다.

```python
import numpy as np

ns_book11 = ns_book7[
    top30_pubs_idx
].pivot_table(
    index='발행년도',
    columns='출판사',
    values='대출건수',
    aggfunc=np.sum
)
```

- 기본 집계 방식 : 평균
- `aggfunc=np.sum` : 합계 계산

---

### 5. 판다스로 스택 영역 그래프

```python
fig, ax = plt.subplots(figsize=(8, 6))

ns_book11[
    top10_pubs
].plot.area(
    ax=ax,
    title='연도별 대출건수',
    xlim=(1985, 2025)
)

ax.legend(
    loc='upper left'
)

fig.show()
```

맷플롯립의

```python
ax.stackplot()
```

과 비슷한 결과를 훨씬 간단한 코드로 만들 수 있다.

---

### 6. 판다스로 스택 막대 그래프

판다스의 `plot.bar()`는 기본적으로 여러 막대를 나란히 배치한다.

```python
DataFrame.plot.bar()
```

그러나

```python
stacked=True
```

를 지정하면 자동으로 스택 막대 그래프를 그린다.

```python
fig, ax = plt.subplots(figsize=(8, 6))

ns_book11.loc[
    1985:2025,
    top10_pubs
].plot.bar(
    ax=ax,
    title='연도별 대출건수',
    stacked=True,
    width=0.8
)

ax.legend(
    loc='upper left'
)

fig.show()
```

맷플롯립으로 직접 스택 막대 그래프를 그릴 때처럼 미리 `cumsum()`을 사용할 필요가 없다.

---

## ※ Matplotlib과 Pandas 그래프 비교

기능 | Matplotlib | Pandas
--- | --- | ---
선 그래프 | `ax.plot()` | `df.plot()`
스택 영역 그래프 | `ax.stackplot()` | `df.plot.area()`
막대 그래프 | `ax.bar()` | `df.plot.bar()`
스택 막대 그래프 | `bottom` 또는 누적값 필요 | `stacked=True`
세밀한 설정 | 매우 자유로움 | 상대적으로 제한적
코드 길이 | 비교적 김 | 비교적 짧음

> 간단하고 빠르게 그래프를 만들 때 → `Pandas`  
> 그래프를 세밀하게 꾸밀 때 → `Matplotlib`

---

## ★ 02. 핵심 함수와 메서드

함수 / 메서드 | 기능
--- | ---
`Axes.plot()` | 선 그래프 출력
`Axes.legend()` | 그래프에 범례 추가
`Axes.set_xlim()` | x축 출력 범위 지정
`Axes.set_ylim()` | y축 출력 범위 지정
`Axes.axis()` | x축·y축 범위 동시 지정
`DataFrame.groupby()` | 특정 열을 기준으로 데이터를 그룹화
`DataFrame.reset_index()` | 인덱스를 일반 열로 변환
`DataFrame.pivot_table()` | 피벗 테이블 생성
`MultiIndex.get_level_values()` | 다단 인덱스에서 특정 단계의 값 추출
`Axes.stackplot()` | 스택 영역 그래프 출력
`DataFrame.fillna()` | 누락값 변경
`Axes.bar()` | 막대 그래프 출력
`DataFrame.cumsum()` | 누적 합 계산
`Axes.pie()` | 원 그래프 출력
`plt.subplots()` | 여러 개의 서브플롯 생성
`Figure.colorbar()` | 컬러 막대 추가
`Figure.savefig()` | 그래프를 이미지 파일로 저장
`DataFrame.plot.area()` | 판다스로 스택 영역 그래프 출력
`DataFrame.plot.bar()` | 판다스로 막대 그래프 출력

---

# 2️⃣ 핵심 개념 한눈에 정리

개념 | 의미 | 대표 코드
--- | --- | ---
객체지향 API | Figure와 Axes 객체를 직접 다루는 그래프 작성 방식 | `fig, ax = plt.subplots()`
rcParams | 맷플롯립 기본 설정 관리 | `plt.rcParams[...]`
범례 | 그래프의 색·선과 데이터 이름을 연결 | `ax.legend()`
컬러맵 | 수치에 따라 색상을 대응 | `cmap='jet'`
컬러 막대 | 색상이 의미하는 실제 수치를 표시 | `fig.colorbar(sc)`
피벗 테이블 | 데이터를 행·열 기준으로 재구성 | `pivot_table()`
스택 영역 그래프 | 여러 영역을 y방향으로 쌓음 | `stackplot()`
스택 막대 그래프 | 여러 막대를 y방향으로 쌓음 | `bar(bottom=...)`
누적 합 | 앞의 값을 계속 더해 나감 | `cumsum()`
원 그래프 | 전체에서 각 항목의 비율을 표현 | `pie()`
서브플롯 | 하나의 Figure 안에 여러 그래프 배치 | `plt.subplots(2, 2)`

---

# 3️⃣ 그래프 선택 기준

상황 | 적합한 그래프
--- | ---
시간에 따른 값의 변화 | 선 그래프
두 변수 사이의 관계 | 산점도
여러 집단의 시간별 구성 변화 | 스택 영역 그래프
항목별 크기 비교 | 막대 그래프
전체값과 구성 요소를 동시에 비교 | 스택 막대 그래프
전체에서 각 항목이 차지하는 비율 | 원 그래프
서로 다른 그래프를 한 화면에서 비교 | 서브플롯

---

# 4️⃣ 이번 주 핵심 코드 흐름

```text
데이터 불러오기
      ↓
value_counts()
출판사별 데이터 개수 확인
      ↓
isin()
원하는 출판사 데이터만 선택
      ↓
groupby()
출판사 × 연도별 집계
      ↓
pivot_table()
그래프에 적합한 형태로 데이터 변환
      ↓
Matplotlib / Pandas
그래프 작성
      ↓
legend / colorbar / title
그래프 정보 추가
      ↓
savefig()
완성된 그래프 저장
```

---

# 5️⃣ 이번 주에 특히 기억할 것

### ① 단순한 그래프

```python
plt.plot(...)
```

### ② 복잡한 그래프

```python
fig, ax = plt.subplots()

ax.plot(...)
```

### ③ 여러 데이터를 하나의 그래프에 표시

```python
ax.plot(..., label='A')
ax.plot(..., label='B')

ax.legend()
```

### ④ 데이터를 그래프에 맞는 형태로 변환

```python
df.pivot_table(...)
```

### ⑤ 누적 그래프

```python
df.cumsum()
```

### ⑥ 스택 영역 그래프

```python
ax.stackplot(...)
```

### ⑦ 판다스 스택 막대 그래프

```python
df.plot.bar(
    stacked=True
)
```

### ⑧ 원 그래프의 비율 표시

```python
ax.pie(
    data,
    autopct='%.1f%%'
)
```

### ⑨ 여러 그래프를 한 화면에 출력

```python
fig, axes = plt.subplots(
    2,
    2
)
```

### ⑩ 그래프 저장

```python
fig.savefig(
    'all_in_one.png'
)
```

## 02. 선 그래프와 막대 그래프 그리기

<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->


# 2️⃣ 수행 인증

<!-- 교재에서 안내된 과정을 직접 실행해본 뒤, 진행 결과가 보이도록 4~6장의 스크린샷을 캡처하여 아래에 첨부해주세요.-->



<br>
<br>

# 3️⃣ 확인 문제

## 문제 1.

> **🧚Q. 다음 데이터를 이용하여 matplotlib으로 선그래프를 그리는 코드를 작성해주세요.**
- x = [1, 2, 3, 4, 5]
- y = [2, 4, 6, 8, 10]
> 조건은 아래와 같습니다.
```
1️⃣ 제목은 "Linear Trend"로 설정해주세요.
2️⃣ x축 이름은 "X values"로 설정해주세요.
3️⃣ y축 이름은 "Y values"로 설정해주세요.
4️⃣ 마커(marker)를 포함하여 선그래프를 그려주세요.
```

```
여기에 코드를 작성해주세요!
```



### 🎉 수고하셨습니다.
