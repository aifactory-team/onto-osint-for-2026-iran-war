# 2026-06-06 온톨로지 분석

## 스키마 변경
없음. 모든 신규 엔티티 및 관계가 기존 Person/Organization/Event/Location/Concept 클래스 및 기존 관계 유형(participatesIn, affiliatedWith, locatedIn, relatedTo, causedBy, follows, opposes, cooperatesWith)으로 표현 가능.

## 신규 엔티티 (9건)
| ID | 유형 | 이름 | 중요도 |
|---|---|---|---|
| ent-516 | Location | Goruk | 중간 |
| ent-517 | Event | CENTCOM Goruk-Qeshm Radar Strikes (Jun 5) | 높음 |
| ent-518 | Person | Eitan Shmuel Lemberg | 높음 |
| ent-519 | Event | Lemberg Anti-Tank Missile Death (Jun 5) | 높음 |
| ent-520 | Person | Milovan Jovanović | 높음 |
| ent-521 | Organization | UNIFIL | 높음 |
| ent-522 | Location | Marjayoun | 중간 |
| ent-523 | Event | UNIFIL Peacekeeper Jovanović Killed (Jun 3-4) | 높음 |
| ent-524 | Event | OFAC LPG Smuggling Network Sanctions (Jun 5-6) | 높음 |

## 기존 엔티티 업데이트 (8건)
- **ent-001 (Trump):** '미국과 중국만 농축 우라늄 회수 가능' 발언 추가
- **ent-004 (Israel):** 레바논 공습 8명 사살(Jun 5), 렘버그 전사 추가
- **ent-005 (IRGC):** 호르무즈 드론 4발 발사(Jun 5) 추가
- **ent-010 (China):** 트럼프 핵 협력 시사, OFAC 상하이 첸예 에너지 제재 추가
- **ent-047 (Hezbollah):** 렘버그 대위 전사·UNIFIL 평화유지군 사망 추가
- **ent-050 (Lebanon):** 전체 사상자 3,516명 사망·10,674명 부상, 추가 8명 사망(Jun 5)
- **ent-059 (CENTCOM):** 고루크·케심섬 레이더 공습, 드론 4발 격추 추가
- **ent-456 (MoU 60-Day Framework):** 이란 '공은 트럼프 측에' 시그널 추가

## 주제별 흐름 분석

### 1. 호르무즈/미-이란 군사 충돌
6/5 CENTCOM-IRGC 교전은 6/1 케심섬 공습, 6/3 쿠웨이트/바레인 미사일 공격에 이은 연속적 군사 에스컬레이션. MoU 협상이 진행되는 와중에도 '자위권 공습' 프레임의 군사 교전이 반복. 이란 최고지도자 고문의 'ball is in Trump's court' 발언은 외교적 톤이나, 현장에서는 IRGC 드론 발사가 계속됨.

### 2. 레바논/파일럿 존 사실상 무력화
6/3 파일럿 존 합의 → 6/4 헤즈볼라 거부·이스라엘 철수 거부 → 6/5 렘버그 대위 전사·8명 사살. 합의 후 48시간 만에 IDF 장교가 헤즈볼라 대전차 미사일로 전사한 것은 합의의 완전한 무력화를 상징. UNIFIL 세르비아 평화유지군 사망(7번째)은 국제 평화유지 활동 자체가 전투 지역에서 불가능해지고 있음을 보여줌.

### 3. 제재/경제전
OFAC의 이란 LPG 밀수 네트워크 제재는 Economic Fury 캠페인의 지속. UAE·중국 프론트 기업 지정은 이란의 제재 회피 네트워크가 걸프-동아시아 축을 따라 운영됨을 공식 확인. 트럼프의 '미중 핵 협력' 시사와 동시에 중국 기업 제재라는 이중적 신호.

### 4. 핵 쟁점
트럼프의 '미국과 중국만 농축 우라늄 회수 가능' 발언은 핵 쟁점의 새로운 차원. 기존 IAEA/제3국 모니터링 프레임워크를 넘어 미중 직접 협력을 시사. 그러나 OFAC의 중국 기업 제재와의 모순이 존재. 6/4 IAEA '변동 없음' 보고와 결합하면, 핵 문제 해결은 군사적이 아닌 외교적 경로에 의존할 수밖에 없는 구조.

## 추론 결과 요약
| 추론 | 신뢰도 | 유형 |
|---|---|---|
| CENTCOM-IRGC 교전 → MoU 환경 악화 | 0.78 | event_chain |
| 헤즈볼라 거부 → 렘버그 전사 인과 | 0.80 | event_chain |
| UNIFIL 사망 ↔ IDF 사망 동시기 전투 격화 | 0.75 | co_participation |
| OFAC 제재 ↔ MoU 최대 압박 병행 | 0.72 | event_chain |
| 트럼프-중국 핵 협력 가능성 | 0.70 | co_participation |
