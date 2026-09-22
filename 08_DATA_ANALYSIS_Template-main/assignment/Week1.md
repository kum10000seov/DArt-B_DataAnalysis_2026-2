# 데이터분석 1주차 정규과제

📌데이터분석 정규과제는 매주 정해진 분량의 『*혼자 공부하는 데이터 분석 with 파이썬*』 을 읽고 학습하는 것입니다. 이번 주는 아래의 **DataAnalysis_1st_TIL**에 나열된 분량을 읽고 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 제시된 강의를 참고하여 보완하는 것이 좋습니다.

<!-- 강의 링크는 아래와 같습니다.
https://www.youtube.com/watch?v=qGE_rT_oQaQ&list=PLVsNizTWUw7FGzSRCkQrPEEe-ljVXgS7k
https://www.youtube.com/watch?v=tp9XmeaHU0E&list=PLVsNizTWUw7FGzSRCkQrPEEe-ljVXgS7k&index=2
https://www.youtube.com/watch?v=D46j-e_IHlI&list=PLVsNizTWUw7FGzSRCkQrPEEe-ljVXgS7k&index=3
-->


## DataAnalysis_1st_TIL

### 1장 데이터 분석을 시작하며
#### 01. 데이터 분석이란
#### 02. 구글 코랩과 주피터 노트북
#### 03. 이 도서가 얼마나 인기가 좋을까요?


## Study Schedule

| 주차  | 공부 범위     | 완료 여부 |
| ----- | ------------- | --------- |
| 1주차 | p.24~81    | ✅         |
| 2주차 | p.84~151   | 🍽️         |
| 3주차 | p.154~219  | 🍽️         |
| 4주차 | p.222~279 | 🍽️         |
| 5주차 | p.282~325 | 🍽️         |
| 6주차 | p.328~379 | 🍽️         |
| 7주차 | p.382~430 | 🍽️         |

<br>

<!-- 여기까진 그대로 둬 주세요-->
<img width="2376" height="1594" alt="데이터분석학습로드맵" src="https://github.com/user-attachments/assets/557bbc8d-51bc-40d2-9623-b10f80ba07ea" />


# 1️⃣ 개념 정리 

## 01. 데이터 분석이란

1) **데이터 분석**은 데이터를 수집, 처리, 정제, 분석, 모델링하여 의사 결정을 내리는 데 도움을 주는 작업을 말한다. 통계학과 머신러닝의 기술을 사용하고, 비즈니스 문제를 해결하기 위해 도메인 지식이 필요하다.
2) 데이터 분석을 통계적 관점에서 3가지 개념으로 나눌 수 있다.

- **기술통계(Descriptive Statistics)** : 관측이나 실험을 통해 수집한 데이터를 정량화하거나 요약하는 기법을 말한다. ex) 평균, 최솟값, 최댓값
- **탐색적 데이터 분석(EDA, Exploratory Data Analysis)** : 데이터를 시각적으로 표현하여 주요 특징을 찾고 분석하는 방법
- **가설검정(Hypothesis Testing)** : 주어진 데이터를 기반으로 특정 가설이 합당한지 평가하는 과정
4) 데이터 과학은 데이터 분석, 머신러닝을 아우르는 개념이다. 데이터 분석에 비해 머신러닝 모델을 만들어 문제를 해결하는 데 많은 비중을 둔다.
5) 좁은 의미의 데이터 분석은 기술통계, EDA, 가설검정만을 포함하지만, 넓은 의미의 데이터 분석은 데이터 수집, 처리, 정제, 모델링까지의 전 과정을 아우르는 표현이다.
<img width="566" height="127" alt="image" src="https://github.com/user-attachments/assets/7cbd984e-b12b-482d-83aa-dfba3f9aa89f" />


6) 파이썬(Python)은 데이터 분석, 데이터 과학, 머신러닝 작업에 사용할 수 있는 인기 있는 프로그래밍 언어이다. 넘파이(Numpy), 판다스(Pandas), 맷플롯립(matplotlib) 등 데이터 분석에 필요한 다양한 패키지를 활용할 수 있는 플랫폼이 된다.
- **넘파이(Numpy)** : numerical python의 준말로, **고성능 과학 계산**과 **다차원 배열**(array)을 위한 파이썬 패키지
- **판다스(Pandas)** : 엑셀의 sheet처럼 숫자와 문자를 섞어서 표로 저장할 수 있는 **데이터프레임**을 사용, 편리한 데이터 처리와 분석 작업, 그래프 출력
- **맷플롯립(matplotlib)** : 데이터 시각화를 위한 기본 패키지로서, 다양한 **그래프와 시각화** 패키지(seaborn, bokeh 등) 사용
- **사이파이(SciPy)** : 넘파이 기반 **수학과학 계산** 전문 패키지로서, 미분, 적분, 확률, 선형대수, 최적화 등을 알고리즘으로 구현
- **사이킷런(scikit-learn)** : **머신러닝** 패키지로서, 넘파이와 사이파이 기반.



## 02. 구글 코랩과 주피터 노트북

1) 구글 코랩(Google CoLab)은 주피터 노트북의 장점을 바탕으로 개발된 웹 브라우저 기반의 파이썬 코드 실행 환경(플랫폼)을 말한다.
2) 노트북은 코랩의 프로그램 작성 파일이다. 일반 프로그램 파일과 달리 대화식으로 프로그램을 만들수 있으므로 교육 및 데이터 분석 목적에 부합. 노트북에서는 코드, 코드 실행 결과, 문서를 모두 저장 가능
3) 코랩에서 만든 노트북은 구글 드라이브의 'Colab Notebooks' 폴더에 저장하면 된다.
4) 깃허브(Github)는 분산 버전 관리 툴인 깃(Git)의 저장소를 호스팅하는 웹 서비스를 말한다. 코드 수정 이력을 버전별로 관리할 수 있고, 여러 사람이 공동으로 작업하기 편한 환경을 제공한다.
5) **마크다운(Markdown)** 은 HTML처럼 **마크업 언어**의 일종으로, 일반 텍스트로 가볍고 직관적인 서식 문서를 작성하는 데 활용한다.
6) 마크업 언어(Markup Language)란, 텍스트가 화면에 어떻게 표시되거나 구조화되어야 하는지를 나타내기 위해 데이터나 텍스트에 태그(Tag)나 특정 기호(Markup)를 덧붙이는 언어를 말한다. 문서의 구조와 서식을 **정의**하여 브라우저나 프로그램이 문서의 체계를 올바르게 인식하도록 지도하는 역할을 한다.

※ HTML과 마크다운의 차이

- HTML과 마크다운은 모두 마크업(MARKUP) 언어의 일종이지만, 기능에 있어 차이가 존재한다.
- HTML(Hypertext Markup Language)은 웹페이지의 멀티미디어, 스타일, 자바스크립트, 복잡한 레이아웃 등 웹의 모든 기능을 정의하고 구현할 수 있다. 즉, HTML은 웹사이트의 뼈대를 잡는 역할을 한다.
- 반면, 마크다운(Markdown)은 HTML과는 독립적으로 최소한의 기호(#, * 등)만을 활용해 일반 텍스트 중심의 서식(제목, 굵기, 링크, 목록 등)만 지원하며 내부적으로는 HTML로 변환되어 화면에 렌더링된다.

<img width="568" height="468" alt="image" src="https://github.com/user-attachments/assets/8d750afa-4b74-4bcb-bb89-1e19bd4d7934" />

<img width="551" height="194" alt="image" src="https://github.com/user-attachments/assets/90cc1e57-f177-4d97-aff8-9af2c0486832" />

## 03. 이 도서가 얼마나 인기가 좋을까요?

1) **공개 데이터 세트**는 기업이나 정부 등이 무료로 공개하는 데이터 세트를 말한다. 누구나 저작권에 상관 없이 내려받아 데이터 분석이나 제품 개발에 활용할 수 있다.
2) **csv 파일**은 콤마(,)로 구분된 텍스트 파일이다. **한 줄이 하나의 레코드이며,** 레코드는 콤마로 구분된 여러 필드 혹은 열로 구성된다. 데이터가 엑셀처럼 표 형태를 가져야 하므로 레코드의 필드 개수는 모두 동일해야 한다.
3) 데이터 프레임은 판다스의 핵심 데이터 구조로 행(Row)과 열(Column)로 구성된다. csv 파일이나 엑셀 파일로부터 데이터프레임을 만들 수 있다.
4) 시리즈는 1차원 배열과 흡사한 판다스의 객체이다. **시리즈는 한 종류의 데이터만 포함할 수 있다.**
<img width="544" height="103" alt="image" src="https://github.com/user-attachments/assets/d845f319-226d-4e0a-95a9-0f264e8d15d4" />



# 2️⃣ 수행 인증

1. 도서관 정보나루 → 남산도서관 2026년 8월 장서 대출목록 다운로드
<img width="1030" height="638" alt="image" src="https://github.com/user-attachments/assets/347ec3d9-5ccb-4130-9f82-2afc2e29fc57" />



2. 장서 대출목록 csv를 메모장으로 열어본 모습
<img width="1262" height="368" alt="image" src="https://github.com/user-attachments/assets/fdc26dde-4418-4357-9a06-5635e41aa226" />



3. 교과서에 나온 모든 코드를 입력하여 실행한 결과
(구글 코랩의 코드는 2021년 6월 데이터로 실행)

<img width="1264" height="689" alt="image" src="https://github.com/user-attachments/assets/e52b005f-5288-4334-a96f-5e7dbf30c067" />


<img width="1267" height="695" alt="image" src="https://github.com/user-attachments/assets/a0a73d75-bfb2-4fb5-973d-fc7056d805e2" />


<img width="1262" height="694" alt="image" src="https://github.com/user-attachments/assets/7d2e914f-b487-40a4-ad17-d5a91e563845" />


<img width="1264" height="693" alt="image" src="https://github.com/user-attachments/assets/62205b8a-21f8-4dd7-b942-fea0a2c90408" />



<br>
<br>

# 3️⃣ 확인 문제

## 문제 1.

> **🧚Q. 데이터 분석의 개념을 넓은 의미와 좁은 의미로 나누어 설명하고, 두 개념의 차이점도 함께 정리해주세요.**


```
좁은 의미의 데이터 분석은 기술통계와 탐색적 데이터 분석, 가설검정 등 통계학적 관점에서의 과정만을 말하지만, 넓은 의미의 데이터 분석은 데이터를 수집, 처리, 정제하는 과정과 모델링까지 포함하는 개념이다.
```



### 🎉 수고하셨습니다.
