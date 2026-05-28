# 2026-05-28 온톨로지 확장 분석

## 신규 소스 중요도 평가

| ID | 제목 | 중요도 | 근거 |
|---|---|---|---|
| src-1426 | 유가 5%+ 급락 (WTI $88.68) | **높음** | MoU 초안 공개 직후 최대 낙폭 — 시장이 딜 임박을 가격에 반영 |
| src-1427 | 트럼프 'negotiating on fumes' 각료회의 | **높음** | Day 90 전략적 수사, 중간선거 불영향 선언, HEU 러/중 이전 거부 |
| src-1428 | 레바논 31명 사살/네타냐후 'press pedal harder' | **높음** | 4/16 휴전 이후 최대 사망자, 에스컬레이션 패턴 전환점 |
| src-1429 | 이란 인터넷 88일 만에 복구 | **높음** | 전쟁 이후 첫 국내 정상화 신호, 협상 의지 해석 가능 |
| src-1430 | 이란 국영TV MoU 초안 세부사항 | **높음** | 14개항 MoU 구체 조항 최초 공개 — 30일 호르무즈 복구 명시 |
| src-1431 | 펜타곤 군사 조정 회의 5/29 | **중간** | 이-레 안보 트랙 신규 채널 — 정치 회담과 병행 |
| src-1432 | 이란전 90일 종합 분석 | **중간** | 한국 매체 종합 분석 — 핵·제재 쟁점 정리 |
| src-1433 | 이란 인터넷 복구 (한국 보도) | **낮음** | src-1429와 동일 사건 한국어 보도 |
| src-1434 | CNN 트럼프 정치적 딜레마 분석 | **중간** | 중간선거 압박, GOP 분열 — 정치적 맥락 분석 |
| src-1435 | MOU 초안 공개 (서울경제) | **낮음** | src-1430과 동일 사건 한국어 보도 |

## 주제별 흐름 분석

### 1. MoU 협상 — 텍스트 공개 + 유가 반응
5/23 트럼프 'largely negotiated' → 5/25 Axios MoU 세부사항 → 5/27 이란 국영TV MoU 초안 전문 공개. 시장은 즉각 반응하여 유가 5%+ 급락(WTI $88.68). 루비오 '모든 기회를 줄 것' 발언도 촉매. **MoU 텍스트가 사실상 완성 단계이며 양측이 의도적으로 공개하고 있다** — 국내 여론 준비 단계로 해석.

### 2. 트럼프 Day 90 레토릭 전환
'largely negotiated'(5/23) → 'not to rush'(5/24) → 'negotiating on fumes'(5/27). 레토릭이 점점 이란을 약자로 묘사. **중간선거 불영향 선언은 역설적으로 중간선거 압박을 인지하고 있음을 시사**. HEU의 러/중 이전 거부는 핵 쟁점에서 새로운 제약.

### 3. 레바논 — 에스컬레이션 최정점
5/26 120+ 공습(12명) → 5/27 100+ 공습(31명, 4 아동). 네타냐후 'press pedal harder'. **2일 연속 100+ 공습은 4/16 휴전 이후 유례없는 수준**. 5/29 펜타곤 군사 회의 직전 압박 극대화. 6/2-3 워싱턴 회담에서 최대한 유리한 입지를 확보하려는 전략.

### 4. 이란 인터넷 복구 — 전쟁 이후 첫 정상화 신호
88일(2,093시간)은 현대 역사상 최장 국가 인터넷 차단. 페제시키안 복구 명령은 전쟁 모드에서 정상화 모드로의 전환 신호. 그러나 행정법원의 부분 중단 명령은 **국내 보수파(사법부/IRGC)와 개혁파(대통령) 간 긴장**을 보여준다.

## 온톨로지 변경 요약

### 스키마 변경
없음 — 금일 발견된 모든 엔티티와 관계는 기존 스키마(Person, Organization, Event, Location, Concept + 9개 관계유형)로 표현 가능.

### 신규 엔티티 (6건)
- ent-450: Oil Price Crash May 27 (Event)
- ent-451: MoU Draft Publication (Concept)
- ent-452: Lebanon 31 Killed May 27 (Event)
- ent-453: Iran Internet Restoration (Event)
- ent-454: Pentagon Military Coordination Meeting May 29 (Event)
- ent-455: Midterm Elections Pressure (Concept)

### 기존 엔티티 업데이트 (7건)
- ent-001 (Trump): 'negotiating on fumes', 중간선거 불영향 선언, HEU 러/중 거부
- ent-004 (Israel): 100+ 공습 31명 사살, 'press pedal harder'
- ent-031 (Netanyahu): 'press pedal harder' 명령
- ent-047 (Hezbollah): 드론/로켓 보복
- ent-050 (Lebanon): 누적 사망자 증가, 31명 추가
- ent-077 (Rubio): 'every chance to succeed'
- ent-149 (Pezeshkian): 인터넷 복구 명령

## 추론 결과 요약
- co_participation: 이란 국영TV MoU 초안 공개(ent-451)와 유가 급락(ent-450) — 인과관계 확정 (0.95)
- event_chain: 네타냐후 명령(temp-004) → 레바논 31명(ent-452) → 펜타곤 회의(ent-454) — 에스컬레이션-외교 사이클
- co_participation: 인터넷 복구(ent-453)와 MoU 초안 공개(ent-451) — 이란 내부의 동시 정상화 신호 (0.72, 잠정)
