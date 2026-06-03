# 2026-06-03 보고서 기초

## 포함 항목

| ID | 제목 | 태그 | 카테고리 | 포함 근거 |
|----|------|------|----------|----------|
| src-1539 | Iran Suspends US Talks | new | 외교 | MoU 이후 최대 외교 후퇴; Araghchi '전 전선 휴전' 조건 — 핵심 뉴스 |
| src-1540 | Trump 'Rapid Pace' Claim | new | 외교 | 이란 중단과 직접 모순; 메시지 전쟁 핵심 |
| src-1541 | Trump-Netanyahu 'Crazy' Call | new | 외교/군사 | 전쟁 이후 미-이스라엘 최대 충돌; 'You're f**king crazy' — 역사적 순간 |
| src-1542 | Trump Lebanon Ceasefire | new | 외교/군사 | 다히에 프레임워크 휴전; 트럼프-네타냐후 통화 직접 후속 |
| src-1543 | IRGC Missiles at Kuwait/Bahrain | new | 군사 | 전쟁 이후 최초 걸프 기지 타격; CENTCOM 요격 — 에스컬레이션 |
| src-1544 | CENTCOM Qeshm Island Strike | new | 군사 | 미국 보복; 드론 관제소 타격 — 이란 ISR 인프라 |
| src-1545 | Tzarfati KIA | new | 군사 | IDF 보포르 전사자; 헤즈볼라 FPV 드론 전술 |
| src-1546 | Rubio Senate Nuclear Testimony | new | 외교 | '심각하고 장기적' 핵 제한; 30-60-90일; 호르무즈만으로 불가 |
| src-1547 | Bab el-Mandeb Closure Threat | new | 전략 | 해양 압박 확대; 30% 컨테이너, 25% 에너지 — 새 위협 차원 |
| src-1548 | Round 4 Washington Talks | new | 외교 | Needham/Holler 수석; State Dept 정치 트랙; 4차 회담 |
| src-1549 | Ghalibaf-Berri Retaliation Threat | new | 외교/군사 | 5월 말 이후 최대 에스컬레이션 시그널; 이란-헤즈볼라 조율 |
| src-1550 | Oil Price Spike Jun 2-3 | new | 경제 | Brent +5%→$95→$91; 이란 중단→급등, 휴전→반락 |

## 제외 항목

| ID | 제목 | 제외 근거 |
|----|------|----------|
| src-1551 | Reuters Iran suspension detail | src-1539와 동일 사건, 추가 사실 미미 (reported) |
| src-1552 | CNN Trump-Netanyahu | src-1541 동일 통화 (reported) |
| src-1553 | BBC Lebanon ceasefire | src-1542 동일 사건 (reported) |
| src-1554 | AJ Day 95-96 roundup | 종합 요약, 개별 항목으로 이미 포함 (reported) |
| src-1555 | Fox News Trump rapid pace | src-1540 동일 발언 (reported) |
| src-1556 | Times of Israel Tzarfati | src-1545 동일 인물 (reported) |
| src-1557 | IRNA Ghalibaf detail | src-1549 동일 사건 (reported) |
| src-1558 | Bloomberg oil analysis | src-1550 동일 추세, 분석 기사 (reported) |
| src-1559 | Ynet Round 4 | src-1548 동일 사건 (reported) |
| src-1560 | AP Rubio testimony | src-1546 동일 증언 (reported) |

## KG 시각화 범위

### 포함 노드 (20개)
- ent-001 (Trump), ent-002 (Iran), ent-004 (Israel), ent-005 (IRGC)
- ent-008 (Hormuz), ent-031 (Netanyahu), ent-044 (Araghchi), ent-045 (Ghalibaf)
- ent-047 (Hezbollah), ent-050 (Lebanon), ent-059 (CENTCOM), ent-077 (Rubio)
- ent-456 (MoU), ent-492 (Iran Suspends), ent-493 (Trump Rapid Pace)
- ent-494 (Trump-Netanyahu Call), ent-495 (Lebanon Ceasefire), ent-496 (IRGC Missiles)
- ent-500 (Bab el-Mandeb), ent-503 (Oil Spike)

### 주제별 세부 그래프
1. 인과 체인: ent-004 → ent-492 → ent-494 → ent-495 (이스라엘 확대→이란 중단→트럼프 압박→휴전)
2. 3축 에스컬레이션: ent-492 + ent-496 + ent-502 (외교 중단 + 군사 타격 + 정치 위협)
3. 이중 해협 위협: ent-008 + ent-500 (호르무즈 + Bab el-Mandeb)
4. 미-이란 메시지 전쟁: ent-492 ↔ ent-493 (중단 vs 'rapid pace')

## 보고서 구성 방향

- **헤드라인:** '3축 동기화 에스컬레이션과 트럼프 딜레마' — 이란이 외교+군사+정치 3축을 동기화하여 에스컬레이션 전환; 트럼프가 이스라엘 억제('crazy' 통화)로 대응하며 이란 딜/이스라엘 지지 딜레마 노출
- **이중 트랙:** 미-이란 협상 중단(상위) + 이스라엘-레바논 휴전(하위, 이란 딜 연계)
- **키 인사이트:** (1) 이스라엘→이란중단→트럼프-네타냐후→휴전 인과 체인이 48시간 실현; (2) IRGC 걸프 BM은 양자→다자 확대; (3) Bab el-Mandeb은 에스컬레이션 사다리의 다음 단계; (4) 유가가 외교 바로미터
- **추적 항목 업데이트:** MoU 교착→이란 중단; 이-레→트럼프 강제 휴전; IRGC→걸프 확대; 신규: Bab el-Mandeb 위협
