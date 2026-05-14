# 2026-05-14 온톨로지 확장 분석

## 신규 소스 중요도 평가

| 소스 ID | 제목 | 중요도 | 근거 |
|---------|------|--------|------|
| src-1053 | 트럼프 베이징 도착, 시진핑 정상회담 | 높음 | 전쟁 궤적 결정 변수, 추적 항목 D-day |
| src-1054 | 트럼프 '미국인 재정 생각 안 해' | 높음 | 정치적 파장, 전쟁 여론 변수 |
| src-1055 | CPI 4월 3.8% — 3년 최고 | 높음 | 전쟁 경제 영향 정량화 |
| src-1056 | 전쟁 비용 $29B | 높음 | 의회 압박 변수 |
| src-1057 | '슬레지해머 작전' 개명 검토 | 높음 | WPR 시계 리셋 시도 — 법적/군사적 핵심 |
| src-1058 | 밴스 '진전 있다' | 중간 | 트럼프 강경론과 대조되는 온건 신호 |
| src-1059 | IRGC 테헤란 군사훈련 | 중간 | 이란 군사 대비 태세 확인 |
| src-1060 | 중국 유조선 호르무즈 시험 | 높음 | 정상회담과 연계된 상징적 행위 |
| src-1061 | IEA 원유 재고 기록적 감소 | 높음 | 글로벌 에너지 위기 심화 정량 데이터 |
| src-1062 | 레바논 Day 28: 15명 사망 | 높음 | 지속적 사상자 추적 |
| src-1063 | IDF 리타니강 이북 진출 | 높음 | 휴전 위반 에스컬레이션 |
| src-1064 | 3차 이-레 워싱턴 회담 개시 | 높음 | 추적 항목 D-day |
| src-1065 | 호르무즈 반도체 공급망 타격 | 중간 | 전쟁의 기술 산업 파급 |
| src-1066 | [한국] 미중 정상회담 보도 | 중간 | 한국 시각 반영 |

## 기존 보도 추적

| update 소스 | 변경사항 |
|------------|---------|
| src-1067 | 유가 Brent $104→$110.87(+6.4%), WTI $98→$102(+4.1%) — 3일 연속 상승 |
| src-1068 | 레바논 사상자: Day 25(51명)→Day 27(26명)→Day 28(15명), 누적 380명+ |
| src-1069~1071 | 라이브블로그 업데이트 — Day 74-75 전개 |

## 온톨로지 변경 요약

### 스키마 변경: 없음
모든 신규 엔티티/관계가 기존 클래스(Person, Organization, Event, Location, Concept)와 관계 유형으로 표현 가능.

### 신규 인스턴스: 12개 (ent-353~ent-364)
- ent-353: Trump 'Americans' financial situation' statement (Event)
- ent-354: CPI April 3.8% (Event)
- ent-355: War cost $29B disclosure (Event)
- ent-356: Operation Sledgehammer concept (Concept)
- ent-357: Yuan Hua Hu supertanker (Organization)
- ent-358: IEA record inventory depletion warning (Event)
- ent-359: IRGC Martyred Commander drill (Event)
- ent-360: IDF Litani River crossing (Event)
- ent-361: Day 28 Lebanon strikes 15 killed (Event)
- ent-362: Hormuz semiconductor disruption (Concept)
- ent-363: Litani River (Location)
- ent-364: Jiyeh (Location)

## 주제별 흐름 분석 (7일 동향)

### 1. 미-이란 협상 → 정상회담 전환
- 5/10 이란 역제안 → 5/10 트럼프 거부 → 5/11 'life support' → 5/12 '미국인 재정 무관' → 5/13 밴스 '진전' → 5/14 베이징 정상회담
- 양자 협상에서 다자 외교(중국 개입)로 축 이동

### 2. 레바논 휴전 붕괴 가속
- Day 25(51명) → Day 27(26명) → Day 28(15명) — 하루 단위 변동 있으나 누적 380명+
- IDF 리타니강 이북 진출 — 휴전 범위 명시적 위반
- 3차 워싱턴 회담(5/14) — 군사 대표 최초 참여

### 3. 경제 충격 심화
- CPI 3.8% (3년 최고), 휘발유 +28.4%, 항공료 +20.7%
- 전쟁 비용 $29B ($25B에서 상향)
- IEA: 원유 재고 4M bbl/day 감소, 10월까지 공급 부족
- 유가 Brent $110.87 — 정상회담 전 추가 상승
- 반도체 공급망: 헬륨 35-40% 차단, TSMC/삼성 영향

### 4. 호르무즈 — 중국 변수
- 중국 유조선 Yuan Hua Hu 호르무즈 통과 시도 — 정상회담 타이밍
- 중국이 이란 원유 80%+ 구매 — 레버리지 핵심
