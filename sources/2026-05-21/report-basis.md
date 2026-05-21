# 2026-05-21 보고서 작성 근거

## 포함 항목

| 순서 | 소스 ID | 제목 | 태그 | 포함 근거 |
|------|---------|------|------|----------|
| 1 | src-1234 | 시진핑-푸틴 베이징 정상회담 (~40건 거래, Power of Siberia 2) | new | **최고 중요도** — 이란 전쟁의 에너지 파급이 중러 동맹을 구조적으로 가속; 지정학적 재편의 핵심 사건 |
| 2 | src-1235 | 사우디 이라크 발원 드론 3대 요격 확인 | new | UAE에 이어 걸프 2국 공동 귀속 확립; 프록시 드론전 구조 공식화 |
| 3 | src-1241 | 알사디 KH 멤버 테러 기소 (20건 공격) | new | 5/20 KH 지도자 체포의 연장선; 법집행 대프록시 전략 확대 |
| 4 | src-1237 | 하원 WPR 고트하이머 결의안 (4차 투표 예정) | new | 상원 통과 → 하원 이동; 전쟁권한 전투의 새 전선 |
| 5 | src-1236 | 이란 군사력 재건 (CSIS: 70% 미사일, 30/33 기지) | new | 휴전 중 군사력 복원의 구체적 수치; 전쟁 재개 시 이란 역량 평가 핵심 |
| 6 | src-1233 | 이란군 '새 전선' 경고 | new | 휴전 중 전투력 강화 인정; 재개 시 에스컬레이션 위협 |
| 7 | src-1239 | 밴스 '많은 진전'/트럼프 '매우 빨리' | new | 외교 낙관 신호; 최후통첩과의 이중 트랙 |
| 8 | src-1238 | 호르무즈 1,600척 유도 작전 | new | 연속 2일 통과 0척; 해상 위기의 현재 상태 |
| 9 | src-1244 | 상원 WPR 8차 투표 (공화당 4명 이탈) | update | 7차 이후 이탈 확대 추적 |
| 10 | src-1246 | 사우디 이라크 드론 후속 (LWJ) | update | 걸프 공동 귀속의 분석적 심화 |
| 11 | src-1240 | 유가 Brent $105 (ADNOC 2027 전망) | new | 에너지 시장 장기 구조화; 맥락 정보 |

## 제외 항목

| 소스 ID | 제목 | 제외 근거 |
|---------|------|----------|
| src-1242 | [한국] 트럼프 최후통첩 종합 | 한국 매체 종합 보도 — 기존 src-1205(5/20)와 중복 |
| src-1243 | 이란 전쟁 재개 준비(유로뉴스) | src-1236(CSIS)이 더 상세한 분석 제공; 중복 회피 |
| src-1245 | 하원 WPR 후속 | src-1237과 중복 |
| src-1247 | 유가 업데이트 | src-1240에 흡수 |
| src-1248 | 이란 군사력 JPost | src-1236(CSIS) 원본이 더 포괄적 |
| src-1249~1259 | reported 태그 항목 | 기존 보도의 반복; 대표 소스에서 커버 완료 |

## KG 시각화 범위

오늘의 핵심 KG 스토리: **중러 에너지 동맹 가속 + 걸프 프록시 귀속 공식화 + 전쟁권한 하원 이동 + KH 법집행 전략**

포함 노드 (22개):
- 인물: Trump(ent-001), Xi Jinping(ent-414), Putin(ent-199), Vance(ent-041), Gottheimer(ent-416), al Saadi(ent-417)
- 조직: Iran(ent-002), US Military(ent-003), IRGC(ent-005), Russia(ent-009), China(ent-010), Saudi Arabia(ent-415), UAE(ent-035), Kata'ib Hezbollah(ent-409), Pakistan(ent-029)
- 사건: WPR Vote(ent-408)
- 장소: Hormuz(ent-008)
- 개념: Power of Siberia 2(ent-418)

핵심 엣지 (15개):
- Xi cooperatesWith Putin (src-1234)
- Russia cooperatesWith China (src-1234)
- Saudi opposes KH (src-1235)
- China cooperatesWith Iran (src-1236)
- Gottheimer participatesIn WPR Vote (src-1237)
- al Saadi affiliatedWith KH (src-1241)
- IRGC controls Hormuz (src-1236)
- Power of Siberia 2 relatedTo Russia/China (src-1234)
- Vance participatesIn Iran diplomacy (src-1239)
- Trump opposes Iran (src-1239)
- al Saadi indirectlyAffiliatedWith Iran (추론)
- Xi potentialRelation Iran (추론)
- Saudi cooperatesWith UAE (추론)

## 보고서 구성 방향
- **핵심 프레임:** Day 83 — 이란 전쟁이 만든 세계: 중러 에너지 동맹, 걸프 프록시 전쟁, 미국 내 전쟁 논쟁
- **1면:** 시진핑-푸틴 정상회담 — 이란 전쟁이 중러 에너지 동맹을 구조적으로 가속 (파워오브시베리아2 합의, 중국 석유 수입 절반 위협)
- **2면:** 걸프 프록시 전쟁 공식화 — 사우디+UAE 이라크 발원 공동 확인 + 알사디 KH 테러 기소 (법집행 전략 확대)
- **3면:** 전쟁권한 하원 이동 — 상원 통과 후 고트하이머 결의안 4차 투표 + 이란 군사력 재건 (CSIS 70% 미사일 보존)
- **4면:** 외교 이중 트랙 — 밴스 낙관 vs. 최후통첩 + 호르무즈 1,600척 유도 + 유가 $105
- **추적:** 핵 12-15년 모라토리엄 진전, 이란 수정안 후속, 하원 WPR 4차 투표 결과, 호르무즈 유도 작전 성과
- **KG 다이어그램:** 중러-이란-걸프 삼각 구도 + WPR-프록시 법집행 이중 추적
