# 데이터분석 4주차 정규과제

📌데이터분석 정규과제는 매주 정해진 분량의 『*혼자 공부하는 데이터 분석 with 파이썬*』 을 읽고 학습하는 것입니다. 이번 주는 아래의 **DataAnalysis_4th_TIL**에 나열된 분량을 읽고 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 제시된 강의를 참고하여 보완하는 것이 좋습니다.

<!-- 강의 링크는 아래와 같습니다.
https://www.youtube.com/watch?v=HNlRYQnLkek&list=PLVsNizTWUw7FGzSRCkQrPEEe-ljVXgS7k&index=8
https://www.youtube.com/watch?v=Cbk_tQtuhbM&list=PLVsNizTWUw7FGzSRCkQrPEEe-ljVXgS7k&index=9
-->


## DataAnalysis_4th_TIL

### 4장 데이터 요약하기
#### 01. 통계로 요약하기
#### 02. 분포 요약하기


## Study Schedule

| 주차  | 공부 범위     | 완료 여부 |
| ----- | ------------- | --------- |
| 1주차 | p.24~81    | ✅         |
| 2주차 | p.84~151   | ✅         |
| 3주차 | p.154~219  | ✅         |
| 4주차 | p.222~279 | ✅         |
| 5주차 | p.282~325 | 🍽️         |
| 6주차 | p.328~379 | 🍽️         |
| 7주차 | p.382~430 | 🍽️         |

<br>

<!-- 여기까진 그대로 둬 주세요-->
<img width="2376" height="1594" alt="데이터분석학습로드맵" src="https://github.com/user-attachments/assets/78bdd7e8-a5f4-4632-af2f-05f7aaa7f886" />


# 1️⃣ 개념 정리 

## 01. 통계로 요약하기
### 01. 불필요한 데이터 삭제하기

---

**핵심 키워드:** `평균` `중앙값` `분위수` `분산` `표준편차` `최빈값`

### 목차

- [가. describe() 메서드](#가.-describe()-메서드)
- [나. 평균 구하기](#나.-평균-구하기)
- [다. 중앙값 구하기](#다.-중앙값-구하기)
- [라. 최솟값, 최댓값, 분위수, 백분위 구하기](#라.-최솟값,-최댓값,-분위수,-백분위-구하기)
- [마. 분산, 표준편차, 최빈값 구하기](마.-분산,-표준편차,-최빈값-구하기)
- [바. 데이터프레임에서 기술통계 구하기](#바.-데이터프레임에서-기술통계-구하기)
- [표로 정리하는 핵심 함수와 메서드](#표로-정리하는-핵심-함수와-메서드)


---

## 기술통계 구하기

- **기술통계, 요약통계(Descriptive Statistics, Summary Statistics):** 정량적 수치로 전체 데이터의 특징을 요약하거나 이해하기 쉬운 간단한 그래프로 시각화하여 표현하는 것
- **탐색적 데이터 분석(Exploratory Data Analysis):** 데이터 시각화를 아우르는 데이터 분석 방법

## 가. describe() 메서드 

판다스는 데이터프레임에서 수치형 열에 대한 8가지 통계량을 계산하여 자동으로 추출해낼 수 있다.

```python
ns_book6.describe()
```

| 통계량 | 의미 |
|:---:|:---:|
| `COUNT` | 누락된 값을 제외한 데이터의 개수 |
| `MEAN` | 평균 |
| `STD` | 표준편차 |
| `MIN` | 최솟값 |
| `0.25, 0.5, 0.75` | 순서대로 늘어 놓았을 때 25% 지점, 중앙값, 75% 지점 |
| `MAX` | 최댓값 |

## 가. describe() 메서드의 응용

### 1. 사분위수 지정

```python
ns_book7.describe(percentiles=[0.3, 0.6, 0.9])
```

> 특정 비율에 위치한 값을 보고 싶다면 괄호 안에 percentiles=[수치]를 작성하면 된다.

### 2. 비수치형 데이터 기술통계 

```python
ns_book7.describe(include='object')
```

> 열의 데이터 타입이 수치가 아닌 다른 데이터 타입의 열의 기술통계를 보고 싶다면 **include='type' 매개변수**에 데이터 타입을 지정할 수도 있다.


| 통계량 | 의미 |
|:---:|:---:|
| `COUNT` | 누락된 값을 제외한 데이터의 개수 |
| `UNIQUE` | 고유한 값의 개수 |
| `TOP` | 가장 많이 등장하는 값 |
| `FREQ` | top행에 등장하는 항목에 대한 빈도수 |

## 나. 평균 구하기

```python
x = [10, 20, 30]
sum = 0
for i in range(3)
  sum += x[i]
print("평균:", sum / len(x))
```

### 1. range() 함수
- range() 함수의 핵심은 반복이다. 하나의 숫자를 입력할 경우 0부터 입력된 숫자 **직전까지** 반복할 수 있는 객체를 만든다.
- 따라서, for 문에 range(3)을 입력하면 변수 i에 0, 1, 2를 대입할 수 있다. 결국 x[0]부터 x[2]까지 반복하며 sum에 값이 누적된다.
- 이러한 반복 구조는 수학의 Σ와 같다고 볼 수 있다.

| 코드 구조 | 수학적 의미 |
|:---:|:---:|
| <img width="194" height="131" alt="image" src="https://github.com/user-attachments/assets/a9335d4d-0eb0-425a-a536-a24f3c9c31fd" /> | <img width="248" height="87" alt="image" src="https://github.com/user-attachments/assets/0185a265-0a7f-4d49-ba27-af865c132211" /> |



### 2. mean() 메서드

```python
ns_book7['대출건수'].mean()
```

판다스 데이터프레임과 시리즈 객체에서 평균을 계산하는 가장 편리한 메서드는 함수 이름 뒤에 .mean()만 붙이면 된다.

## 다. 중앙값 구하기

### 1. 기본함수 median()

```python
ns_book7['대출건수'].median()
```

```python
temp_df = pd.DataFrame([1,2,3,4])
temp_df.median()
```
> 데이터 개수가 짝수이면 가운데 두 개의 값을 평균하여 중앙값을 결정한다.

### 2. 중복값 제거하고 중앙값 구하기

```python
ns_book7['대출건수'].drop_duplicates().median()
```

## 라. 최솟값, 최댓값, 분위수, 백분위 구하기

### 1. 최솟값과 최댓값 구하기

```python
ns_book7['대출건수'].min()
```

```python
ns_book7['대출건수'].max()
```

### 2. 분위수 구하기 quantile()

```python
ns_book7['대출건수'].quantile([0.25, 0.5, 0,75])
```

```python
pd.Series([1,2,3,4,5]).quantile(0.9)
```
> interpolation 매개변수의 기본적인 보간 방식은 linear이다.

### ※ interpolation 매개변수

두 지점 사이에 놓인 특정 위치의 값을 구하는 방법을 보간(interpolation)이라고 하며, 판다스에서 보간을 수행하는 매개변수를 interpolation 매개변수라고 한다.
quantile 메서드의 interpolation 매개변수를 통해 두 지점 사이에 놓인 특정 위치의 값을 어떻게 구할지 그 방식을 내 마음대로 정할 수 있다.

interpolation 매개변수의 보간방식 : linear, midpoint, nearest, lower, higher

#### 1. midpoint

```python
pd.Series([1,2,3,4,5]).quantile(0.9, interpolation='midpoint')
```
> midpoint는 분위수에 상관없이 무조건 두 수 사이의 중앙값을 사용한다.

#### 2. nearest

```python
pd.Series([1,2,3,4,5]).quantile(0.9, interpolation='nearest')
```
> nesrest는 두 수 중에서 더 가까운 값을 선택한다.
> 이 외에도 더 작은 값을 선택하는 lower, 더 큰 값을 선택하는 higher가 있다.

### 3. 백분위 구하기

#### 1. 불리언 배열 만들기

```python
borrow_10_flag = ns_book7['대출건수'] < 10
```

#### 2. 평균 구하기

```python
borrow_10_flag.mean()
```

## 마. 분산, 표준편차, 최빈값 구하기

### 1. 분산(s^2) 구하기

```python
ns_book7['대출건수'].var()
```
> 분산(Variation)은 제곱을 했기 때문에 데이터가 평균에서 멀어질수록 그 값이 급속도로 커진다. 또한, 단위도 제곱 처리되어 해석하기 어려워진다. 그래서 보통의 경우 분산에 제곱근을 취한 표준 편차를 사용한다.

### 2. 표준편차(s) 구하기

```python
ns_book7['대출건수'].std()
```
> 표준편차(Standard Deviation)는 평균을 중심으로 데이터가 대략 얼만큼 떨어져 분포해 있는지 표현하는 값이다. 어떤 도서의 대출 건수를 확인했을 때 평균보다 s만큼 더 많거나 적을 수 있다는 것이다.

### 3. 최빈값(mode) 구하기

```python
ns_book7['도서명'].mode()
```
```python
ns_book7['발행년도'].mode()
```
> mode() 메서드는 텍스트뿐만 아니라 수치형에도 적용할 수 있다.

## 바. 데이터프레임에서 기술통계 구하기

수치형 열에 대해서만 기술통계량을 구할 수 있으므로, **numeric_only() 매개변수**를 통해 기술통계를 구할 열을 지정해줘야 한다.

지정 안 해두면 모든 데이터 타입의 열에 대해 수행하기 때문에 시간이 매우 오래 걸리거나 에러가 난다.

```python
ns_book7.mean(numeric_only=True)
```

### loc 메서드와 최빈값 mode

```python
ns_book7.loc[:, '도서명'].mode()
```
> loc 메서드로 데이터프레임의 각 열에 대해 최빈값을 찾을 수 있다. 이때, mode() 메서드 출력 결과물 사이에는 서로 연관이 없음에 유의한다.

```python
ns_book7.to_csv('ns_book7.csv', index=False)
```
> CSV 파일로 저장하기

## ★ 표로 정리하는 핵심 함수와 메서드

| 함수/메서드 | 기능 |
|---|---|
| `DataFrame.describe()` | 데이터프레임의 기술통계량 출력 |
| `Series.mean()` | 데이터의 평균 계산 |
| `numpy.mean()` | 입력된 배열의 평균 계산 |
| `Series.median()` | 데이터의 중앙값 도출 |
| `numpy.median()` | 입력된 배열의 중앙값 도출 |
| `Series.quantile()` | 데이터의 분위수 계산 |
| `numpy.quantile()` | 입력된 배열의 분위수 계산 |
| `Series.var()` | 데이터의 분산 계산 |
| `numpy.var()` | 입력된 배열의 분산 계산 |
| `Series.std()` | 데이터의 표준편차 계산 |
| `numpy.std()` | 입력된 배열의 표준편차 계산 |
| `Series.mode()` | 데이터의 최빈값 도출 |

---

### 02. 분포 요약하기

---

**핵심 키워드:** `산점도` `히스토그램` `도수` `로그스케일` `상자수염그림`

### 목차

- [가. 산점도](#가.-산점도)
- [나. 히스토그램](#나.-히스토그램)
- [다. 상자 수염 그림](#다.-상자-수염-그림)
- [표로 정리하는 핵심 함수와 메서드](#표로-정리하는-핵심-함수와-메서드)

---

## 가. 산점도 scatter()
### 1. 맷플롯립 호출 후 산점도 그리기

산점도는 두 변수(variable) 혹은 두 가지 특성(feature)값을 직교 좌표계에 점으로 찍는 그래프로, 데이터를 화면에 뿌리듯 그리는 그래프라고 볼 수 있다.

산점도를 통해 두 변수 간 상관관계를 확인하는 것도 가능하다.

파이썬에서 그래프를 그리는 데 사용하는 대표적인 패키지는 맷플롯립(matplotlib)이다.

```python
import matplotlib.pyplot as plt
plt.scatter([1,2,3,4], [1,2,3,4])
plt.show()
```
```python
plt.scatter(ns_book7['번호'], ns_book7['대출건수'])
plt.show()
```
```python
average_borrows = ns_book7['대출건수']/ns_book7['도서권수']
plt.scatter(average_borrows, ns_book7['대출건수'], alpha=0.1)
plt.show()
```

### 2. 투명도 조절하기 alpha
```python
plt.scatter(ns_book7['도서권수'], ns_book7['대출건수'], alpha=0.1)
plt.show
```
> alpha는 투명도를 지정한다. 0에 가까울수록 투명해지고, 1에 가까울수록 불투명해진다.


## 나. 히스토그램 hist()

히스토그램은 수치형 특성의 값을 일정한 구간, 계급(bin)으로 나누어 구간 안에 포함된 데이터 개수를 막대 그래프로 그린 그래프이다.

구간 안에 속한 데이터의 갯수를 도수(frequency)라고 부른다.

히스토그램에 나오는 구간과 도수를 표로 요약한 것을 도수분포표(frequency table)이라고 한다.

### 히스토그램 그리기
- **hist() 함수**는 1차원 데이터를 입력받아 히스토그램을 그리며, 기본적으로 데이터를 10개의 구간으로 나눈다.
- **bins 매개변수**를 통해 데이터를 몇 개 구간으로 나눌지 정할 수 있다.

```python
plt.hist([0,3,5,6,7,7,9,13], bins=5)
plt.show()
```

### 히스토그램 구간 파악하기
- numpy에서 제공하는 **histogram_bin_edges() 함수**를 통해 다섯 구간의 경곗값을 확인한다.
```python
import numpy as np
np.histogram_bin_edges([0,3,5,6,7,7,9,13], bins=5)
```

## 표준정규분포 난수 생성

넘파이의 `randn()` 함수는 평균이 0이고 표준편차가 1인 표준정규분포에서 난수를 생성한다. 원하는 표본의 개수를 인수로 전달하여 난수 배열을 만들 수 있다.

### 주요 함수

| 함수 | 기능 |
|---|---|
| `np.random.seed()` | 난수 생성기의 초기값 고정 |
| `np.random.randn()` | 표준정규분포를 따르는 난수 생성 |
| `np.mean()` | 배열의 평균 계산 |
| `np.std()` | 배열의 표준편차 계산 |
| `print()` | 계산 결과 출력 |

### 난수 생성

```python
import numpy as np

np.random.seed(42)
random_samples = np.random.randn(1000)
```

> **함수 설명**
>
> - `np.random.seed(42)`: 난수 생성기의 초기값을 42로 고정
> - `np.random.randn(1000)`: 표준정규분포를 따르는 난수 1,000개 생성
> - `random_samples`: 생성된 난수 1,000개를 저장한 넘파이 배열

`randn()` 함수는 코드를 실행할 때마다 다른 난수를 생성한다. `seed()` 함수로 초기값을 고정하면 코드를 반복 실행하더라도 동일한 난수를 생성할 수 있다. 이는 분석 결과의 재현성을 확보하는 데 활용된다.

> **함수 설명**
>
> - `np.mean(random_samples)`: 생성된 난수의 평균 계산
> - `np.std(random_samples)`: 생성된 난수의 표준편차 계산
> - `print()`: 평균과 표준편차를 차례대로 출력

### 결과 해석

- 표본 평균: 약 `0.019`
- 표본 표준편차: 약 `0.979`
- 이론적 평균: `0`
- 이론적 표준편차: `1`

생성된 표본의 평균이 0에 가깝고 표준편차가 1에 가까우므로, `random_samples`가 표준정규분포의 특성과 대체로 일치함을 확인할 수 있다.

### 로그 스케일로 구간 조정하기

- 한 구간의 도수가 너무 커서 다른 구간에는 도수가 표시되지 않을 정도라면 y축을 로그 스케일로 바꿔 해결할 수 있다.
- 로그 스케일(log scale)로 바꾼다는 것은 y축에 로그 함수를 적용하여 간극을 크게 줄이는 것을 말한다.
- **즉, 로그 스케일로 변환된 그래프를 볼 경우 실제 데이터는 훨씬 더 격차가 크다는 점을 반드시 감안해야 한다.**

```python
plt.hist(ns_book7['대출건수'], bins=100)
plt.yscale('log')
plt.show()
```
> x축에 로그 스케일을 적용하고 싶다면 xscale() 함수를 적용하면 된다.

## 다. 상자 수염 그림 그리기

### 상자 수염 그림 그리기 순서
(1) 사분위수를 계산한다. 25% 지점과 75% 지점이 각각 밑면과 윗면이 되는 직사각형을 그린다. 이때, 두 지점간 거리를 IQR(Interquartile Range)라고 한다.

(2) 50% 지점, 즉 중간값에 해당하는 지점에 수평선을 긋는다.

(3) 사각형의 밑면과 윗면에서 사각형 높이의 1.5배만큼 떨어진 거리 안에서 가장 멀리 있는 샘플까지 수직선을 긋는다.

(4) 이 수직선 밖에서 최솟값과 최댓값까지 데이터를 점으로 표시한다. 이 영역의 데이터를 **이상치**(outliar)라고 부른다.



### boxplot() 함수

```python
plt.boxplot(ns_book7[['대출건수', '도서권수']])
plt.show()
```

```python
plt.boxplot(ns_book7[['대출건수', '도서권수']])
plt.yscale('log')
plt.show()
```


### 수평으로 그리기

```python
plt.boxplot(ns_book7[['대출건수', '도서권수']], vert=False)
plt.xscale('log')
plt.show()
```

### 수염 길이 조정하기

boxplot() 함수의 **whis 매개변수**에서 수염 길이를 조정할 수 있다. 기본값은 1.5이다.

```python
plt.boxplot(ns_book7[['대출건수', '도서권수']], whis=10)
plt.yscale('log')
plt.show()
```

whis 매개변수는 백분율로도 지정할 수 있다. (10, 90)으로 지정한다면 10%, 90% 백분위수에 해당하는 데이터까지 수염을 그린다.

```python
plt.boxplot(ns_book7[['대출건수', '도서권수']], whis=(0,100))
plt.yscale('log')
plt.show()
```

## ★ 표로 정리하는 핵심 함수와 메서드
<img width="587" height="223" alt="image" src="https://github.com/user-attachments/assets/4e2ed5a5-532b-4ac2-be37-1bf8ba439042" />



# 2️⃣ 수행 인증

<!-- 교재에서 안내된 과정을 직접 실행해본 뒤, 진행 결과가 보이도록 3장 이상의 스크린샷을 캡처하여 아래에 첨부해주세요.-->



<br>
<br>

# 3️⃣ 확인 문제

## 문제 1.

> **🧚Q. 이번 주차에는 확인문제 대신 실습 과제를 진행합니다. 캐글에서 원하는 데이터셋을 선택하여 기술통계를 계산하고, 다양한 시각화를 수행해보세요.
작업은 코랩에서 진행한 뒤, 코랩 링크를 아래에 첨부해주세요.**

```
여기에 코랩 링크를 첨부해주세요!
(제출 전, 코랩의 공유 설정을 ‘링크가 있는 모든 사용자가 보기 가능’으로 변경했는지 반드시 확인해주세요.)
```



### 🎉 수고하셨습니다.
