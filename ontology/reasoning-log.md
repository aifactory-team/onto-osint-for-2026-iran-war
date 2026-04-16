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

---

## 2026-04-11 추론 결과

### 추론 #13: event_chain (미해군 호르무즈 통과 ← 2주 휴전)
- **입력:** (ent-030/2-Week Ceasefire, 호르무즈 개방 조건 포함), (ent-058/US Navy Hormuz Transit, 호르무즈에서 기뢰 제거 작전)
- **추론:** (ent-058/US Navy Hormuz Transit, causedBy, ent-030/2-Week Ceasefire)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 미해군의 호르무즈 통과는 휴전 조건인 호르무즈 개방을 군사적으로 실행하는 것. 기뢰 제거 및 상선 항로 개척이 목적.

### 추론 #14: co_participation (미해군 통과 ↔ 이슬라마바드 협상 동시성)
- **입력:** (ent-058/US Navy Hormuz Transit, date=2026-04-11), (ent-054/Islamabad Talks, date=2026-04-11)
- **추론:** (ent-058/US Navy Hormuz Transit, relatedTo, ent-054/Islamabad Talks)
- **신뢰도:** 0.75
- **상태:** 확정 (잠정에 가까움)
- **비고:** 외교 협상과 군사 작전이 동시에 진행. 밴스가 이슬라마바드에서 협상하는 동안 미해군이 호르무즈에서 작전 수행 — 전형적인 "협상-압박" 이중 트랙. 의도적 동시성인지 우연인지는 불확실.

### 추론 #15: transitivity (CENTCOM → Trump 간접 소속)
- **입력:** (ent-059/CENTCOM, affiliatedWith, ent-003/US Military), (ent-003/US Military → ent-001/Trump via command)
- **추론:** (ent-059/CENTCOM, indirectlyAffiliatedWith, ent-001/Trump)
- **신뢰도:** 0.81
- **상태:** 확정
- **비고:** CENTCOM은 미군 통합전투사령부로 대통령 직할. 호르무즈 작전은 대통령 명령에 의한 것.

### 추론 #16: event_chain (워싱턴 회담 → 레바논 공습 후속)
- **입력:** (ent-053/Israel Lebanon Attacks, date=2026-04-08), (ent-060/Washington Talks, date=2026-04-15 planned)
- **추론:** (ent-060/Israel-Lebanon Washington Talks, follows, ent-053/Israel Lebanon Attacks)
- **신뢰도:** 0.78
- **상태:** 확정
- **비고:** 이스라엘이 4/8 레바논 공습 후 레바논과 워싱턴에서 직접 회담에 합의. 공습의 외교적 후속 조치이나, 이스라엘은 헤즈볼라 휴전은 거부하면서 회담만 수용하는 이중 전략.

### 스키마 변경 없음
- 5개 새 엔티티 모두 기존 클래스(Event, Organization, Concept)로 분류 가능
- 12개 새 관계 모두 기존 관계 유형으로 표현 가능

---

## 2026-04-12 추론 결과

### 추론 #17: event_chain (봉쇄 선언 ← 협상 결렬 ← 휴전 합의)
- **입력:** (ent-054/Islamabad Talks, follows, ent-030/2-Week Ceasefire), (ent-063/Blockade Declaration, causedBy, ent-054/Islamabad Talks)
- **추론:** (ent-063/Trump Hormuz Blockade, causalChain, ent-030/2-Week Ceasefire)
- **신뢰도:** 0.76 (3단계 체인: 휴전 합의 → 이슬라마바드 협상 → 협상 결렬 → 봉쇄 선언)
- **상태:** 확정
- **비고:** 2주 휴전이 이슬라마바드 협상의 전제였고, 협상 결렬 후 트럼프가 즉각 봉쇄를 선언함으로써 휴전의 실질적 사망 선고를 내렸다. 4월 22일 휴전 만료 전에 전쟁이 재개될 가능성 대두.

### 추론 #18: event_chain (봉쇄 → 협상 결렬 직접 후속)
- **입력:** (ent-054/Islamabad Talks, 결과: 결렬), (ent-063/Blockade Declaration, 시점: 결렬 직후)
- **추론:** (ent-063/Trump Hormuz Blockade, follows, ent-054/Islamabad Talks)
- **신뢰도:** 0.95
- **상태:** 확정
- **비고:** 봉쇄 선언은 협상 결렬 발표 수시간 후 트루스소셜에서 이루어졌다. 명백한 인과적 후속 조치.

### 추론 #19: transitivity (이샤크 다르 → 셰바즈 샤리프 간접 소속)
- **입력:** (ent-065/Ishaq Dar, affiliatedWith, ent-029/Pakistan), (ent-027/Shehbaz Sharif, affiliatedWith, ent-029/Pakistan)
- **추론:** (ent-065/Ishaq Dar, indirectlyAffiliatedWith, ent-027/Shehbaz Sharif)
- **신뢰도:** 0.81
- **상태:** 확정
- **비고:** 다르 부총리/외무장관은 샤리프 총리 정부의 핵심 인사. 협상 결렬 후 외교적 후속 조치를 주도.

### 추론 #20: co_participation (핵 문제 ↔ 이란 4대 레드라인)
- **입력:** (ent-064/Enriched Uranium, relatedTo, ent-054/Islamabad Talks), (ent-061/Iran 4 Red Lines, relatedTo, ent-054/Islamabad Talks)
- **추론:** (ent-064/Enriched Uranium, relatedTo, ent-061/Iran 4 Red Lines)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 흥미로운 비대칭: 이란의 4대 레드라인에는 핵이 포함되지 않았으나, 미국의 핵심 요구는 핵이었다. 양측이 다른 쟁점을 최우선으로 설정한 것이 결렬의 근본 원인.

### 추론 #21: co_participation (50% 관세 → 중국)
- **입력:** (ent-068/50% Tariff Threat, 대상: 이란 지원국), (ent-010/China, 이란 지원 의심국)
- **추론:** (ent-068/50% Tariff Threat, relatedTo, ent-010/China)
- **신뢰도:** 0.75
- **상태:** 확정 (잠정에 가까움)
- **비고:** 트럼프가 "이란을 돕는 국가"에 50% 관세를 부과하겠다고 밝혔으며, 이는 사실상 중국을 겨냥한 것. 중국은 이란산 원유의 최대 수입국이자, UN 안보리에서 이란 관련 결의안에 거부권을 행사한 국가.

### 스키마 변경 없음
- 6개 새 엔티티 모두 기존 클래스(Event, Concept, Person)로 분류 가능
- 15개 새 관계 모두 기존 관계 유형(causedBy, follows, relatedTo, affiliatedWith, opposes, participatesIn)으로 표현 가능

---

## 2026-04-13 추론 결과

### 추론 #22: event_chain (봉쇄 시행 ← 선언 ← 협상 결렬 ← 휴전)
- **입력:** (ent-030/2-Week Ceasefire → ent-054/Islamabad Talks → ent-063/Blockade Declaration → ent-069/Blockade Implementation)
- **추론:** (ent-069/US Hormuz Blockade Implementation, causalChain, ent-030/2-Week Ceasefire)
- **신뢰도:** 0.72 (4단계 체인: 휴전 합의 → 이슬라마바드 협상 → 결렬 → 봉쇄 선언 → 봉쇄 시행, 0.5배 감쇠 적용)
- **상태:** 확정
- **비고:** 봉쇄 시행은 협상 결렬의 군사적 귀결. 휴전이 이행되지 않으면 봉쇄가 전면전 재개의 전주곡이 될 수 있다. 4/22 휴전 만료까지 8일.

### 추론 #23: event_chain (헤즈볼라 회담 거부 ← 레바논 공습)
- **입력:** (ent-053/Israel Lebanon Attacks, date=2026-04-08), (ent-060/Washington Talks, planned Apr 15), (ent-074/Hezbollah Rejects, date=2026-04-13)
- **추론:** (ent-074/Hezbollah Rejects Talks, relatedTo, ent-053/Israel Lebanon Attacks)
- **신뢰도:** 0.78
- **상태:** 확정
- **비고:** 헤즈볼라의 회담 거부는 4/8 이스라엘의 레바논 공습('블랙 웬즈데이', 357명 사망)에 대한 직접적 반응. "적과 협상하지 않는다"는 입장은 공습 이후 더욱 강화됨.

### 추론 #24: transitivity (사파 → 헤즈볼라 → 이란 간접 소속)
- **입력:** (ent-072/Wafiq Safa, affiliatedWith, ent-047/Hezbollah), (ent-047/Hezbollah, affiliatedWith, ent-002/Iran)
- **추론:** (ent-072/Wafiq Safa, indirectlyAffiliatedWith, ent-002/Iran)
- **신뢰도:** 0.81 (0.95 × 0.85)
- **상태:** 확정
- **비고:** 사파는 헤즈볼라 정치평의회의 핵심 인사. 이란의 '저항 축' 네트워크를 통해 간접적으로 이란과 연결.

### 추론 #25: transitivity (카셈 → 헤즈볼라 → 이란 간접 소속)
- **입력:** (ent-073/Naim Qassem, affiliatedWith, ent-047/Hezbollah), (ent-047/Hezbollah, affiliatedWith, ent-002/Iran)
- **추론:** (ent-073/Naim Qassem, indirectlyAffiliatedWith, ent-002/Iran)
- **신뢰도:** 0.81 (0.95 × 0.85)
- **상태:** 확정
- **비고:** 카셈은 헤즈볼라 사무총장으로 조직의 최고 지도자. 워싱턴 회담 거부 결정은 이란과의 조율 하에 이루어졌을 가능성 높음.

### 추론 #26: co_participation (FAO 식량 위기 ↔ 이중 봉쇄)
- **입력:** (ent-076/FAO Warning, causedBy, ent-069/Blockade Implementation), (ent-075/Dual Blockade, relatedTo, ent-008/Strait of Hormuz)
- **추론:** (ent-076/FAO Warning, relatedTo, ent-075/Dual Blockade)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 이란 봉쇄(통행료/기뢰) + 미국 역봉쇄(이란 항구 차단) = 호르무즈 이중 봉쇄. FAO 식량 위기 경고는 이 이중 봉쇄로 인한 농산물 수송 차질의 직접적 결과. 세계 석유 공급의 1/5이 이 해협을 통과하며, 식량/비료 물류도 영향.

### 스키마 변경 없음
- 8개 새 엔티티 모두 기존 클래스(Event, Concept, Person)로 분류 가능
- 21개 새 관계 모두 기존 관계 유형(participatesIn, opposes, causedBy, follows, relatedTo, affiliatedWith, locatedIn, mentions, causalChain, indirectlyAffiliatedWith)으로 표현 가능

---

## 2026-04-14 추론 결과

### 추론 #27: co_participation (이스라엘-레바논 대사 잠재적 관계)
- **입력:** (ent-078/Yechiel Leiter, participatesIn, ent-060/Washington Talks), (ent-079/Nada Mouawad, participatesIn, ent-060/Washington Talks)
- **추론:** (ent-078/Yechiel Leiter, potentialRelation, ent-079/Nada Mouawad)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 1993년 이후 최초의 이스라엘-레바논 직접 대면 외교 회담. 양국 대사가 루비오 국무장관 중재 하에 2시간 동안 면담하고 후속 회담에 합의.

### 추론 #28: co_participation (인도-중국 잠재적 관계 — 봉쇄 공동 피해)
- **입력:** (ent-080/India, relatedTo, ent-063/Blockade), (ent-010/China, opposes, ent-063/Blockade)
- **추론:** (ent-080/India, potentialRelation, ent-010/China)
- **신뢰도:** 0.75
- **상태:** 확정 (잠정에 가까움)
- **비고:** 인도와 중국 모두 호르무즈 봉쇄의 주요 피해국. 인도는 호르무즈에서 ~3 mb/d를 상실하고 러시아 원유 면제까지 만료(4/11)되어 이중 타격. 중국은 이란산 원유의 80%(1.4 mb/d)를 수입하는 최대 고객. 양국이 봉쇄 해제를 위해 공조할 가능성이 있으나, 미국의 50% 관세 위협이 제약 요인.

### 추론 #29: event_chain (제재 유조선 통과 ← 봉쇄 ← 협상 결렬)
- **입력:** (ent-087/Sanctioned Tankers Defy, relatedTo, ent-063/Blockade), (ent-063/Blockade, follows, ent-054/Islamabad Talks)
- **추론:** (ent-087/Sanctioned Tankers Defy, causalChain, ent-054/Islamabad Talks)
- **신뢰도:** 0.72 (3단계 체인: 협상 결렬 → 봉쇄 선언 → 유조선 봉쇄 무시)
- **상태:** 확정
- **비고:** 미국의 봉쇄 실효성에 의문을 제기하는 신호. 중국 국적 제재 유조선 Rich Starry가 봉쇄 첫 날 통과하고, Kpler 데이터상 최소 9척이 통과. CENTCOM은 "이란 항구로 향하는 선박은 차단선을 넘지 않았다"고 주장하나, 통과 자체가 봉쇄의 공백을 시사.

### 추론 #30: event_chain (유가 급반전 ← 2차 협상 시사 ← 협상 결렬)
- **입력:** (ent-084/Oil Price Reversal, causedBy, ent-088/Trump 2nd Round Hints), (ent-088/Trump 2nd Round Hints, follows, ent-054/Islamabad Talks)
- **추론:** (ent-084/Oil Price Reversal, causalChain, ent-054/Islamabad Talks)
- **신뢰도:** 0.72 (3단계 체인: 협상 결렬 → 2차 협상 시사 → 유가 하락)
- **상태:** 확정
- **비고:** 시장은 협상 결렬(4/12)에 유가 급등으로 반응하고, 2차 협상 시사(4/14)에 급락으로 반응. WTI가 하루 만에 -8%를 기록. 그러나 IEA에 따르면 물리적 현물 가격은 $150/bbl 근처로 선물시장과의 괴리가 확대 — 구조적 공급 부족은 해소되지 않음.

### 추론 #31: transitivity (루비오 → 트럼프 간접 소속)
- **입력:** (ent-077/Marco Rubio, Secretary of State), (US Government → ent-001/Trump, President)
- **추론:** (ent-077/Marco Rubio, indirectlyAffiliatedWith, ent-001/Donald Trump)
- **신뢰도:** 0.81
- **상태:** 확정
- **비고:** 루비오는 트럼프 행정부 국무장관으로 이스라엘-레바논 워싱턴 회담을 직접 중재. 트럼프의 중동 전략(이란 봉쇄 + 레바논 개별 협상)을 실행하는 핵심 인물.

### 스키마 변경 없음
- 14개 새 엔티티 모두 기존 클래스(Person, Organization, Event, Location, Concept)로 분류 가능
- 21개 새 관계 모두 기존 관계 유형(participatesIn, affiliatedWith, opposes, follows, causedBy, relatedTo, causalChain, potentialRelation, indirectlyAffiliatedWith)으로 표현 가능

---

## 2026-04-15 추론 결과

### 추론 #32: transitivity (소속 전이)
- **입력:** (ent-093/Brad Cooper, participatesIn, ent-095/CENTCOM Blockade), (ent-059/CENTCOM, affiliatedWith, ent-003/US Military), (ent-003, cooperatesWith, ent-001/Trump)
- **추론:** (ent-093/Brad Cooper, indirectlyAffiliatedWith, ent-001/Donald Trump)
- **신뢰도:** 0.81
- **상태:** 확정
- **비고:** CENTCOM 사령관 쿠퍼 제독이 봉쇄 '완전 시행'을 선언. 트럼프의 봉쇄 명령을 직접 이행하는 실행자.

### 추론 #33: transitivity (소속 전이)
- **입력:** (ent-091/Ali Abdollahi, affiliatedWith, ent-002/Iran), (ent-005/IRGC, affiliatedWith, ent-002/Iran)
- **추론:** (ent-091/Ali Abdollahi, indirectlyAffiliatedWith, ent-005/IRGC)
- **신뢰도:** 0.81
- **상태:** 확정
- **비고:** 압돌라히는 하탐 알안비야 중앙군사본부 사령관으로 이란 군의 통합지휘 체계에 속하며, IRGC와 병렬적 지휘 관계.

### 추론 #34: event_chain (인과 체인)
- **입력:** (ent-054/Islamabad Talks, causedBy→ent-063/Blockade Declaration), (ent-069/Blockade Implementation, follows→ent-063), (ent-095/Blockade Fully Implemented, follows→ent-069), (ent-096/Red Sea Threat, causedBy→ent-095)
- **추론:** (ent-096/Iran Red Sea Threat, causalChain, ent-054/Islamabad Talks)
- **신뢰도:** 0.72 (4단계 체인 → 0.5배 감쇠 적용)
- **상태:** 확정 (임계치 초과)
- **비고:** 이슬라마바드 결렬 → 봉쇄 선언 → 봉쇄 시행 → 봉쇄 완전 시행 → 홍해 봉쇄 위협. 이란의 에스컬레이션이 미국 봉쇄 강화에 대한 직접적 반응임을 보여주는 인과 체인.

### 추론 #35: co_participation (잠재적 관계)
- **입력:** ent-028/Asim Munir이 테헤란 방문(ent-097)과 동일 날 ent-091/Ali Abdollahi가 홍해 봉쇄 위협(ent-096). 같은 날 이란 수도에서 발생.
- **추론:** (ent-028/Asim Munir, potentialRelation, ent-091/Ali Abdollahi)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 무니르의 테헤란 방문이 미국 메시지 전달 목적인 반면, 압돌라히의 홍해 위협은 이란의 대응 카드 과시. 같은 날 같은 도시에서 '당근과 채찍'이 동시에 작동. 직접 면담 여부는 확인 불가.

### 추론 #36: event_chain (인과 체인)
- **입력:** (ent-054/Islamabad Talks collapse), (ent-063/Blockade Declaration), (ent-094/Trump 'close to over'), (ent-099/S&P Record)
- **추론:** (ent-099/S&P 500 Record, causalChain, ent-054/Islamabad Talks)
- **신뢰도:** 0.72 (3단계 체인)
- **상태:** 확정
- **비고:** 이슬라마바드 결렬 → 봉쇄 선언 → 트럼프 '전쟁 거의 끝' → S&P 신고가. 시장이 '역설적'으로 봉쇄(악재)를 협상 레버리지(호재)로 해석. 전쟁 시작 이후 모든 손실을 회복한 것은 시장이 단기 종전에 강하게 베팅하고 있음을 시사.

### 스키마 변경 없음
- 13개 새 엔티티 모두 기존 클래스(Person, Organization, Event, Concept)로 분류 가능
- 20개 새 관계 + 5개 추론 모두 기존 관계 유형으로 표현 가능
- 홍해 위협은 기존 Concept 클래스 + relatedTo 관계로 충분히 모델링됨

---

## 2026-04-16 추론 결과

### 추론 #37: transitivity (소속 전이)
- **입력:** (ent-104/Pete Hegseth, affiliatedWith, ent-003/US Military), (ent-003/US Military, affiliatedWith 간접, ent-001/Trump)
- **추론:** (ent-104/Pete Hegseth, indirectlyAffiliatedWith, ent-001/Donald Trump)
- **신뢰도:** 0.81
- **상태:** 확정
- **비고:** 국방장관 → US Military → 대통령 지휘체계. "as long as it takes" 발언은 트럼프의 최대 압박 전략의 군사적 표현.

### 추론 #38: transitivity (소속 전이)
- **입력:** (ent-105/Dan Caine, affiliatedWith, ent-003/US Military), (ent-003, 간접 → ent-001/Trump)
- **추론:** (ent-105/Dan Caine, indirectlyAffiliatedWith, ent-001/Donald Trump)
- **신뢰도:** 0.81
- **상태:** 확정
- **비고:** 합참의장 → US Military → 대통령. 봉쇄의 글로벌 확장 결정은 대통령 직속 명령 체계.

### 추론 #39: event_chain (사건 체인)
- **입력:** (ent-109/Israel-Lebanon Ceasefire, follows, ent-060/Washington Talks), (ent-060, follows, ent-053/Israel Lebanon Attacks)
- **추론:** (ent-109/Israel-Lebanon Ceasefire, causalChain, ent-054/Islamabad Talks)
- **신뢰도:** 0.72 (4단계 체인, 0.5배 감쇠 적용)
- **상태:** 확정
- **비고:** Islamabad 결렬 → 봉쇄 → 최대 압박 → 레바논 분리 해결. 봉쇄가 이스라엘에게 레바논 전선을 '양보'할 여유를 제공했다는 해석. 이스라엘이 '선의의 제스처'로 표현한 것은 미국의 봉쇄 레버리지가 이스라엘의 전략적 계산을 변경했음을 시사.

### 추론 #40: co_participation (공동 참여)
- **입력:** (ent-108/Ibrahim al-Moussawi, affiliatedWith, ent-047/Hezbollah), (ent-073/Naim Qassem, affiliatedWith, ent-047/Hezbollah)
- **추론:** (ent-108/al-Moussawi, potentialRelation, ent-073/Naim Qassem)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 같은 조직 내 상반된 입장: Qassem(4/13)은 워싱턴 회담 거부, Moussawi(4/16)는 조건부 수용. 헤즈볼라 내부에서 강경파(Qassem)와 실용파(Moussawi) 간 균열 가능성. 또는 전술적 역할 분담(강경 발언 → 조건부 수용으로 협상 레버리지 확보).

### 추론 #41: transitivity (소속 전이)
- **입력:** (ent-108/al-Moussawi, affiliatedWith, ent-047/Hezbollah), (ent-047/Hezbollah, affiliatedWith, ent-002/Iran)
- **추론:** (ent-108/al-Moussawi, indirectlyAffiliatedWith, ent-002/Iran)
- **신뢰도:** 0.81
- **상태:** 확정

### 추론 #42: event_chain (사건 체인)
- **입력:** (ent-111/Global Blockade Expansion, follows, ent-095/Blockade Fully Implemented), (ent-095, follows, ent-069/Blockade Implementation), (ent-069, follows, ent-063/Blockade Declaration)
- **추론:** (ent-111/Global Blockade Expansion, causalChain, ent-054/Islamabad Talks)
- **신뢰도:** 0.72 (5단계 체인, 0.5배 감쇠)
- **상태:** 확정
- **비고:** 이슬라마바드 결렬 → 봉쇄 선언(4/12) → 봉쇄 시행(4/13) → 완전 시행(4/15) → 글로벌 확장(4/16). 5일 만에 지역적 봉쇄에서 전 세계적 해상 제재 체제로 진화. 이란의 해상 우회로를 차단하려는 선제적 조치.

### 스키마 변경 없음
- 13개 새 엔티티 모두 기존 클래스(Person, Organization, Event, Concept)로 분류 가능
- 28개 새 관계 + 6개 추론 모두 기존 관계 유형으로 표현 가능
- 레바논 휴전, 글로벌 봉쇄, 핵 돌파구 보도 모두 기존 온톨로지 구조로 모델링 가능
