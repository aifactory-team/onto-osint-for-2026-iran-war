# 온톨로지 추론 로그

이 파일은 온톨로지 추론 엔진이 생성한 추론 결과를 기록한다.
각 엔트리는 추론 규칙, 입력 트리플, 추론된 트리플, 신뢰도를 포함한다.

---

## 2026-04-07 추론 결과 (1차)

### 추론 #1: transitivity (소속 전이)
- **입력:** (ent-006/Majid Khademi, affiliatedWith, ent-005/IRGC), (ent-005/IRGC, affiliatedWith, ent-002/Iran)
- **추론:** (ent-006/Majid Khademi, indirectlyAffiliatedWith, ent-002/Iran)
- **신뢰도:** 0.855 (= 0.90 × 0.95)
- **상태:** 확정

### 추론 #2: co_participation (공동 참여)
- **입력:** (ent-001/Donald Trump, participatesIn, ent-016/Ceasefire Negotiations), (ent-002/Iran, participatesIn via ent-019/10-Point Peace Plan → follows → ent-016)
- **추론:** (ent-001/Donald Trump, potentialRelation, ent-002/Iran)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 양측이 휴전 협상에 참여하고 있으나, 적대적 관계로 '대립' 관계가 이미 존재. 이 추론은 협상이라는 프레임에서의 잠재적 관계를 나타냄.

### 추론 #3: co_participation (암시적 협력)
- **입력:** Russia/China가 UN 안보리에서 호르무즈 결의안에 공동 거부권 행사 → 이란 입장 지지
- **추론:** (ent-009/Russia, potentialRelation, ent-002/Iran)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 직접적인 군사 협력은 아니나, 외교적 측면에서 이란의 호르무즈 봉쇄 유지를 간접 지원하는 형태.

### 스키마 변경 없음
- 금일 발견된 모든 엔티티와 관계는 기존 seed 스키마(Person, Organization, Event, Location, Concept 및 9개 관계 유형)로 충분히 표현 가능
- 새 클래스/관계 유형 추가 불필요

---

## 2026-04-07 추론 결과 (2차 — 업데이트)

### 추론 #4: co_participation (파키스탄-미국 중재 관계)
- **입력:** (ent-027/Shehbaz Sharif, participatesIn, ent-030/2-Week Ceasefire), (ent-001/Donald Trump, participatesIn, ent-030/2-Week Ceasefire)
- **추론:** (ent-027/Shehbaz Sharif, potentialRelation, ent-001/Donald Trump)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 파키스탄 총리가 미국-이란 휴전의 핵심 중재자로 활동. 양측과 직접 소통하여 2주 휴전을 성사시킴.

### 추론 #5: co_participation (파키스탄-이란 중재 관계)
- **입력:** (ent-027/Shehbaz Sharif, participatesIn, ent-030/2-Week Ceasefire), (ent-002/Iran, participatesIn, ent-030/2-Week Ceasefire)
- **추론:** (ent-027/Shehbaz Sharif, potentialRelation, ent-002/Iran)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 파키스탄이 이란과의 지리적 인접성과 역사적 관계를 기반으로 중재자 역할 수행.

### 추론 #6: event_chain (철도 공격 → 전쟁 인과 체인)
- **입력:** (ent-032/Railway Bridge Strikes, causedBy, ent-020/Trump Deadline), (ent-020/Trump Deadline, relatedTo, ent-015/2026 Iran War via ent-008/Strait of Hormuz)
- **추론:** (ent-032/Railway Bridge Strikes, causalChain, ent-015/2026 Iran War)
- **신뢰도:** 0.72 (3단계 체인으로 0.85 × 0.85 = 0.72)
- **상태:** 확정
- **비고:** 이스라엘의 철도/교량 공격은 트럼프 마감시한을 앞두고 이란에 대한 최대 압박의 일환.

### 추론 #7: event_chain (걸프 에너지 공격 → 하르그섬 보복 체인)
- **입력:** (ent-033/Operation Sadeq 4, follows, ent-023/Iran Retaliatory Strikes), (ent-023, follows, ent-017/Kharg Island Strikes)
- **추론:** (ent-033/Operation Sadeq 4, causalChain, ent-017/Kharg Island Strikes)
- **신뢰도:** 0.72 (3단계 체인으로 0.85 × 0.85 = 0.72)
- **상태:** 확정
- **비고:** IRGC의 걸프 에너지 시설 대규모 공격(Sadeq 4)은 미군의 하르그섬 공습에 대한 보복의 확대 버전.

### 스키마 변경 없음
- 14개 새 엔티티 모두 기존 클래스(Person, Organization, Event, Location)로 분류 가능
- 19개 새 관계 모두 기존 관계 유형(participatesIn, affiliatedWith, cooperatesWith, follows, causedBy, locatedIn, opposes)으로 표현 가능

---

## 2026-04-10 추론 결과

### 추론 #8: co_participation (밴스-아라그치 잠재적 관계)
- **입력:** (ent-041/JD Vance, participatesIn, ent-054/Islamabad Peace Talks), (ent-044/Abbas Araghchi, participatesIn, ent-054/Islamabad Peace Talks)
- **추론:** (ent-041/JD Vance, potentialRelation, ent-044/Abbas Araghchi)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 미국 부통령과 이란 외무장관이 이슬라마바드 평화회담에 공동 참여. 전쟁 시작 이래 최초의 직접 대면 협상.

### 추론 #9: co_participation (밴스-갈리바프 잠재적 관계)
- **입력:** (ent-041/JD Vance, participatesIn, ent-054/Islamabad Peace Talks), (ent-045/Ghalibaf, participatesIn, ent-054/Islamabad Peace Talks)
- **추론:** (ent-041/JD Vance, potentialRelation, ent-045/Mohammad Bagher Ghalibaf)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 이란 의회의장이 협상단에 포함되어 미국 부통령과 직접 대면 가능성.

### 추론 #10: transitivity (밴스 → 미군 간접 소속)
- **입력:** (ent-041/JD Vance, affiliatedWith, ent-001/Trump), (ent-001/Trump → ent-003/US Military via command)
- **추론:** (ent-041/JD Vance, indirectlyAffiliatedWith, ent-003/US Military)
- **신뢰도:** 0.81
- **상태:** 확정
- **비고:** 밴스는 해병대 참전 경력(이라크전)도 있어 군과의 간접 연결 강화.

### 추론 #11: event_chain (레바논 공격 → 호르무즈 통행료 분쟁)
- **입력:** (ent-053/Israel Lebanon Attacks, causedBy, ent-030/2-Week Ceasefire), 이란이 레바논 공격에 반발하여 호르무즈 재봉쇄 → (ent-055/Hormuz Toll Dispute)
- **추론:** (ent-053/Israel Lebanon Attacks, causalChain, ent-055/Hormuz Toll Dispute)
- **신뢰도:** 0.72 (3단계 체인: 휴전 → 레바논 공격 → 이란 반발 → 호르무즈 재봉쇄/통행료)
- **상태:** 확정
- **비고:** 이스라엘의 레바논 공격이 이란의 호르무즈 재봉쇄 결정에 직접적 영향을 미침. 휴전 조건인 호르무즈 개방이 레바논 사태로 무산.

### 추론 #12: transitivity (헤즈볼라 → 이란 간접 소속)
- **입력:** (ent-047/Hezbollah, affiliatedWith, ent-002/Iran)
- **추론:** (ent-047/Hezbollah, indirectlyAffiliatedWith, ent-002/Iran)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 헤즈볼라는 이란의 직접적 무장 대리 세력으로 "저항 축(Resistance Axis)"의 핵심 구성원. 이란은 레바논 공격을 자국에 대한 공격과 동일시.

### 스키마 변경 없음
- 17개 새 엔티티 모두 기존 클래스(Person, Organization, Event, Location, Concept)로 분류 가능
- 23개 새 관계 모두 기존 관계 유형으로 표현 가능
- "Hormuz Toll/Management"는 기존 Concept 클래스로 충분히 표현
