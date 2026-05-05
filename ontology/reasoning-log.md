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

---

## 2026-04-17 추론 결과

### 추론 #43: co_participation (이란 내부 분열)
- **입력:** (ent-044/Araghchi, participatesIn, ent-117/Hormuz Opening), (ent-005/IRGC, participatesIn, ent-118/Hormuz Re-closure Threat)
- **추론:** (ent-118/IRGC Re-closure, potentialRelation, ent-117/Hormuz Opening)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 아라그치(외교부)가 호르무즈 '완전 개방'을 선언한 같은 날, IRGC 계열 파르스통신이 재폐쇄를 위협. 실용파(외교부)와 강경파(IRGC/SNSC)의 공개적 불일치. 이란 내부의 전쟁 종결 여부를 둘러싼 노선 갈등이 수면 위로 부상.

### 추론 #44: event_chain (5단계 인과 체인)
- **입력:** (ent-054/Islamabad Talks, 결렬) → (ent-063/Blockade Declaration) → (ent-109/Lebanon Ceasefire) → (ent-117/Hormuz Opening)
- **추론:** (ent-117/Hormuz Opening, causalChain, ent-054/Islamabad Talks)
- **신뢰도:** 0.72 (5단계 체인, 0.5배 감쇠)
- **상태:** 확정
- **비고:** 이슬라마바드 결렬 → 봉쇄 선언 → 최대 압박 → 레바논 분리 해결 → 이란 호르무즈 '선제적 개방'. 이란의 개방은 레바논 휴전이라는 명분을 활용했으나, 실질적으로는 봉쇄의 경제적 압박이 원동력.

### 추론 #45: event_chain (3단계 인과 체인)
- **입력:** (ent-109/Lebanon Ceasefire) → (ent-117/Hormuz Opening) → (ent-122/Oil Price Crash)
- **추론:** (ent-122/Oil Crash, causalChain, ent-109/Lebanon Ceasefire)
- **신뢰도:** 0.72 (3단계)
- **상태:** 확정
- **비고:** 레바논 휴전 → 이란 호르무즈 개방 → 유가 11% 폭락. 시장은 레바논 휴전을 이란 전체 종전의 전주곡으로 해석. WTI $83.85는 3/10 이후 최저.

### 추론 #46: transitivity (에르도안 → 파키스탄 간접 관련)
- **입력:** (ent-127/Erdogan, cooperatesWith, ent-027/Sharif), (ent-027/Sharif, affiliatedWith, ent-029/Pakistan)
- **추론:** (ent-127/Erdogan, indirectlyAffiliatedWith, ent-029/Pakistan)
- **신뢰도:** 0.81
- **상태:** 확정
- **비고:** 에르도안은 안탈리아 외교포럼에서 샤리프와 양자 회담. 4국 외무장관 회담(터키/파키스탄/사우디/이집트)으로 확대. 터키가 파키스탄 주도 중재에 지역적 지지 제공.

### 추론 #47: co_participation (트럼프 PROHIBITED ↔ 레바논 휴전)
- **입력:** (ent-001/Trump, participatesIn, ent-109/Lebanon Ceasefire), (ent-001/Trump, opposes via ent-121/PROHIBITED, ent-031/Netanyahu)
- **추론:** (ent-121/PROHIBITED Warning, potentialRelation, ent-109/Lebanon Ceasefire)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 트럼프가 중재한 레바논 휴전이 이스라엘에 의해 위반되자, 트럼프는 공개적으로 이스라엘을 견제. 이는 트럼프가 레바논 휴전을 자신의 대이란 종전 전략의 핵심 요소로 보고 있음을 확인.

### 추론 #48: event_chain (호르무즈 개방 → 2차 회담 확정)
- **입력:** (ent-117/Hormuz Opening, date=2026-04-17), (ent-119/2nd Round Talks, date=2026-04-21 expected)
- **추론:** (ent-119/2nd Round Talks, causalChain, ent-117/Hormuz Opening)
- **신뢰도:** 0.72
- **상태:** 확정
- **비고:** 이란의 호르무즈 개방은 선의의 제스처이자 협상 레버리지. 같은 날 2차 회담이 구체적으로 확정된 것은 양측의 상호 신호(goodwill signaling)가 작동하고 있음을 시사. 이란이 '개방'하고 미국이 '봉쇄 유지'하면서도 '회담 확정'이라는 모순적이면서도 논리적인 구도.

### 스키마 변경 없음
- 11개 새 엔티티 모두 기존 클래스(Event, Concept, Person)로 분류 가능
- 22개 새 관계 + 6개 추론 모두 기존 관계 유형으로 표현 가능

---

## 2026-04-18 추론 결과

### 추론 #49: event_chain (호르무즈 재폐쇄 ← 인과 체인 ← 이슬라마바드)
- **입력:** (ent-054/Islamabad Talks, 결렬) → (ent-063/Blockade Declaration) → (ent-095/Blockade Fully Implemented) → (ent-128/Hormuz Re-closure)
- **추론:** (ent-128/Iran Hormuz Re-closure, causalChain, ent-054/Islamabad Talks)
- **신뢰도:** 0.72 (4단계 체인, 0.5배 감쇠)
- **상태:** 확정
- **비고:** 이슬라마바드 결렬 → 봉쇄 선언 → 완전 시행 → IRGC 재폐쇄. 아라그치의 24시간 전 개방 선언을 IRGC가 직접 무력화한 것은, 이란 내 군부(IRGC/SNSC)가 외교부를 압도하는 권력 구조를 노출. 재폐쇄의 직접적 명분은 미국 봉쇄 지속이지만, 근본 인과 체인은 이슬라마바드 결렬까지 거슬러 올라간다.

### 추론 #50: event_chain (IRGC 선박 발포 ← 호르무즈 개방)
- **입력:** (ent-117/Hormuz Opening, date=2026-04-17) → (ent-128/Hormuz Re-closure, date=2026-04-18) → (ent-129/IRGC Fires on Ships)
- **추론:** (ent-129/IRGC Fires on Ships, causalChain, ent-117/Hormuz Opening)
- **신뢰도:** 0.72 (3단계 체인)
- **상태:** 확정
- **비고:** 개방 선언 → 24시간 내 재폐쇄 → 선박 발포. IRGC가 아라그치의 개방을 무력화한 후 인도 국적 유조선 Sanmar Herald에 실탄 발포. 이란 전쟁 이후 최초의 직접적 해상 군사 행동. 개방이 IRGC의 통제권을 침해한다는 인식이 발포의 동기.

### 추론 #51: event_chain (유가 반등 ← 호르무즈 개방 역전)
- **입력:** (ent-117/Hormuz Opening) → (ent-122/Oil Crash -11%) → (ent-128/Hormuz Re-closure) → (ent-137/Oil Price Rebound)
- **추론:** (ent-137/Oil Price Rebound, causalChain, ent-117/Hormuz Opening)
- **신뢰도:** 0.72 (4단계 체인)
- **상태:** 확정
- **비고:** 개방 → 유가 폭락 → 재폐쇄 → 유가 반등. 24시간 내 완전한 시장 역전. WTI가 재폐쇄 소식에 $83.85에서 $89+ 수준으로 반등. 시장의 종전 낙관이 얼마나 취약한 기반 위에 있는지를 보여주는 사례.

### 추론 #52: co_participation ($20B 딜 ↔ 20년 모라토리엄)
- **입력:** (ent-130/$20B Deal, relatedTo, ent-064/Enriched Uranium), (ent-071/20-Year Moratorium, relatedTo, ent-064/Enriched Uranium)
- **추론:** (ent-130/$20B Deal, relatedTo, ent-071/20-Year Moratorium)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** $20B 현금-우라늄 딜과 20년 농축 모라토리엄은 같은 핵심 쟁점(농축 우라늄 900파운드)에 대한 두 가지 타협 경로. $20B 딜은 동결자산 해제 + 우라늄 제3국 이전이라는 경제적 인센티브, 모라토리엄은 시간 기반 타협. 두 경로가 합쳐질 가능성 — '$20B + 제한적 모라토리엄'이라는 패키지 딜.

### 추론 #53: co_participation (IRGC ↔ 이란 — 내부 분열의 구조적 의미)
- **입력:** (ent-005/IRGC, affiliatedWith, ent-002/Iran), (ent-005/IRGC, opposes, ent-044/Araghchi), (ent-044/Araghchi, affiliatedWith, ent-002/Iran)
- **추론:** (ent-005/IRGC, potentialRelation, ent-002/Iran)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** IRGC는 이란에 소속(affiliatedWith)되어 있으나 이란 외교부와 공개적으로 대립. '바보(idiot)' 발언은 군-외교부 분열이 개인적 모욕 수준까지 에스컬레이션했음을 보여준다. IRGC가 아라그치의 호르무즈 개방을 24시간 만에 뒤집은 것은 이란의 공식 외교 정책이 군부에 의해 사실상 거부권을 행사당할 수 있다는 구조적 문제를 노출. 2차 회담에서 이란 대표단의 합의 능력에 근본적 의문.

### 추론 #54: co_participation (이스라엘 PROHIBITED 항의 ↔ 레바논 휴전)
- **입력:** (ent-133/Israel Demands Explanation, causedBy, ent-121/Trump PROHIBITED), (ent-121/PROHIBITED, potentialRelation, ent-109/Lebanon Ceasefire)
- **추론:** (ent-133/Israel Demands Explanation, potentialRelation, ent-109/Lebanon Ceasefire)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 이스라엘이 PROHIBITED에 '충격'을 받고 백악관에 설명을 요구한 것은, 미-이스라엘 동맹 관계에서 전례 없는 공개적 마찰. 네타냐후는 레바논이 휴전에 포함된 것조차 부인(denial)하면서도 미국의 지원 없이 전쟁 지속이 불가능하다는 딜레마. 이 긴장은 2차 미-이란 회담에서 이스라엘 요소가 변수가 될 수 있음을 시사.

### 스키마 변경 없음
- 10개 새 엔티티 모두 기존 클래스(Event, Concept)로 분류 가능
- 24개 새 관계 + 6개 추론 모두 기존 관계 유형(participatesIn, follows, causedBy, locatedIn, opposes, relatedTo, causalChain, potentialRelation)으로 표현 가능

---

## 2026-04-19 추론 결과

### 추론 #55: event_chain (Touska 나포 ← 봉쇄 ← 이슬라마바드 결렬)
- **입력:** (ent-054/Islamabad Talks, 결렬) → (ent-063/Blockade Declaration) → (ent-095/Blockade Fully Implemented) → (ent-128/Hormuz Re-closure) → (ent-139/Touska Seizure)
- **추론:** (ent-139/US Navy Seizes Touska, causalChain, ent-054/Islamabad Talks)
- **신뢰도:** 0.72 (5단계 체인, 0.5배 감쇠)
- **상태:** 확정
- **비고:** 이슬라마바드 결렬 → 봉쇄 선언 → 완전 시행 → IRGC 재폐쇄 → 미 해군 Touska 나포. 봉쇄가 '차단'에서 '나포/발포'로 에스컬레이션한 것은 외교 교착의 직접적 군사적 귀결. USS Spruance가 6시간 경고 후 기관실에 사격한 것은 전쟁 이후 미군의 첫 이란 선박 직접 무력 행사.

### 추론 #56: co_participation (이란 회담 거부 ↔ IRGC-외교부 분열)
- **입력:** (ent-140/Iran Rejects Talks, 주체: Iran/IRNA), (ent-135/IRGC-Diplomatic Rift, IRGC가 외교부 결정 무력화)
- **추론:** (ent-140/Iran Rejects Talks, relatedTo, ent-135/IRGC-Diplomatic Rift)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 이란의 공식적 2차 회담 거부는 IRGC 강경파가 외교 노선을 완전히 장악했음을 의미. 4/18 Araghchi '바보' 사건 이후 24시간 만에 외교 채널 자체를 차단. Vahidi의 '배후 권력' 확인과 시기적으로 일치하며, IRGC가 협상 자체를 차단하는 구조적 결정임을 시사.

### 추론 #57: transitivity (Vahidi → IRGC → Iran 소속 전이)
- **입력:** (ent-138/Ahmad Vahidi, affiliatedWith, ent-005/IRGC), (ent-005/IRGC, affiliatedWith, ent-002/Iran)
- **추론:** (ent-138/Ahmad Vahidi, indirectlyAffiliatedWith, ent-002/Iran)
- **신뢰도:** 0.855 (= 0.95 × 0.90)
- **상태:** 확정
- **비고:** Vahidi는 IRGC 사령관이자 이란의 '배후 권력자'. Pezeshkian 대통령과 Araghchi 외무장관을 무력화하고 국가를 사실상 통제. IRGC 직속이면서 이란 전체를 간접 지배하는 이중적 위치. 이란 협상단의 합의 능력에 대한 근본적 의문을 더욱 강화.

### 추론 #58: event_chain (유가 급등 ← Touska 나포 ← 재폐쇄 ← 개방 역전)
- **입력:** (ent-117/Hormuz Opening) → (ent-122/Oil Crash -11%) → (ent-128/Re-closure) → (ent-137/Oil Rebound) → (ent-139/Touska Seizure) → (ent-144/Oil Surge +7%)
- **추론:** (ent-144/Oil Price Surge Apr 19, causalChain, ent-128/Hormuz Re-closure)
- **신뢰도:** 0.72 (3단계 체인)
- **상태:** 확정
- **비고:** 재폐쇄 → Touska 나포 → 유가 +7%. 3일 연속 대형 변동(4/17 -11%, 4/18 반등, 4/19 +7%)으로 에너지 시장이 완전한 불확실성에 진입. WTI $89.74, Brent $95.59로 다시 $90대 복귀. 호르무즈 '완전 운항 중단'(일요일 0척)이 가격 상승의 구조적 기반.

### 추론 #59: co_participation (옐로 라인 ↔ 레바논 내부 분열)
- **입력:** (ent-143/Israel Yellow Line, locatedIn, ent-050/Lebanon), (ent-090/Lebanon Internal Divisions, relatedTo, ent-074/Hezbollah Rejects Talks)
- **추론:** (ent-143/Israel Yellow Line, potentialRelation, ent-090/Lebanon Internal Divisions)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 이스라엘의 '옐로 라인' 10km 군사구역 설정은 레바논 내부 분열을 악화시킬 가능성. 정부(아운 대통령)는 휴전을 지지하나 헤즈볼라(카셈)는 이스라엘의 사실상 점령 확대에 반발할 수밖에 없음. 55개 마을의 가옥 철거는 '가자처럼'이라는 표현이 시사하듯 인도주의적 위기를 촉발할 수 있으며, 이는 레바논 정치의 종파적 긴장을 다시 분출시킬 변수.

### 추론 #60: event_chain (인프라 파괴 위협 ← 전면 위반 ← IRGC 발포 ← 재폐쇄)
- **입력:** (ent-128/Hormuz Re-closure) → (ent-129/IRGC Fires on Ships) → (ent-141/Trump Total Violation) → (ent-147/Infrastructure Destruction Threat)
- **추론:** (ent-147/Trump Infrastructure Threat, causalChain, ent-128/Hormuz Re-closure)
- **신뢰도:** 0.72 (4단계 체인, 0.5배 감쇠)
- **상태:** 확정
- **비고:** 재폐쇄 → IRGC 선박 발포 → 트럼프 '전면 위반' → 발전소/교량 파괴 위협. 이란의 군사적 에스컬레이션(재폐쇄+발포)이 트럼프의 가장 구체적인 인프라 파괴 위협을 촉발. '모든 발전소와 교량'이라는 표현은 이전의 '봉쇄 AND 폭격'(헤그세스 4/16)보다 더 구체적이며, 휴전 만료(4/23) 4일 전의 최후통첩적 성격. 2차 회담 불참과 결합되면 휴전 만료 후 전면전 재개의 가능성을 크게 높이는 신호.

### 스키마 변경 없음
- 11개 새 엔티티 모두 기존 클래스(Person, Event, Concept)로 분류 가능
- 31개 새 관계(명시적) + 6개 추론 모두 기존 관계 유형(affiliatedWith, opposes, participatesIn, follows, locatedIn, causedBy, relatedTo, causalChain, indirectlyAffiliatedWith, potentialRelation)으로 표현 가능

---

## 2026-04-20 추론 결과

### 추론 #1: transitivity (Zolghadr 간접 소속)
- **입력:** (ent-150/Zolghadr, affiliatedWith, ent-005/IRGC), (ent-005/IRGC, affiliatedWith, ent-002/Iran)
- **추론:** (ent-150/Zolghadr, indirectlyAffiliatedWith, ent-002/Iran)
- **신뢰도:** 0.855 (= 0.90 × 0.95)
- **상태:** 확정
- **비고:** Zolghadr는 Vahidi가 이슬라마바드 협상팀에 삽입한 IRGC 감시관. 외교 경험 없이 Araghchi/Ghalibaf의 반대를 무시하고 배치됨. Araghchi가 '저항의 축' 지원에 유연성을 보였다는 불만을 IRGC 상부에 보고.

### 추론 #2: transitivity (Bessent/Ratcliffe 간접 소속)
- **입력:** (ent-151/Bessent, affiliatedWith, ent-003/US Military-Gov), (ent-003, cooperatesWith, ent-001/Trump)
- **추론:** (ent-151/Bessent, indirectlyAffiliatedWith, ent-001/Trump)
- **신뢰도:** 0.81
- **상태:** 확정
- **비고:** 재무장관 Bessent과 CIA 국장 Ratcliffe의 긴급 회의 참석은 이란 전쟁 대응이 순수 군사를 넘어 경제(제재/봉쇄)와 정보(핵물질 추적) 차원으로 확대됨을 시사.

### 추론 #3: co_participation (Pezeshkian ↔ Vahidi 내부 분열)
- **입력:** (ent-149/Pezeshkian, affiliatedWith, ent-002/Iran), (ent-138/Vahidi, affiliatedWith via ent-005 → ent-002/Iran)
- **추론:** (ent-149/Pezeshkian, potentialRelation, ent-138/Vahidi)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 같은 국가 소속이나 구조적 대립 관계. Vahidi는 Pezeshkian의 정보장관 임명을 차단하고, Mojtaba Khamenei에 대한 유일한 접근 경로를 독점. '군사 정권' 다수 분석은 이란의 외교적 타협 능력이 IRGC에 의해 구조적으로 차단됨을 의미. 2차 회담 성사 여부는 IRGC의 최종 승인에 달려 있음.

### 추론 #4: event_chain (쿠웨이트 불가항력 인과 체인)
- **입력:** (ent-156/Kuwait FM, causedBy, ent-128/Hormuz Re-closure), (ent-128, follows, ent-117/Hormuz Opening), (ent-117, causedBy, ent-109/Israel-Lebanon Ceasefire)
- **추론:** (ent-156/Kuwait FM, causalChain, ent-054/Islamabad Peace Talks)
- **신뢰도:** 0.72 (3단계 이상이므로 감쇠 적용)
- **상태:** 확정
- **비고:** 이슬라마바드 회담 결렬 → 미 봉쇄 → 이란 재폐쇄 → 호르무즈 완전 마비 → 쿠웨이트 불가항력. 걸프국 에너지 수출 중단이 공식화됨은 전쟁의 경제적 충격이 새 단계에 진입했음을 의미. 200+ 탱커 체류, 글로벌 공급 10-11 mb/d 감소.

### 스키마 변경 없음
- 4개 새 엔티티 모두 기존 클래스(Person, Event)로 분류 가능
- 27개 새 관계(명시적) + 5개 추론 모두 기존 관계 유형으로 표현 가능

---

## 2026-04-21 추론 결과

### 추론 #61: event_chain (휴전 연장 ← 이슬라마바드 결렬 인과 체인)
- **입력:** (ent-054/Islamabad Talks, 결렬) → (ent-063/Blockade Declaration) → (ent-095/Blockade Fully Implemented) → (ent-140/Iran Rejects Talks) → (ent-158/Ceasefire Extension Indefinite)
- **추론:** (ent-158/Trump Ceasefire Extension, causalChain, ent-054/Islamabad Talks)
- **신뢰도:** 0.72 (5단계 체인, 0.5배 감쇠)
- **상태:** 확정
- **비고:** 이슬라마바드 결렬 → 봉쇄 선언 → 완전 시행 → 이란 회담 거부 → 트럼프 무기한 연장. 트럼프의 180도 선회(4/20 "highly unlikely" → 4/21 무기한 연장)는 이란의 완전 거부에 대한 전술적 대응. 봉쇄는 유지하면서 시간을 번다는 전략은 이란 내부 분열("seriously fractured")이 자연스럽게 타협파를 강화할 것이라는 계산에 기반. 핵심: 파키스탄(Munir+Sharif)의 요청을 직접 인용함으로써 중재 채널 보존.

### 추론 #62: event_chain (헤즈볼라 로켓 ← 레바논 휴전 인과 체인)
- **입력:** (ent-109/Lebanon Ceasefire Apr 16) → (ent-120/Lebanon Ceasefire Violations Apr 17) → (ent-143/Israel Yellow Line Apr 19) → (ent-161/Hezbollah First Rockets Apr 21)
- **추론:** (ent-161/Hezbollah First Rocket Fire, causalChain, ent-109/Israel-Lebanon Ceasefire)
- **신뢰도:** 0.72 (4단계 체인, 0.5배 감쇠)
- **상태:** 확정
- **비고:** 레바논 휴전(4/16) → 이스라엘 위반(4/17, 1명 사망) → 옐로 라인 10km 점령(4/19, 55개 마을) → 헤즈볼라 최초 로켓(4/21). 5일 만에 휴전 붕괴 경로에 진입. 헤즈볼라가 220+ 이스라엘 위반을 명분으로 사용한 것은 "조건부 수용"(4/16 Moussawi)의 조건이 충족되지 않았다는 판단. Legal Agenda의 220회 위반/3명 사망 통계가 이를 뒷받침. 이는 레바논 휴전(4/26 만료)이 이란-미국 휴전보다 먼저 붕괴될 수 있음을 시사.

### 추론 #63: event_chain (이스라엘-미국 전쟁 준비 ← 이슬라마바드 인과 체인)
- **입력:** (ent-054/Islamabad Talks, 결렬) → (ent-140/Iran Rejects Talks Apr 19) → (ent-160/Iran Official Refusal Apr 21) → (ent-162/Israel-US Joint Attack Planning)
- **추론:** (ent-162/Israel-US Joint Attack Planning, causalChain, ent-054/Islamabad Talks)
- **신뢰도:** 0.72 (4단계 체인, 0.5배 감쇠)
- **상태:** 확정
- **비고:** 이슬라마바드 결렬 → 이란 거부 → 공식 거부 → 이스라엘-미국 공동 전쟁 준비. Kan 보도의 "jointly preparing with Washington for war's resumption"은 이란 딜 회의론이 군사적 대안 모색으로 직결됨을 보여준다. 트럼프가 휴전을 연장하면서도 이스라엘과 공동 전쟁 준비를 진행하는 것은 "당근과 채찍"의 전형적 구조. 이스라엘 입장에서는 레바논 휴전 위반(옐로 라인)과 이란 딜 실패가 겹치면서 전쟁 재개의 명분과 동기가 모두 강화.

### 추론 #64: event_chain (유가 변동 ← 재폐쇄 인과 체인)
- **입력:** (ent-128/Hormuz Re-closure Apr 18) → (ent-139/Touska Seizure) → (ent-144/Oil Surge Apr 19) → (ent-163/Oil Movements Apr 21)
- **추론:** (ent-163/Oil Price Movements Apr 21, causalChain, ent-128/Hormuz Re-closure)
- **신뢰도:** 0.72 (4단계 체인)
- **상태:** 확정
- **비고:** 재폐쇄 → Touska 나포 → 유가 +7%(4/19) → Brent $98.48/WTI $92.13(4/21) → 장 마감 후 휴전 연장에 하락(WTI $88.60). 5일 연속 대형 변동으로 에너지 시장 불확실성 극대화. 장중 상승(이란 회담 거부·밴스 연기)과 장후 하락(휴전 연장)이 같은 날 교차하는 것은 시장이 매 시간 뉴스에 반응하는 "뉴스 트레이딩" 구조에 완전히 진입했음을 확인.

### 추론 #65: co_participation (이스라엘-미국 공동 참여)
- **입력:** (ent-004/Israel, participatesIn, ent-162/Joint Attack Planning), (ent-003/US Military, participatesIn, ent-162)
- **추론:** (ent-004/Israel, potentialRelation, ent-003/US Military)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 이스라엘과 미군이 전쟁 재개를 공동으로 준비한다는 것은 기존 cooperatesWith 관계의 강화. 이란 딜 무산 시 즉각적인 공동 군사 작전 가능성. 이는 이란의 협상 레버리지를 약화시키는 동시에, 이스라엘의 레바논 군사 행동에 대한 미국의 암묵적 용인 가능성도 시사.

### 추론 #66: co_participation (파키스탄 Munir-Sharif 공동 참여)
- **입력:** (ent-028/Asim Munir, participatesIn, ent-158/Ceasefire Extension), (ent-027/Shehbaz Sharif, participatesIn, ent-158)
- **추론:** (ent-028/Asim Munir, potentialRelation, ent-027/Shehbaz Sharif)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 트럼프가 Munir과 Sharif를 모두 이름으로 인용한 것은 파키스탄의 군-정 이원 중재 구조가 미국에서 인정받고 있음을 확인. Munir(군사 채널, IRGC 접근) + Sharif(정치 채널, Pezeshkian 접근)의 이중 트랙이 유일한 작동 가능 외교 경로로 재확인.

### 스키마 변경 없음
- 6개 새 엔티티 모두 기존 클래스(Event)로 분류 가능
- 30개 새 관계(명시적) + 6개 추론 모두 기존 관계 유형(participatesIn, follows, causedBy, relatedTo, locatedIn, opposes, cooperatesWith, causalChain, potentialRelation)으로 표현 가능
- 레바논 휴전 붕괴, 이스라엘-미국 공동 전쟁 준비 모두 기존 온톨로지 구조로 모델링 가능

## 2026-04-22 추론 결과

### 추론 #1: event_chain (IRGC 나포 → 유가)
- **입력:** (ent-164/IRGC 선박 나포, locatedIn, ent-008/Hormuz), (ent-167/Brent $100, causedBy, ent-164)
- **추론:** (ent-164, causalChain, ent-167)
- **신뢰도:** 0.72
- **상태:** 확정
- **비고:** IRGC의 선박 나포 → 호르무즈 불안 심화 → Brent $100 재돌파. 직접적 인과관계.

### 추론 #2: event_chain (휴전 연장 → IRGC 나포)
- **입력:** (ent-158/휴전 무기한 연장), (ent-164/IRGC 나포, causedBy, ent-158)
- **추론:** (ent-158, causalChain, ent-164)
- **신뢰도:** 0.72
- **상태:** 확정
- **비고:** 역설적 인과: 휴전 연장이 IRGC의 대응 도발을 촉발. 트럼프의 양보가 IRGC에게 추가 에스컬레이션 공간을 제공한 구조.

### 추론 #3: co_participation (페제시키안 개방 ↔ 이란 공식 거부)
- **입력:** (ent-166/페제시키안 개방, relatedTo, ent-160/이란 공식 거부)
- **추론:** (ent-166, potentialRelation, ent-160)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 같은 국가의 대통령(개방)과 IRGC/의회(거부)가 정반대 신호를 동시에 송출. 이란 내부 분열이 외교적 메시지 수준에서도 가시화.

### 추론 #4: co_participation (주가 신기록 ↔ 유가 $100)
- **입력:** (ent-168/S&P Nasdaq 신기록, causedBy, ent-158/휴전 연장), (ent-167/Brent $100, causedBy, ent-164/나포)
- **추론:** (ent-168, potentialRelation, ent-167)
- **신뢰도:** 0.70
- **상태:** 잠정
- **비고:** 동일 전쟁에서 유가(공급 위기 반영)와 주가(전쟁 종료 기대 반영)가 동시에 상승하는 디커플링 현상. 구조적 해석 필요.

### 추론 #5: co_participation (2차 이스라엘-레바논 회담 ↔ 헤즈볼라 공격)
- **입력:** (ent-169/2차 워싱턴 회담 예정), (ent-161/헤즈볼라 최초 로켓, follows, ent-109/레바논 휴전)
- **추론:** (ent-169, potentialRelation, ent-161)
- **신뢰도:** 0.72
- **상태:** 확정
- **비고:** 외교(목요일 회담 예정)와 군사(헤즈볼라 공격 지속)가 동시에 진행되는 레바논 이중구조. 헤즈볼라가 회담에 참여하지 않으므로, 회담 결과에 무관하게 공격이 지속될 수 있음.

### 스키마 변경 없음
- 7개 새 엔티티 모두 기존 클래스(Event 6개, Person 1개)로 분류 가능
- 19개 새 관계(명시적) + 5개 추론 모두 기존 관계 유형으로 표현 가능

## 2026-04-23 추론 결과

### 추론 #1: event_chain (기뢰 격침 명령 → 유가)
- **입력:** (ent-171/기뢰 격침 명령, locatedIn, ent-008/Hormuz), (ent-174/유가 $105, causedBy, ent-171)
- **추론:** (ent-171, causalChain, ent-174)
- **신뢰도:** 0.72
- **상태:** 확정
- **비고:** 트럼프의 shoot-to-kill 명령 → 호르무즈 긴장 극대화 → Brent $105(+3%), 스파이크 $107. 직접 인과. 갈리바프 사임 보도 이중 요인도 작용.

### 추론 #2: event_chain (IRGC → 갈리바프 사임)
- **입력:** (ent-005/IRGC, causedBy, ent-173/갈리바프 사임)
- **추론:** (ent-005, causalChain, ent-173)
- **신뢰도:** 0.75
- **상태:** 잠정 (사임 미확인)
- **비고:** IRGC의 졸가르드 삽입(4/20) → 아라그치 위임 초과 보고 → 갈리바프 사임(미확인). IRGC 간섭이 협상팀 해체의 직접 원인으로 보도됨. 확인 시 이란 외교 노선 전환의 결정적 전환점.

### 추론 #3: co_participation (3주 연장 ↔ 기존 10일 휴전)
- **입력:** (ent-172/3주 연장, follows, ent-109/10일 휴전)
- **추론:** (ent-172, potentialRelation, ent-169/2차 회담 예정)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 4/22 예고된 2차 회담이 실제 개최되어 3주 연장으로 이어짐. 외교 채널이 작동하고 있음을 입증. 그러나 현장(남부 레바논)에서의 위반은 계속됨.

### 추론 #4: co_participation (페제시키안 ↔ 갈리바프)
- **입력:** (ent-149/페제시키안, opposes, ent-001/트럼프), (ent-045/갈리바프, participatesIn, ent-173/사임)
- **추론:** (ent-149, potentialRelation, ent-045)
- **신뢰도:** 0.72
- **상태:** 잠정
- **비고:** 페제시키안(대화 의지)과 갈리바프(사임 보도) 모두 이란 내부에서 IRGC에 밀리는 온건/실용파. 공동 피해자 관계. IRGC-바히디 라인이 외교와 의회 모두 장악 중.

### 스키마 변경 없음
- 8개 새 엔티티 모두 기존 클래스(Event 4개, Person 3개, Location 1개)로 분류 가능
- 22개 새 관계(명시적) + 4개 추론 모두 기존 관계 유형(participatesIn, follows, causedBy, locatedIn, opposes, cooperatesWith, causalChain, potentialRelation)으로 표현 가능

## 2026-04-24 추론 결과

### 추론 #67: co_participation (Jalili-Araghchi 협상단 경쟁)
- **입력:** (ent-179/Saeed Jalili, relatedTo, ent-045/Ghalibaf), (ent-044/Araghchi, participatesIn, ent-183/Islamabad Visit), (ent-179/Jalili, affiliatedWith, ent-002/Iran)
- **추론:** (ent-179/Saeed Jalili, opposes, ent-044/Abbas Araghchi)
- **신뢰도:** 0.72
- **상태:** 잠정
- **비고:** Jalili는 핵 협상 시절부터 대표적 강경파(타협 거부 노선). Ghalibaf 대체 시 이란 협상팀의 강경화는 필연적. Araghchi(실용파)와의 노선 대립은 IRGC-외교부 분열의 또 다른 차원. 그러나 Araghchi가 이슬라마바드에 도착하는 것은 Jalili 임명이 아직 공식화되지 않았거나, 병렬적 외교 채널이 유지되고 있음을 시사.

### 추론 #68: event_chain (Araghchi 이슬라마바드 → 이란 거부 역전)
- **입력:** (ent-140/Iran Rejects 2nd Round, date=2026-04-19), (ent-183/Araghchi Islamabad Visit, date=2026-04-24)
- **추론:** (ent-183/Araghchi Islamabad Visit, follows, ent-140/Iran Rejects 2nd Round)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 이란의 공식 거부(4/19) → 5일 후 외무장관 이슬라마바드 도착. IRNA는 "미국 만남이 아님"이라 부인하나, Witkoff/Kushner와 같은 도시에 같은 주말 체류는 사실상 간접 회담 구조. 거부→뒤채널→재개 패턴은 1차 회담(이슬라마바드)에서도 동일하게 관찰됨. 이란의 '거부'는 국내 강경파를 위한 공식 포지션이며, 실질적 외교는 별도 경로로 진행되는 이중 구조.

### 추론 #69: event_chain (2차 회담 준비 → 이전 확정 부활)
- **입력:** (ent-119/2nd Round Confirmed, date=2026-04-17), (ent-140/Iran Rejects, date=2026-04-19), (ent-184/2nd Islamabad Talks Prep, date=2026-04-25)
- **추론:** (ent-184/2nd Islamabad Talks Prep, follows, ent-119/2nd Round Confirmed)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 2차 회담 확정(4/17) → 이란 거부(4/19)로 붕괴 → 5일 후 재가동(4/24-25). 외교 사이클의 '확정→붕괴→재건' 패턴. 미국 측(Witkoff/Kushner)은 이란의 거부를 전술적 포지셔닝으로 판단하고 회담 준비를 계속한 것으로 보임. 파키스탄(Sharif+Munir)의 뒤채널 중재가 재건의 핵심 메커니즘.

### 추론 #70: event_chain (Hegseth 브리핑 → 유가 $106 인과 체인)
- **입력:** (ent-171/기뢰 격침 명령, date=2026-04-23), (ent-182/Hegseth-Caine Pentagon Briefing, follows, ent-171), (ent-185/Oil $106, causedBy, ent-171)
- **추론:** (ent-182/Hegseth-Caine Pentagon Briefing, causalChain, ent-185/Oil $106)
- **신뢰도:** 0.72
- **상태:** 확정
- **비고:** 기뢰 격침 명령(4/23) → Hegseth 펜타곤 브리핑(4/24) "as long as it takes" → Brent $106+(장중 $107.38). 봉쇄 장기화 공식 선언이 유가 구조적 상승의 추가 요인. "freeriding" 비판은 동맹국 참여 없이 미국이 단독으로 봉쇄를 유지해야 하는 비용을 인정한 것이며, 이는 역설적으로 봉쇄의 지속 가능성에 대한 의문을 제기. 유가 종가($104.50)가 장중 최고($107.38)에서 하락한 것은 파키스탄 회담 희망이 부분적 완충 역할.

### 추론 #71: event_chain (레바논 3주 연장 → Day 8 위반)
- **입력:** (ent-172/3-Week Extension, date=2026-04-23), (ent-186/Day 8 Violations, follows, ent-172), (ent-180/Fayyad, opposes, ent-172)
- **추론:** (ent-186/Lebanon Ceasefire Day 8 Violations, causalChain, ent-172/3-Week Extension)
- **신뢰도:** 0.72
- **상태:** 확정
- **비고:** 3주 연장 합의(4/23) → 24시간 내 Day 8 위반: 빈트 주바일 6명 + 투린 2명 사살(4/24). 합의-위반 즉시 사이클은 10일 휴전(4/16)에서도 동일 패턴(합의 24시간 내 첫 위반). Ali Fayyad의 "meaningless" 발언은 헤즈볼라가 연장을 전혀 구속력 있는 것으로 보지 않음을 공식화. 이스라엘 역시 빈트 주바일 공습으로 연장 존중 의사가 없음을 행동으로 확인. 양측 모두 연장을 무시하는 구조에서 5월 14일 만료 전에 본격적 충돌 재개 가능성.

### 스키마 변경 없음
- 9개 새 엔티티 모두 기존 클래스(Person, Event, Concept)로 분류 가능
- 26개 새 관계(명시적) + 1개 업데이트 + 5개 추론 모두 기존 관계 유형(participatesIn, follows, causedBy, locatedIn, opposes, relatedTo, affiliatedWith, causalChain, potentialRelation)으로 표현 가능
- Saeed Jalili(Person), Ali Fayyad(Person), WPR Deadline(Concept) 모두 기존 클래스로 충분히 모델링됨

---

## 2026-04-25 추론 결과

### 추론 #1: event_chain (회담 인과 체인)
- **입력:** (ent-188/Trump Cancels Pakistan Trip, follows, ent-184/2nd Talks Prep), (ent-184, follows, ent-119/2nd Round Talks Monday)
- **추론:** (ent-188/Trump Cancels Pakistan Trip, causalChain, ent-054/Islamabad Peace Talks)
- **신뢰도:** 0.76
- **상태:** 확정
- **비고:** 트럼프 취소 → 2차 회담 준비 → 이슬라마바드 평화회담 전체 인과 체인. 회담 프로세스가 "거부→뒤채널→재개→취소" 사이클로 반복되고 있음.

### 추론 #2: co_participation (아라그치 출국-트럼프 취소 인과)
- **입력:** (ent-044/Araghchi, participatesIn, ent-192/Araghchi Departs), (ent-188/Trump Cancel, causedBy, ent-192/Araghchi Departs)
- **추론:** (ent-192/Araghchi Departs, relatedTo, ent-188/Trump Cancels Pakistan Trip)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 아라그치 출국이 트럼프 취소의 직접 트리거. 시간적 선후 관계 명확: 아라그치 토요일 오전 출국 → 트럼프 오후 취소 발표.

### 추론 #3: event_chain (네타냐후 공격-휴전 위반 체인)
- **입력:** (ent-191/Netanyahu Strikes, follows, ent-186/Day 8 Violations), (ent-186, follows, ent-172/3-Week Extension)
- **추론:** (ent-191/Netanyahu Strikes, causalChain, ent-172/3-Week Ceasefire Extension)
- **신뢰도:** 0.76
- **상태:** 확정
- **비고:** 네타냐후 "강력 공격" 명령 → Day 8/9 위반 → 3주 연장 합의. 합의-위반-에스컬레이션 즉시 사이클 패턴 확인.

### 추론 #4: co_participation (페제시키안-아라그치 외교 트랙)
- **입력:** (ent-149/Pezeshkian, participatesIn, ent-193/Forced Negotiations Refusal), (ent-044/Araghchi, participatesIn, ent-192/Departs Islamabad)
- **추론:** (ent-149/Pezeshkian, potentialRelation, ent-044/Araghchi)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 둘 다 이란 외교 트랙 대표. 그러나 페제시키안 강경화(4/25)와 아라그치 외교 순방(오만/러시아)은 다른 방향을 시사 — 이란 내부에서 대통령과 외무장관 사이에서도 미묘한 입장차 존재 가능.

### 추론 #5: co_participation (오만-파키스탄 중재 채널 다변화)
- **입력:** (ent-044/Araghchi, locatedIn, ent-189/Muscat), (ent-044, cooperatesWith, ent-028/Munir via Pakistan)
- **추론:** (ent-190/Oman, potentialRelation, ent-029/Pakistan)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 아라그치가 이슬라마바드 → 무스카트(오만) → 모스크바 순방. 오만은 전통적 미-이란 뒤채널 국가(2015 JCPOA 초기 비밀 협상). 파키스탄과 오만이 병렬 중재 채널로 기능할 가능성.

### 스키마 변경 없음
- 7개 새 엔티티 모두 기존 클래스(Event, Location, Organization)로 분류 가능
- 26개 새 관계(명시적) + 3개 업데이트 + 5개 추론 모두 기존 관계 유형으로 표현 가능
- 오만(Organization/state)과 무스카트(Location/city)는 기존 클래스로 충분히 모델링됨

---

## 2026-04-26 추론 결과

### 추론 #1: co_participation (오만-파키스탄 병렬 중재)
- **입력:** (ent-044/Araghchi, locatedIn, ent-190/Oman) AND (ent-044/Araghchi, locatedIn, ent-029/Pakistan) — 같은 날 양국 방문
- **추론:** (ent-190/Oman, potentialRelation, ent-029/Pakistan)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 2015 JCPOA 비밀 협상에서 오만이 뒤채널 역할을 한 전례. 파키스탄(공식 중재자)과 오만(비공식 뒤채널)의 병렬 중재 구조 형성 중.

### 추론 #2: event_chain (레바논 에스컬레이션 체인)
- **입력:** (ent-199/강제 퇴거, follows, ent-191/네타냐후 공격 명령), (ent-201/Day 10 에스컬레이션, causedBy, ent-199/강제 퇴거)
- **추론:** (ent-201/Day 10 에스컬레이션, causalChain, ent-109/Israel-Lebanon 10-Day Ceasefire)
- **신뢰도:** 0.76
- **상태:** 확정
- **비고:** 4/16 휴전 → 4/23 3주 연장 → 4/25 네타냐후 공격 명령 → 4/26 Fooks 전사 + 14명 사살 + 7개 마을 퇴거. 10일 만에 휴전이 사실상 붕괴 상태로 전이.

### 추론 #3: co_participation (영국-파키스탄 호르무즈 해법)
- **입력:** (ent-202/Starmer, cooperatesWith, ent-001/Trump) on Hormuz shipping, (ent-029/Pakistan, cooperatesWith, ent-001/Trump) as sole mediator
- **추론:** (ent-202/Starmer, potentialRelation, ent-029/Pakistan)
- **신뢰도:** 0.72
- **상태:** 확정
- **비고:** 50국 해양 자유항행 이니셔티브(Starmer-Macron)와 파키스탄 중재 트랙은 별도이나, 호르무즈 해법이라는 공통 목표로 수렴 가능.

### 추론 #4: co_participation (푸틴-아라그치 협력)
- **입력:** (ent-198/Putin, participatesIn, Araghchi Moscow Trip), (ent-044/Araghchi, participatesIn, Araghchi Moscow Trip)
- **추론:** (ent-198/Putin, potentialRelation, ent-044/Araghchi)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 러시아는 이란 농축 우라늄 보관/재처리 제안. 푸틴-아라그치 회담은 러시아의 핵 딜 중재자 역할을 공식화할 수 있음.

### 추론 #5: co_participation (WHCD 총격-이란전쟁 연관)
- **입력:** (ent-195/Cole Allen, participatesIn, ent-196/WHCD Shooting), (ent-001/Trump, participatesIn, ent-196/WHCD Shooting), (ent-001/Trump, participatesIn, ent-015/2026 Iran War)
- **추론:** (ent-195/Cole Allen, relatedTo, ent-015/2026 Iran War)
- **신뢰도:** 0.50
- **상태:** 잠정 (threshold 0.7 미달)
- **비고:** 트럼프 본인이 이란전쟁 연관을 부인("I don't think so"). 매니페스토에서 이란전쟁 직접 언급 여부 미확인. 간접적 연관에 그침.

### 스키마 변경 없음
- 금일 발견된 모든 엔티티/관계는 기존 seed 스키마로 충분히 표현 가능

---

## 2026-04-27 추론 결과

### 추론 #1: co_participation (러시아-파키스탄 병렬 중재)
- **입력:** (ent-198/Putin, cooperatesWith, ent-002/Iran), (ent-029/Pakistan, relatedTo, ent-209/Hormuz Proposal via mediation)
- **추론:** (ent-198/Putin, potentialRelation, ent-029/Pakistan)
- **신뢰도:** 0.72
- **상태:** 확정
- **비고:** 러시아와 파키스탄 모두 이란과 활발하게 접촉 중. 아라그치가 이슬라마바드→무스카트→상트페테르부르크를 순회하며 양국을 병렬 중재 채널로 활용. 두 채널이 조율될 가능성.

### 추론 #2: co_participation (메르츠-스타머 유럽 수렴)
- **입력:** (ent-205/Merz, opposes, ent-001/Trump [US 전략 비판]), (ent-202/Starmer, cooperatesWith, ent-001/Trump [해양 이니셔티브])
- **추론:** (ent-205/Merz, potentialRelation, ent-202/Starmer)
- **신뢰도:** 0.70
- **상태:** 확정
- **비고:** 유럽 내 두 가지 대응: (1) 메르츠의 공개적 미국 비판, (2) 스타머의 실용적 해양 이니셔티브. 목표는 동일(호르무즈 해법)하나 접근법이 다름. 유럽 공통 포지션으로 수렴 가능.

### 추론 #3: event_chain (호르무즈 제안 → 핵 후순위 전략)
- **입력:** (ent-209/Iran Hormuz Proposal, mentions, ent-212/Nuclear Deferral), Iran 명시적으로 핵을 2단계로 분리
- **추론:** (ent-209/Hormuz Proposal, causalChain, ent-212/Nuclear Deferral Strategy)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 이란의 호르무즈 재개방 제안은 핵 후순위 전략의 구현체. 4/12 이슬라마바드 결렬 이후 핵이 최대 장애물임을 인식하고 우회 전략 채택. 그러나 루비오의 즉각 거부는 미국이 핵을 분리할 의사가 없음을 확인.

### 추론 #4: transitivity (코스튜코프 → 이란 간접 소속)
- **입력:** (ent-206/Kostyukov, affiliatedWith, Russia/GRU), (ent-009/Russia, cooperatesWith, ent-002/Iran)
- **추론:** (ent-206/Kostyukov, indirectlyAffiliatedWith, ent-002/Iran)
- **신뢰도:** 0.72
- **상태:** 확정
- **비고:** GRU 군사정보국장이 푸틴-아라그치 외교 회담에 배석한 것은 이례적. 러시아의 이란 지원이 외교를 넘어 군사 정보 공유 수준임을 시사. 이란전쟁 관련 미국/이스라엘 군사 정보가 러시아를 통해 이란에 전달될 가능성.

### 추론 #5: event_chain (베카 공습 → 3주 연장 인과 체인)
- **입력:** (ent-211/Beqaa Strikes, follows, ent-201/Day 10 Escalation), (ent-201, causedBy, ent-199/7-Town Evacuation), (ent-172/3-Week Extension → ent-199 → ent-201 → ent-211)
- **추론:** (ent-211/Beqaa Strikes, causalChain, ent-172/3-Week Extension)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 3주 연장(4/23) → 7마을 퇴거(4/26) → Fooks 전사/14명 보복(Day 10) → 베카 밸리 3주 만 공습(Day 11). 휴전 확대가 군사 작전 지리적 확대로 이어지는 인과 체인. 이스라엘이 휴전을 점령 확대와 작전 범위 확장의 도구로 활용.

### 스키마 변경 없음
- 금일 발견된 모든 엔티티/관계는 기존 seed 스키마로 충분히 표현 가능

---

## 2026-04-28 추론 결과

### 추론 #1: event_chain (UAE OPEC 탈퇴 ← 이란 전쟁)
- **입력:** (ent-219/UAE OPEC Exit, relatedTo, ent-008/Hormuz), (ent-002/Iran, opposes, ent-035/UAE — 2,256 drones + 563 missiles)
- **추론:** (ent-219/UAE OPEC Exit, causedBy, ent-002/Iran war attacks)
- **신뢰도:** 0.78
- **상태:** 확정
- **비고:** UAE는 이란 전쟁에서 가장 많은 공격을 받은 GCC 국가(드론 2,256기, 미사일 563기). GCC '역대 최약' 대응에 불만 → 독자 노선 선택 → OPEC 탈퇴로 에너지 정책 자율화. 전쟁이 걸프 동맹 구조를 재편하는 인과 체인.

### 추론 #2: transitivity (모르다쇼프 → 러시아 → 이란 연결)
- **입력:** (ent-217/Mordashov, relatedTo, ent-009/Russia), (ent-009/Russia, cooperatesWith, ent-002/Iran — 4/27 푸틴-아라그치 회담)
- **추론:** (ent-217/Mordashov, indirectlyAffiliatedWith, ent-002/Iran — Nord 호르무즈 통과 가능 이유)
- **신뢰도:** 0.72
- **상태:** 확정
- **비고:** 러시아 제재 대상 억만장자의 $500M 요트가 이란+미국 이중 봉쇄를 무사히 통과한 것은 러시아-이란 군사 협력(GRU 참석 4/27)의 연장선에서 양측 모두 러시아 선박에 특혜를 부여했음을 시사. 봉쇄 '선택적 집행'의 증거.

### 추론 #3: co_participation (가르가쉬 비판 + OPEC 탈퇴 = 조율된 UAE 전략)
- **입력:** (ent-214/Gargash, affiliatedWith, ent-035/UAE), (ent-035/UAE, participatesIn, ent-219/OPEC Exit), (ent-214/Gargash, opposes, ent-216/GCC Summit — 'weakest in history')
- **추론:** (ent-214/Gargash criticism, potentialRelation, ent-219/OPEC Exit — 조율된 전략)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 가르가쉬의 GCC 비판(4/27)이 GCC 정상회의(4/28) 직전에 나온 것은 타이밍상 OPEC 탈퇴와 조율된 UAE의 독자 노선 선언으로 해석 가능. '실망 → 독립' 서사 구성.

### 추론 #4: co_participation (UN 호르무즈 촉구 ↔ 이란 호르무즈 제안 수렴)
- **입력:** (ent-221/UN Call, relatedTo, ent-008/Hormuz), (ent-209/Iran Proposal, relatedTo, ent-008/Hormuz)
- **추론:** (ent-221/UN Call, potentialRelation, ent-209/Iran Proposal — 동일 목표 수렴)
- **신뢰도:** 0.73
- **상태:** 확정
- **비고:** UN의 호르무즈 즉시 개방 요구와 이란의 호르무즈 재개방 제안이 동일한 목표(해협 개방)를 지향. 이란에게 다자적 정당성을 부여하는 구도. 미국은 핵 연계를 고수하므로 UN 압박도 미국 입장 변화에는 직접 영향 제한적이나, 도덕적 고지를 이란에 양보하는 효과.

### 추론 #5: event_chain (트럼프 '붕괴' 주장 vs 이란 제안 무력화)
- **입력:** (ent-220/Trump Collapse Claim, follows, ent-209/Iran Proposal — 루비오 거부 다음날), (ent-001/Trump, participatesIn, ent-220)
- **추론:** (ent-220/Collapse Claim, opposes, ent-209/Iran Proposal — 협상 지위 무력화 시도)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 이란 제안(4/27)을 루비오가 거부(4/27)한 다음날 트럼프가 '이란 붕괴' 주장(4/28)을 내놓은 것은, 이란의 제안을 '강자의 제안'이 아닌 '절박한 요청'으로 프레이밍하려는 전략. 이란군 대변인이 즉각 반박('전쟁 상황 지속')한 것도 같은 맥락.

### 스키마 변경 없음
- 금일 발견된 모든 엔티티/관계는 기존 seed 스키마(Entity, Person, Organization, Event, Location, Concept + 9개 관계 유형)로 충분히 표현 가능

---

## 2026-04-29 추론 결과

### 추론 #72: event_chain (헤그세스 청문회 ← WPR Day 60)
- **입력:** (ent-181/WPR May 1 Deadline, day=60 reached Apr 29), (ent-224/Hegseth Hearing, date=2026-04-29)
- **추론:** (ent-224/Hegseth Congressional Hearing, causedBy, ent-181/WPR May 1 Deadline)
- **신뢰도:** 0.82
- **상태:** 확정
- **비고:** WPR 60일 도달(4/29)이 의회의 첫 전쟁 청문회를 촉발. 민주당은 $25B 비용 공개를 활용하여 행정부의 '불법 전쟁' 프레이밍을 강화. 소송 위협(Blumenthal)과 시기적 연동. 청문회-WPR-소송이 삼중 압박 구조를 형성.

### 추론 #73: event_chain (이란 '실질 행동' ← 트럼프 봉쇄 명시화)
- **입력:** (ent-001/Trump, vows blockade until nuclear deal), (ent-226/Iran Practical Action Threat, follows, Trump vow)
- **추론:** (ent-226/Iran Practical Action Threat, causedBy, Trump Blockade-Until-Nuclear-Deal policy)
- **신뢰도:** 0.78
- **상태:** 확정
- **비고:** 트럼프의 '핵 딜까지 봉쇄' 명시 → 이란 '실질적 전례 없는 행동' 위협. 같은 뉴스 사이클 내의 직접 인과. 이란의 위협은 4/22 IRGC 선박 나포, 4/18 Sanmar Herald 발포에 이은 에스컬레이션 경로의 다음 단계일 수 있음. '전례 없는'이라는 수식어는 기존 해상 행동(나포/발포)을 넘어서는 것을 시사.

### 추론 #74: event_chain (FOMC 분열 ← 이란 전쟁 → 에너지 → 인플레)
- **입력:** (ent-015/2026 Iran War) → (ent-008/Hormuz blockade) → (Oil $119) → (ent-225/FOMC cites "elevated inflation from global energy prices")
- **추론:** (ent-225/FOMC April Decision, causedBy, ent-015/2026 Iran War — via energy prices)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** FOMC 성명이 '글로벌 에너지 가격 상승'을 인플레이션 원인으로 명시적 인용. 8-4 분열(34년 만 최대)은 전쟁→에너지→인플레→통화정책 연쇄의 최종 단계. 전쟁이 미국 국내 경제 정책에 구조적으로 영향을 미치는 공식 경로.

### 추론 #75: event_chain (IDF '휴전 없다' ← 3주 연장 역설)
- **입력:** (ent-172/3-Week Extension, date=2026-04-23), (ent-223/Zamir 'no ceasefire', date=2026-04-29, follows ent-172)
- **추론:** (ent-223/Zamir Statement, opposes, ent-172/3-Week Ceasefire Extension)
- **신뢰도:** 0.78
- **상태:** 확정
- **비고:** IDF 참모총장이 공식 휴전 기간에 '휴전은 없다'고 선언한 것은 군사-외교 괴리의 극단적 사례. 옐로 라인 너머와 리타니 강 북쪽까지 '자유 행동'을 지시한 것은 이스라엘이 휴전을 작전 범위 확대의 도구로 활용함을 군 최고사령관 수준에서 확인. Day 13에 구조대원 이중타격(3명 사망)은 이 전략의 실행.

### 추론 #76: event_chain (이중타격 ← Day 10 ← Day 8 ← 3주 연장)
- **입력:** (ent-172/3-Week Extension) → (ent-186/Day 8 Violations) → (ent-201/Day 10 Fooks+14) → (ent-227/Day 13 Double-Tap)
- **추론:** (ent-227/Day 13 Double-Tap Strike, causalChain, ent-172/3-Week Ceasefire Extension)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 3주 연장(4/23) → Day 8 위반(4/24, 8명) → Day 10(4/26, Fooks 전사+14명) → Day 13(4/29, 구조대원 이중타격+8명). 사상자 증가 트렌드(8→14+→8). 이중타격(double-tap)은 구조대원을 의도적 표적으로 삼는 전술로, 레바논 PM의 '전쟁 범죄' 비난의 근거. 사상자 총계 2,534명 사망, 7,863명 부상.

### 스키마 변경 없음
- 7개 새 엔티티 모두 기존 클래스(Person 3개, Event 4개)로 분류 가능
- 13개 새 관계(명시적) + 2개 업데이트 + 5개 추론 모두 기존 관계 유형(participatesIn, follows, causedBy, opposes, affiliatedWith, relatedTo, mentions, causalChain, potentialRelation)으로 표현 가능

---

## 2026-04-30 추론 결과

### 추론 #77: event_chain (Hegseth 청문회 ← WPR 6차 표결)
- **입력:** (ent-234/Hegseth Senate Hearing, date=2026-04-30), (ent-235/Senate WPR Vote 6, date=2026-04-30, relatedTo ent-181/WPR)
- **추론:** (ent-234/Hegseth Senate Hearing, causedBy, ent-235/Senate WPR Vote 6)
- **신뢰도:** 0.82
- **상태:** 확정
- **비고:** 상원 군사위 청문회와 WPR 6차 표결이 같은 날(May 1 전야) 동시 진행. 헤그세스의 '시계 정지' 주장은 내일 데드라인에 대한 법적 방어를 위한 것. 청문회-표결-데드라인이 삼중으로 맞물리며 법적 위기 최고조.

### 추론 #78: event_chain (CENTCOM 브리핑 ← 이란 '실질 행동' 위협)
- **입력:** (ent-226/Iran Practical Action Threat, date=2026-04-29), (ent-236/CENTCOM Military Briefing, date=2026-04-30)
- **추론:** (ent-236/CENTCOM Briefing, causedBy, ent-226/Iran Practical Action Threat)
- **신뢰도:** 0.78
- **상태:** 확정
- **비고:** 이란의 '전례 없는 실질 행동' 위협(4/29) 다음 날 트럼프가 CENTCOM으로부터 군사옵션 브리핑을 받은 것은 직접적 인과 관계. 3가지 옵션(단기 공습, 호르무즈 지상작전, 우라늄 탈취)은 모두 이란 '실질 행동'에 대한 선제적/대응적 성격.

### 추론 #79: event_chain (검은 수요일 ← 자미르 '휴전 없다')
- **입력:** (ent-223/Zamir 'no ceasefire', date=2026-04-29), (ent-237/Black Wednesday, date=2026-04-30, 28 killed)
- **추론:** (ent-237/Black Wednesday, causalChain, ent-223/Zamir 'no ceasefire')
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** IDF 참모총장의 '휴전 없다' 공식 선언(4/29) 직후 Day 14에 28명 사망(휴전 후 최다). 군 최고사령관의 지시가 현장에서 즉시 실행되는 명령-실행 인과 체인. 레바논 군인 2명 사망은 새로운 에스컬레이션 — 비전투원/민간인을 넘어 국가 군대가 타격받은 것은 사실상 국가 간 충돌.

### 추론 #80: event_chain (유가 급반전 ← CENTCOM 브리핑)
- **입력:** (ent-238/Oil $126 High, date=2026-04-30, peak then reversal), (ent-236/CENTCOM Briefing report)
- **추론:** (ent-238/Oil Price Reversal, causedBy, ent-236/CENTCOM Briefing)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** Brent가 $126(4년 최고)에서 CENTCOM 브리핑 보도 직후 $111로 급반전(-12%). 시장은 군사행동 가능성을 역설적으로 '교착 해결책'으로 해석. 봉쇄 장기화보다 단기 군사 충격 후 협상을 선호하는 시장 심리 반영.

### 추론 #81: co_participation (Johnson-Hegseth WPR 공동 방어)
- **입력:** (ent-232/Johnson, action='not at war'), (ent-098/Hegseth, action='clock pauses'), 같은 날 동시 발언
- **추론:** (ent-232/Johnson, cooperatesWith, ent-098/Hegseth)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 존슨 '전쟁이 아니다' + 헤그세스 '시계가 정지된다' = 행정부-의회 공화당의 협조된 WPR 방어 전략. 두 가지 상호 보완적 법적 논리: (1) 전쟁 자체를 부정하여 WPR 적용 자체를 회피, (2) 설사 전쟁이라도 휴전으로 시계가 정지되었다는 차선 논리.

### 스키마 변경 없음
- 10개 새 엔티티 모두 기존 클래스(Person 4개, Event 5개, Concept 1개)로 분류 가능
- 14개 새 관계(명시적) + 2개 업데이트 + 5개 추론 모두 기존 관계 유형으로 표현 가능

---

## 2026-05-01 추론 결과

### 추론 #1: event_chain (WPR 부결 → 종료 선언)
- **입력:** (ent-235/Senate WPR Vote 6, relatedTo, ent-184/WPR), (ent-240/Hostilities Terminated Letter, relatedTo, ent-184/WPR)
- **추론:** (ent-240/Hostilities Terminated Letter, causedBy, ent-235/Senate WPR Vote 6)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** WPR 6차 부결(50-47, 4/30)이 법적 방어선의 취약성을 드러내자, 다음 날 트럼프가 '적대행위 종료' 서한이라는 전혀 새로운 법적 전략으로 전환. 부결 → 서한의 인과 체인.

### 추론 #2: event_chain (CENTCOM 브리핑 → 테헤란 방공)
- **입력:** (ent-236/CENTCOM Briefing, relatedTo, ent-002/Iran), (ent-242/Tehran Air Defense, relatedTo, ent-002/Iran)
- **추론:** (ent-242/Tehran Air Defense Activation, causedBy, ent-236/CENTCOM Military Briefing)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** CENTCOM 3가지 군사옵션 브리핑(4/30) 다음 날 테헤란 방공망이 20분간 가동. 이란이 미국의 군사행동 준비에 방어적으로 대응한 것으로 해석. 다만 드론 대응이라는 공식 설명도 존재.

### 추론 #3: event_chain (메르츠 비판 → 주둔군 철수)
- **입력:** (ent-205/Merz, opposes, ent-001/Trump), (ent-243/Troop Withdrawal, participatesIn, ent-003/US Military)
- **추론:** (ent-243/US Troop Withdrawal Germany, causedBy, ent-001/Donald Trump)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 메르츠 총리의 '미국 굴욕' 비판(4/27) → 트럼프 독일 주둔군 5,000명 철수 확정(5/1). 이란 전쟁이 미-유럽 동맹에 미치는 파급 효과. 이탈리아·스페인으로 위협 확대.

### 추론 #4: co_participation (블루먼솔-트럼프 대립)
- **입력:** (ent-244/Blumenthal, opposes, ent-240/Terminated Letter), (ent-001/Trump, participatesIn, ent-240)
- **추론:** (ent-240/Hostilities Terminated Letter, opposes, ent-244/Richard Blumenthal)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 트럼프 '종료' vs 블루먼솔 '봉쇄=전쟁행위' — 동일 법적 사안에 대한 정면 대립. '종료 선언'이 법적 도전에 직면할 가능성.

### 추론 #5: co_participation (루비오-하메네이 교착)
- **입력:** (ent-087/Rubio, opposes, ent-241/Iran Proposal), (ent-046/Khamenei, opposes, ent-241/Iran Proposal)
- **추론:** (ent-087/Rubio, potentialRelation, ent-046/Khamenei)
- **신뢰도:** 0.72
- **상태:** 확정
- **비고:** 역설적 공동 거부: 루비오는 핵 미포함을 이유로 거부, 하메네이는 핵 포기 불가를 선언. 양측 모두 핵 문제를 양보 불가 입장으로 설정 → 구조적 교착 심화.

### 스키마 변경 없음
- 9개 새 엔티티 모두 기존 클래스(Person 2개, Event 5개, Concept 2개)로 분류 가능
- 15개 새 관계(명시적) + 1개 업데이트 + 5개 추론 모두 기존 관계 유형으로 표현 가능

---

## 2026-05-02 추론 결과

### 추론 #1: co_participation (이중 트랙 모순)
- **입력:** (ent-001/Trump, relatedTo, ent-250/$8.6B Arms), (ent-001/Trump, opposes, ent-249/14-Point Proposal)
- **추론:** (ent-250/$8.6B Arms, opposes, ent-249/14-Point Proposal)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 트럼프가 14개항 제안을 '검토'하면서 동시에 $8.6B 무기를 긴급 판매 — 외교적 열림과 군사적 닫힘이 동시 진행. 무기 판매는 이란 전쟁 참전국(이스라엘, 카타르, UAE, 쿠웨이트) 보상 성격으로, 외교 실패 시 군사 재개 준비를 시사.

### 추론 #2: co_participation (이란 내부 분열: 군부 vs 외교)
- **입력:** (ent-251/Asadi, affiliatedWith, ent-005/IRGC), (ent-002/Iran, relatedTo, ent-249/14-Point Proposal)
- **추론:** (ent-251/Asadi, opposes, ent-249/14-Point Proposal)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 이란이 14개항 외교 제안서를 내놓은 같은 날, IRGC 연계 인물(아사디)이 전쟁 재개 'likely' 발언. 페제시키안-외교팀 vs IRGC-군부 분열 지속. Fars 통신(IRGC 매체)이 전쟁 재개 메시지를 확산.

### 추론 #3: event_chain (이란 전쟁 → Spirit Airlines 파산 인과 체인)
- **입력:** (ent-015/2026 Iran War, causedBy 역방향, ent-008/Hormuz blockade), (ent-252/Spirit Shutdown, causedBy, ent-008/Hormuz)
- **추론:** (ent-252/Spirit Shutdown, causedBy, ent-015/2026 Iran War)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 인과 체인: 이란 전쟁 → 호르무즈 봉쇄 → 유가 급등 → 항공유 $4.51 → Spirit 파산. 전쟁의 미국 본토 실물경제 영향 첫 대형 사례. Time: "Other Low-Cost Airlines Could Be Next" — 도미노 가능성.

### 추론 #4: co_participation (공화당 군사 기득권 반발)
- **입력:** (ent-255/Wicker, opposes, ent-243/Germany Withdrawal), (ent-256/Rogers, opposes, ent-243/Germany Withdrawal)
- **추론:** (ent-255/Wicker, potentialRelation, ent-256/Rogers)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 상원·하원 군사위 양원 의장(공화당)이 공동 성명으로 대통령 정책에 반대. '푸틴에게 잘못된 신호' — 이란 전쟁이 공화당 내부 균열로 전이.

### 추론 #5: co_participation ('해적' vs '종료' 자기모순)
- **입력:** (ent-001/Trump, relatedTo, ent-254/Pirates Statement), (ent-001/Trump, relatedTo, ent-248/Terminated Doctrine)
- **추론:** (ent-254/Pirates Statement, opposes, ent-248/Terminated Doctrine)
- **신뢰도:** 0.78
- **상태:** 확정
- **비고:** '적대행위 종료'를 선언한 다음 날, '해적처럼 선박을 나포하고 화물을 압류한다'고 자랑 — 자기 법적 논거를 자기가 훼손. 블루먼솔의 '봉쇄=전쟁행위' 주장을 자기 발언으로 뒷받침.

### 스키마 변경 없음
- 11개 새 엔티티 모두 기존 클래스(Person 4개, Event 6개, Organization 1개, Concept 1개 — 총 12 but Sean Duffy 제외 11개 주요)로 분류 가능
- 15개 새 관계(명시적) + 2개 업데이트 + 5개 추론 모두 기존 관계 유형으로 표현 가능

---

## 2026-05-03 추론 결과

### 추론 #1: co_participation (Project Freedom ↔ IRGC 군사 대치)
- **입력:** (ent-260/Project Freedom, locatedIn, ent-008/Hormuz), (ent-005/IRGC, locatedIn, ent-008/Hormuz)
- **추론:** (ent-260/Project Freedom, opposes, ent-005/IRGC)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 미국이 월요일부터 중립 선박을 호르무즈 밖으로 호위하겠다고 발표. CENTCOM: 구축함, 항공기 100+대, 15,000명 배치. IRGC가 호르무즈를 사실상 통제하고 있는 상황에서 군사 호위 작전은 직접 충돌 가능성을 내포. 트럼프: "interference will be dealt with forcefully."

### 추론 #2: co_participation (이란 항행법 vs Project Freedom — 경쟁적 법적 프레임워크)
- **입력:** (ent-262/Iran Navigation Law, relatedTo, ent-008/Hormuz), (ent-260/Project Freedom, locatedIn, ent-008/Hormuz)
- **추론:** (ent-262/Iran Navigation Law, opposes, ent-260/Project Freedom)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 동일한 수역에 대해 양측이 경쟁적 법적/군사적 프레임워크를 동시 구축. 이란: 의회 입법(허가제, 통행료, 몰수). 미국: 군사 호위 작전('Project Freedom'). 호르무즈가 군사 대치에서 **법적 주권 분쟁**으로 전환.

### 추론 #3: event_chain (14개항 제안 → 거부 → 검토 — 협상 사이클)
- **입력:** (ent-249/14-Point Proposal, date=May 2), (ent-265/Trump Rejects, date=May 3)
- **추론:** (ent-265/Trump Rejects, follows, ent-249/14-Point Proposal)
- **신뢰도:** 0.90
- **상태:** 확정
- **비고:** 이란 14개항 제출(5/2) → 트럼프 '수용 불가' 공식 거부(5/3) → 미국 파키스탄 경유 답변 → 이란 검토 중(5/3). 공개 거부와 비공식 대화가 동시 진행되는 'negotiation by rejection' 패턴.

### 추론 #4: event_chain (이란 검토 → 트럼프 거부 후속 — 채널 유지)
- **입력:** (ent-266/Iran Reviews, follows, ent-265/Trump Rejects)
- **추론:** (ent-266/Iran Reviews, relatedTo, ent-030/Pakistan)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 트럼프가 공개적으로 '불가'라 했음에도 파키스탄 채널로 공식 답변을 전달. Witkoff "we're in conversation" — 비공식 채널 활성. 공개 거부 ≠ 협상 중단.

### 추론 #5: event_chain (하이칼-클리어필드 → 이스라엘-레바논 휴전 모니터링 연속)
- **입력:** (ent-267/Haykal-Clearfield Meeting, date=May 3), (ent-109/Israel-Lebanon Ceasefire, date=Apr 16)
- **추론:** (ent-267/Haykal-Clearfield Meeting, relatedTo, ent-109/Israel-Lebanon Ceasefire)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 4/16 휴전 이후 Day 17. 하이칼-클리어필드 '예외적 회담'은 모니터링 메커니즘 강화 시도이나, 같은 날 이스라엘이 11개 마을 퇴거 명령. 휴전 형식 유지와 사실상 붕괴가 동시 진행.

### 스키마 변경 없음
- 8개 새 엔티티 모두 기존 클래스(Person 3개, Event 5개)로 분류 가능
- 13개 새 관계(명시적) + 2개 업데이트 + 5개 추론 모두 기존 관계 유형으로 표현 가능

---

## 2026-05-04 추론 결과

### 추론 #1: event_chain (Project Freedom → 호르무즈 교전 — 군사 충돌 전환)
- **입력:** (ent-260/Project Freedom, locatedIn, ent-008/Hormuz), (ent-268/US-Iran Exchange of Fire, locatedIn, ent-008/Hormuz)
- **추론:** (ent-268/US-Iran Exchange of Fire, follows, ent-260/Project Freedom)
- **신뢰도:** 0.95
- **상태:** 확정
- **비고:** Project Freedom Day 1에 IRGC가 미사일·드론·쾌속정으로 공격, 미군이 6척 격침. 5/3의 '법적 대립'이 5/4에 '군사 충돌'로 전환. 4/8 휴전 이후 최초 직접 교전.

### 추론 #2: event_chain (Project Freedom → 푸자이라 공격 — 이란 보복 확전)
- **입력:** (ent-260/Project Freedom, date=May 4), (ent-269/Fujairah Attack, date=May 4)
- **추론:** (ent-269/Fujairah Attack, causedBy, ent-260/Project Freedom)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 푸자이라는 ADCOP 파이프라인의 종점으로 호르무즈 우회 경로. 이란이 호르무즈 직접 대치와 동시에 우회 경로도 공격하여 '이중 봉쇄' 의지를 과시. 4/8 이후 최초 UAE 공격.

### 추론 #3: co_participation (IRGC 통제구역 ↔ 이란 항행법 — 입법과 군사의 동기화)
- **입력:** (ent-262/Iran Navigation Law, date=May 3), (ent-270/IRGC Maritime Control Zone, date=May 4)
- **추론:** (ent-270/IRGC Maritime Control Zone, relatedTo, ent-262/Iran Navigation Law)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 5/3 의회 입법 추진 → 5/4 IRGC 공식 통제구역 선포. 니크자드(의회)와 IRGC가 동시에 호르무즈 법제화·군사화를 추진. 의회-IRGC 동기화는 이란 내부 '강경 통합'을 시사.

### 추론 #4: co_participation (UAE ↔ US Military — 암시적 동맹 강화)
- **입력:** (ent-275/UAE, opposes, ent-002/Iran), (ent-003/US Military, participatesIn, ent-268/Exchange of Fire)
- **추론:** (ent-275/UAE, potentialRelation, ent-003/US Military)
- **신뢰도:** 0.75
- **상태:** 잠정 (직접 군사 협력 미확인)
- **비고:** 같은 날 UAE가 이란 미사일 15발 요격 + 미군이 호르무즈에서 IRGC 교전. 직접 공동 작전은 아니나 동시 이란 공격 대응에서 암시적 전략 동맹.

### 추론 #5: co_participation (베리 → 이-레 휴전 약화 — 정치적 장벽)
- **입력:** (ent-271/Nabih Berri, opposes, ent-004/Israel), (ent-109/Israel-Lebanon Ceasefire, date=Apr 16)
- **추론:** (ent-271/Nabih Berri, opposes, ent-109/Israel-Lebanon Ceasefire)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 레바논 최고위 시아파 지도자가 이스라엘 협상을 '전쟁 중단 전 불가'로 거부. 4/14 워싱턴 회담, 4/23 휴전 연장에도 불구하고 정치적 프레임워크가 약화. 5/17 만료까지 13일.

### 스키마 변경 없음
- 10개 새 엔티티: Event 3개, Person 3개, Location 1개, Organization 2개, Concept 0개
- 16개 새 관계(명시적) + 2개 업데이트 + 5개 추론 모두 기존 관계 유형으로 표현 가능
- 새 클래스/관계 유형 추가 불필요
