# 2026-04-07 온톨로지 확장 분석

## 신규 소스 중요도 평가

| 소스 ID | 제목 | 태그 | 중요도 | 근거 |
|---------|------|------|--------|------|
| src-026 | US, Iran agree to 2-week ceasefire | new | **높음** | 전쟁의 전환점이 될 수 있는 핵심 사건 |
| src-027 | Pakistan proposes 2-week ceasefire | new | **높음** | 중재 메커니즘의 구체적 내용 |
| src-028 | Israel hits railway bridge, threatens trains | new | **높음** | 새로운 군사 에스컬레이션 유형 (교통 인프라) |
| src-029 | Netanyahu confirms bridge/railway strikes | new | 중간 | src-028의 확인 보도 (이스라엘 총리 공식 확인) |
| src-030 | Iran fires ballistic missiles at Israel on Jewish holiday | new | **높음** | 이란의 이스라엘 본토 공격 지속 |
| src-031 | Iran intensifies attacks on Gulf energy sites | new | **높음** | IRGC 걸프 에너지 시설 공격의 상세 내용 |
| src-032 | Pakistan appeals to both sides | new | 중간 | src-027과 동일 사건, 추가 인용 |
| src-033 | UN Security Council veto (UN News) | new | 중간 | 기존 보도의 공식 UN 보도, 투표 상세 |
| src-034 | Soufan Center civilian plight report | new | 중간 | 분석 자료, 민간 피해 종합 |
| src-035 | 최후통첩 13시간 앞으로 (MBC) | new | 낮음 | 한국어 분석 보도 |
| src-036 | 휴전안 협상 전망 (MBC) | new | 낮음 | 한국어 분석 보도 |

## 업데이트 항목 변경사항

| 소스 ID | 주요 변경 | 근거 |
|---------|----------|------|
| src-002 (CNN) | 2주 휴전 합의 내용 추가 | 실시간 업데이트 페이지에 새 내용 추가 |
| src-006 (CBS) | 휴전 합의, 인간 방패(human chains), 이스라엘 열차 공격 포함 | 실시간 업데이트 페이지 |
| src-007 (NBC) | 2주 휴전 합의 내용 추가 | 실시간 업데이트 페이지 |

## 온톨로지 변경 요약

### 새 엔티티 (14개)
- **인물 3명:** Shehbaz Sharif (파키스탄 총리), Asim Munir (파키스탄 야전원수), Benjamin Netanyahu (이스라엘 총리)
- **조직 4개:** Pakistan, UAE, Bahrain, Kuwait
- **사건 4개:** 2-Week Ceasefire Agreement, Israel Railway Bridge Strikes, IRGC Operation Sadeq 4, Iran Ballistic Missiles on Israel (Apr 7)
- **장소 3개:** Kashan, Qom, Mashhad

### 스키마 확장
- 기존 클래스/관계 유형으로 모든 새 엔티티와 관계를 표현 가능
- 스키마 변경 불필요

## 주제별 흐름 분석

### 1. 군사 에스컬레이션 → 휴전 전환
- 오전: 이스라엘 철도/교량 8개소 공격 (테헤란, 카라지, 타브리즈, 카샨, 쿰), 미군 하르그섬 추가 공습
- 오후: 이란 이스라엘 탄도미사일 공격 (유대교 공휴일), IRGC 걸프 에너지 시설 공격 (Sadeq 4 작전 96차)
- 저녁: 트럼프 "전체 문명이 오늘 밤 죽을 수 있다" 최후통첩 → 파키스탄 중재 → **2주 휴전 합의**

### 2. 외교 채널
- 직접 채널: 이란-미국 외교 단절 (4/7 초)
- 중재 채널: **파키스탄이 핵심 중재자로 부상** (Sharif PM + Munir FM)
- 다자 채널: UN 안보리 러시아/중국 거부권으로 무력화 (11-2-2 투표)

### 3. 에너지 전쟁
- IRGC Operation Sadeq 4 96차: UAE Habshan (Exxon/Chevron), Al Ruwais (UAE), Sitrah (Bahrain), Shuaiba (Kuwait) 공격
- 이란: "2차 작전은 더 파괴적" 경고
- 호르무즈 봉쇄: 2주 휴전 기간 동안 개방이 조건

## 추론 결과 요약

1. **Sharif ↔ Trump 잠재적 관계** (0.85): 양측 모두 휴전 합의에 참여
2. **Sharif ↔ Iran 잠재적 관계** (0.85): 양측 모두 휴전 합의에 참여
3. **철도 공격 → 이란 전쟁 인과 체인** (0.72): 마감 → 철도 공격 → 전쟁의 일부
4. **Sadeq 4 → 하르그섬 인과 체인** (0.72): 하르그섬 공격에 대한 보복의 확대
