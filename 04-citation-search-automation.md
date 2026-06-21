# 04. Citation 검색 자동화

## 목적

슬라이드별로 필요한 논문 종류가 다르므로, 검색어도 슬라이드 역할에 맞춰 다르게 만듭니다.

## 기본 흐름

```text
선택된 발표 주제
→ 핵심 키워드 추출
→ 슬라이드별 검색어 생성
→ PubMed 후보 수집
→ 논문 metadata 확인
→ 슬라이드별 후보 논문 점수화
→ 사용자 검수
→ 논문 한 줄 요약
→ 슬라이드 bullet과 논문 매칭
→ 발표용 인용 문장 작성
→ 최종 citation 배정
```

## 단계별 진행 원칙

논문 검색과 citation 배정은 한 번에 최종 확정하지 않습니다.

### 1단계: 슬라이드별 후보 논문 점수화

- 각 슬라이드마다 후보 논문을 대략 3개씩 제시합니다.
- 후보 논문은 해당 슬라이드의 bullet을 직접 뒷받침할 수 있어야 합니다.
- 점수는 슬라이드/bullet 직접 관련성, 최신성, 저널/학회 권위, 인용수 또는 landmark 여부를 기준으로 매깁니다.
- 1단계가 끝나면 사용자 검수를 받고, 승인 후 다음 단계로 넘어갑니다.

### 2단계: 논문 요약과 bullet 매칭

- 검수된 후보 논문을 한 줄로 요약합니다.
- 각 논문이 어떤 대제목 또는 세부 내용과 연결되는지 명시합니다.
- 발표 내용과 직접 연결되지 않는 논문은 이 단계에서 제외하거나 보조 논문으로 낮춥니다.

### 3단계: 발표용 인용 문장 작성

- 각 슬라이드에서 실제로 말할 수 있는 인용 문장을 작성합니다.
- 논문의 결론을 과장하지 않고, 연구 설계와 한계를 반영합니다.
- 예를 들어 comparative study에서 우월성이 명확하지 않으면 "더 좋다"가 아니라 "선택 가능한 fixation strategy"처럼 표현합니다.

## 네트워크 승인 원칙

PubMed API, NCBI E-utilities, Crossref, Semantic Scholar 등 외부 네트워크 접근이 필요하면 사용자에게 승인 요청을 보냅니다.

승인된 접근은 해당 케이스의 논문 검색 작업 범위에서만 사용합니다.

## 슬라이드별 검색 대상

| 슬라이드 | 검색 대상 |
|---|---|
| Slide 15 | anatomy, biomechanics, radiographic parameter |
| Slide 16 | clinical outcome, functional outcome, symptom, prognosis |
| Slide 17 | mechanism, malalignment, why correction matters |
| Slide 18 | treatment strategy, surgical technique, fixation method |
| Slide 19 | review, systematic review, meta-analysis, landmark paper |

## 검색어 생성 예시

주제:

`Dorsal Barton fracture malunion, double plating, dorsal angulation correction`

검색어:

```text
Slide 15:
distal radius radiographic evaluation volar tilt dorsal tilt ulnar variance

Slide 16:
distal radius malunion functional outcome corrective osteotomy

Slide 17:
distal radius malunion corrective osteotomy volar tilt carpal alignment

Slide 18:
combined dorsal volar plate fixation distal radius
fragment-specific fixation distal radius dorsal rim

Slide 19:
distal radius malunion corrective osteotomy review systematic review
```

## PubMed 조회 시 수집할 정보

- PMID
- 제목
- 저자
- 저널
- 출판 연도
- 논문 유형
- abstract
- DOI가 있으면 DOI

## 보조 metadata 확인

PubMed는 인용수와 impact factor를 직접 제공하지 않습니다.

- 인용수는 가능하면 OpenAlex, Semantic Scholar, Google Scholar 등으로 보조 확인합니다.
- impact factor는 정확 수치 대신 저널/학회 권위 등급으로 반영할 수 있습니다.
- 최신 논문은 인용수가 낮을 수 있으므로, 직접 관련성이 높으면 낮은 인용수만으로 제외하지 않습니다.

## 최종 출력

각 논문은 아래 형식으로 정리합니다.

```md
- PMID:
- Title:
- Journal:
- Year:
- Study type:
- 왜 이 슬라이드에 적합한가:
- 슬라이드 하단 표기:
```

슬라이드별 후보 점수표는 아래 형식을 사용합니다.

```md
| Slide | 순위 | 논문 | PMID | 관련성 | 최신성 | 권위 | 인용 | 총점 |
|---|---:|---|---:|---:|---:|---:|---:|---:|
```
