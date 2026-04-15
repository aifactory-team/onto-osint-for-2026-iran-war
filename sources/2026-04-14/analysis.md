# 2026-04-14 온톨로지 분석

## 신규 소스 중요도 평가

### 높음 (High)
| ID | 제목 | 근거 |
|----|------|------|
| src-152 | Trump hints US-Iran talks could resume in 2 days | 전쟁 방향 전환 가능성을 시사하는 최고위급 발언 |
| src-158 | Israel, Lebanon launch historic direct talks | 1993년 이후 최초의 이스라엘-레바논 직접 외교 — 전쟁의 레바논 전선 해결 시도 |
| src-161 | IMF cuts global growth forecast | 전쟁의 글로벌 경제 영향을 공식 수치로 확인 |
| src-163 | IEA: 'largest energy security threat in history' | 에너지 공급 위기의 역사적 규모 공식 확인 |
| src-153 | Sanctioned tankers transit Hormuz despite blockade | 봉쇄 실효성 의문 제기 — 전략적 함의 대 |

### 중간 (Medium)
| ID | 제목 | 근거 |
|----|------|------|
| src-154 | China calls blockade 'dangerous and irresponsible' | 중국 수사 격상 (자제 촉구 → 위험/무책임) |
| src-155 | US-Iran could hold new talks this week | 2차 협상 구체적 일정(16일) 거론 |
| src-162 | Oil price tumbles WTI -8% | 시장의 즉각적 반응, 선물-현물 괴리 확대 |
| src-165 | India hit by blockade + Russian waiver expiry | 새로운 피해국(인도) 등장, 이중 에너지 위기 |
| src-172 | 레바논 정부-헤즈볼라 내부 충돌 | 레바논 내 종파 갈등 재연 조짐 |

### 낮음 (Low)
| ID | 제목 | 근거 |
|----|------|------|
| src-177 | CBS Live Updates | 종합 실시간 보도, 신규 정보 제한적 |
| src-175/176 | 헤즈볼라 회담 거부 (한국어) | 4/13 보도의 반복 + 소폭 업데이트 |

## 기존 보도 추적 (update 항목)

| ID | 변경사항 | 기존 보도 |
|----|----------|-----------|
| src-154 | 중국 수사 "자제 촉구" → "위험하고 무책임" 격상 | 2026-04-13 src-133 |
| src-175 | 헤즈볼라 회담 거부 재확인 + 실제 회담 중 포격 | 2026-04-13 src-131 |
| src-176 | 이스라엘 회담 당일에도 레바논 공습 지속 | 2026-04-13 src-131 |

## 주제별 흐름 분석 (7일 동향)

### 1. 호르무즈 해협 (Day 7→12→13→14)
- 4/7: 이란 봉쇄(통행료/기뢰) → 4/11: 미해군 첫 통과 → 4/12: 트럼프 역봉쇄 선언 → 4/13: 봉쇄 시행(15척) → **4/14: 제재 유조선 봉쇄 무시 통과, 실효성 의문. 이중 봉쇄 지속(4~10척/일)**

### 2. 외교 협상 트랙 (Day 7→10→11→12→13→14)
- 4/7: 2주 휴전 합의 → 4/10: 이슬라마바드 협상단 도착 → 4/11: 21시간 마라톤 → 4/12: 결렬 → 4/13: 아라그치 "MoU 직전이었다" → **4/14: 트럼프 "이틀 내 뭔가", NBC "이번 주 내 가능, 16일?", 이란 3~5년 모라토리엄 역제안 공개**

### 3. 레바논 전선 (Day 8→10→11→13→14)
- 4/8: 이스라엘 레바논 공습('블랙 웬즈데이') → 4/11: 워싱턴 회담 예고 → 4/13: 헤즈볼라 회담 거부 → **4/14: 워싱턴에서 33년 만의 직접 회담 실현, 루비오 중재, 추가 회담 합의. 그러나 헤즈볼라 회담 중 포격 강화, 내부 종파 갈등 표면화**

### 4. 경제 영향 (Day 12→13→14)
- 4/12: 유가 급등(브렌트 $102) → 4/13: $103 추가 상승 + FAO 식량위기 경고 → **4/14: 유가 급반전(WTI -8%, $91.28) 협상 재개 기대감. IMF 성장률 3.1% 하향. IEA "역대 최대 에너지 위협", 공급 10.1 mb/d 감소. 인도 러시아 면제 만료로 이중 타격**

### 5. 핵 문제 (Day 12→13→14)
- 4/12: 900파운드 농축 우라늄 쟁점 → 4/13: 20년 모라토리엄 미국 제안 공개 → **4/14: 이란의 3~5년 역제안 확인. 핵심 간극 여전히 존재하나 양측 모두 대안을 제시하고 있어 협상 여지 존재**

## 온톨로지 변경 요약
- **신규 엔티티:** 14개 (ent-077~ent-090)
  - Person: Marco Rubio, Yechiel Leiter, Nada Mouawad, António Guterres (4)
  - Organization: India, IMF, IEA (3)
  - Event: Oil Price Reversal, IMF Downgrade, IEA Report, Tankers Defy, 2nd Round Hints (5)
  - Concept: Russian Oil Waiver Expiry, Lebanon Internal Divisions (2)
- **기존 엔티티 업데이트:** ent-060 (Washington Talks: planned → held)
- **스키마 변경:** 없음 (기존 클래스/관계 유형으로 충분)

## 추론 결과 요약
- **추론 #27:** 이스라엘-레바논 대사 잠재적 관계 (co_participation, 0.85)
- **추론 #28:** 인도-중국 봉쇄 공동 피해 관계 (co_participation, 0.75)
- **추론 #29:** 유조선 봉쇄 무시 ← 협상 결렬 인과 체인 (event_chain, 0.72)
- **추론 #30:** 유가 급반전 ← 2차 협상 시사 ← 협상 결렬 인과 체인 (event_chain, 0.72)
- **추론 #31:** 루비오 → 트럼프 간접 소속 (transitivity, 0.81)
