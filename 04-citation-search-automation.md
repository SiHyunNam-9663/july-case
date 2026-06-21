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
→ 점수화
→ 슬라이드별 citation 배정
→ 최종 핵심 논문 4개 선정
```

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
