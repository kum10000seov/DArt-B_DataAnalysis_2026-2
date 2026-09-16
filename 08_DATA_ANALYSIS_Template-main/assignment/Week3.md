# 데이터분석 3주차 정규과제

📌데이터분석 정규과제는 매주 정해진 분량의 『*혼자 공부하는 데이터 분석 with 파이썬*』 을 읽고 학습하는 것입니다. 이번 주는 아래의 **DataAnalysis_3rd_TIL**에 나열된 분량을 읽고 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 제시된 강의를 참고하여 보완하는 것이 좋습니다.

<!-- 강의 링크는 아래와 같습니다.
https://www.youtube.com/watch?v=CE3_InvbmLY&list=PLVsNizTWUw7FGzSRCkQrPEEe-ljVXgS7k&index=6
https://www.youtube.com/watch?v=hhbzUEQWdTg&list=PLVsNizTWUw7FGzSRCkQrPEEe-ljVXgS7k&index=7
-->


## DataAnalysis_3rd_TIL

### 3장 데이터 정제하기
#### 01. 불필요한 데이터 삭제하기
#### 02. 잘못된 데이터 수정하기


## Study Schedule

| 주차  | 공부 범위     | 완료 여부 |
| ----- | ------------- | --------- |
| 1주차 | p.24~81    | ✅         |
| 2주차 | p.84~151   | ✅         |
| 3주차 | p.154~219  | ✅         |
| 4주차 | p.222~279 | 🍽️         |
| 5주차 | p.282~325 | 🍽️         |
| 6주차 | p.328~379 | 🍽️         |
| 7주차 | p.382~430 | 🍽️         |

<br>

<!-- 여기까진 그대로 둬 주세요-->


# 1️⃣ 개념 정리 

## 01. 불필요한 데이터 삭제하기

1. **데이터 정제**(Data Cleaning)는 수집된 데이터에서 잘못된 부분을 고치거나 제거하여 필요한 데이터를 준비하는 과정을 말한다. 데이터가 올바르게 정제되지 못하면 분석된 결과를 왜곡시킬 수 있으며 잘못된 의사 결정을 초래할 수 있다.
2. 데이터를 정제하는 과정과 데이터 분석 및 머신러닝에 적합한 형태로 데이터를 변환하는 과정을 합쳐서 **데이터 랭글링 및 데이터 먼징**(Data Wrangling, Data Munging)이라고 한다.
3. 판다스의 데이터프레임과 인덱스를 하나의 값과 비교하면 데이터프레임과 인덱스에 있는 모든 원소와 비교하는데, 이를 **원소별 비교**라고 한다. 비교한 결과는 True 혹은 False로 구성된 **불리언 배열**(Boolean Array)로 변환된다.
4. **넘파이**(Numpy)는 파이썬의 대표적인 다차원 배열이다. 판다스의 데이터프레임과 달리 한 종류의 데이터만 담을 수 있지만 매우 효율적이고 성능이 높다. 파이썬의 여타 과학 패키지와 호환성이 높으며 기본 데이터 구조로 널리 사용된다.

※ 표로 정리하는 핵심 함수와 메서드

<img width="590" height="308" alt="image" src="https://github.com/user-attachments/assets/dabcb0e2-7d09-4971-b5c9-137463a63fc6" />

## 02. 잘못된 데이터 수정하기

1. **NaN**은 판다스에서 누락된 값을 표시하는 기호이다. isna() 메서드를 사용하여 NaN의 여부를 확인하거나 nonta() 메서드를 활용해 NaN이 아닌 값인지 체크할 수 있다.
2. **정규 표현식**은 문자열에서 패턴을 찾고 대체하기 위한 규칙의 모음이다. 정규 표현식을 사용하면 복잡한 패턴을 가진 문자열을 쉽게 검색할 수 있다.

※ 표로 정리하는 핵심 함수와 메서드

<img width="585" height="235" alt="image" src="https://github.com/user-attachments/assets/d1b2961d-cf1c-44ae-b962-de0309a0ce77" />


# 2️⃣ 수행 인증

※ API 발급 결과 (도서관 정보나루)

<img width="611" height="508" alt="image" src="https://github.com/user-attachments/assets/24325ffe-3b99-47e5-94f8-593df8057bb2" />



※ 데이터 분석 수행 과정


<br>
<br>

# 3️⃣ 확인 문제

## 문제 1.

> **🧚Q. 다음 두 데이터프레임 df1, df2를 합쳐서 데이터프레임 df3를 만들려고 합니다.**  
> 적절한 판다스 명령을 선택해주세요.

<table>
<tr>

<td>

### df1

| index | col1 | col2 |
|-------|------|------|
| 0     | x    | 5    |
| 1     | y    | 6    |
| 2     | z    | 7    |

</td>

<td>

### df2

| index | col3 | col4 |
|-------|------|------|
| 0     | x    | 50   |
| 1     | y    | 60   |
| 2     | w    | 70   |

</td>

<td align="center" valign="middle">

<h2> ➜ </h2>

</td>

<td>

### df3 (결과)

| index | col1 | col2 | col3 | col4 |
|-------|------|------|------|------|
| 0     | x    | 5.0  | x    | 50.0 |
| 1     | y    | 6.0  | y    | 60.0 |
| 2     | z    | 7.0  | NaN  | NaN  |
| 3     | NaN  | NaN  | w    | 70.0 |

</td>

</tr>
</table>

```
1️⃣ pd.merge(df1, df2)
2️⃣ pd.merge(df1, df2, how='left')
3️⃣ pd.merge(df1, df2, left_on='col1', right_on='col3', how='outer')
4️⃣ pd.merge(df1, df2, left_on='col1', right_on='col3', how='inner')
```

```
여기에 선택한 답과 그 이유를 간단히 서술해주세요!
```



### 🎉 수고하셨습니다.
