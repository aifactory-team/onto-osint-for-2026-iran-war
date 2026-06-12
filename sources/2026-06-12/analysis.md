# 2026-06-12 온톨로지 확장 분석

## 신규 소스 중요도 평가

| 소스 ID | 제목 | 태그 | 중요도 | 근거 |
|---------|------|------|--------|------|
| src-1710 | Trump cancels strikes, claims deal | new | **높음** | 전쟁 경로 전환 가능성; 11개국 합의 주장; 전날 '폭격' → 오늘 '취소' 180도 전환 |
| src-1711 | Trump Kharg Island seizure threat | new | **높음** | 새로운 에스컬레이션 유형(영토 점령 위협); 이란 석유 수출 90% 지점 |
| src-1712 | IRGC 2nd night attacks on US bases | new | **높음** | 2일 연속 미군기지 공격; 새로운 기지 표적(Ahmed Al Jaber, Sheikh Isa) |
| src-1713 | Iran Hormuz full closure declaration | new | **높음** | 부분 봉쇄→완전 봉쇄 선언 격상; 2척 유조선 공격 |
| src-1714 | Oil price crash | new | **중간** | WTI $87.71/Brent $90.38; 상호 중단 이후 최저 |
| src-1715 | Trump 'ended the war' claim | new | **높음** | 전쟁 종식 주장 — 가장 극단적 수사; 이란 미확인 |
| src-1716 | Trump whiplash VERY HARD → cancel | new | **중간** | 동일 일 180도 전환 패턴 기록; 38회 딜 임박 주장 통계 |
| src-1717 | 한국일보 — 공습 철회 보도 | new | **중간** | 한국어 대표 보도 |
| src-1718 | Iran denies deal | update | **높음** | Fars/FM 공식 부인; 트럼프 주장과 직접 모순 |
| src-1719 | 나스닥 2.5%↑ | update | **중간** | 시장 반응 데이터 |
| src-1720 | 파이낸셜뉴스 급선회 분석 | update | **낮음** | 한국어 분석 |
| src-1721 | 파이낸셜뉴스 종합 분석 | update | **낮음** | 한국어 종합 |

## 기존 보도 추적 (update 항목)

1. **MoU 협상 (src-1718, src-1721):** 6/11 '사실상 사망' → 6/12 트럼프 '종결 주장' vs 이란 '부인'. 메시지 전쟁 격화. 트럼프는 38번째 딜 임박 주장.
2. **한국 시장 (src-1719):** 유가 급락 + 증시 급등. 나스닥 2.5%↑는 전쟁 이후 가장 급격한 단일일 반응 중 하나.

## 주제별 흐름 분석 (7일 동향 + 오늘)

### 1. 미-이란 군사 교전
- 6/5-6: CENTCOM-IRGC 교전(드론→레이더→미사일) 지속
- 6/7: IRGC 7발 BM 쿠웨이트/바레인 공격
- 6/8: 이란 라맛다비드 10+발 BM, 다히에 공습
- 6/9: 상호 중단 성립
- 6/10: EU 제재, 'disappointing' 톤 변화
- 6/11: 상호 중단 48시간 붕괴, 49 토마호크, 21건 보복
- **6/12: IRGC 2일째 미군기지 공격 → 트럼프 공격 취소 + 딜 종결 주장. 전쟁 수사에서 평화 수사로 급선회.**

### 2. 호르무즈 해협
- 6/7: 유조선 공격(4척 중 1척 피격)
- 6/11: IRGC '완전 봉쇄' 주장
- **6/12: '모든 해상 교통 폐쇄' 선언 + 2척 유조선 공격. 봉쇄 범위 공식 확대.**
- 트럼프 '봉쇄 완전 유지' 재확인(딜 완료 전까지)

### 3. 외교/딜 메시지 전쟁
- 6/10: '1% 생존 가능성', 'disappointing'
- 6/11: 'bomb the S out of them', 'less confident'
- **6/12: 'ended the war', 'great settlement', 'approved by all parties' vs 이란 'no text approved', 'merely speculation'. 역대 최대 메시지 격차.**

## 온톨로지 변경 요약

### 스키마 변경: 없음
금일 발견된 모든 엔티티와 관계는 기존 Person/Organization/Event/Location/Concept 클래스 및 기존 관계 유형으로 표현 가능.

### 새 엔티티 (8건)
| ID | 유형 | 이름 | 근거 |
|----|------|------|------|
| ent-567 | Event | Trump Strike Cancellation & Deal Claim Jun 12 | 공격 취소 + 종결 주장 |
| ent-568 | Event | Kharg Island Seizure Threat | 영토 점령 위협 — 새 에스컬레이션 유형 |
| ent-569 | Event | IRGC Second Night Attacks Jun 12 | 2일 연속 미군기지 공격 |
| ent-570 | Event | Iran Full Hormuz Closure Declaration Jun 12 | 완전 봉쇄 선언 |
| ent-571 | Event | Oil Price Crash Jun 12 | WTI $87.71/Brent $90.38 |
| ent-572 | Location | Sheikh Isa Air Base | 바레인 IRGC 공격 대상 |
| ent-573 | Location | Ahmed Al Jaber Air Base | 쿠웨이트 IRGC 공격 대상 |
| ent-574 | Event | US Stock Market Rally Jun 12 | 나스닥 2.5%↑ |

### 기존 엔티티 업데이트 (5건)
- ent-001 Trump: 공격 취소, 딜 종결 주장, Kharg 위협
- ent-002 Iran: 딜 부인, 호르무즈 완전 폐쇄
- ent-005 IRGC: 2일째 미군기지 공격, 호르무즈 완전 봉쇄, 유조선 공격
- ent-007 Kharg Island: 트럼프 점령 위협 대상
- ent-008 Strait of Hormuz: 완전 폐쇄 선언

## 추론 결과 요약

1. **트럼프 딜 주장-이란 부인 = 역대 최대 메시지 격차** (신뢰도 0.90)
2. **Kharg 위협은 협상 레버리지** — 실행 의지 부재 인정 (신뢰도 0.85)
3. **IRGC 공격 지속 = 이란 내 협상파/강경파 분열 심화** (신뢰도 0.80)
4. **유가 급락 = 시장의 조건부 낙관** — 이전 38회 딜 주장 실패 히스토리 대비 제한적 신뢰 (신뢰도 0.75)
