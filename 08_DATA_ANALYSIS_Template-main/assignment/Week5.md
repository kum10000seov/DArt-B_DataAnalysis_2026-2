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

# 데이터분석 6주차 정규과제

## Chapter 06. 복잡한 데이터 표현하기

> 학습 범위 : p.328 ~ p.379  
> 연습 문제 제외

---

## 목차

### 06-1 객체지향 API로 그래프 꾸미기
- pyplot 방식과 객체지향 API 방식
- 그래프에 한글 출력하기
- 출판사별 발행 도서 개수 산점도 그리기
- 값에 따라 마커 크기를 다르게 나타내기
- 마커 꾸미기
- 값에 따라 색상 표현하기 : 컬러맵
- 컬러 막대

### 06-2 맷플롯립의 고급 기능 배우기
- 실습 준비하기
- 하나의 피겨에 여러 개의 그래프 그리기
- 범례 추가하기
- 스택 영역 그래프
- 피벗 테이블
- 하나의 피겨에 여러 개의 막대 그래프 그리기
- 스택 막대 그래프
- 데이터값 누적하여 그리기
- 원 그래프 그리기
- 여러 종류의 그래프가 있는 서브플롯 그리기
- 판다스로 여러 개의 그래프 그리기

---

# 06-1. 객체지향 API로 그래프 꾸미기

> 핵심 키워드 : `객체지향 API` `컬러맵` `컬러 막대`

---

## 1. pyplot 방식과 객체지향 API 방식

맷플롯립으로 그래프를 그리는 방법은 크게 두 가지가 있다.

| 방식 | 설명 |
| --- | --- |
| `pyplot` 방식 | `matplotlib.pyplot`의 함수를 이용해 그래프를 그림 |
| 객체지향 API 방식 | `Figure` 객체와 `Axes` 객체를 명시적으로 만든 뒤 객체의 메서드로 그래프를 그림 |

간단한 그래프는 `pyplot` 방식으로 쉽게 그릴 수 있지만,  
여러 개의 서브플롯을 만들거나 그래프를 복잡하게 꾸밀 때는 **객체지향 API 방식**이 유용하다.

---

### 그래프 해상도 설정

```python
import matplotlib.pyplot as plt

plt.rcParams['figure.dpi'] = 100
```

- `rcParams` : 맷플롯립 그래프의 여러 기본 설정값을 관리
- `figure.dpi` : 그래프의 DPI 설정

---

## 1-1. pyplot 방식

```python
plt.plot([1, 4, 9, 16])
plt.title('simple line graph')
plt.show()
```

`plot()` 함수에 리스트를 하나만 전달하면 리스트의 원소는 `y축` 값으로 사용되고,  
리스트의 인덱스가 자동으로 `x축` 값이 된다.

```text
x축 : [0, 1, 2, 3]
y축 : [1, 4, 9, 16]
```

---

## 1-2. 객체지향 API 방식

```python
fig, ax = plt.subplots()

ax.plot([1, 4, 9, 16])
ax.set_title('simple line graph')

fig.show()
```

구조는 다음처럼 생각할 수 있다.

```text
fig : 그래프 전체를 담는 틀
ax  : 실제 그래프를 그리는 영역
```

객체지향 API에서는 `plt.plot()` 대신 `ax.plot()`처럼  
`Axes` 객체가 제공하는 메서드를 사용한다.

---

### pyplot과 객체지향 API 비교

| pyplot 방식 | 객체지향 API 방식 |
| --- | --- |
| `plt.plot()` | `ax.plot()` |
| `plt.title()` | `ax.set_title()` |
| `plt.xlim()` | `ax.set_xlim()` |
| `plt.ylim()` | `ax.set_ylim()` |
| `plt.legend()` | `ax.legend()` |

> 책에서는 두 방식을 상황에 따라 함께 사용한다.  
> 간단한 그래프는 `pyplot`, 여러 그래프를 만들거나 세부 설정을 변경할 때는 객체지향 API를 활용한다.

---

# 2. 그래프에 한글 출력하기

맷플롯립의 기본 폰트는 한글을 지원하지 않으므로  
한글을 출력하려면 한글 폰트를 설치하고 설정해야 한다.

---

## 2-1. 코랩에서 나눔 폰트 설치

```python
# 노트북이 코랩에서 실행 중인지 체크합니다.
import sys

if 'google.colab' in sys.modules:
    !echo 'debconf debconf/frontend select Noninteractive' | debconf-set-selections

    # 나눔 폰트를 설치합니다.
    !sudo apt-get -qq -y install fonts-nanum

    import matplotlib.font_manager as fm

    font_files = fm.findSystemFonts(
        fontpaths=['/usr/share/fonts/truetype/nanum']
    )

    for fpath in font_files:
        fm.fontManager.addfont(fpath)
```

코랩에서 나눔 폰트를 설치한 뒤 다시 그래프 설정을 적용한다.

```python
import matplotlib.pyplot as plt

plt.rcParams['figure.dpi'] = 100
```

---

## 2-2. `font.family` 확인

```python
plt.rcParams['font.family']
```

기본 설정은 다음과 같이 `sans-serif` 계열이다.

```text
['sans-serif']
```

---

## 2-3. `rcParams`로 폰트 변경

```python
# 나눔고딕 폰트를 사용합니다.
plt.rcParams['font.family'] = 'NanumGothic'
```

`rcParams` 객체의 설정값을 직접 변경하는 방법이다.

---

## 2-4. `rc()` 함수로 폰트 변경

```python
# 위와 동일하지만 이번에는 나눔바른고딕 폰트로 설정합니다.
plt.rc('font', family='NanumBarunGothic')
```

폰트와 글자 크기를 한 번에 설정할 수도 있다.

```python
plt.rc('font', family='NanumBarunGothic', size=11)
```

현재 설정값 확인

```python
print(
    plt.rcParams['font.family'],
    plt.rcParams['font.size']
)
```

---

## 2-5. 시스템 폰트 확인

```python
from matplotlib.font_manager import findSystemFonts

findSystemFonts()
```

맷플롯립이 현재 시스템에서 찾을 수 있는 폰트 목록을 확인한다.

---

## 2-6. 한글 제목 출력

```python
plt.plot([1, 4, 9, 16])
plt.title('간단한 선 그래프')
plt.show()
```

폰트 크기를 다시 기본값으로 변경한다.

```python
plt.rc('font', size=10)
```

---

# 3. 출판사별 발행 도서 개수 산점도 그리기

## 3-1. 데이터 다운로드

```python
import gdown

gdown.download(
    'https://bit.ly/3pK7iuu',
    'ns_book7.csv',
    quiet=False
)
```

---

## 3-2. 데이터 불러오기

```python
import pandas as pd

ns_book7 = pd.read_csv(
    'ns_book7.csv',
    low_memory=False
)

ns_book7.head()
```

산점도에서는

```text
x축 → 발행년도
y축 → 출판사
```

를 사용한다.

전체 출판사를 모두 표시하면 그래프가 너무 복잡해지기 때문에  
발행 도서가 많은 **상위 30개 출판사**만 선택한다.

---

# 4. 고유한 출판사 목록 만들기

## 4-1. `value_counts()`

```python
top30_pubs = ns_book7['출판사'].value_counts()[:30]

top30_pubs
```

`value_counts()`는 고유한 값이 각각 몇 번 등장하는지 계산한다.

결과는 등장 횟수가 많은 순서대로 정렬되므로

```python
[:30]
```

을 사용해 상위 30개 출판사를 선택한다.

---

## 4-2. `isin()`

```python
top30_pubs_idx = ns_book7['출판사'].isin(
    top30_pubs.index
)

top30_pubs_idx
```

`isin()`은 각 값이 전달받은 목록에 포함되어 있는지를 검사한다.

```text
상위 30개 출판사에 포함 → True
포함되지 않음          → False
```

---

## 4-3. `True` 개수 확인

```python
top30_pubs_idx.sum()
```

불리언 값은 계산할 때

```text
True  → 1
False → 0
```

으로 처리되므로 `sum()`을 사용해 `True`의 개수를 셀 수 있다.

---

# 5. 산점도에 사용할 데이터 샘플링

상위 30개 출판사의 데이터도 5만 건 이상이므로  
산점도로 모두 표현하기에는 너무 많다.

따라서 1,000개만 무작위로 선택한다.

```python
ns_book8 = ns_book7[
    top30_pubs_idx
].sample(
    1000,
    random_state=42
)

ns_book8.head()
```

### `sample()`

데이터프레임에서 무작위로 행을 선택한다.

### `random_state`

```python
random_state=42
```

처럼 값을 고정하면 코드를 다시 실행해도 동일한 표본을 얻을 수 있다.

---

# 6. 산점도 그리기

```python
fig, ax = plt.subplots(figsize=(10, 8))

ax.scatter(
    ns_book8['발행년도'],
    ns_book8['출판사']
)

ax.set_title('출판사별 발행도서')

fig.show()
```

| 요소 | 사용 데이터 |
| --- | --- |
| x축 | `발행년도` |
| y축 | `출판사` |
| 점 하나 | 하나의 도서 |

---

# 7. 값에 따라 마커 크기를 다르게 나타내기

`scatter()`의 `s` 매개변수는 마커 크기를 결정한다.

```python
fig, ax = plt.subplots(figsize=(10, 8))

ax.scatter(
    ns_book8['발행년도'],
    ns_book8['출판사'],
    s=ns_book8['대출건수']
)

ax.set_title('출판사별 발행도서')

fig.show()
```

`대출건수` 값을 `s`에 전달했기 때문에

```text
대출건수 증가
     ↓
마커 크기 증가
```

형태로 표현된다.

입력 데이터와 동일한 길이의 배열을 `s`에 전달하면  
각 데이터마다 서로 다른 크기의 마커를 사용할 수 있다.

---

# 8. 마커 꾸미기

산점도의 마커에 여러 속성을 동시에 적용할 수 있다.

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

ax.set_title('출판사별 발행도서')

fig.show()
```

---

## 주요 매개변수

| 매개변수 | 역할 |
| --- | --- |
| `s` | 마커의 크기 |
| `c` | 마커의 색을 결정할 값 |
| `alpha` | 마커의 투명도 |
| `edgecolors` | 마커 테두리 색 |
| `linewidths` | 마커 테두리 두께 |

---

## `alpha`

```python
alpha=0.3
```

마커의 투명도를 지정한다.

마커가 많이 겹치는 부분은 상대적으로 진하게 보이므로  
데이터가 많이 모인 영역을 파악하는 데 도움이 된다.

---

## `edgecolors`

```python
edgecolors='k'
```

마커의 테두리 색을 설정한다.

`'k'`는 검은색을 의미한다.

---

## `linewidths`

```python
linewidths=0.5
```

마커 테두리의 두께를 설정한다.

---

## `c`

```python
c=ns_book8['대출건수']
```

데이터값에 따라 마커의 색을 다르게 표현한다.

---

# 9. 값에 따라 색상 표현하기 : 컬러맵

## 컬러맵

컬러맵(Color Map)은 데이터값에 따라 사용할 색상을 미리 정의해 둔 색상 목록이다.

맷플롯립의 기본 컬러맵은 `viridis`이다.

책에서는 `jet` 컬러맵도 함께 소개한다.

```text
jet 컬러맵

낮은 값                         높은 값
파란색 → 초록색 → 노란색 → 빨간색
```

---

## `cmap='jet'`

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

ax.set_title('출판사별 발행도서')

fig.colorbar(sc)

fig.show()
```

---

# 10. 컬러 막대

```python
fig.colorbar(sc)
```

컬러 막대(Color Bar)는  
그래프에 사용된 색깔이 어떤 실제 데이터값을 나타내는지 보여준다.

```text
색상
 ↓
실제 대출건수 값
```

`scatter()`가 반환한 객체를 변수 `sc`에 저장한 뒤  
`colorbar()`에 전달한다.

---

## 마커 크기 사용 시 주의점

책에서는 마커 크기를 이용하면 산점도에 추가 정보를 넣을 수 있지만,  
크기를 조절하는 방식에 따라 데이터가 과장되거나 왜곡되어 보일 수도 있다고 설명한다.

따라서 마커 크기를 변환해 사용한다면  
어떤 방식으로 크기를 계산했는지 함께 알려 주는 것이 좋다.

---

# 06-1 핵심 정리

### 객체지향 API

명시적으로 `Figure` 객체와 `Axes` 객체를 만든 뒤  
객체의 메서드를 이용해 그래프를 그리는 방법이다.

### 컬러맵

데이터값을 색상으로 표현하기 위해 미리 정의한 색상 목록이다.

### 컬러 막대

데이터값과 컬러맵의 색상 사이의 관계를 보여주는 막대이다.

---

## 교재 핵심 함수와 메서드

| 함수 / 메서드 | 기능 |
| --- | --- |
| `matplotlib.pyplot.rc()` | `rcParams` 객체의 설정값 변경 |
| `Figure.colorbar()` | 그래프에 컬러 막대 추가 |

---

---

# 06-2. 맷플롯립의 고급 기능 배우기

> 핵심 키워드 : `범례` `피벗 테이블` `스택 영역 그래프` `스택 막대 그래프` `원 그래프`

이번 절에서는 하나의 피겨에 여러 개의 그래프를 함께 표현하고,  
서로 다른 데이터를 비교하기 위한 고급 시각화 방법을 다룬다.

---

# 1. 실습 준비하기

## 한글 폰트 설치

```python
# 노트북이 코랩에서 실행 중인지 체크합니다.
import sys

if 'google.colab' in sys.modules:
    !echo 'debconf debconf/frontend select Noninteractive' | debconf-set-selections

    # 나눔 폰트를 설치합니다.
    !sudo apt-get -qq -y install fonts-nanum

    import matplotlib.font_manager as fm

    font_files = fm.findSystemFonts(
        fontpaths=['/usr/share/fonts/truetype/nanum']
    )

    for fpath in font_files:
        fm.fontManager.addfont(fpath)
```

---

## 맷플롯립 설정

```python
import matplotlib.pyplot as plt

# 나눔바른고딕 폰트로 설정합니다.
plt.rc('font', family='NanumBarunGothic')

# 그래프 DPI 기본값을 변경합니다.
plt.rcParams['figure.dpi'] = 100
```

---

## 데이터 다운로드

```python
import gdown

gdown.download(
    'https://bit.ly/3pK7iuu',
    'ns_book7.csv',
    quiet=False
)
```

---

## 데이터 불러오기

```python
import pandas as pd

ns_book7 = pd.read_csv(
    'ns_book7.csv',
    low_memory=False
)

ns_book7.head()
```

---

# 2. 하나의 피겨에 여러 개의 그래프 그리기

여러 개의 선 그래프를 하나의 `Axes`에 나타내려면  
`plot()`을 여러 번 호출하면 된다.

먼저 상위 30개 출판사를 선택한다.

```python
top30_pubs = ns_book7['출판사'].value_counts()[:30]

top30_pubs_idx = ns_book7['출판사'].isin(
    top30_pubs.index
)
```

---

## 필요한 열만 추출

```python
ns_book9 = ns_book7[
    top30_pubs_idx
][
    ['출판사', '발행년도', '대출건수']
]
```

---

## 출판사와 발행년도별로 대출건수 합계 계산

```python
ns_book9 = ns_book9.groupby(
    by=['출판사', '발행년도']
).sum()
```

같은 출판사의 같은 연도 데이터는 하나로 모아  
대출건수를 합한다.

```text
출판사
  +
발행년도
  ↓
그룹화
  ↓
대출건수 합계
```

---

## 인덱스 초기화

```python
ns_book9 = ns_book9.reset_index()
```

확인

```python
ns_book9[
    ns_book9['출판사'] == '황금가지'
].head()
```

---

# 3. 두 개의 선 그래프 그리기

```python
line1 = ns_book9[
    ns_book9['출판사'] == '황금가지'
]

line2 = ns_book9[
    ns_book9['출판사'] == '비룡소'
]
```

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

`plot()`을 연속해서 호출하면 하나의 피겨 안에 여러 선 그래프를 표현할 수 있다.

색상을 직접 지정하지 않아도 맷플롯립이 그래프마다 다른 색을 사용한다.

---

# 4. 범례 추가하기

여러 그래프를 함께 그리면 어떤 선이 어떤 데이터를 의미하는지 구분하기 어렵다.

각 그래프의 `label`을 지정하고 `legend()`를 사용한다.

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

### 범례

그래프에 사용된 데이터의 이름과 색상을 함께 보여 주는 표이다.

---

# 5. 여러 출판사의 그래프 그리기

상위 5개 출판사는 반복문을 이용해 한 번에 그릴 수 있다.

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

---

# 6. 축의 출력 범위 지정

## x축

```python
ax.set_xlim(1985, 2025)
```

## y축

```python
ax.set_ylim(0, 13000)
```

pyplot 방식에서는 다음과 같이 사용한다.

```python
plt.xlim(1985, 2025)
plt.ylim(0, 13000)
```

---

## `axis()`로 x축과 y축을 한 번에 설정

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
    x축 최솟값,
    x축 최댓값,
    y축 최솟값,
    y축 최댓값
]
```

객체지향 API에서는

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

# 7. 스택 영역 그래프

여러 개의 선 그래프가 서로 겹치면 비교하기 어려워질 수 있다.

이때 여러 그래프를 y축 방향으로 차례대로 쌓아 표현하는  
**스택 영역 그래프(Stacked Area Graph)**를 사용할 수 있다.

```text
출판사 C  █████████████
출판사 B  █████████
출판사 A  █████
           ──────────
              연도
```

맷플롯립에서는 `stackplot()`을 사용한다.

---

# 8. 피벗 테이블

스택 영역 그래프에 사용할 데이터는

```text
행 → 출판사
열 → 발행년도
값 → 대출건수
```

와 같은 2차원 형태가 필요하다.

이때 `pivot_table()`을 사용한다.

```python
ns_book10 = ns_book9.pivot_table(
    index='출판사',
    columns='발행년도'
)

ns_book10.head()
```

---

## 피벗 테이블의 구조

기존 데이터

| 출판사 | 발행년도 | 대출건수 |
| --- | ---: | ---: |
| A | 2020 | 10 |
| B | 2021 | 20 |
| A | 2021 | 30 |

피벗 후

| 출판사 | 2020 | 2021 |
| --- | ---: | ---: |
| A | 10 | 30 |
| B | NaN | 20 |

즉, 특정 열에 있던 값들을 새로운 열의 이름으로 펼쳐서  
2차원 형태의 데이터로 변환한다.

---

# 9. 다단 열에서 발행년도 가져오기

`ns_book10`의 열은 다단 구조로 만들어진다.

```python
ns_book10.columns[:10]
```

상위 10개의 출판사를 선택한다.

```python
top10_pubs = top30_pubs.index[:10]
```

발행년도만 추출한다.

```python
year_cols = ns_book10.columns.get_level_values(1)
```

`get_level_values()`는 다단 인덱스 또는 다단 열에서  
특정 단계의 값을 가져오는 데 사용한다.

---

# 10. `stackplot()`으로 스택 영역 그래프 그리기

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

## `loc`

범례의 위치를 지정한다.

```python
ax.legend(loc='upper left')
```

```text
upper left → 왼쪽 위
```

`loc`의 기본값은 그래프에 적절한 위치를 자동으로 선택하는 값이다.

---

## `fillna(0)`

```python
ns_book10.loc[top10_pubs].fillna(0)
```

피벗 테이블에는 특정 연도에 데이터가 없는 경우 `NaN`이 생길 수 있다.

책에서는 맷플롯립이 누락값 때문에 그래프를 제대로 그리지 못하는 경우를 방지하기 위해  
그래프를 그리기 전에 누락값을 `0`으로 채운다.

피벗 테이블을 만들 때

```python
fill_value=0
```

을 지정하는 방법도 있다.

---

# 11. 하나의 피겨에 여러 개의 막대 그래프 그리기

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

선 그래프와 달리 막대 그래프는 내부가 채워져 있기 때문에  
같은 위치에 그리면 뒤에 그린 막대가 앞의 막대를 덮는다.

---

# 12. 막대 그래프를 나란히 그리기

막대의 너비를 줄이고 x축 위치를 조금씩 이동한다.

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

```text
첫 번째 막대 → -0.2 이동
두 번째 막대 → +0.2 이동
막대 너비   → 0.4
```

---

# 13. 스택 막대 그래프

막대를 옆으로 배치하지 않고 위로 쌓아 표현할 수도 있다.

이를 **스택 막대 그래프(Stacked Bar Graph)**라고 한다.

맷플롯립에는 스택 막대 그래프만을 위한 별도의 함수가 없으므로  
`bar()`의 `bottom` 매개변수를 사용한다.

---

## `bottom`

```python
height1 = [5, 4, 7, 9, 8]
height2 = [3, 2, 4, 1, 2]

plt.bar(
    range(5),
    height1,
    width=0.5
)

plt.bar(
    range(5),
    height2,
    bottom=height1,
    width=0.5
)

plt.show()
```

```python
bottom=height1
```

은 두 번째 막대의 시작 위치를  
첫 번째 막대가 끝나는 위치로 지정한다.

---

# 14. 데이터를 먼저 누적하여 그리기

막대를 그릴 때마다 `bottom`을 계산하는 대신  
막대의 높이를 미리 누적해 둘 수도 있다.

```python
height3 = [
    a + b
    for a, b in zip(height1, height2)
]
```

```python
plt.bar(
    range(5),
    height3,
    width=0.5
)

plt.bar(
    range(5),
    height1,
    width=0.5
)

plt.show()
```

---

## `zip()`

두 리스트에서 같은 위치의 값을 하나씩 묶는다.

```text
height1 : 5  4  7  9  8
height2 : 3  2  4  1  2
           ↓  ↓  ↓  ↓  ↓
합계     : 8  6 11 10 10
```

---

# 15. `cumsum()`으로 데이터값 누적하기

실제 데이터에서는 직접 값을 더하는 대신  
판다스의 `cumsum()`을 이용한다.

먼저 일부 데이터를 확인한다.

```python
ns_book10.loc[
    top10_pubs[:5],
    ('대출건수', 2013):('대출건수', 2020)
]
```

누적 합 계산

```python
ns_book10.loc[
    top10_pubs[:5],
    ('대출건수', 2013):('대출건수', 2020)
].cumsum()
```

전체 상위 10개 출판사의 누적값을 만든다.

```python
ns_book12 = ns_book10.loc[
    top10_pubs
].cumsum()
```

`cumsum()`은 데이터를 차례대로 더하여 누적 합을 계산한다.

---

# 16. 누적값으로 스택 막대 그래프 그리기

```python
fig, ax = plt.subplots(figsize=(8, 6))

for i in reversed(
    range(len(ns_book12))
):

    bar = ns_book12.iloc[i]     # 행 추출
    label = ns_book12.index[i]  # 출판사 이름 추출

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

## `reversed()`를 사용하는 이유

누적값을 사용해 스택 막대를 그릴 경우  
가장 큰 막대를 먼저 그려야 한다.

그렇지 않으면 나중에 그린 큰 막대가  
이전에 그려 놓은 작은 막대를 덮어 버릴 수 있다.

따라서

```python
reversed(
    range(len(ns_book12))
)
```

를 이용해 마지막 행부터 역순으로 그린다.

---

# 17. 원 그래프 그리기

원 그래프는 전체 데이터에 대한 각 항목의 비율을  
원의 부채꼴 형태로 나타낸 그래프이다.

파이 차트(Pie Chart)라고도 한다.

---

## 데이터 준비

```python
data = top30_pubs[:10]

labels = top30_pubs.index[:10]
```

---

## 기본 원 그래프

```python
fig, ax = plt.subplots(figsize=(8, 6))

ax.pie(
    data,
    labels=labels
)

ax.set_title('출판사 도서비율')

fig.show()
```

`pie()`는 전달된 데이터의 합계를 기준으로  
각 데이터의 비율을 자동으로 계산한다.

---

# 18. 원 그래프의 시작 위치 지정

```python
plt.pie(
    [10, 9],
    labels=['A제품', 'B제품'],
    startangle=90
)

plt.title('제품의 매출비율')

plt.show()
```

`startangle`은 원 그래프를 그리기 시작할 각도를 지정한다.

```python
startangle=90
```

이면 12시 방향에서 그래프를 그리기 시작한다.

---

# 19. 원 그래프에 비율 표시하기

`autopct`에 포맷 문자열을 전달한다.

```python
autopct='%.1f%%'
```

```text
%.1f → 소수점 첫째 자리까지 표시
%%   → % 기호 출력
```

---

# 20. 특정 부채꼴 강조하기

`explode`를 사용하면 특정 조각을 원에서 떨어뜨려 강조할 수 있다.

```python
explode=[0.1] + [0] * 9
```

첫 번째 항목만 원의 중심에서 조금 떨어뜨린다.

---

## 완성 코드

```python
fig, ax = plt.subplots(figsize=(8, 6))

ax.pie(
    data,
    labels=labels,
    startangle=90,
    autopct='%.1f%%',
    explode=[0.1] + [0] * 9
)

ax.set_title('출판사 도서비율')

fig.show()
```

---

## 원 그래프의 단점

책에서는 원 그래프가 항목 간의 크기를 정확하게 비교하기 어려울 수 있다고 설명한다.

특히 데이터의 크기가 비슷하면 부채꼴 크기만 보고 차이를 판단하기 어렵다.

따라서

```python
autopct='%.1f%%'
```

처럼 실제 비율을 함께 표시하면 그래프의 의미를 더 명확하게 전달할 수 있다.

---

# 21. 여러 종류의 그래프가 있는 서브플롯 그리기

이번에는 지금까지 만든

```text
산점도
스택 영역 그래프
스택 막대 그래프
원 그래프
```

4개를 하나의 피겨에 함께 그린다.

---

## 2 × 2 서브플롯

```python
fig, axes = plt.subplots(
    2,
    2,
    figsize=(20, 16)
)
```

생성되는 구조

```text
axes[0, 0]    axes[0, 1]

axes[1, 0]    axes[1, 1]
```

---

## 전체 코드

```python
fig, axes = plt.subplots(2, 2, figsize=(20, 16))

# 산점도
ns_book8 = ns_book7[top30_pubs_idx].sample(
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

axes[0, 0].set_title('출판사별 발행도서')

fig.colorbar(
    sc,
    ax=axes[0, 0]
)


# 스택 영역 그래프
axes[0, 1].stackplot(
    year_cols,
    ns_book10.loc[top10_pubs].fillna(0),
    labels=top10_pubs
)

axes[0, 1].set_title('연도별 대출건수')

axes[0, 1].legend(
    loc='upper left'
)

axes[0, 1].set_xlim(
    1985,
    2025
)


# 스택 막대 그래프
for i in reversed(
    range(len(ns_book12))
):

    bar = ns_book12.iloc[i]     # 행 추출
    label = ns_book12.index[i]  # 출판사 이름 추출

    axes[1, 0].bar(
        year_cols,
        bar,
        label=label
    )

axes[1, 0].set_title('연도별 대출건수')

axes[1, 0].legend(
    loc='upper left'
)

axes[1, 0].set_xlim(
    1985,
    2025
)


# 원 그래프
axes[1, 1].pie(
    data,
    labels=labels,
    startangle=90,
    autopct='%.1f%%',
    explode=[0.1] + [0] * 9
)

axes[1, 1].set_title(
    '출판사 도서비율'
)


# 이미지 저장
fig.savefig(
    'all_in_one.png'
)

fig.show()
```

---

# 22. 컬러 막대를 특정 서브플롯에 추가하기

여러 개의 서브플롯이 있는 경우에는  
컬러 막대를 어느 `Axes`에 추가할 것인지 명확히 지정한다.

```python
fig.colorbar(
    sc,
    ax=axes[0, 0]
)
```

---

# 23. 그래프 이미지 저장하기

```python
fig.savefig(
    'all_in_one.png'
)
```

현재 Figure 전체를 이미지 파일로 저장한다.

---

# 24. 판다스로 여러 개의 그래프 그리기

판다스 데이터프레임도 다양한 그래프 기능을 제공한다.

책에서는 같은 스택 영역 그래프와 스택 막대 그래프를  
판다스로 더 간단하게 그리는 방법을 설명한다.

다만 세부적인 그래프 설정이 필요할 때는  
맷플롯립을 직접 사용하는 것이 더 적합하다.

---

# 25. 판다스용 피벗 테이블 만들기

이번에는 이전 피벗 테이블과 반대로

```text
행 → 발행년도
열 → 출판사
값 → 대출건수
```

형태로 데이터를 만든다.

```python
ns_book11 = ns_book9.pivot_table(
    index='발행년도',
    columns='출판사',
    values='대출건수'
)

ns_book11.loc[2000:2005]
```

---

## `values`

```python
values='대출건수'
```

집계할 데이터 열을 직접 지정한다.

이렇게 하면 이전 `ns_book10`처럼  
열 이름이 다단 구조로 만들어지지 않는다.

---

# 26. `pivot_table()`과 `groupby()`

두 메서드 모두 데이터를 특정 기준으로 묶어 집계할 수 있다.

| 메서드 | 결과의 특징 |
| --- | --- |
| `groupby()` | 집계 기준이 인덱스로 구성 |
| `pivot_table()` | 집계 기준을 행과 열로 나누어 배치 |

---

# 27. 원본 데이터에서 바로 피벗 테이블 만들기

원본 데이터에는 같은 출판사와 발행년도를 가진 행이 여러 개 존재하므로  
집계 방식을 지정해야 한다.

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

ns_book11.loc[2000:2005]
```

### `aggfunc`

집계 방법을 지정한다.

```python
aggfunc=np.sum
```

→ 같은 그룹의 값을 모두 합한다.

책에서는 `pivot_table()`의 기본 집계 방식은 평균이라고 설명한다.

---

# 28. 판다스로 스택 영역 그래프 그리기

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

을 사용하는 대신

```python
DataFrame.plot.area()
```

로 스택 영역 그래프를 만들 수 있다.

---

# 29. 판다스로 스택 막대 그래프 그리기

판다스의 `plot.bar()`는 기본적으로 막대를 나란히 그린다.

```python
DataFrame.plot.bar()
```

`stacked=True`를 설정하면 스택 막대 그래프가 된다.

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

판다스를 사용하면 맷플롯립에서처럼  
직접 `cumsum()`으로 누적값을 준비하지 않아도 된다.

> 책에서는 당시 판다스의 막대 그래프에서 x축 범위 설정에 문제가 있어  
> `ax.set_xlim()` 대신 데이터프레임에서 `1985:2025` 범위의 행을 먼저 선택해 사용한다.

---

# 06-2 핵심 정리

## 범례

그래프에서 데이터의 이름과 색상을 알려 주는 표

```python
ax.legend()
```

---

## 피벗 테이블

테이블 형태의 데이터를 행과 열 기준으로 재구성하고  
평균이나 합 등의 방식으로 집계한 요약표

```python
df.pivot_table()
```

---

## 스택 영역 그래프

여러 개의 그래프를 y축 방향으로 쌓고  
그래프 사이 영역을 색으로 채운 형태

```python
ax.stackplot()
```

또는

```python
df.plot.area()
```

---

## 스택 막대 그래프

여러 막대를 y축 방향으로 쌓아서 표현한 그래프

맷플롯립

```python
ax.bar(
    ...,
    bottom=...
)
```

또는 누적값 이용

```python
df.cumsum()
```

판다스

```python
df.plot.bar(
    stacked=True
)
```

---

## 원 그래프

전체 데이터에서 각 항목이 차지하는 비율을  
원의 부채꼴로 표현한 그래프

```python
ax.pie()
```

비율을 함께 표시할 때

```python
autopct='%.1f%%'
```

---

# 교재 핵심 함수와 메서드

| 함수 / 메서드 | 기능 |
| --- | --- |
| `Axes.legend()` | 그래프에 범례 추가 |
| `Axes.set_xlim()` | x축 출력 범위 지정 |
| `DataFrame.pivot_table()` | 피벗 테이블 생성 |
| `Axes.stackplot()` | 스택 영역 그래프 생성 |
| `DataFrame.plot.area()` | 판다스로 스택 영역 그래프 생성 |
| `DataFrame.plot.bar()` | 판다스로 막대 그래프 생성 |
| `DataFrame.cumsum()` | 누적 합 계산 |
| `Axes.pie()` | 원 그래프 생성 |

---

# Chapter 06 전체 흐름

```text
데이터 불러오기
        ↓
value_counts()
상위 출판사 선택
        ↓
isin()
필요한 데이터 필터링
        ↓
groupby()
출판사 × 발행년도 단위로 집계
        ↓
pivot_table()
그래프에 적합한 2차원 구조로 변환
        ↓
Matplotlib
산점도 / 선 그래프 / 스택 영역 / 막대 / 원 그래프
        ↓
legend / colorbar
그래프 정보 보완
        ↓
subplots()
여러 그래프를 하나의 Figure에 배치
        ↓
savefig()
완성된 그래프 저장
```

---

# 핵심 코드 한눈에 보기

| 목적 | 코드 |
| --- | --- |
| Figure + Axes 생성 | `fig, ax = plt.subplots()` |
| 여러 서브플롯 생성 | `fig, axes = plt.subplots(2, 2)` |
| 선 그래프 | `ax.plot()` |
| 산점도 | `ax.scatter()` |
| 막대 그래프 | `ax.bar()` |
| 범례 | `ax.legend()` |
| x축 범위 | `ax.set_xlim()` |
| 컬러 막대 | `fig.colorbar()` |
| 피벗 테이블 | `df.pivot_table()` |
| 스택 영역 | `ax.stackplot()` |
| 누적 합 | `df.cumsum()` |
| 원 그래프 | `ax.pie()` |
| 판다스 영역 그래프 | `df.plot.area()` |
| 판다스 막대 그래프 | `df.plot.bar()` |
| Figure 저장 | `fig.savefig()` |
---

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
