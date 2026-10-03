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

# 05-1. 맷플롯립 기본 요소 알아보기

---

> 핵심 키워드 : `Figure` `rcParams` `Axis` `Marker` `Subplot`

### 목차

- [1. Figure 객체](#1-figure-객체)
- [2. 그래프 크기 조절하기](#2-그래프-크기-조절하기)
- [3. figsize와 DPI](#3-figsize와-dpi)
- [4. rcParams 객체](#4-rcparams-객체)
- [5. 마커 모양 바꾸기](#5-마커-모양-바꾸기)
- [6. Figure · Axes · Axis 구조](#6-figure--axes--axis-구조)
- [7. 여러 개의 서브플롯 출력하기](#7-여러-개의-서브플롯-출력하기)
- [8. 서브플롯을 가로로 배치하기](#8-서브플롯을-가로로-배치하기)
- [핵심 함수와 메서드](#05-1-핵심-함수와-메서드)

---

## 1. Figure 객체

`Figure`는 맷플롯립 그래프를 구성하는 모든 요소를 담는 **최상위 객체**이다.

`scatter()`와 같은 그래프 함수를 실행하면 Figure 객체가 자동으로 만들어지지만,

```python
plt.figure()
```

를 사용하면 Figure 객체를 명시적으로 생성하여 크기나 해상도 등의 옵션을 조절할 수 있다.

### `alpha`

산점도를 그리기 위해 맷플롯립을 불러온다.

```python
import matplotlib.pyplot as plt

plt.scatter(
    ns_book7['도서권수'],
    ns_book7['대출건수'],
    alpha=0.1
)

plt.show()
```

이때, **alpha**는 산점도 마커의 **투명도**를 조절한다. 값이 작을수록 점이 더 투명하게 나타난다.

---

## 2. 그래프 크기 조절하기

### `figure()` + `figsize`

```python
plt.figure(
    figsize=(9, 6)
)

plt.scatter(
    ns_book7['도서권수'],
    ns_book7['대출건수'],
    alpha=0.1
)

plt.show()
```

`figsize`는 Figure의 크기를 지정한다.

```python
figsize=(너비, 높이)
```

단위는 **인치**(inch)이다.

현재 맷플롯립의 기본 Figure 크기는 다음과 같이 확인할 수 있다.

```python
print(
    plt.rcParams['figure.figsize']
)
```

---

## 3. figsize와 DPI

그래프의 실제 이미지 크기는 `figsize`만으로 결정되지 않는다.

함께 알아야 할 값이 **DPI**이다.

### DPI

DPI는 `Dots Per Inch`의 약자로, 1인치를 몇 개의 점 또는 픽셀로 표현할 것인지를 나타내는 값이다. PPI(Pixels Per Inch)라고도 한다.

---

### 기본 DPI 확인

```python
print(
    plt.rcParams['figure.dpi']
)
```

맷플롯립의 기본 DPI는 **버전과 실행 환경에 따라 달라질 수 있다.**

따라서 특정 값을 무조건 가정하지 말고 `rcParams`로 확인하는 것이 좋다.

---

### 픽셀 크기와 figsize의 관계

대략적인 관계는 다음과 같다.

```text
픽셀 크기 = 인치 크기 × DPI
```

따라서 반대로 원하는 픽셀 크기를 인치로 바꾸려면

```text
인치 크기 = 원하는 픽셀 크기 ÷ DPI
```

를 사용한다.

교재에서는 DPI가 72인 환경을 기준으로 900 × 600 픽셀 크기의 그래프를 다음처럼 만든다.

```python
plt.figure(
    figsize=(900/72, 600/72)
)

plt.scatter(
    ns_book7['도서권수'],
    ns_book7['대출건수'],
    alpha=0.1
)

plt.show()
```

> 주의! 현재 실행 환경의 DPI가 72가 아니라면 결과 픽셀 크기도 달라진다.

---

### Colab의 타이트 레이아웃

코랩에서는 그래프 주변의 여백을 자동으로 줄여 출력하기 때문에  
실제 저장된 그림 크기가 예상보다 작아질 수 있다.

타이트 레이아웃을 사용하지 않으려면 다음과 같이 설정한다.

```python
%config InlineBackend.print_figure_kwargs = {'bbox_inches': None}
```

```python
plt.figure(
    figsize=(900/72, 600/72)
)

plt.scatter(
    ns_book7['도서권수'],
    ns_book7['대출건수'],
    alpha=0.1
)

plt.show()
```

다시 기본적인 타이트 레이아웃으로 되돌린다.

```python
%config InlineBackend.print_figure_kwargs = {'bbox_inches': 'tight'}
```

---

### `dpi` 매개변수로 크기와 해상도 조절

`figsize` 대신 Figure의 `dpi` 값을 변경할 수도 있다.

```python
plt.figure(
    dpi=144
)

plt.scatter(
    ns_book7['도서권수'],
    ns_book7['대출건수'],
    alpha=0.1
)

plt.show()
```

DPI가 커지면 인치당 픽셀 수가 증가하므로 그래프가 더 크게 표현되며,  
축의 숫자나 마커 등 그래프 구성 요소도 함께 커진다.

### 핵심 구분

| 요소 | 의미 |
| --- | --- |
| `figsize` | 그래프를 그리는 캔버스의 크기 |
| `dpi` | 인치당 표현하는 픽셀의 수 |
| `figsize × dpi` | 최종 이미지 크기와 관련 |

---

## 4. rcParams 객체

`rcParams`는 맷플롯립 그래프의 **기본 설정값을 관리하는 객체**로서, runtime configuration parameters의 약자이다.

쉽게 말하면 **맷플롯립이 실행될 때 사용하는 기본 설정값 모음**이라고 이해할 수 있다.

설정값을 읽는 것뿐 아니라 직접 바꿀 수도 있다. 이때, 변경된 값은 이후에 만들어지는 그래프에 적용된다.

---

### Figure의 DPI 기본값 변경

```python
plt.rcParams['figure.dpi'] = 100
```

이후부터 생성되는 그래프의 기본 DPI가 100으로 설정된다.

---

### 현재 산점도 마커 확인

```python
plt.rcParams['scatter.marker']
```

기본값

```text
'o'
```

`'o'`는 동그라미 모양을 의미한다.

---

## 5. 마커 모양 바꾸기

### 전체 산점도의 기본 마커 변경

```python
plt.rcParams['scatter.marker'] = '*'
```

이후 그리는 산점도의 기본 마커가 별표(`*`)로 바뀐다.

---

### 특정 그래프의 마커만 변경

그래프마다 다른 마커를 사용하고 싶다면 `rcParams` 자체를 바꾸기보다  
`scatter()`의 `marker` 매개변수를 사용한다.

```python
plt.scatter(
    ns_book7['도서권수'],
    ns_book7['대출건수'],
    alpha=0.1,
    marker='+'
)

plt.show()
```

### 차이

```text
rcParams['scatter.marker']
    ↓
이후 산점도의 기본값 자체를 변경

marker='+'
    ↓
현재 그리는 산점도에만 적용
```

---

## 6. Figure · Axes · Axis 구조

맷플롯립 그래프의 구조는 다음과 같이 이해할 수 있다.

```text
Figure
│
├── Axes (서브플롯)
│    ├── x Axis
│    └── y Axis
│
└── Axes (서브플롯)
     ├── x Axis
     └── y Axis
```

### Figure : 큰 도화지 전체

그래프의 모든 요소를 담는 가장 큰 객체, 즉 그래프 전체라고 이야기할 수 있다.

### Axes : 도화지 안의 개별 그래프 칸

Figure 안에서 **실제 그래프가 그려지는 영역**

일반적으로 하나의 `Axes` 객체를 하나의 **서브플롯**(subplot)이라고 부른다.

서브플롯이란, 쉽게 말하면 한 장의 큰 그림(Figure) 안에 들어가는 각각의 작은 그래프 칸이다.

### Axis : 그 subplot을 나타내는 객체

그래프의 좌표축을 표현하는 객체이다.

2차원 그래프라면 x축과 y축 두 개의 Axis가 존재한다.

Axis에는 눈금(tick)과 축 이름(label) 등이 포함된다.

> 주의! `Axes`와 `Axis`는 서로 다른 개념이므로 구분한다.


---

## 7. 여러 개의 서브플롯 출력하기

하나의 Figure 안에 여러 개의 그래프를 넣을 때 `subplots()`를 사용한다.

### 세로 방향으로 2개 출력

```python
fig, axs = plt.subplots(2)

axs[0].scatter(
    ns_book7['도서권수'],
    ns_book7['대출건수'],
    alpha=0.1
)

axs[1].hist(
    ns_book7['대출건수'],
    bins=100
)

axs[1].set_yscale('log')

fig.show()
```

`subplots(2)`라면 2행 × 1열 구조의 서브플롯을 만든다.

```text
axs[0]
────────

axs[1]
────────
```

---

### Figure 크기 함께 조절

```python
fig, axs = plt.subplots(
    2,
    figsize=(6, 8)
)

axs[0].scatter(
    ns_book7['도서권수'],
    ns_book7['대출건수'],
    alpha=0.1
)

axs[0].set_title(
    'scatter plot'
)

axs[1].hist(
    ns_book7['대출건수'],
    bins=100
)

axs[1].set_title(
    'histogram'
)

axs[1].set_yscale(
    'log'
)

fig.show()
```

### 제목 설정

```python
Axes.set_title()
```

각각의 서브플롯에 제목을 설정한다.

---

## 8. 서브플롯을 가로로 배치하기

`subplots()`의 첫 번째 값에는 **행의 개수**,  
두 번째 값에는 **열의 개수**를 지정한다.

```python
plt.subplots(
    행,
    열
)
```

1행 2열로 만들면 두 그래프가 가로로 나란히 배치된다.

```python
fig, axs = plt.subplots(
    1,
    2,
    figsize=(10, 4)
)

axs[0].scatter(
    ns_book7['도서권수'],
    ns_book7['대출건수'],
    alpha=0.1
)

axs[0].set_title(
    'scatter plot'
)

axs[0].set_xlabel(
    'number of books'
)

axs[0].set_ylabel(
    'borrow count'
)


axs[1].hist(
    ns_book7['대출건수'],
    bins=100
)

axs[1].set_title(
    'histogram'
)

axs[1].set_yscale(
    'log'
)

axs[1].set_xlabel(
    'borrow count'
)

axs[1].set_ylabel(
    'frequency'
)

fig.show()
```

### 서브플롯 관련 메서드

| 메서드 | 기능 |
| --- | --- |
| `set_title()` | 그래프 제목 설정 |
| `set_xlabel()` | x축 이름 설정 |
| `set_ylabel()` | y축 이름 설정 |
| `set_xscale()` | x축 스케일 설정 |
| `set_yscale()` | y축 스케일 설정 |

---

# 05-1 핵심 정리

| 개념 | 핵심 |
| --- | --- |
| `Figure` | 맷플롯립 그래프의 모든 요소를 담는 최상위 객체 |
| `rcParams` | 맷플롯립의 기본 설정값을 관리 |
| `Axis` | x축·y축과 같은 좌표축 |
| `Axes` | 실제 그래프가 그려지는 영역 |
| `Marker` | 데이터 포인트를 표시하는 모양 |
| `Subplot` | Figure 안에 들어가는 각각의 그래프 영역 |

---

## 05-1 핵심 함수와 메서드

| 함수 / 메서드 | 기능 |
| --- | --- |
| `matplotlib.pyplot.figure()` | Figure 객체 생성 |
| `matplotlib.pyplot.subplots()` | Figure와 서브플롯 생성 |
| `Axes.set_xscale()` | x축 스케일 지정 |
| `Axes.set_yscale()` | y축 스케일 지정 |
| `Axes.set_title()` | 서브플롯 제목 지정 |
| `Axes.set_xlabel()` | x축 이름 지정 |
| `Axes.set_ylabel()` | y축 이름 지정 |

---

---

# 05-2. 선 그래프와 막대 그래프 그리기

---

> 핵심 키워드 : `선 그래프` `막대 그래프`

### 목차

- [1. 연도별 발행 도서 개수 구하기](#1-연도별-발행-도서-개수-구하기)
- [2. 주제별 도서 개수 구하기](#2-주제별-도서-개수-구하기)
- [3. 선 그래프 그리기](#3-선-그래프-그리기)
- [4. 선 모양 · 마커 · 색상 변경](#4-선-모양--마커--색상-변경)
- [5. 그래프 눈금 조절](#5-그래프-눈금-조절)
- [6. 그래프에 데이터값 표시하기](#6-그래프에-데이터값-표시하기)
- [7. 막대 그래프 그리기](#7-막대-그래프-그리기)
- [8. 막대와 텍스트 꾸미기](#8-막대와-텍스트-꾸미기)
- [9. 가로 막대 그래프](#9-가로-막대-그래프)
- [10. 이미지 읽고 출력하기](#10-이미지-읽고-출력하기)
- [11. 이미지와 그래프 저장하기](#11-이미지와-그래프-저장하기)
- [핵심 함수와 메서드](#05-2-핵심-함수와-메서드)

---

## 선 그래프와 막대 그래프

### 선 그래프(Line Graph)

데이터 포인트 사이를 선으로 연결한 그래프

시간의 흐름 등에 따른 **데이터의 변화**를 살펴보는 데 적합하다.

### 막대 그래프(Bar Graph)

데이터 포인트의 크기를 막대의 높이 또는 길이로 표현한 그래프

**범주별 값**을 서로 비교할 때 유용하다.

---

## 1. 연도별 발행 도서 개수 구하기

### `value_counts()`

연도별 도서 개수를 계산한다.

```python
count_by_year = (
    ns_book7['발행년도']
    .value_counts()
)

count_by_year
```

`value_counts()`는 고유한 값이 각각 몇 번 등장하는지 계산한다.

기본적으로 **개수가 많은 순서**로 결과가 정렬된다.

하지만 발행년도는 시간의 흐름에 따라 표현해야 하므로  
연도순으로 다시 정렬한다.

---

### `sort_index()`

```python
count_by_year = (
    count_by_year.sort_index()
)

count_by_year
```

시리즈의 **인덱스 순서**를 기준으로 정렬한다.

```text
value_counts()
    ↓
도서 개수가 많은 순

sort_index()
    ↓
발행년도 순
```

---

### 잘못된 미래 연도 제거

데이터에는 2030년 이후와 같이 현실적으로 잘못된 발행년도가 포함되어 있다.

교재에서는 2030년 이하의 데이터만 사용한다.

```python
count_by_year = count_by_year[
    count_by_year.index <= 2030
]

count_by_year
```

시리즈에서도 불리언 인덱싱을 이용해 원하는 데이터만 선택할 수 있다.

---

## 2. 주제별 도서 개수 구하기

`주제분류번호`의 첫 번째 문자를 이용해 도서의 큰 주제를 구분한다.

예를 들어 교재에서는

```text
1 → 철학
2 → 종교
8 → 문학
```

처럼 설명한다.

단, `주제분류번호`에는 누락값 `NaN`도 있기 때문에 이를 처리해야 한다.

---

### 첫 번째 문자 추출 함수

```python
import numpy as np

def kdc_1st_char(no):
    if no is np.nan:
        return '-1'
    else:
        return no[0]
```

> 위 함수는 교재에 제시된 코드 그대로이다.

---

### `apply()` + `value_counts()`

```python
count_by_subject = (
    ns_book7['주제분류번호']
    .apply(kdc_1st_char)
    .value_counts()
)

count_by_subject
```

흐름은 다음과 같다.

```text
주제분류번호
    ↓
apply(kdc_1st_char)
    ↓
첫 번째 문자만 추출
    ↓
value_counts()
    ↓
주제별 도서 개수 계산
```

---

### 명목형 데이터와 순서형 데이터

교재에서는 범주형 데이터를 설명하면서 다음을 구분한다.

| 종류 | 의미 | 예 |
| --- | --- | --- |
| 명목형 데이터 | 범주 사이에 순서가 없음 | 성별, 국가 |
| 순서형 데이터 | 범주 사이에 순서가 있음 | 만족도, 성적 등급 |

도서의 주제분류번호는 범주 사이의 크고 작음에 의미가 없으므로  
교재에서는 **명목형 데이터**의 예로 설명한다.

---

## 3. 선 그래프 그리기

먼저 그래프 해상도를 높인다.

```python
import matplotlib.pyplot as plt

plt.rcParams['figure.dpi'] = 100
```

---

### `plot()`

```python
plt.plot(
    count_by_year.index,
    count_by_year.values
)

plt.title(
    'Books by year'
)

plt.xlabel(
    'year'
)

plt.ylabel(
    'number of books'
)

plt.show()
```

### 각 함수 역할

| 함수 | 역할 |
| --- | --- |
| `plot()` | 선 그래프 생성 |
| `title()` | 그래프 제목 설정 |
| `xlabel()` | x축 이름 설정 |
| `ylabel()` | y축 이름 설정 |

---

### Series 자체를 전달하기

판다스 Series를 `plot()`에 바로 전달할 수도 있다.

이 경우 시리즈의

```text
index → x축
value → y축
```

으로 사용된다.

```python
plt.plot(
    count_by_year
)
```

---

## 4. 선 모양 · 마커 · 색상 변경

`plot()`은 그래프의 모양을 다양하게 조절할 수 있다.

### 마커 + 선 스타일 + 색상

```python
plt.plot(
    count_by_year,
    marker='.',
    linestyle=':',
    color='red'
)

plt.title('Books by year')
plt.xlabel('year')
plt.ylabel('number of books')

plt.show()
```

---

### `linestyle`

대표적인 선 스타일

| 값 | 형태 |
| --- | --- |
| `'-'` | 실선 |
| `':'` | 점선 |
| `'--'` | 파선 |
| `'-.'` | 쇄선 |

---

### `marker`

```python
marker='.'
```

데이터 포인트의 위치를 마커로 표시하면 실제 데이터 포인트의 위치를 더 명확하게 확인할 수 있다.

---

### 포맷 문자열로 한 번에 지정

마커, 선 모양, 색상을 하나의 문자열로 지정할 수도 있다.

```python
plt.plot(
    count_by_year,
    '*-g'
)

plt.title('Books by year')
plt.xlabel('year')
plt.ylabel('number of books')

plt.show()
```

```text
* → 별 모양 마커
- → 실선
g → green
```

---

## 5. 그래프 눈금 조절

그래프의 눈금을 **tick**이라고 한다.

### x축 눈금 : `xticks()`

```python
plt.xticks(
    range(1947, 2030, 10)
)
```

1947년부터 10년 간격으로 x축 눈금을 표시한다.

### y축 눈금

```python
plt.yticks(...)
```

객체지향 방식의 서브플롯에서는

```python
ax.set_xticks(...)
ax.set_yticks(...)
```

를 사용한다.

### scale과 tick의 구분

```text
scale = 자의 눈금 체계 자체
tick = 그 자에 실제로 찍혀 있는 눈금 하나하나
```

---

## 6. 그래프에 데이터값 표시하기

### `annotate()`

특정 좌표에 텍스트를 표시한다.

```python
plt.plot(
    count_by_year,
    '*-g'
)

plt.title('Books by year')
plt.xlabel('year')
plt.ylabel('number of books')

plt.xticks(
    range(1947, 2030, 10)
)

for idx, val in count_by_year[::5].items():
    plt.annotate(
        val,
        (idx, val)
    )

plt.show()
```

### `items()`

Series의 **인덱스와 값**을 함께 가져온다.

```python
for idx, val in series.items():
```

---

### 텍스트 위치 이동

```python
plt.annotate(
    val,
    (idx, val),
    xytext=(idx + 1, val + 10)
)
```

하지만 x축과 y축의 스케일이 크게 다르면 데이터 좌표 기준 이동량을 조절하기 어렵다.

---

### 포인트 단위로 상대 위치 지정

```python
plt.annotate(
    val,
    (idx, val),
    xytext=(2, 2),
    textcoords='offset points'
)
```

```text
xytext=(2, 2)
    ↓
원래 위치에서 오른쪽 2포인트,
위쪽 2포인트 이동
```

1포인트는 `1/72 인치`이다.

마커에서 일정한 간격으로 텍스트를 띄울 때 포인트나 픽셀과 같은 상대 단위를 사용하는 것이 효과적이다.

---

## 7. 막대 그래프 그리기

### `bar()`

```python
plt.bar(
    count_by_subject.index,
    count_by_subject.values
)

plt.title(
    'Books by subject'
)

plt.xlabel(
    'subject'
)

plt.ylabel(
    'number of books'
)

for idx, val in count_by_subject.items():
    plt.annotate(
        val,
        (idx, val),
        xytext=(0, 2),
        textcoords='offset points'
    )

plt.show()
```

`bar()`에는 x축은 각 범주, y축은 각 범주의 값을 전달한다.

---

## 8. 막대와 텍스트 꾸미기

### 막대 너비 : `width`

```python
width=0.7
```

세로 막대 그래프의 두께를 지정하며, 기본값(별도 지시가 없을 경우)은 `0.8`이다.

---

### 텍스트 가로 정렬 : `ha`

```python
ha='center'
```

`ha`는 **horizontal alignment**를 의미한다.

막대의 중앙에 텍스트의 중앙을 맞춘다.

---

### 최종 완성 코드

```python
plt.bar(
    count_by_subject.index,
    count_by_subject.values,
    width=0.7,
    color='blue'
)

plt.title('Books by subject')
plt.xlabel('subject')
plt.ylabel('number of books')

for idx, val in count_by_subject.items():
    plt.annotate(
        val,
        (idx, val),
        xytext=(0, 2),
        textcoords='offset points',
        fontsize=8,
        ha='center',
        color='green'
    )

plt.show()
```

---

## 9. 가로 막대 그래프

### `barh()`

가로 방향 막대 그래프를 만든다.

```python
plt.barh(
    count_by_subject.index,
    count_by_subject.values,
    height=0.7,
    color='blue'
)

plt.title('Books by subject')

plt.xlabel(
    'number of books'
)

plt.ylabel(
    'subject'
)

for idx, val in count_by_subject.items():
    plt.annotate(
        val,
        (val, idx),
        xytext=(2, 0),
        textcoords='offset points',
        fontsize=8,
        va='center',
        color='green'
    )

plt.show()
```

---

### 세로 막대와 가로 막대 비교

| 세로 막대 | 가로 막대 |
| --- | --- |
| `bar()` | `barh()` |
| 막대 두께 `width` | 막대 두께 `height` |
| 좌표 `(idx, val)` | 좌표 `(val, idx)` |
| 텍스트 가로 정렬 `ha` | 텍스트 세로 정렬 `va` |

### `va`

```python
va='center'
```

`va`는 **vertical alignment**를 의미한다.

가로 막대의 중앙과 텍스트의 중앙을 맞춘다.

---

# 10. 이미지 읽고 출력하기

맷플롯립은 그래프뿐 아니라 이미지 파일도 읽고 화면에 출력할 수 있다.

---

### 구글 코랩에서 이미지 내려받기

```python
import sys

if 'google.colab' in sys.modules:
    !wget https://bit.ly/3wrj4xf -O jupiter.png
```

---

### `imread()`

```python
img = plt.imread(
    'jupiter.png'
)

img.shape
```

이미지를 **넘파이 배열**로 읽어 반환한다.

배열의 형태는

```text
(높이, 너비, 채널)
```

순서이다.

출력 시 다음과 같이 나온다.

```text
(1561, 1646, 3)
```

---

### `imshow()`

```python
plt.imshow(img)
plt.show()
```

넘파이 배열로 읽은 이미지를 화면에 출력한다.

---

### 축과 눈금 제거

```python
plt.figure(
    figsize=(8, 6)
)

plt.imshow(img)

plt.axis(
    'off'
)

plt.show()
```

`axis('off')`를 사용하면 이미지 주변의 좌표축과 눈금이 사라진다.

---

### Pillow로 이미지 읽기

맷플롯립의 이미지 처리에는 Pillow 패키지도 활용할 수 있다.

```python
from PIL import Image

pil_img = Image.open(
    'jupiter.png'
)

plt.figure(
    figsize=(8, 6)
)

plt.imshow(pil_img)
plt.axis('off')
plt.show()
```

Pillow 이미지 객체를 넘파이 배열로 변환할 수도 있다.

```python
import numpy as np

arr_img = np.array(
    pil_img
)

arr_img.shape
```

---

# 11. 이미지와 그래프 저장하기

## `imsave()`

넘파이 배열을 이미지 파일로 저장한다.

```python
plt.imsave(
    'jupiter.jpg',
    arr_img
)
```

파일 이름의 확장자를 이용하여 저장 형식을 결정한다.

---

## `savefig()`

그래프를 이미지 파일로 저장한다.

저장할 때 사용할 기본 DPI 확인

```python
plt.rcParams[
    'savefig.dpi'
]
```

기본값은

```text
'figure'
```

로, Figure의 DPI 설정을 따른다.

---

### 그래프 저장

```python
plt.barh(
    count_by_subject.index,
    count_by_subject.values,
    height=0.7,
    color='blue'
)

plt.title('Books by subject')
plt.xlabel('number of books')
plt.ylabel('subject')

for idx, val in count_by_subject.items():
    plt.annotate(
        val,
        (val, idx),
        xytext=(2, 0),
        textcoords='offset points',
        fontsize=8,
        va='center',
        color='green'
    )

plt.savefig(
    'books_by_subject.png'
)

plt.show()
```

> `show()`가 실행된 뒤에는 현재 Figure가 사라질 수 있으므로  
> 교재에서는 `savefig()`를 `show()`보다 먼저 호출한다.

---

# 05-2 핵심 정리

### 선 그래프

데이터 포인트를 직선으로 연결하여 **값의 변화**를 표현한다.

```python
plt.plot()
```

선 스타일, 색상, 마커 등을 이용해 데이터를 더 명확하게 나타낼 수 있다.

---

### 막대 그래프

데이터 포인트의 **크기**를 막대의 높이 또는 길이로 나타낸다.

세로 막대

```python
plt.bar()
```

가로 막대

```python
plt.barh()
```

일반적으로 범주형 데이터의 값을 비교할 때 사용한다.

---

## 05-2 핵심 함수와 메서드

| 함수 / 메서드 | 기능 |
| --- | --- |
| `matplotlib.pyplot.plot()` | 선 그래프 생성 |
| `matplotlib.pyplot.title()` | 그래프 제목 설정 |
| `matplotlib.pyplot.xlabel()` | x축 이름 설정 |
| `matplotlib.pyplot.ylabel()` | y축 이름 설정 |
| `matplotlib.pyplot.xticks()` | x축 눈금 위치와 레이블 설정 |
| `matplotlib.pyplot.annotate()` | 지정한 좌표에 텍스트 출력 |
| `matplotlib.pyplot.bar()` | 세로 막대 그래프 생성 |
| `matplotlib.pyplot.barh()` | 가로 막대 그래프 생성 |
| `matplotlib.pyplot.imread()` | 이미지 파일을 넘파이 배열로 읽기 |
| `matplotlib.pyplot.imshow()` | 이미지 출력 |
| `matplotlib.pyplot.imsave()` | 넘파이 배열을 이미지로 저장 |
| `matplotlib.pyplot.savefig()` | 그래프를 이미지 파일로 저장 |

---

# 3️⃣ Chapter 05 전체 흐름

```text
데이터 불러오기
        ↓
시각화할 데이터 만들기
        ↓
┌───────────────────┐
│ 연도별 도서 개수 │
│ value_counts()    │
│ sort_index()      │
└─────────┬─────────┘
          ↓
       선 그래프
       plot()
          ↓
선 스타일 · 마커 · 색상
          ↓
xticks() · annotate()


┌───────────────────┐
│ 주제별 도서 개수 │
│ apply()           │
│ value_counts()    │
└─────────┬─────────┘
          ↓
       막대 그래프
    bar() / barh()
          ↓
width · height · color
          ↓
annotate()로 값 표시
```

---

# 4️⃣ 꼭 기억할 코드

### Figure 크기

```python
plt.figure(
    figsize=(9, 6)
)
```

### Figure DPI

```python
plt.figure(
    dpi=144
)
```

### 기본 설정 변경

```python
plt.rcParams[
    'figure.dpi'
] = 100
```

### 마커 변경

```python
plt.scatter(
    x,
    y,
    marker='+'
)
```

### 여러 서브플롯

```python
fig, axs = plt.subplots(
    1,
    2
)
```

### 연도별 개수

```python
count_by_year = (
    ns_book7['발행년도']
    .value_counts()
    .sort_index()
)
```

### 선 그래프

```python
plt.plot(
    count_by_year
)
```

### 선 스타일

```python
plt.plot(
    count_by_year,
    '*-g'
)
```

### 그래프에 값 표시

```python
plt.annotate(
    value,
    (x, y)
)
```

### 세로 막대 그래프

```python
plt.bar(
    x,
    y
)
```

### 가로 막대 그래프

```python
plt.barh(
    x,
    y
)
```

### 이미지 읽기

```python
img = plt.imread(
    'image.png'
)
```

### 이미지 출력

```python
plt.imshow(img)
```

### 그래프 저장

```python
plt.savefig(
    'graph.png'
)
```

---

# 5️⃣ Chapter 05 핵심 비교

| 구분 | 핵심 |
| --- | --- |
| `Figure` | 그래프 전체를 담는 최상위 객체 |
| `Axes` | 실제 그래프가 그려지는 영역 |
| `Axis` | x축·y축 등 좌표축 |
| `rcParams` | 그래프의 기본 설정값 관리 |
| `figsize` | Figure의 너비와 높이, 단위는 인치 |
| `dpi` | 인치당 픽셀 수 |
| `marker` | 데이터 포인트의 모양 |
| `subplots()` | 한 Figure 안에 여러 그래프 배치 |
| `plot()` | 선 그래프 |
| `bar()` | 세로 막대 그래프 |
| `barh()` | 가로 막대 그래프 |
| `annotate()` | 그래프에 텍스트 표시 |
| `imread()` | 이미지 읽기 |
| `imshow()` | 이미지 출력 |
| `imsave()` | 배열을 이미지로 저장 |
| `savefig()` | 그래프를 이미지로 저장 |


---

# 2️⃣ 수행 인증

<img width="1261" height="695" alt="image" src="https://github.com/user-attachments/assets/d63bc6c2-7f3a-448b-a1ee-b2f8aad0c942" />

<img width="1253" height="691" alt="image" src="https://github.com/user-attachments/assets/72b5be61-2972-4e57-8c49-5f56bc6aadf5" />

<img width="1259" height="691" alt="image" src="https://github.com/user-attachments/assets/ea169ca4-2cd9-4928-9a9e-7d27d93a8516" />

<img width="1261" height="695" alt="image" src="https://github.com/user-attachments/assets/26c73e96-4e60-46d5-ac75-91e00a9eb84c" />

<img width="1254" height="686" alt="image" src="https://github.com/user-attachments/assets/94c4f903-7ead-42d0-83c0-ffa49f80fbb3" />

<img width="1259" height="693" alt="image" src="https://github.com/user-attachments/assets/998afc1e-dd21-4a92-8de3-df5db5e14d61" />

<img width="1263" height="697" alt="image" src="https://github.com/user-attachments/assets/f845da27-0ee5-4a8a-a0c1-7e9aa58bc115" />

<img width="1258" height="687" alt="image" src="https://github.com/user-attachments/assets/2363f4dc-adf1-41bf-a215-c46ac192850c" />

<img width="1259" height="690" alt="image" src="https://github.com/user-attachments/assets/e72e20bc-0e2d-4cc7-8b4f-6735bfbdbb6a" />

<img width="1263" height="697" alt="image" src="https://github.com/user-attachments/assets/c21dc529-487a-4f8b-8683-fa8028e7b4b2" />

<img width="1262" height="694" alt="image" src="https://github.com/user-attachments/assets/479fab99-a4c6-49c0-beb2-ecf1f30731d9" />

<img width="1268" height="699" alt="image" src="https://github.com/user-attachments/assets/f39767ed-4778-4ef0-a176-36966ae7449c" />

<img width="1253" height="693" alt="image" src="https://github.com/user-attachments/assets/f412e791-6cc4-4da2-a858-6521c6dda932" />

<img width="1256" height="691" alt="image" src="https://github.com/user-attachments/assets/cfe34423-b6a2-44a0-a680-0b3d3a7eb650" />

<img width="1260" height="692" alt="image" src="https://github.com/user-attachments/assets/81f84b06-e8b7-4b40-b1a0-560cebc3ff75" />

<img width="1261" height="695" alt="image" src="https://github.com/user-attachments/assets/f06aa3e1-70c5-42e0-91dd-572942ba5dc2" />

<img width="1255" height="692" alt="image" src="https://github.com/user-attachments/assets/426abdb6-06a1-4f3b-99f0-1a4c74441486" />

<img width="1259" height="692" alt="image" src="https://github.com/user-attachments/assets/22447909-9de9-4b0e-b38e-89a1846fa029" />

<img width="1253" height="694" alt="image" src="https://github.com/user-attachments/assets/99c6c031-dd8e-4b1d-a57f-3a87f8bf365b" />

<img width="1250" height="695" alt="image" src="https://github.com/user-attachments/assets/8503cdd9-cb61-4df4-886e-c16eba140403" />

<img width="1253" height="689" alt="image" src="https://github.com/user-attachments/assets/a4f0620c-22e7-4db1-9d56-9140803b5e7c" />

<img width="1255" height="693" alt="image" src="https://github.com/user-attachments/assets/59b9806d-3562-425f-986e-a51a9807ad36" />

<img width="1254" height="694" alt="image" src="https://github.com/user-attachments/assets/037d1286-f00d-4323-9293-b1a1ab46075b" />

<img width="1262" height="696" alt="image" src="https://github.com/user-attachments/assets/e4acc39d-b2c2-46f5-908e-568031a3f0cc" />

<img width="595" height="564" alt="image" src="https://github.com/user-attachments/assets/8b204432-4d96-420a-88b5-5d6fe35713cf" />

<img width="1250" height="689" alt="image" src="https://github.com/user-attachments/assets/5dd4daee-e0ff-4057-975b-6220637e8dee" />

<img width="696" height="541" alt="image" src="https://github.com/user-attachments/assets/92980199-9dc3-4192-a0bd-e0fc07e777cc" />

<img width="1255" height="692" alt="image" src="https://github.com/user-attachments/assets/1daf4a87-0b7c-453c-8dd6-4ec018afec5b" />

<img width="1256" height="692" alt="image" src="https://github.com/user-attachments/assets/dd3b7b25-fc6d-4fa0-a624-0fce7d7aa863" />

<img width="1256" height="690" alt="image" src="https://github.com/user-attachments/assets/d98b03a5-7e74-42a3-8e55-07095b4de04d" />

<img width="1258" height="693" alt="image" src="https://github.com/user-attachments/assets/e13f26ee-a3d4-4741-ab3d-e009ac4d5513" />








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

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [2, 4, 6, 8, 10]

plt.plot(x, y, marker='o')

plt.title('Linear Trend')
plt.xlabel('X values')
plt.ylabel('Y values')

plt.show()
```

## 실행 결과

<img width="640" height="480" alt="image" src="https://github.com/user-attachments/assets/19606dd0-2590-49de-b84a-16127a2ef724" />


### 🎉 수고하셨습니다.
