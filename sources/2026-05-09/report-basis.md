# 2026-05-09 보고서 작성 근거

## 포함 항목

| ID | 제목 | 태그 | 카테고리 | 포함 근거 |
|-----|------|------|---------|----------|
| src-963 | IRGC 해군·항공우주군 쌍방 보복 위협 | new | 군사 | 전례 없는 이중 병과 동시 보복 위협, 전쟁 재개 가능성 직접 시사 |
| src-964 | Mokhber '원자폭탄 수준' 호르무즈 독트린 | new | 전략/교리 | 호르무즈 통제를 핵무기급 전략자산으로 격상하는 공식 수사, 교리 전환 신호 |
| src-965 | 헤즈볼라 이스라엘 영내 공격 | new | 군사/레바논 | 4월 휴전 이후 최초 이스라엘 영토 내 공격 주장, 휴전 질적 붕괴 |
| src-966 | 레바논 23일차 19명+ 사망 | new | 군사/레바논 | 드론으로 베이루트 근교까지 타격, 어린이 포함 사상자 지속 |
| src-967 | UAE 3차 공격 | new | 군사/걸프 | 탄도미사일 2발 + 드론 3기, IRGC 부인 패턴 지속 |
| src-968 | MoU 검토 지연 — 갈리바프 조롱 | new | 외교 | 이란 '데드라인 무시', 강경파 우세 확인, 협상 교착 |
| src-969 | Ocean Koi 유조선 나포 | new | 군사/해상 | 이란 해군의 대응 나포, 해상 tit-for-tat 에스컬레이션 |
| src-970 | FAO 식량가격 3년 최고 | new | 경제 | 130.7 지수, 비료 +20%, 글로벌 식량 공급망 파급 |
| src-971 | Trump-Xi 5/14-15 베이징 정상회담 | new | 외교/지정학 | 이란 전쟁이 관세·희토류 의제 밀어낼 가능성, 사실상 소프트 데드라인 |
| src-972 | 한국 유가 6주 연속 상승 | new | 경제/국내 | 휘발유 2011.2원/L, 석유류 +21.9%, 소비자물가 21개월 최고 |

## 제외 항목

### update (5건) — 본문 내 관련 섹션에서 언급

| ID | 제목 | 제외 근거 |
|-----|------|----------|
| src-973 | CNN live updates Day 71 | update — src-963/965/967 내용 통합 |
| src-974 | Al Jazeera live | update — src-966/968 내용 통합 |
| src-975 | CBS live updates | update — src-968 내용 통합 |
| src-976 | 레바논 19명+ 사망 (AJ) | update — src-966에 통합 |
| src-977 | 이란 호르무즈 '영구 폐쇄' 경고 | update — src-964 내용 보강 |

### reported (15건) — 출처 목록에만 기재

| ID | 제목 | 제외 근거 |
|-----|------|----------|
| src-978~982 | Mokhber '원자폭탄' 보도 5건 | reported — src-964 대표, Asharq Al-Awsat/RT/MEE/L'Orient/Turkiye Today |
| src-983~985 | 레바논 공습 보도 3건 | reported — src-966 대표, WaPo/PBS/NBC |
| src-986~987 | Ocean Koi 나포 2건 | reported — src-969 대표, Just The News/IRNA |
| src-988 | FAO 식량가격 | reported — src-970 대표 |
| src-989 | UAE 공격 | reported — src-967 대표 |
| src-990 | 한국 물가 상승 | reported — src-972 대표 |
| src-991 | Trump-Xi 정상회담 | reported — src-971 대표 |
| src-992 | 이란 UAE 보복 경고 | reported — src-967 대표 |

## KG 시각화 범위

### 다이어그램 1: 호르무즈 에스컬레이션 & 보복 위협
- 노드: IRGC (ent-005), IRGC Naval Command (ent-322), IRGC Aerospace Force (ent-323), US Military (ent-003), Strait of Hormuz (ent-008), Mokhber (ent-321), Hormuz Atomic Bomb Doctrine (ent-328), Ocean Koi Seizure (ent-327), M/T Ocean Koi (ent-332), Iran (ent-002)
- 엣지: affiliatedWith, opposes, mentions, relatedTo, participatesIn
- 강조: IRGC 이중 병과 동시 위협 + Mokhber 교리 격상의 수렴

### 다이어그램 2: 레바논 휴전 붕괴 & MoU 교착
- 노드: Hezbollah (ent-043), Israel (ent-004), Lebanon (ent-044), Cross-Border Strikes (ent-324), Day 23 Airstrikes (ent-325), Ghalibaf (ent-051), 14-Point MoU (ent-287), Trump (ent-001), Trump-Xi Summit (ent-331)
- 엣지: participatesIn, locatedIn, opposes, follows

### 다이어그램 3: 글로벌 경제 파급
- 노드: Iran (ent-002), UAE (ent-214), UAE 3rd Attack (ent-326), FAO Food Price (ent-330)
- 엣지: participatesIn, locatedIn, causedBy

총 주요 노드: 20개 이내

## 보고서 구성 방향

### 헤드라인
- **IRGC 해군·항공우주군 동시 보복 위협 + Mokhber '원자폭탄' 독트린** — 호르무즈를 핵무기급 전략자산으로 격상하는 전례 없는 수사. 5/8 유조선 타격 → 5/9 이중 병과 보복 위협으로 에스컬레이션 사이클 가속.

### 주요 섹션 구성

1. **군사/호르무즈** (src-963, 964, 969)
   - 리드: IRGC 쌍방 보복 위협 (해군 '미국 기지 강타', 항공우주군 '미사일·드론 대기')
   - Mokhber '원자폭탄' 비유의 교리적 의미
   - Ocean Koi 나포 — 해상 tit-for-tat

2. **레바논/헤즈볼라** (src-965, 966)
   - 리드: 헤즈볼라 이스라엘 영내 최초 공격 주장 (나하리야·메론 기지)
   - 이스라엘 23일차 공습 — 19명+ 사망, 드론으로 베이루트 근교까지

3. **외교/협상** (src-968, 971)
   - 리드: MoU 응답 불발, 이란 '데드라인 무시'
   - 갈리바프 'Operation Trust Me Bro' 조롱 — 강경파 우세
   - Trump-Xi 5/14-15 정상회담 — 이란 의제가 관세·희토류 밀어냄

4. **걸프/UAE** (src-967)
   - UAE 3차 공격 (탄도미사일 2발 + 드론 3기), IRGC 부인
   - 반복 패턴의 의미

5. **경제/글로벌 파급** (src-970, 972)
   - FAO 식량가격 3년 최고 (130.7), 비료 +20%
   - 한국 유가 6주 연속 상승, 소비자물가 21개월 최고
   - 에너지 → 식량 → 소비자물가 전이 경로

### Mermaid KG 시각화
- 다이어그램 1 (호르무즈 에스컬레이션) 중심, 다이어그램 2·3은 간략 통합
- 주요 노드 20개 이내로 제한
