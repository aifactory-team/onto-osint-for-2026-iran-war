# 2026-05-29 보고서 작성 근거

## 포함 항목 (10건)

| # | 소스 ID | 제목 | 태그 | 카테고리 | 포함 근거 |
|---|---------|------|------|---------|----------|
| 1 | src-1454 | US-Iran tentative MoU 60일 합의 | new | MoU/협상 | **최고 중요도** — 전쟁 이후 가장 구체적인 합의 도달 |
| 2 | src-1455 | Vance 'TBD' 트럼프 승인 대기 | new | MoU/협상 | 높음 — MoU 서명 여부의 핵심 변수 |
| 3 | src-1456 | 이란 '합의한 것 없다' 부인 (Bagheri-Kani) | new | MoU/협상 | 높음 — 이란의 공식 반박, 딜 불확실성 증대 |
| 4 | src-1457 | 백악관 '완전한 조작' 반박 | new | MoU/협상 | 높음 — 양측 메시지 전쟁, 딜 내용 공방 |
| 5 | src-1458 | IRGC 호르무즈 4척 경고사격 | new | 호르무즈/군사 | 높음 — MoU 중 IRGC 독자 행동, 이란 내부 분열 |
| 6 | src-1459 | 펜타곤 이-레 안보 트랙 개시 | new | 레바논/외교 | 높음 — 최초 군사급 직접 회담 |
| 7 | src-1460 | 리타니강 전투 (IDF-헤즈볼라) | new | 레바논/군사 | 높음 — 리타니 이북 진출 새 에스컬레이션 |
| 8 | src-1461 | 유가 혼조 Brent $93.71 | new | 시장/경제 | 중간 — MoU 기대와 불확실성 반영 |
| 9 | src-1462 | 이스라엘 '서방 vs 이란 선택하라' | new | 레바논/외교 | 중간 — 펜타곤 회담 전 이스라엘 압박 |
| 10 | src-1463 | Washington Institute 분석 | new | 레바논/분석 | 중간 — 펜타곤 트랙 전문 분석 |

## 제외 항목

| 소스 ID | 제목 | 제외 근거 |
|---------|------|----------|
| src-1464~1468 | CNN/Bloomberg/Euronews/FNN/머니투데이 후속 | update — 포함 항목의 후속/보완, 출처 목록에 기재 |
| src-1469~1478 | Fox/FP/CBS/ABC/ToI/JPost 등 중복 | reported — 동일 뉴스 중복 보도 |

## KG 시각화 범위

### 포함 노드 (15개)
ent-001(Trump), ent-002(Iran), ent-004(Israel), ent-005(IRGC), ent-008(Hormuz), ent-025(Nuclear), ent-041(Vance), ent-045(Ghalibaf), ent-047(Hezbollah), ent-050(Lebanon), ent-077(Rubio), ent-456(MoU), ent-457(Bagheri-Kani), ent-460(Pentagon Meeting), ent-463(Litani Clashes)

### 포함 엣지
- Trump/Vance/Iran → participatesIn → MoU
- MoU → relatedTo → Hormuz, Nuclear
- Bagheri-Kani → opposes → MoU
- IRGC → participatesIn → Warning Shots → locatedIn → Hormuz
- Israel/Lebanon/US Military → participatesIn → Pentagon Meeting
- Pentagon Meeting → relatedTo → Hezbollah
- Litani Clashes → locatedIn → Lebanon
- Israel → opposes → Hezbollah
- 추론: Warning Shots → relatedTo → MoU (이중 신호)
- 추론: Litani Clashes → relatedTo → Pentagon Meeting (에스컬레이트-투-네고시에이트)

## 보고서 구성 방향

1. **리드**: Day 91 — MoU 잠정 합의 도달, 트럼프 승인 대기, 양측 메시지 전쟁
2. **강조**: MoU 진전과 불확실성 병존 (합의 vs 부인 vs 조작 주장)
3. **집중**: 두 전선의 병행 — (1) 미-이란 MoU (2) 이-레 펜타곤 안보 트랙
4. **추적**: 호르무즈 IRGC 이중 신호, 레바논 에스컬레이션 패턴
