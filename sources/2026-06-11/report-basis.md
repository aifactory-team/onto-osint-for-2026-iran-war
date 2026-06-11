# Phase 4 보고서 작성 근거 — 2026-06-11 (Day 104)

## 보고서 포함 항목

### 신규 소스 (src-1690 ~ src-1701)

| src-ID | 제목 | 핵심 내용 | 보고서 섹션 |
|--------|------|----------|-----------|
| src-1690 | US 49 Tomahawk strikes on Iran | 49발 토마호크 + 전투기 폭격, 이란 남서부 표적, 테헤란 40마일, 상황실 결정 | 핵심 뉴스 1 |
| src-1691 | Hegseth: "negotiate with bombs" | 국방장관 강압 외교 독트린 공식 표명 | 핵심 뉴스 1 부속 |
| src-1692 | Iran retaliatory strikes on 4 countries | IRGC 21건 보복, Al-Harir/Ali Al-Salem/Muwaffaq Salti/바레인 5th Fleet | 핵심 뉴스 2 |
| src-1693 | US embassy evacuation order | 바그다드 명령 철수, 바레인/쿠웨이트 허용 출국, 부양가족 자발적 퇴거 | 핵심 뉴스 3 |
| src-1694 | Mutual halt collapse analysis | 상호 중단 48시간 내 붕괴, Apache -> 에스컬레이션 사이클 | 핵심 분석 |
| src-1695 | Trump ultimatum via Qatar | "bomb the S out of them tomorrow night", 카타르 경유, 이란 중단 요청 주장 | 핵심 뉴스 4 |
| src-1696 | Houthi Red Sea maritime ban | 이스라엘 항행 완전 금지, 바브엘만데브 봉쇄 위협 | 해상 섹션 |
| src-1697 | M/T Settebello tanker attack | CENTCOM 팔라우 기국 유조선 무력화, 3명 인도 선원 실종, 인도 항의 | 해상 섹션 |
| src-1698 | IRGC Hormuz closure claim | IRGC "완전 봉쇄" 주장, CENTCOM 부인 | 해상 섹션 |
| src-1699 | Trump less confident about deal | "협상 자신감 낮아져", MoU 사실상 사망 | 외교 섹션 |
| src-1700 | Situation Room briefing details | 밴스/쿠슈너/위트코프 참석, 공습 결정 과정 | 핵심 뉴스 1 부속 |
| src-1701 | India protests missing crew | 인도 외교부 선원 실종 항의, 인도-미국 긴장 | 국제 반응 |

### 기존 엔티티 업데이트

| 엔티티 | 업데이트 내용 |
|--------|-------------|
| ent-001 (Trump) | action_jun11: 상황실 공습 승인, 카타르 경유 최후통첩, "less confident" |
| ent-002 (Iran) | action_jun11: 4개국 보복, 호르무즈 봉쇄 주장, 에스컬레이션 사이클 |
| ent-003 (US Military) | last_seen: 2026-06-11 |
| ent-004 (Israel) | last_seen: 2026-06-11 |
| ent-005 (IRGC) | action_jun11: 21건 보복, 호르무즈 봉쇄 주장 |
| ent-008 (Hormuz) | status_jun11: IRGC 봉쇄 주장 vs CENTCOM 부인 |
| ent-104 (Hegseth) | action_jun11: "negotiate with bombs" 독트린 |
| ent-456 (MoU) | status: 군사 에스컬레이션으로 사실상 사망 |
| ent-544 (Mutual Halt) | status: 48시간 내 완전 붕괴 |

---

## 보고서 제외 항목 (src-1702 ~ src-1709)

| src-ID | 제목 | 제외 사유 |
|--------|------|----------|
| src-1702 | 2026 Iran war overview | 일반 배경 (Britannica) |
| src-1703 | 2026 Iran war Wikipedia | 일반 배경 |
| src-1704 | CSIS latest analysis | 기존 보도된 전략 분석 |
| src-1705 | Trump 'total victory' claim (Jun 8) | 이전 보고서에 포함 |
| src-1706 | Day 100 CBS analysis | 이전 보고서에 포함 |
| src-1707 | Wikipedia ceasefire article | 일반 배경 |
| src-1708 | NPR Israel-Lebanon ceasefire | 6/4 보고서에 포함 |
| src-1709 | KDI 경제 영향 보고서 | 일반 배경, 금일 특정 뉴스 아님 |

---

## KG 시각화 범위

### 포함 노드 (핵심)
- ent-001 (Trump), ent-002 (Iran), ent-003 (US Military), ent-005 (IRGC)
- ent-104 (Hegseth), ent-059 (CENTCOM)
- ent-557 (US Strikes), ent-558 (Iran Retaliatory Strikes), ent-559 (Embassy Evacuation)
- ent-560 (Al-Harir), ent-561 (Ali Al-Salem), ent-562 (Muwaffaq Salti)
- ent-563 (Settebello), ent-564 (Houthi Ban), ent-565 (Trump Ultimatum)
- ent-566 (Mutual Halt Collapse), ent-544 (Mutual Halt), ent-456 (MoU)
- ent-008 (Hormuz), ent-500 (Bab el-Mandeb)

### 포함 노드 (부차)
- ent-036 (Bahrain), ent-037 (Kuwait)

### 시각화 주안점
1. **에스컬레이션 사이클**: Apache -> US Strikes -> Iran Retaliation -> Embassy Evacuation -> Trump Ultimatum
2. **이중 초크포인트**: Hormuz + Bab el-Mandeb 동시 위협
3. **외교 트랙 사망**: Mutual Halt -> Collapse -> MoU death

---

## 보고서 구조 권장

### 1. 헤드라인 요약
- 상호 중단 48시간 내 붕괴, 전쟁 최대 에스컬레이션

### 2. 핵심 뉴스
1. 미국 이란 본토 49 토마호크 폭격 (상황실 결정, 헤그세스 독트린)
2. 이란 4개국 미군기지 21건 보복 공격
3. 미 대사관 철수 명령 (바그다드/바레인/쿠웨이트)
4. 트럼프 카타르 경유 최후통첩

### 3. 해상 전선
- IRGC 호르무즈 봉쇄 주장 vs CENTCOM 부인
- 후티 Red Sea 완전 금지
- M/T Settebello 유조선 무력화

### 4. 외교 트랙
- MoU 사실상 사망
- 트럼프 "협상 자신감 낮아져"
- 헤그세스 "negotiate with bombs"

### 5. KG 시각화
- Mermaid 다이어그램: 에스컬레이션 사이클 + 이중 초크포인트

### 6. 전망
- 대사관 철수 = 더 큰 공습 사전 배치 시그널
- 이란 내부 IRGC 에스컬레이션 경로 vs 외교 경로 갈등 격화
- 이중 초크포인트 위협이 글로벌 에너지 공급망 위기 심화
