# 06. 최종 출력 형식

## 1단계: 주제 후보 제안

케이스만 주어진 경우 먼저 아래 형식으로 답합니다.

```md
## 케이스 핵심
...

## 발표 주제 후보

| 순위 | 주제 후보 | 강조 질문 | 케이스 연결성 | 문헌 풍부도 | 발표 난이도 | 추천 이유 |
|---|---|---|---|---|---|---|
| 1 | ... | ... | 높음 | 높음 | 중간 | ... |
| 2 | ... | ... | 높음 | 중간 | 중간 | ... |
| 3 | ... | ... | 중간 | 높음 | 낮음 | ... |

## 추천
1순위는 `...`입니다.
선택하면 이 주제로 슬라이드 14 이후 bullet과 논문 검색을 진행합니다.
```

## 2단계: 선택된 주제의 슬라이드별 초안

사용자가 주제를 선택하면 아래 형식으로 답합니다.

```md
## 선택된 주제
...

## 핵심 질문
...

## Slide 14. 제목

### 발표 bullet
- ...
- ...
- ...

### PPT용 대제목/세부 내용
- 대제목: ...
  - ...
  - ...
  - ...

- 대제목: ...
  - ...
  - ...

### 심화 설명
...

### Citation 후보
- ...
```

## 3단계: 논문 검색 및 선정

논문 검색 후 아래 형식으로 정리합니다.

```md
## 슬라이드별 검색어

Slide 15:
...

Slide 16:
...

## 3-1단계. 슬라이드별 후보 논문 점수화

| Slide | 순위 | 논문 | PMID | 관련성 | 최신성 | 권위 | 인용 | 총점 |
|---|---:|---|---:|---:|---:|---:|---:|---:|
| Slide 15 | 1 | ... | ... | 40 | 18 | 23 | 10 | 91 |

여기까지가 1단계입니다.
사용자 검수 후 2단계인 논문 요약과 bullet 매칭으로 진행합니다.
```

사용자가 검수하면 아래 형식으로 2단계를 진행합니다.

```md
## 3-2단계. 논문 한 줄 요약과 bullet 매칭

| Slide | 논문 | 한 줄 요약 | 연결할 bullet |
|---|---|---|---|
| Slide 15 | ... | ... | ... |
```

사용자가 다시 요청하면 아래 형식으로 3단계를 진행합니다.

```md
## 3-3단계. 발표용 인용 문장

### Slide 15
발표 문장:
...

하단 citation:
Author et al. Journal. Year. PMID.
```

## 4단계: PPT 제작용 정리

PPT에 바로 옮길 수 있도록 아래처럼 압축합니다.

```md
## Slide 18. Why Double Plating?

- 대제목: Fragment-specific stability
  - Double plating can help control dorsal and volar fragments when one plate is insufficient.
  - This is useful when articular fragments and metaphyseal alignment require separate control.

- 대제목: Maintain corrected alignment
  - Stable fixation supports restored volar tilt and metaphyseal alignment until union.
  - Bone graft can support the correction when an opening gap or structural defect remains.

하단 citation:
Author et al. Journal. Year
```

## 답변 원칙

- 사용자가 케이스만 주면 1단계부터 시작합니다.
- 사용자가 이미 주제와 강조 질문을 주면 2단계부터 시작합니다.
- 사용자가 PPT에 옮길 bullet 정리를 요청하면 `대제목/세부 내용` 형식으로 압축합니다.
- 이때 슬라이드별 대제목은 1-3개, 각 대제목 아래 세부 내용은 2-4줄을 기본으로 합니다.
- 논문 검색을 요청하면 먼저 슬라이드별 후보 논문 점수표를 제시하고, 사용자 검수 후 요약/bullet 매칭으로 넘어갑니다.
- 논문을 bullet과 연결할 때는 발표 전체 주제가 아니라 해당 bullet을 직접 뒷받침하는지를 우선합니다.
- 논문 검색에 네트워크 승인이 필요하면 즉시 승인 요청을 보냅니다.
- 최종 논문은 PubMed 링크 또는 PMID를 함께 제공합니다.
