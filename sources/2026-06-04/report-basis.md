# 2026-06-04 보고서 기초

## 포함 항목

| ID | 제목 | 태그 | 카테고리 | 포함 근거 |
|----|------|------|----------|----------|
| src-1561 | Iran Kuwait Airport Drone Attack | new | 군사/에스컬레이션 | 전쟁 이후 최초 중립국 민간 인프라 공격; 1명 사망 63+ 부상 |
| src-1562 | House WPR 215-208 | new | 내정/의회 | 하원 최초 WPR 통과; 4 GOP 이탈 |
| src-1563 | Israel-Lebanon Pilot Zones | new | 외교/군사 | 파일럿 존 최초 도입; LAF 독점 통제; 무장해제 첫 메커니즘 |
| src-1564 | Araghchi 'no progress' / 'final formula' | new | 외교 | '소통 미차단' 톤 변화; '최종 공식' 신규 표현 |
| src-1565 | Iran Navy Destroyer Claim | new | 군사/정보전 | 이란 주장 vs CENTCOM 부인; 정보전 |
| src-1566 | Trump 'this weekend' | new | 외교 | 구체적 시한; 이란 '진전 없음'과 모순 |
| src-1567 | Oil $96.89 toward $98 | new | 경제 | 3거래일 연속 상승; $98 근접 |

## 제외 항목

| ID | 제목 | 제외 근거 |
|----|------|----------|
| src-1568 | WashPost Kuwait airport | src-1561 동일 사건 (reported) |
| src-1569 | WashTimes Kuwait airport | src-1561 동일 사건 (reported) |
| src-1570 | PBS House WPR | src-1562 동일 사건 (reported) |
| src-1571 | AJ House WPR | src-1562 동일 사건 (reported) |
| src-1572 | Arab News pilot zones | src-1563 동일 사건 (reported) |
| src-1573 | US News ceasefire | src-1563 동일 사건 (reported) |
| src-1575 | 파이낸셜뉴스 쿠웨이트 | src-1561 한국어 (reported) |
| src-1576 | 서울경제 쿠웨이트 | src-1561 한국어 (reported) |
| src-1577 | 뉴스핌 트럼프 대화 | src-1566 한국어 (reported) |

## 업데이트 항목

| ID | 제목 | 처리 |
|----|------|------|
| src-1574 | NBC News Kuwait+strikes | src-1561 본문에 추가 출처; 6/1-2→6/3 에스컬레이션 흐름 |

## KG 시각화 범위

### 포함 노드 (20개)
- ent-001 (Trump), ent-002 (Iran), ent-004 (Israel), ent-005 (IRGC)
- ent-008 (Hormuz), ent-037 (Kuwait), ent-044 (Araghchi), ent-047 (Hezbollah)
- ent-050 (Lebanon), ent-059 (CENTCOM), ent-456 (MoU)
- ent-492 (Iran Suspends), ent-496 (IRGC BM)
- ent-504 (House WPR), ent-505 (Kuwait Airport Attack)
- ent-506 (Pilot Zones Agreement), ent-507 (Pilot Zones Concept)
- ent-508 (Navy Destroyer Claim), ent-495 (Lebanon Ceasefire)

### 주제별 세부 그래프
1. 걸프 에스컬레이션: ent-496 → ent-505 → ent-037
2. 파일럿 존 프레임워크: ent-495 → ent-506 → ent-507 ← ent-047
3. 협상 메시지 전쟁: ent-001 vs ent-044
4. 의회 반발: ent-504 → ent-001

## 보고서 구성 방향

- **헤드라인:** '쿠웨이트 민간시설 타격·하원 전쟁권한법·파일럿 존 — 전쟁의 3중 전환점'
- **핵심 테마:** 군사(쿠웨이트), 정치(WPR), 외교(파일럿 존) 3축 동시 전환
- **추적 항목 업데이트:** MoU→'최종 공식'; 이-레→파일럿 존; IRGC→민간 인프라; WPR→하원 최초
