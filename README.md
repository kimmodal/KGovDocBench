# KGovDocBench
A Benchmark to evaluate the ability to understand insane South Korean Government documents, especially "보고서"s

## Sources

- 문서 유형: ‘공무원이 작성하는 보고서’ (not 인포그래픽, 논문)
- 출처: 중앙행정기관의 공개자료
- 기간: contamination을 막기 위해 최근 자료 위주
- 파일 형식: PDF와 HWPX 모두
    - HWPX는 지원하는 모델만

## Protocol

- MCQ (Multiple Choice Question) or short definite answers
    - not the entire annotations
- 각 카테고리별 여러개의 문서
- 같은 질문을 5번 반복해서 평균 계산
    - ml은 probabilistic 하기 때문
- 과도한 reasoning 없게 최대한 단순한 질의
- sanity check을 위해 쉬운 질문 20%

## Categories

- 표
    - 표 안의 표
    - 셀 병합
        - 비중
    - 여러 페이지에 걸쳐있는 커다란 표
    - 단위/범례
- 시각적 정보 #1: 표의 ‘형식’을 가졌으나, 실제로는 다른 용도로 쓰이는 것
    - 표로 만든 조직도
    - 표로 만든 절차도
    - 표로 색을 칠해서 만든 일정/계획
    - ‘비전’ 페이지
    - 표로 된 제목
    - 법령의 민원 서식, 별표
    - 표 여러개가 나열되어 있는 경우
- 시각적 정보 #2: 차트
- 목차/항목
    - ㅁ,ㅇ,-
    - 문서 전체의 구조/목차를 이해하는지 여부
    - (소제목)
- 기호
    - '*' as a footnote
    - ①②③ / ❶❷❸ / ㉮㉯㉰ / 네모 1,2,3 등 

## TODO

- actual grounding truth / annotation
    - 절차도, 조직도: mermaid
    - 표: html with each line's header information for merged cells
