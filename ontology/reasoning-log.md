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

---

## 2026-05-05 추론 결과

### 추론 #1: event_chain (교전→일시중단)
- **입력:** (ent-260/Project Freedom, follows → ent-268/호르무즈 교전 May 4)
- **추론:** (ent-277/Project Freedom Pause, causedBy, ent-268/호르무즈 교전 May 4)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** Day 1 교전의 강도(7척 격침, 미사일 교환, UAE 공격)가 트럼프의 정치적 계산을 변경하여 24시간 만에 일시중단 결정. 봉쇄는 유지하되 호송은 중단 — 군사적 비용 대비 외교적 여지 확보.

### 추론 #2: event_chain (Project Freedom→UAE 2차 공격)
- **입력:** (ent-260/Project Freedom, → ent-269/푸자이라 공격), (ent-269, follows → ent-278/제벨알리 공격)
- **추론:** (ent-278/제벨알리 공격 May 5, causedBy, ent-260/Project Freedom)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 이란의 UAE 공격이 2일 연속 지속되면서 표적이 푸자이라(ADCOP 우회 경로)에서 제벨알리(중동 최대 항구)로 확대. Project Freedom 시행에 대한 이란의 보복 패턴이 확립됨.

### 추론 #3: event_chain (입법→통제구역→Strait Authority 3단계)
- **입력:** (ent-265/이란 항행법, → ent-270/IRGC 통제구역, → ent-279/Strait Authority)
- **추론:** (ent-279/Iran Strait Authority, relatedTo, ent-265/이란 항행법)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 5/3 의회 입법 → 5/4 IRGC 통제구역 선포 → 5/5 Strait Authority 통과허가 메커니즘. 이란이 호르무즈 주권적 통제를 입법·군사·행정 3단계로 체계화. de facto에서 de jure로의 전환 완결.

### 추론 #4: co_participation (중국-러시아 이란 지원 잠재)
- **입력:** (ent-286/China, cooperatesWith, ent-002/Iran), (ent-009/Russia, potentialRelation, ent-002/Iran)
- **추론:** (ent-286/China, potentialRelation, ent-009/Russia)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 아라그치가 러시아(4/27 상트페테르부르크)에 이어 중국(5/5 베이징)을 방문. 양국 모두 UNSC 거부권 보유국이며 이란의 대미 외교전에서 핵심 지원 축.

### 추론 #5: co_participation (UAE-US 암시적 동맹 강화)
- **입력:** (ent-275/UAE, opposes, ent-005/IRGC), (ent-003/US Military, opposes, ent-005/IRGC)
- **추론:** (ent-275/UAE, cooperatesWith, ent-003/US Military)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 이란의 동시다발 공격(호르무즈+UAE)에 UAE와 미군이 동일 적에 대응. 국제 규탄에서도 걸프+서방이 동일 진영. 직접적 공동 작전은 미확인이나 방위 동맹 강화가 추론됨.

### 스키마 변경 없음
- 금일 발견된 모든 엔티티와 관계는 기존 스키마로 충분히 표현 가능
- Strait Authority는 Concept 클래스로 분류 (새 클래스 불필요)

---

## 2026-05-06 추론 결과

### 추론 #1: event_chain (PF 일시중단 → MoU 근접)
- **입력:** (ent-277/PF 일시중단, follows, ent-260/Project Freedom), (ent-287/14-Point MoU, relatedTo, ent-277)
- **추론:** (ent-287/14-Point MoU, causedBy, ent-277/PF 일시중단)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** PF 일시중단(5/5)이 외교적 공간을 열어 MoU 최종 단계 진입을 가능하게 함. 군사적 비용 회피와 외교적 레버리지 유지의 절충이 MoU 근접의 전제조건.

### 추론 #2: event_chain (Strait Authority → IRGC 통행 재개)
- **입력:** (ent-279/Strait Authority, locatedIn, ent-008/Hormuz), (ent-289/IRGC 통행 재개, locatedIn, ent-008/Hormuz)
- **추론:** (ent-289/IRGC 통행 재개, follows, ent-279/Strait Authority)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 5/3 의회 항행법 → 5/4 IRGC 통제구역 → 5/5 Strait Authority → 5/6 실제 통행 허용. 4단계 제도화·집행 시퀀스 완성. 이란은 호르무즈 주권 통제를 기정사실화하면서 '부분 개방'으로 국제 압력을 완화하려 함.

### 추론 #3: co_participation (베이루트 공습 ↔ 포괄적 휴전 충돌)
- **입력:** (ent-004/Israel, attacks, ent-291/베이루트 공습), (ent-280/Wang Yi, calls_for, ent-293/포괄적 휴전)
- **추론:** (ent-291/베이루트 공습, opposes, ent-293/포괄적 휴전)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 이스라엘의 4/16 이후 최초 베이루트 공습은 중국이 촉구하는 '포괄적 휴전' 분위기와 정면 충돌. MoU 근접 시점에 레바논 전선 확대는 전체 평화 프로세스의 불안 요소.

### 추론 #4: co_participation (Trump-Xi 정상회담 ↔ MoU 시한 연동)
- **입력:** (ent-001/Trump, participatesIn, ent-294/Trump-Xi Summit), (ent-001/Trump, participatesIn, ent-287/MoU)
- **추론:** (ent-294/Trump-Xi Summit, relatedTo, ent-287/14-Point MoU)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 5/14-15 정상회담은 트럼프가 '이란 딜 완료' 상태로 시진핑을 만나려는 동기를 제공. MoU의 사실상 데드라인은 Trump-Xi 정상회담('no deadline' 발언에도 불구).

### 추론 #5: event_chain (위협 + 협상 = 'Madman Theory')
- **입력:** (ent-001/Trump, threatens, ent-288/폭격 위협), (ent-001/Trump, participatesIn, ent-287/MoU)
- **추론:** (ent-288/폭격 위협, opposes, ent-287/MoU) — 역설적으로 위협이 협상 레버리지로 기능
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 'much higher level' 위협과 'great progress' 주장이 동시. 전형적 닉슨 독트린(Madman Theory): 비합리적 위협으로 상대의 양보를 유도. 이란에 24-48시간 내 응답 압박.

### 스키마 변경 없음
- 금일 발견된 모든 엔티티와 관계는 기존 스키마로 충분히 표현 가능
- MoU는 Concept 클래스, 나머지 사건은 Event 클래스로 분류

---

## 2026-05-07 추론 결과

### 추론 #1: event_chain (IRGC 공격 → US 보복 공습)
- **입력:** (ent-005/IRGC, participatesIn, ent-304/IRGC 함정 공격), (ent-003/US Military, participatesIn, ent-305/US 자위권 공습)
- **추론:** (ent-305/US 자위권 공습, follows, ent-304/IRGC 함정 공격) — 명확한 시간적·인과적 시퀀스
- **신뢰도:** 0.90
- **상태:** 확정
- **비고:** IRGC가 USS Truxtun/Rafael Peralta/Mason에 미사일·드론·쾌속정으로 공격 → CENTCOM이 미사일/드론 발사 시설, C2, ISR 노드를 즉시 보복 타격. 양측 모두 '휴전은 유지된다'고 주장하나, 실질적으로 전투 상태.

### 추론 #2: co_participation (군사 충돌 ↔ MoU 협상 역설)
- **입력:** (ent-305/US 공습, 2026-05-07), (ent-287/14-Point MoU, 2026-05-07 이란 응답 예정)
- **추론:** (ent-305/US 공습, potentialRelation, ent-287/MoU) — '무장 외교'(armed diplomacy) 패턴
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 폭격하면서 협상하는 역설. 트럼프는 '휴전은 끝나지 않았다'고 주장하며 군사 행동과 외교를 동시 추진. 이란은 '휴전 위반'으로 규정하면서도 목요일 MoU 응답을 예고. 양측 모두 완전한 결렬을 원하지 않음.

### 추론 #3: co_participation (IRGC 함정 공격과 MoU 훼손)
- **입력:** (ent-005/IRGC, participatesIn, ent-304), (ent-002/Iran, participatesIn, ent-287/MoU)
- **추론:** (ent-304/IRGC 함정 공격, potentialRelation, ent-287/MoU) — IRGC의 군사 행동이 외교 트랙을 잠재적으로 훼손
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 이란 내부 분열 패턴 재확인. 외교부(아라그치/바가에이)는 MoU 검토 중이나, IRGC는 군사적 도발 지속. 4/18 아라그치 '바보' 모욕 사건 이후 이란 이원체계(문민 vs 군부)의 정책 불일치가 지속.

### 추론 #4: event_chain (12년 모라토리엄 ↔ MoU 누락 쟁점)
- **입력:** (ent-306/12년 모라토리엄, relatedTo, ent-287/MoU), (ent-308/MoU 누락 쟁점, relatedTo, ent-287/MoU)
- **추론:** (ent-306, potentialRelation, ent-308) — 기간은 절충하나 본질적 쟁점은 미해결
- **신뢰도:** 0.72
- **상태:** 확정
- **비고:** 핵 모라토리엄 기간(12~15년)은 좁혀졌으나, 핵 검증(IAEA 사찰 구체 조건), 탄도미사일 제한, 대리세력(헤즈볼라/하마스/후시) 무장해제, HEU 900파운드 처리 등 핵심 쟁점이 30일 후속 협상으로 미뤄짐.

### 추론 #5: transitivity (구축함 → 미군 → 트럼프 지휘 체인)
- **입력:** (ent-297/USS Truxtun, affiliatedWith, ent-003/US Military), (ent-003, affiliatedWith, ent-001/Trump)
- **추론:** (ent-297/USS Truxtun, indirectlyAffiliatedWith, ent-001/Trump) — Commander-in-Chief 지휘 체인
- **신뢰도:** 0.81
- **상태:** 확정
- **비고:** 트럼프가 ABC News에 '휴전은 끝나지 않았다'고 발언한 것은 자위권 공습이 대통령 승인 하에 이루어졌음을 시사.

### 스키마 변경 없음
- 금일 발견된 모든 엔티티와 관계는 기존 스키마로 충분히 표현 가능
- 군함은 Organization 클래스, 타격 지역은 Location 클래스로 분류

---

## 2026-05-08 추론 결과

### 추론 #1: co_participation ('Love Tap' ↔ MoU)
- **입력:** (ent-001/Trump, relatedTo, ent-313/Love Tap Doctrine), (ent-001/Trump, relatedTo, ent-287/14-Point MoU)
- **추론:** (ent-313/Love Tap Doctrine, relatedTo, ent-287/14-Point MoU)
- **신뢰도:** 0.78
- **상태:** 확정
- **비고:** 트럼프가 군사 행동을 'love tap'으로 최소화하면서 동시에 MoU 협상을 지속하는 것은 수사적 에스컬레이션 관리 전략. 군사적 위협과 외교적 공간 보존을 양립시키려는 의도.

### 추론 #2: event_chain (석유 저장 위기 → MoU 압박)
- **입력:** (ent-319/Iran Oil Storage Crisis, causedBy, ent-008/Strait of Hormuz), (ent-008/Strait of Hormuz, relatedTo, ent-287/14-Point MoU)
- **추론:** (ent-319/Iran Oil Storage Crisis, relatedTo, ent-287/14-Point MoU)
- **신뢰도:** 0.82
- **상태:** 확정
- **비고:** 이란의 석유 저장 위기(6-7주 내 용량 한계)는 봉쇄의 경제적 효과가 시간제한적 레버리지로 기능함을 보여줌. 이란이 MoU를 수용할 경제적 압박의 타임라인.

### 추론 #3: event_chain (5/7 IRGC 공격 → 5/8 유조선 무력화)
- **입력:** (ent-304/IRGC 함정 공격 5/7, locatedIn, ent-008), (ent-312/US Tanker Strike 5/8, locatedIn, ent-008)
- **추론:** (ent-312/US Tanker Strike 5/8, relatedTo, ent-304/IRGC 함정 공격 5/7)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 5/7 IRGC의 미 구축함 공격 → 5/7 CENTCOM 자위권 공습 → 5/8 이란 유조선 무력화로 이어지는 에스컬레이션 사이클. '휴전' 프레임 내에서 실질적 전투 강도가 증가.

### 추론 #4: event_chain (카르그 섬 유출 원인 — 잠정)
- **입력:** (ent-317/Kharg Island Oil Spill, locatedIn, ent-007/Kharg Island), (ent-312/US Tanker Strike 5/8, locatedIn, ent-008)
- **추론:** (ent-317/Kharg Island Oil Spill, causedBy, ent-312/US Tanker Strike 5/8)
- **신뢰도:** 0.55
- **상태:** 잠정 (confidence_threshold 0.7 미달)
- **비고:** 카르그 섬 유출(45㎢)은 전쟁 이후 최대 규모이나 원인 미확인. 군사 작전과의 시간적 상관관계는 있으나 인과관계 증거 부족.

### 추론 #5: co_participation (NATO ↔ 교황 — 미국 정당성 위기)
- **입력:** (ent-318/NATO, opposes, ent-001/Trump), (ent-316/Pope Leo XIV, opposes, ent-001/Trump)
- **추론:** (ent-318/NATO, relatedTo, ent-316/Pope Leo XIV)
- **신뢰도:** 0.72
- **상태:** 확정
- **비고:** NATO(군사 동맹)와 교황(도덕적 권위)이 동시에 미국의 이란 전쟁 수행에 이의를 제기 — 정당성의 양면적 도전. 군사적·도덕적 정당성이 동시에 흔들리는 구조.

### 스키마 변경 없음
- 금일 발견된 모든 엔티티와 관계는 기존 스키마로 충분히 표현 가능
- 유조선은 Organization 클래스, 항모는 Organization 클래스, 유출 사건은 Event 클래스로 분류
- 'Love Tap Doctrine', 'Iran Oil Storage Crisis', 'US Consumer Confidence Collapse'는 Concept 클래스로 분류

---

## 2026-05-09 추론 결과

### 추론 #1: transitivity (IRGC 해군사령부 → 이란 간접 소속)
- **입력:** (ent-322/IRGC Naval Command, affiliatedWith, ent-005/IRGC), (ent-005/IRGC, affiliatedWith, ent-002/Iran)
- **추론:** (ent-322/IRGC Naval Command, indirectlyAffiliatedWith, ent-002/Iran)
- **신뢰도:** 0.855 (= 0.90 × 0.95)
- **상태:** 확정

### 추론 #2: transitivity (IRGC 항공우주군 → 이란 간접 소속)
- **입력:** (ent-323/IRGC Aerospace Force, affiliatedWith, ent-005/IRGC), (ent-005/IRGC, affiliatedWith, ent-002/Iran)
- **추론:** (ent-323/IRGC Aerospace Force, indirectlyAffiliatedWith, ent-002/Iran)
- **신뢰도:** 0.855 (= 0.90 × 0.95)
- **상태:** 확정

### 추론 #3: transitivity (모흐베르 → 이란 간접 소속)
- **입력:** (ent-321/Mohammad Mokhber, affiliatedWith, ent-047/Mojtaba Khamenei), (ent-047/Mojtaba Khamenei, affiliatedWith, ent-002/Iran)
- **추론:** (ent-321/Mohammad Mokhber, indirectlyAffiliatedWith, ent-002/Iran)
- **신뢰도:** 0.81 (= 0.90 × 0.90)
- **상태:** 확정

### 추론 #4: event_chain (헤즈볼라 이스라엘 영내 공격 → 4/21 첫 로켓 발사 후속)
- **입력:** (ent-324/Hezbollah Cross-Border Strikes May 9, follows, ent-161/Hezbollah First Rocket Fire Apr 21)
- **추론:** (ent-324, causalChain, ent-161)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 4/21 첫 로켓 발사 → 5/9 이스라엘 영내 공격으로 에스컬레이션 단계 상승. 휴전 후 헤즈볼라의 공격 범위가 점진적으로 확대되는 패턴 확인.

### 추론 #5: co_participation (Mokhber-Ghalibaf 반협상 동맹)
- **입력:** (ent-321/Mokhber, mentions, ent-328/Hormuz Atomic Bomb Doctrine — 전쟁 성과 포기 불가), (ent-051/Ghalibaf, opposes, ent-287/14-Point MoU — 'Operation Trust Me Bro failed')
- **추론:** (ent-321/Mohammad Mokhber, potentialRelation, ent-051/Mohammad Baqer Ghalibaf)
- **신뢰도:** 0.75
- **상태:** 잠정
- **비고:** 양자 모두 협상 반대 입장을 공개적으로 표명. 직접 연대 증거는 없으나, IRGC-의회 강경파 축이 외교부(아라그치)를 견제하는 패턴이 반복됨.

### 스키마 변경 없음
- 금일 발견된 모든 엔티티와 관계는 기존 스키마로 표현 가능
- IRGC 하위 조직(Naval Command, Aerospace Force)은 Organization 클래스로 충분
- 'Hormuz as Atomic Bomb Doctrine'은 Concept 클래스로 표현

---

## 2026-05-10 추론 결과

### 추론 #1: event_chain (이란 응답→MoU 인과 체인)
- **입력:** (ent-289/14-Point MoU, relatedTo, ent-002/Iran), (ent-333/Iran formal response, follows, ent-289)
- **추론:** (ent-333/Iran formal response, causedBy, ent-289/14-Point MoU)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 미국의 14개항 MoU 제안이 이란 역제안을 유발. 5/6 Axios 공개 → 5/10 공식 응답으로 약 4일 소요.

### 추론 #2: event_chain (레바논 에스컬레이션 체인)
- **입력:** (ent-326/Day 23 strikes 19+ killed, locatedIn, ent-079/Lebanon), (ent-339/Day 24 strikes 39+ killed, locatedIn, ent-079)
- **추론:** (ent-339/Day 24 strikes, follows, ent-326/Day 23 strikes)
- **신뢰도:** 0.9
- **상태:** 확정
- **비고:** Day 23(19명)→Day 24(39명)으로 사상자 2배 증가. 5/14-15 워싱턴 3차 회담 전 이스라엘 '최대 압박' 전략의 패턴 확인.

### 추론 #3: co_participation (카타르-이란 간접 연결)
- **입력:** (ent-336/Qatar, cooperatesWith, ent-093/Pakistan), (ent-002/Iran, cooperatesWith, ent-336/Qatar — LNG 통과 승인)
- **추론:** (ent-336/Qatar, indirectlyAffiliatedWith, ent-002/Iran)
- **신뢰도:** 0.72
- **상태:** 확정
- **비고:** 파키스탄 중개를 통한 이란-카타르 협력 구조. 이란이 카타르 LNG 통과를 '선택적으로' 승인한 것은 정치적 도구로서의 해협 통제를 입증.

### 추론 #4: co_participation (트럼프-시진핑 레버리지 역학)
- **입력:** (ent-001/Trump, participatesIn, ent-338/Beijing Summit), (ent-283/Xi Jinping, participatesIn, ent-338)
- **추론:** (ent-001/Trump, potentialRelation, ent-283/Xi Jinping)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 미해결 이란 전쟁이 시진핑에게 협상 레버리지를 제공. 중국이 이란 최대 원유 구매국 → 이란에 대한 압박 카드.

### 추론 #5: transitivity (중국-IRGC 간접 자금 연결)
- **입력:** (ent-282/China, cooperatesWith, ent-002/Iran — oil purchases), (ent-005/IRGC, affiliatedWith, ent-002/Iran)
- **추론:** (ent-282/China, potentialRelation, ent-005/IRGC)
- **신뢰도:** 0.70
- **상태:** 잠정
- **비고:** 중국의 이란 원유 구매가 이란 정부 예산을 통해 IRGC 자금원에 간접 기여할 수 있으나, 직접적 증거는 부족. 3단계 전이이므로 신뢰도 감쇠 적용.

### 스키마 변경 없음
- 금일 발견된 모든 엔티티와 관계는 기존 스키마로 표현 가능
- Al Kharaitiyat은 Organization(vessel) 클래스로, Qatar는 Organization(state)으로, 핵 역제안은 Event로 충분히 표현됨

---

## 2026-05-11 추론 결과

### 추론 #1: event_chain (협상 에스컬레이션 인과 체인)
- **입력:** (ent-333/Iran formal response, follows, ent-289/14-Point MoU), (ent-334/Trump REJECTS, follows, ent-333), (ent-345/Life Support, follows, ent-334)
- **추론:** (ent-345/Ceasefire 'life support', causedBy, ent-333/Iran formal response)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** Iran Response(5/10) → Trump Rejects(5/10) → 'Life Support'(5/11)의 3단계 인과 체인. 트럼프 rhetoric이 'TOTALLY UNACCEPTABLE' → 'garbage'/'life support'로 24시간 내 에스컬레이션.

### 추론 #2: event_chain (레바논 사상자 에스컬레이션)
- **입력:** (ent-339/Day 24 strikes 39+, locatedIn, ent-079/Lebanon), (ent-347/Day 25 strikes 51, locatedIn, ent-079)
- **추론:** (ent-347/Day 25 strikes, causedBy, ent-339/Day 24 strikes)
- **신뢰도:** 0.9
- **상태:** 확정
- **비고:** Day 23(19명)→Day 24(39명)→Day 25(51명)으로 3일 연속 에스컬레이션. 의료진 사망(103명 누적)은 국제인도법 위반 쟁점. 5/14-15 3차 워싱턴 회담 전 '최대 압박' 패턴 지속.

### 추론 #3: co_participation (UK-France 공동 호르무즈 대응)
- **입력:** (ent-320/Baghaei, opposes, ent-348/UK), (ent-320/Baghaei, opposes, ent-349/France)
- **추론:** (ent-348/UK, potentialRelation, ent-349/France)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** UK와 France가 모두 호르무즈 해군 증강을 검토 중 → 잠재적 공동 유럽 해군 대응. 이란이 양국을 명시적으로 경고한 것은 이 가능성을 인지하고 있음을 시사.

### 추론 #4: event_chain (베이징 정상회담 긴급성 상승)
- **입력:** (ent-345/Ceasefire 'life support', follows, ent-334/Trump Rejects), (ent-001/Trump, participatesIn, ent-338/Beijing Summit)
- **추론:** (ent-338/Beijing Summit, causedBy, ent-345/Life Support)
- **신뢰도:** 0.8
- **상태:** 확정
- **비고:** 협상 결렬 → 정상회담 의미 상승. 트럼프가 시진핑에 이란 원유 구매 중단 압박 가능성. 중국이 이란 최대 원유 구매국이라는 점에서 정상회담이 협상 동력 복원의 핵심 변수.

### 스키마 변경 없음
- 금일 발견된 모든 엔티티와 관계는 기존 스키마로 표현 가능
- UK/France는 Organization(state), 호르무즈 경고/봉쇄 현황은 Event, 3차 워싱턴 회담은 Event로 분류

---

## 2026-05-14 추론 결과

### 추론 #1: event_chain (호르무즈 → CPI → 트럼프 발언 인과 체인)
- **입력:** (ent-008/Hormuz, causedBy, ent-354/CPI 3.8%), (ent-354/CPI 3.8%, causedBy, ent-353/Trump 'Americans' finances')
- **추론:** (ent-354/CPI 3.8%, causalChain, ent-353/Trump 발언)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 호르무즈 봉쇄 → 에너지 가격 급등 → CPI 3.8%(3년 최고) → 트럼프 '미국인 재정 생각 안 해' 발언. 전쟁의 실물경제 충격이 정치적 파장으로 전이되는 인과 체인.

### 추론 #2: co_participation (중국 유조선 — 정상회담 연계)
- **입력:** (ent-357/Yuan Hua Hu, affiliatedWith, ent-282/China), (ent-001/Trump, participatesIn, ent-338/Beijing Summit), (ent-283/Xi, participatesIn, ent-338)
- **추론:** (ent-357/Yuan Hua Hu, potentialRelation, ent-338/Beijing Summit)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 중국 국영 Cosco Shipping 소속 VLCC가 정상회담 당일 호르무즈 통과 시도. 이란이 통행료 없이 통과 허용 — 테헤란의 중국에 대한 제스처이자, 시진핑에게 레버리지를 제공하는 조정된 시그널링.

### 추론 #3: event_chain (IDF 리타니 진출 ↔ 워싱턴 회담 모순)
- **입력:** (ent-004/Israel, participatesIn, ent-360/Litani crossing), (ent-004/Israel, participatesIn, ent-352/3rd Washington talks)
- **추론:** (ent-360/Litani crossing, opposes, ent-352/3rd Washington talks)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** IDF가 리타니강 이북으로 진출하여 100+ 표적을 파괴하면서 동시에 워싱턴에서 평화 회담을 진행. 군사 행동이 외교를 약화시키는 구조적 모순.

### 추론 #4: event_chain ($29B → 슬레지해머 연계)
- **입력:** (ent-003/US Military, relatedTo, ent-355/$29B), (ent-003, relatedTo, ent-356/Sledgehammer)
- **추론:** (ent-356/Sledgehammer, follows, ent-355/$29B)
- **신뢰도:** 0.75
- **상태:** 잠정
- **비고:** 전쟁 비용 $29B 공개 → 의회 압박 → '슬레지해머' 개명으로 WPR 시계 리셋 시도. 비용 정당화와 법적 우회가 연동되는 패턴.

### 추론 #5: co_participation (IEA 경고 ↔ 반도체 위기 수렴)
- **입력:** (ent-358/IEA warning, causedBy, ent-008/Hormuz), (ent-362/Semiconductor disruption, causedBy, ent-008)
- **추론:** (ent-358/IEA warning, relatedTo, ent-362/Semiconductor disruption)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** IEA 원유 재고 기록적 감소와 반도체 공급망 타격 모두 호르무즈 봉쇄에서 기인. 에너지 위기와 기술 위기가 수렴하는 복합 공급망 위기.

### 스키마 변경 없음
- 금일 발견된 모든 엔티티와 관계는 기존 스키마로 표현 가능
- 신규 개념(Operation Sledgehammer, Hormuz semiconductor disruption)은 Concept 클래스로 분류

## 2026-05-15 추론 결과

### 추론 #1: co_participation (Cooper 90% 열화 vs Araghchi '전쟁 승리' — 모순적 평가)
- **입력:** (ent-235/Brad Cooper, participatesIn, ent-371/Senate testimony — '90% 열화'), (ent-043/Araghchi, mentions, ent-377/'Iran was the victor')
- **추론:** (ent-371/Cooper testimony, opposes, ent-377/Iran victory narrative)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 같은 날 CENTCOM 사령관은 이란 군사력 90% 파괴를 증언하고, 이란 외무장관은 '전쟁 승리'를 선언. 정보전 차원의 상반된 내러티브. 양측 모두 국내 청중을 겨냥한 메시지이며, 객관적 평가와 선전 사이의 간극을 보여줌.

### 추론 #2: co_participation (45일 휴전 연장 vs 48시간 55명 사망 — 명목적 휴전)
- **입력:** (ent-352/3rd Washington talks, relatedTo, ent-368/45-day extension), (ent-004/Israel, opposes, ent-046/Hezbollah via ent-376/55 killed 48h)
- **추론:** (ent-368/45-day extension, opposes, ent-376/Day 29-30 strikes)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 워싱턴에서 '매우 생산적' 회담 후 45일 연장을 발표하는 동시에 48시간 동안 55명이 사망. 휴전 누적 사망자 657명+. 휴전은 법적 프레임워크이지 실질적 전투 중단이 아님.

### 추론 #3: co_participation (중국 석유 구매 + Yuan Hua Hu 통과 — 조율된 석유 외교)
- **입력:** (ent-282/China, cooperatesWith, ent-366/Boeing), (ent-357/Yuan Hua Hu, locatedIn, ent-008/Hormuz), (ent-367/Beijing Trade Deal, follows, ent-338/Beijing Summit)
- **추론:** (ent-367/Trade Deal, relatedTo, ent-357/Yuan Hua Hu)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 중국이 미국산 석유 구매를 약속하면서 동시에 Yuan Hua Hu가 이라크 원유를 실고 호르무즈를 통과. 중국은 양방향 석유 외교를 구사 — 미국으로부터 석유를 사면서 이란/이라크 원유도 확보. 시진핑의 레버리지 극대화 전략.

### 추론 #4: event_chain (Epic Fury 종료 → Sledgehammer 전환 — WPR 시계 리셋)
- **입력:** (ent-042/Rubio, participatesIn, ent-379/Epic Fury declared over), (ent-356/Sledgehammer, follows, ent-379)
- **추론:** (ent-379/Epic Fury over, relatedTo, ent-356/Sledgehammer)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 루비오가 Epic Fury '종료'를 선언하면서 60일 WPR 시한 논쟁을 종결시키려는 시도. 다음 단계로 Sledgehammer 개명을 통해 시계를 리셋하려는 법적 전략. 의회 우회 시도의 진화.

### 추론 #5: co_participation (가자 하다드 타격 ↔ 휴전 연장 동시 — 다중 전선 에스컬레이션)
- **입력:** (ent-004/Israel, opposes, ent-372/Haddad via ent-373/Haddad strike), (ent-368/45-day extension announced same day)
- **추론:** (ent-373/Haddad strike, opposes, ent-368/45-day extension)
- **신뢰도:** 0.75
- **상태:** 잠정
- **비고:** 이스라엘이 레바논 휴전 45일 연장 발표 당일 가자에서 하마스 최고위 지휘관을 타격. 다중 전선에서 외교와 군사 행동을 동시 추진하는 이스라엘의 전략 패턴. 트럼프 20점 가자 계획과의 연계 가능성.

### 스키마 변경 없음
- 금일 발견된 모든 엔티티와 관계는 기존 스키마로 표현 가능
- 신규 개념(Constructive Strategic Stability Framework, Iran victory narrative, Trump 20-point Gaza plan)은 Concept 클래스로 분류

---

## 2026-05-16 추론 결과

### 추론 #1: co_participation (간접 대립)
- **입력:** (ent-385/Shamkhani, opposes, ent-384/20년 모라토리엄), (ent-001/Trump, participatesIn, ent-384/20년 모라토리엄)
- **추론:** (ent-385/Shamkhani, opposes, ent-001/Trump)
- **신뢰도:** 0.81
- **상태:** 확정
- **비고:** 샴카니가 트럼프의 핵 제안을 직접 거부하면서 '올리브 가지=가시철사' 수사를 사용. 이란 최고지도자 측근이 트럼프와 직접 대립하는 구도.

### 추론 #2: event_chain (핵 교착→슬레지해머 인과)
- **입력:** (ent-370/Nuclear deadlock, relatedTo, ent-338/Xi summit), (ent-338/Xi summit, causedBy, ent-380/Sledgehammer threat)
- **추론:** (ent-380/Sledgehammer, causedBy, ent-370/Nuclear deadlock)
- **신뢰도:** 0.76
- **상태:** 확정
- **비고:** 핵 교착 인정(5/15 아라그치) → 정상회담 구체적 성과 부재 → 슬레지해머 위협 격상. 외교 실패가 군사 에스컬레이션으로 전환되는 인과 체인.

### 추론 #3: co_participation (동시 에스컬레이션)
- **입력:** (ent-383/IDF 공습, follows, ent-368/45일 연장), (ent-380/Sledgehammer, follows, ent-379/Epic Fury Over)
- **추론:** (ent-383/IDF 공습, relatedTo, ent-380/Sledgehammer)
- **신뢰도:** 0.72
- **상태:** 확정
- **비고:** 이스라엘과 미국 모두 외교 합의 직후 군사 행동을 격화. 45일 연장과 에픽 퓨리 종료라는 '형식적 평화'가 실제로는 군사 활동의 면허로 기능하는 패턴.

### 추론 #4: event_chain (Ford 귀환→재배치 잠재)
- **입력:** (ent-381/USS Ford, participatesIn, ent-003/US Military), (ent-003/US Military, relatedTo, ent-380/Sledgehammer)
- **추론:** (ent-381/USS Ford, relatedTo, ent-380/Sledgehammer)
- **신뢰도:** 0.70
- **상태:** 잠정
- **비고:** Ford 11개월 배치 후 귀환 → 정비/재충전 기간 후 슬레지해머 작전에 재투입 가능성. 현재는 추론적 연결이나 미 해군 전력 재배치 패턴상 모니터링 대상.

### 스키마 변경 없음
- 금일 발견된 모든 엔티티와 관계는 기존 스키마로 표현 가능
- 신규 개념(Sledgehammer threat escalation, 20-year moratorium proposal)은 Event 클래스로 분류

---

## 2026-05-17 추론 결과

### 추론 #1: co_participation (바라카 드론→이란 연계)
- **입력:** (ent-390/Barakah drone strike, locatedIn, ent-157/UAE), 이란의 기존 UAE 공격 패턴(5/4 푸자이라, 5/5 제벨알리, 5/9 3차 공격)
- **추론:** (ent-390/Barakah drone strike, relatedTo, ent-002/Iran)
- **신뢰도:** 0.75
- **상태:** 잠정
- **비고:** UAE 서쪽 국경에서 드론 진입. 이란은 공격 확인·부인 모두 거부. 기존 4차례 UAE 공격 패턴과 일치하나 원전 표적은 질적 변화. JPost 소스 "메시지 전달 의도."

### 추론 #2: co_participation (사우디+UAE 동시 공격→동일 지휘)
- **입력:** (ent-396/Saudi drone attack, date=2026-05-17), (ent-390/Barakah drone strike, date=2026-05-17)
- **추론:** (ent-396, causedBy, ent-390) — 동일 지휘 체계에서의 동시다발 작전
- **신뢰도:** 0.72
- **상태:** 잠정
- **비고:** 사우디 드론은 이라크 영공에서, UAE 드론은 서쪽 국경에서 진입. 발사 주체 미확인이나 동시 공격 타이밍은 조율된 작전 시사.

### 추론 #3: event_chain (네타냐후-트럼프 통화→슬레지해머 사전 조율)
- **입력:** (ent-001/Trump, cooperatesWith, ent-012/Netanyahu via src-1143), (ent-001/Trump, relatedTo, ent-380/Sledgehammer)
- **추론:** (temp-001/Netanyahu-Trump call, causedBy, ent-380/Sledgehammer) — 전쟁 재개 사전 조율
- **신뢰도:** 0.78
- **상태:** 확정
- **비고:** 5/16 슬레지해머 공식 위협 → 5/17 네타냐후 통화 + 안보각의 소집 + 5/19 군사회의 예고. 7일 연속 에스컬레이션 경로의 최고위 조율 단계.

### 추론 #4: co_participation (호르무즈 수익화→장기전 전략)
- **입력:** (ent-393/Hormuz toll plan, relatedTo, ent-008/Hormuz), (ent-394/Cable fees, relatedTo, ent-008/Hormuz)
- **추론:** (ent-393, relatedTo, ent-394) — 이란의 호르무즈 다중 수익화 전략
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 5/17 하루에 해상 통행료 체계 공식화 + 해저케이블 사용료 위협 동시 발표. 석유·무역·디지털 인프라 전방위 수익화로 장기전 자금 확보 전략.

### 스키마 변경 없음
- 금일 발견된 모든 엔티티와 관계는 기존 스키마로 표현 가능
- Barakah Nuclear Power Plant → Location 클래스
- Hormuz Safe insurance, Submarine cable fees → Concept 클래스
- IAEA, KEPCO → Organization 클래스

---

## 2026-05-19 추론 결과

### 추론 #1: co_participation (걸프 3국 공동 중재)
- **입력:** (ent-399/Tamim, cooperatesWith, ent-001/Trump), (ent-220/MBS, cooperatesWith, ent-001/Trump), (ent-400/MBZ, cooperatesWith, ent-001/Trump)
- **추론:** (ent-399, cooperatesWith, ent-220), (ent-399, cooperatesWith, ent-400), (ent-220, cooperatesWith, ent-400) — 걸프 3국 공동 중재 블록
- **신뢰도:** 0.90
- **상태:** 확정
- **비고:** 카타르·사우디·UAE 3국이 동시에 트럼프에게 공습 보류를 요청한 것은 걸프 3국이 이란 전쟁에서 공동 중재자 블록으로 활동하고 있음을 확인. GCC 제다 정상회의(4/28) 이후 걸프 국가 결속력의 실질적 발현.

### 추론 #2: event_chain (공습 보류 ← 수정안 전달 인과 체인)
- **입력:** (ent-402/Iran Revised Proposal, 2026-05-18), (ent-401/Strike Postponement, 2026-05-18)
- **추론:** (ent-401/Strike Postponement, causedBy, ent-402/Revised Proposal) — 이란 수정안 전달이 걸프 중재의 근거가 되어 공습 보류를 가능하게 함
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 시간 순서상 이란 수정안이 파키스탄 경유로 전달된 직후 걸프 3국이 '진지한 협상 진행 중'을 근거로 보류를 요청. 수정안 내용이 핵심 쟁점을 해결하지 못했음에도 협상 동력이 살아있다는 신호로 기능.

### 추론 #3: co_participation (UAE 이중 역할 — 피해자이자 중재자)
- **입력:** (ent-400/MBZ, cooperatesWith, ent-001/Trump → 공습 보류 요청), (ent-157/UAE, 피해자 → ent-390/Barakah drone attack)
- **추론:** (ent-400, potentialRelation, ent-002/Iran) — UAE가 이란 연계 공격의 피해자이면서도 이란을 위한 중재를 수행
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** UAE가 5/17 바라카 원전 드론 공격을 받고도 5/18 트럼프에게 이란 공습 보류를 요청한 것은 전략적 이중 역할을 보여줌. 이란 직접 비난을 회피하면서 협상 공간을 유지하는 실리적 접근.

### 추론 #4: co_participation (제재 유예 + 공습 보류 = 유가 급반전)
- **입력:** (ent-403/Sanctions Waiver, 2026-05-18 보도), (ent-401/Strike Postponement, 2026-05-18)
- **추론:** (ent-403, relatedTo, ent-401) — 두 사건이 동시에 유가 하락의 이중 촉매로 작용
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 브렌트 $111→$102 일중 $9 급반전은 전쟁 이후 최대 일일 낙폭 중 하나. 제재 유예 보도(공급측 완화 기대)와 공습 보류(지정학적 리스크 완화)가 동시에 작용.

### 스키마 변경 없음
- 금일 발견된 모든 엔티티와 관계는 기존 스키마로 표현 가능
- Sheikh Tamim, MBZ → Person 클래스
- PGSA, USS Alaska → Organization 클래스
- Strike Postponement, Revised Proposal → Event 클래스
- Sanctions Waiver → Concept 클래스
- Gibraltar → Location 클래스

---

## 2026-05-20 추론 결과

### 추론 #1: transitivity (프록시 전이 — KH → IRGC → Iran)
- **입력:** (ent-409/Kata'ib Hezbollah, affiliatedWith, ent-005/IRGC), (ent-005/IRGC, affiliatedWith, ent-002/Iran)
- **추론:** (ent-409/Kata'ib Hezbollah, indirectlyAffiliatedWith, ent-002/Iran)
- **신뢰도:** 0.86 (= 0.95 × 0.90)
- **상태:** 확정
- **비고:** 카타이브 헤즈볼라는 IRGC 쿠드스 포스의 직접 후원을 받는 이라크 기반 민병대. UAE가 바라카 드론의 이라크 발원을 공식 확인함으로써, 이란의 프록시 전쟁 구조가 명확해짐. KH → IRGC → Iran의 지휘 체계는 미국의 KH 지도자 체포(ent-412)가 대이란 프록시 전략 전환을 의미하는 근거.

### 추론 #2: co_participation (캐시디-케인 초당파 전쟁권한 동맹)
- **입력:** (ent-407/Bill Cassidy, participatesIn, ent-408/WPR 7th Vote), (ent-413/Tim Kaine, participatesIn, ent-408/WPR 7th Vote)
- **추론:** (ent-407/Bill Cassidy, potentialRelation, ent-413/Tim Kaine) — 초당파 전쟁권한 동맹
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 공화당 캐시디(예비선거 패배 후 이탈)와 민주당 케인(WPR 주요 발의자)이 동일 투표에 참여하여 50-47 역사적 통과를 만들어냄. 이전 6차 부결 대비 결정적 변화는 캐시디의 이탈로, 공화당 내부에서도 전쟁에 대한 의회 감시 요구가 확산되고 있음을 시사.

### 추론 #3: event_chain (이라크 발원 확인 ← 바라카 드론 공격 인과 체인)
- **입력:** (ent-411/Iraq Origin Confirmation, follows, ent-390/Barakah Drone Strike), (ent-411, locatedIn, ent-410/Iraq)
- **추론:** (ent-411, causedBy, ent-390) — 이라크 발원 확인은 바라카 드론 공격의 직접적 조사 결과
- **신뢰도:** 0.90
- **상태:** 확정
- **비고:** 5/17 바라카 원전 드론 공격 → 5/19 UAE 국방부 공식 발표(이라크 영토 발원 확인 + 48시간 내 6대 추가 요격). 이 인과 체인은 이란 프록시(KH)의 이라크 기반 작전이 걸프국 핵 인프라까지 위협하는 새로운 에스컬레이션 경로를 확립. 바라카 공격의 귀속 문제가 '미확인'에서 '이라크 발원'으로 진전되었으나, 최종 발사 주체(KH vs. 다른 민병대)는 여전히 미확인.

### 추가 관찰: 루비오-왕이 이례적 협력
- **입력:** (ent-077/Rubio, cooperatesWith, ent-280/Wang Yi), (ent-077, opposes, ent-404/PGSA), (ent-280, opposes, ent-404/PGSA)
- **관찰:** 미중 양국이 이란의 호르무즈 통행료 체계(PGSA)에 공동 반대하는 것은 전쟁 82일 만에 최초의 이례적 합의. 이란의 해상 수익화 전략이 미중 모두의 이해에 반하는 것으로 판명됨.
- **신뢰도:** 해당 없음 (관찰, 추론 아님)
- **상태:** 관찰
- **비고:** 5/15 트럼프-시진핑 정상회담의 실질적 후속 조치로 볼 수 있음. 호르무즈 통행의 자유는 미국(군사적 이해)과 중국(에너지 수입 경로)의 공통 관심사로, 이란의 PGSA 설립이 양국을 공동 전선으로 묶는 역설적 효과를 생성.

### 스키마 변경 없음
- 금일 발견된 모든 엔티티와 관계는 기존 스키마로 표현 가능
- Bill Cassidy, Tim Kaine → Person 클래스
- Kata'ib Hezbollah → Organization 클래스
- Senate WPR 7th Vote, Barakah Drones Iraq Origin Confirmation, US Arrest of KH Leader → Event 클래스
- Iraq → Location 클래스

---

## 2026-05-21 추론 결과

### 추론 #1: transitivity (간접 소속)
- **입력:** (ent-417 al Saadi, affiliatedWith, ent-409 KH), (ent-409 KH, affiliatedWith, ent-005 IRGC), (ent-005 IRGC, affiliatedWith, ent-002 Iran)
- **추론:** (ent-417 al Saadi, indirectlyAffiliatedWith, ent-002 Iran)
- **신뢰도:** 0.81 (3단계 체인 감쇠 적용)
- **상태:** 확정
- **의미:** KH 테러 혐의자의 이란 간접 소속 확인 — 프록시 지휘 체인의 법적 귀속 근거

### 추론 #2: co_participation (에너지 위기 연결)
- **입력:** (ent-414 Xi, cooperatesWith, ent-199 Putin, src-1234), Iran war disrupts China energy
- **추론:** (ent-414 Xi, potentialRelation, ent-002 Iran)
- **신뢰도:** 0.75
- **상태:** 확정
- **의미:** 이란 전쟁의 에너지 파급이 중러 정상회담 의제를 지배 — 간접 행위자 연결

### 추론 #3: co_participation (걸프 정보 공유)
- **입력:** (ent-415 Saudi, confirms Iraq drones), (ent-035 UAE, confirms Iraq drones)
- **추론:** (ent-415 Saudi, cooperatesWith, ent-035 UAE)
- **신뢰도:** 0.85
- **상태:** 확정
- **의미:** 사우디-UAE 동시 이라크 발원 확인은 걸프국 간 정보 공유/조율을 시사

---

## 2026-05-22 추론 결과

### 추론 #1: co_participation (하메네이-이스라엘 대립)
- **입력:** (ent-046 Khamenei, opposes, ent-001 Trump, src-1260), Israeli officials told Reuters Trump assured Israel HEU would be sent abroad
- **추론:** (ent-046 Khamenei, opposes, ent-004 Israel)
- **신뢰도:** 0.78
- **상태:** 확정
- **의미:** 하메네이의 HEU 보유 명령은 트럼프뿐 아니라 이스라엘의 HEU 반출 보장 요구도 정면 거부 — 이스라엘은 이란 핵 위협을 가장 직접적으로 받는 국가

### 추론 #2: co_participation (한국-중국 병행 채널)
- **입력:** (ent-420 South Korea, cooperatesWith, ent-002 Iran, src-1266), (ent-010 China, cooperatesWith, ent-002 Iran, prior)
- **추론:** (ent-420 South Korea, potentialRelation, ent-010 China)
- **신뢰도:** 0.72
- **상태:** 확정
- **의미:** 한국과 중국 모두 이란과 개별 호르무즈 통과 협상을 완료 — 이란의 '선별적 허가' 체제가 양자 외교 채널을 통해 확대되는 패턴

### 추론 #3: event_chain (하메네이 명령 → 다운블렌드 경로)
- **입력:** (ent-422 Khamenei HEU Order, src-1260), (ent-425 Domestic Downblend, src-1267)
- **추론:** Khamenei order enables domestic downblend path but opposes Trump's removal demand
- **신뢰도:** 0.70
- **상태:** 잠정
- **의미:** 하메네이 명령은 HEU를 '없애는' 것을 거부한 게 아니라 '반출'을 거부한 것. 국내 다운블렌드는 양립 가능한 타협안이나, 미국이 이를 수용할지는 미지수

---

## 2026-05-23 추론 결과

### 추론 #1: co_participation (카타르-파키스탄 공동 중재 동맹)
- **입력:** (ent-336/Qatar, participatesIn, ent-016/Ceasefire Negotiations), (ent-029/Pakistan, participatesIn, ent-016/Ceasefire Negotiations)
- **추론:** (ent-336/Qatar, potentialRelation, ent-029/Pakistan) — 공동 중재 동맹
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 카타르가 이란의 LNG 인프라 공격 이후 중재에서 후퇴했다가 복귀. 카타르 중재팀이 테헤란에 도착하고 미국과 조율을 확인하면서, 파키스탄(군사/안보 채널)과 카타르(금융/에너지 채널)의 이중 트랙 중재 구조가 형성됨. 카타르의 복귀는 호르무즈 통행의 자유(LNG 수출 경로)라는 자국 이해와 미국과의 전략적 관계가 추동한 것으로 판단.

### 추론 #2: event_chain (하메네이 HEU 명령 → 핵 협상 교착 → 호르무즈 딜 영향)
- **입력:** (ent-422/Khamenei HEU Order, src-1260), (ent-016/Ceasefire Negotiations, 시퀀싱 교착)
- **추론:** (ent-422/Khamenei HEU Order, relatedTo, ent-016/Ceasefire Negotiations)
- **신뢰도:** 0.78
- **상태:** 확정
- **비고:** Bloomberg 분석에 따르면 호르무즈와 핵 농축이 양대 핵심 교착 지점. 하메네이의 HEU 보유 명령이 핵 협상을 교착시키고, 이것이 호르무즈 합의에도 연쇄적으로 영향. 무니르의 테헤란 방문 취소는 이 교착의 직접적 결과(US '핵 먼저' vs 이란 '30일 신뢰구축 먼저').

### 추론 #3: co_participation (무니르-카타르 중재 조율)
- **입력:** (ent-028/Munir, participatesIn, ent-016/Ceasefire Negotiations), (ent-336/Qatar, participatesIn, ent-016/Ceasefire Negotiations)
- **추론:** (ent-028/Munir, relatedTo, ent-336/Qatar) — 중재 채널 간 잠재적 조율
- **신뢰도:** 0.75
- **상태:** 잠정
- **비고:** 무니르의 테헤란 방문 취소(시퀀싱 교착)와 카타르의 테헤란 도착이 시간적으로 겹침. 파키스탄 군사 채널이 교착에 빠진 시점에서 카타르 금융/에너지 채널이 개입한 것은 의도적 역할 분담일 수 있으나, 우연의 일치일 가능성도 존재. 추가 정보 필요.

### 추가 관찰: IRGC 관리 통행 체계 정착 추이
- **입력:** IRGC 호르무즈 통과 선박: 0→8→17→22→26→31→35 (5/16~5/23)
- **관찰:** 7일간 0에서 35척으로 증가. 3일 연속 증가(26→31→35)는 체계가 실험 단계를 넘어 정착 단계에 진입했음을 시사. 국제 해운사들이 IRGC 허가 체계를 사실상 수용하는 양상.
- **신뢰도:** 해당 없음 (관찰, 추론 아님)
- **상태:** 관찰
- **비고:** 미국 봉쇄의 실효성 약화와 이란의 호르무즈 레버리지 유지가 동시에 진행. 이란은 완전 폐쇄 없이도 선택적 통행 허가를 통해 경제적/외교적 레버리지를 유지하는 전략을 구사 중.

### 추가 관찰: 시퀀싱 교착의 구조
- **입력:** US '핵 먼저 마무리' 주장 vs 이란 '30일 신뢰구축 기간 우선' 요구
- **관찰:** 양측의 교착은 내용(핵 처리 방식)이 아닌 순서(시퀀싱)에서 발생. 양측 모두 최종 합의의 대략적 윤곽(핵 모라토리엄 + 호르무즈 개방)에는 접근하고 있으나, 누가 먼저 양보하느냐에서 교착. 이는 신뢰 부족의 표현으로, 카타르나 제3자의 보증 메커니즘이 해결의 열쇠가 될 수 있음.
- **신뢰도:** 해당 없음 (관찰, 추론 아님)
- **상태:** 관찰

### 스키마 변경 없음
- 금일 발견된 모든 엔티티와 관계는 기존 스키마로 표현 가능
- Jared Golden → Person 클래스
- Qatar 중재 복귀 → 기존 Organization 엔티티(ent-336)의 속성 업데이트
- 모든 관계(cooperatesWith, participatesIn, opposes, relatedTo, mentions)는 기존 관계 유형

---

## 2026-05-23 추론 결과 (업데이트 — breaking news 포함)

### 추론 #1: co_participation (카타르-미국 공동 중재)
- **입력:** (ent-336/Qatar, cooperatesWith, ent-029/Pakistan), (ent-029/Pakistan, cooperatesWith, ent-001/Trump via mediation)
- **추론:** (ent-336/Qatar, potentialRelation, ent-001/Trump)
- **신뢰도:** 0.78
- **상태:** 확정
- **비고:** 카타르가 파키스탄과 함께 공동 중재자로 복귀. 트럼프가 9개국 통화에 카타르를 포함시켜 공동 중재 체제를 공식화.

### 추론 #2: event_chain (MoU 진화)
- **입력:** (ent-136/$20B Cash-for-Uranium Framework, relatedTo, nuclear/finance), (ent-428/MoU Framework Peace, relatedTo, ent-429/$25B)
- **추론:** (ent-428/MoU Framework Peace, follows, ent-136/$20B Cash-for-Uranium)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** $20B 현금-우라늄 딜(4/18)이 $25B MoU 프레임워크(5/23)로 확대 진화. 핵 이슈를 분리하고 종전·호르무즈·자산·제재로 범위 확장.

### 추론 #3: event_chain (무니르 면담 → 트럼프 선언)
- **입력:** (ent-028/Munir, cooperatesWith, ent-002/Iran — Tehran meetings), (ent-427/Trump Declaration, date: same day)
- **추론:** (ent-427/Trump Declaration, causedBy, ent-028/Munir Tehran visit)
- **신뢰도:** 0.72
- **상태:** 잠정
- **비고:** 무니르의 테헤란 면담(페제시키안/갈리바프)에서 '고무적 진전' 보고 → 같은 날 트럼프 'largely negotiated' 선언. 인과관계 가능하나 확정 불가.

### 스키마 변경 없음
- 모든 엔티티와 관계는 기존 클래스(Person, Organization, Event, Location, Concept)와 관계 유형으로 표현 가능.

---

## 2026-05-25 추론 결과

### 추론 #1: co_participation — GOP 내부 분열
- **입력:** (ent-432 opposes ent-428), (ent-433 opposes ent-428), (ent-434 opposes ent-428), (ent-001 participatesIn ent-431)
- **추론:** (ent-432/433/434 potentialRelation ent-001) — 같은 당 내에서 트럼프 딜에 대한 반대 형성
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 상원군사위원장 위커가 '재앙'으로 규정한 것이 가장 강력한 신호. 그레이엄/크루즈는 기존 매파 성향 감안 시 예상 가능하나, 위커의 반대는 군사적 대안 선호를 시사. 폼페이오는 전직 관료로서의 비판이나, 2028 대선 잠재 후보로서의 포지셔닝 가능성도 있음.

### 추론 #2: event_chain — MoU 진화
- **입력:** (ent-427 relatedTo ent-428), (ent-431 relatedTo ent-428)
- **추론:** (ent-431 follows ent-427) — 'largely negotiated' 선언 → 60일 MoU 세부 공개
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 5/23 'largely negotiated' 선언에서 48시간 만에 Axios가 60일 구조 세부사항을 입수. 갈리바프/밴스/위트코프/쿠슈너 4자 승인으로 협상 내부자 그룹이 확인됨. 그러나 트럼프 본인은 '서두르지 말라'며 속도 조절 — 최종 서명까지는 추가 시간 필요.

### 추론 #3: co_participation — 이스라엘-GOP 이해관계 수렴
- **입력:** (ent-004 opposes ent-428), (ent-432/433/434 opposes ent-428)
- **추론:** (ent-004 potentialRelation ent-436) — 이란 딜 반대라는 공통 이해관계
- **신뢰도:** 0.72
- **상태:** 확정
- **비고:** IDF가 레바논 작전계획을 별도로 수립한 것은, 이란 딜이 헤즈볼라 전선에 미칠 제약을 우려하기 때문. 이는 GOP 매파의 '재앙' 비판과 같은 맥락 — 딜이 이란에 너무 유리하고 이스라엘의 군사적 자유를 제한한다는 인식. 이스라엘과 GOP 비판 세력 간 직접적 조율 증거는 없으나, 이해관계의 구조적 수렴은 명확.

### 추가 관찰: 딜 내부 구조의 모순
- **입력:** (ent-431 60일 MoU: 핵무기 불추구 약속 + HEU 제거 협상) vs (5/22 하메네이 HEU 보유 명령)
- **관찰:** 최고지도자가 5/22 HEU 보유를 명령했으나, CBS는 5/25 최고지도자가 HEU 폐기 '템플릿'을 승인했다고 보도. 48시간 만의 180도 전환이거나, 서로 다른 내부 소식통의 상충 정보. 두 보도 모두 사실이라면, 하메네이가 '보유 명령'으로 협상 레버리지를 높인 후 '템플릿 승인'으로 실질 양보한 전술적 시퀀싱일 가능성.
- **신뢰도:** 해당 없음 (관찰, 추론 아님)
- **상태:** 관찰

### 추가 관찰: 트럼프의 속도 조절 전환
- **입력:** 5/20 '2-3일 최후통첩' → 5/23 '50/50' → 5/25 '서두르지 말라'
- **관찰:** 5일간 트럼프의 톤이 극적으로 변화. 최후통첩 → 결단 → 속도 조절. 가능한 해석: (1) 딜 세부사항이 복잡하여 추가 시간 필요, (2) GOP 반발에 대한 정치적 거리두기, (3) 봉쇄 유지를 레버리지로 활용하는 의도적 지연. 백악관이 '이번 주말 서명 없다'고 명시한 것은 (1)+(2) 조합을 시사.
- **신뢰도:** 해당 없음 (관찰, 추론 아님)
- **상태:** 관찰

### 스키마 변경 없음
- 금일 발견된 모든 엔티티와 관계는 기존 스키마로 표현 가능
- Roger Wicker, Lindsey Graham, Ted Cruz, Mike Pompeo → Person 클래스
- MoU 60-Day Framework → Event 클래스
- GOP Blowback on Iran Deal → Concept 클래스
- 모든 관계(opposes, participatesIn, cooperatesWith, relatedTo, potentialRelation, follows)는 기존 관계 유형

---

## 2026-05-26 추론 결과

### 추론 #1: co_participation (헤마티-갈리바프 공동 참여)
- **입력:** (ent-437/Hemmati, participatesIn, ent-438/Doha Talks), (ent-045/Ghalibaf, participatesIn, ent-438/Doha Talks)
- **추론:** (ent-437/Hemmati, indirectlyAffiliatedWith, ent-045/Ghalibaf)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 중앙은행 총재가 의회 의장과 함께 도하 대표단을 구성 — 이란 내 경제-정치 결합 협상 구조를 나타냄. 헤마티의 참여는 동결자산 해제가 MoU 서명의 최종 관문임을 시사.

### 추론 #2: co_participation (카타르-이란 잠재적 관계)
- **입력:** (ent-442/Qatar, locatedIn, ent-438/Doha Talks), (ent-002/Iran, participatesIn → ent-438 via delegation)
- **추론:** (ent-442/Qatar, potentialRelation, ent-002/Iran)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 카타르가 $6B 동결자산 보관처이면서 동시에 중재자 역할을 수행 — 이해관계자와 중재자의 이중 역할. 파키스탄(안보 중재)과 카타르(금융 중재)의 역할 분화가 진행 중.

### 추론 #3: co_participation (아브라함 협정-GOP 반발 교차 압력)
- **입력:** (ent-439/Abraham Accords Demand, relatedTo, ent-004/Israel), (ent-436/GOP Blowback, opposes, ent-428/MoU)
- **추론:** (ent-439, potentialRelation, ent-436)
- **신뢰도:** 0.75
- **상태:** 잠정
- **비고:** 트럼프의 정상화 요구는 이스라엘 지지 매파를 달래려는 의도로 보이나, 딜 자체에 반대하는 GOP 비판과 교차. 위커/크루즈는 딜 자체를 반대하므로 정상화 조건 추가가 그들을 설득하기 어려움. 반면 정상화 지지자들은 MoU 전체에는 우호적일 수 있어 교차 압력이 발생.

### 관찰 #1: 협상 지형 이동 (파키스탄→카타르)
- **입력:** 4/11~5/23 파키스탄 중심 중재(이슬라마바드 회담, 파키스탄 경유 제안 전달) → 5/25 이란 대표단 카타르 도하 이동
- **관찰:** 중재 지형이 안보 축(파키스탄/무니르)에서 금융 축(카타르/헤마티)으로 이동. 이는 MoU의 최종 장벽이 군사/핵이 아닌 금융(동결자산·제재 해제)에 있음을 시사. 파키스탄은 여전히 채널을 유지하나 카타르가 동결자산 소재지로서 실질적 협상 파트너로 부상.
- **신뢰도:** 해당 없음 (관찰)
- **상태:** 관찰

### 관찰 #2: 하원 WPR — 6월 초 데드라인
- **입력:** 상원 50-47 통과(5/20) → 하원 3차 투표 취소(5/22) → 6월 메모리얼 데이 후 투표 예정
- **관찰:** MoU가 6월 초까지 서명되지 않으면 하원 WPR 투표가 실시될 가능성 높음. 이는 트럼프에게 시간 압박을 가하며, 역설적으로 이란에게는 협상 레버리지를 제공(미국이 의회 압박으로 조급해질 수 있음). 5/25 '서두르지 말라' 발언과 하원 WPR 데드라인 사이의 긴장.
- **신뢰도:** 해당 없음 (관찰)
- **상태:** 관찰

### 스키마 변경 없음
- 금일 발견된 모든 엔티티와 관계는 기존 스키마로 표현 가능
- Abdolnaser Hemmati → Person 클래스
- Iran Doha Talks, House GOP WPR Vote Cancellation → Event 클래스
- Abraham Accords Normalization Demand, Iran Frozen Assets ($6B Qatar) → Concept 클래스
- Qatar → Organization 클래스
- Hakeem Jeffries → Person 클래스
- 모든 관계는 기존 관계 유형으로 표현 가능

## 2026-05-27 추론 결과

### 추론 #1: event_chain (MQ-9 → CENTCOM)
- **입력:** (ent-446 [MQ-9 Shootdown], follows, ent-445 [US Strikes]), (ent-445, causedBy, ent-005 [IRGC provocations])
- **추론:** (ent-446, relatedTo, ent-059 [CENTCOM])
- **신뢰도:** 0.80
- **상태:** 확정
- **근거:** IRGC의 MQ-9 격추는 CENTCOM 자위권 공습에 대한 직접 대응 — CENTCOM 자산을 표적으로 한 보복 행위

### 추론 #2: co_participation (Shekarchi → IRGC)
- **입력:** (ent-444 [Shekarchi], affiliatedWith, ent-002 [Iran]), IRGC(ent-005) 보복 위협 동시 발생
- **추론:** (ent-444, relatedTo, ent-005 [IRGC])
- **신뢰도:** 0.80
- **상태:** 확정
- **근거:** 군 대변인과 IRGC의 동시 보복 위협은 이란 군사 기관 전체의 통일된 메시지 — 외교부와의 이원화된 신호와 대조

### 추론 #3: event_chain (US Strikes → Doha Talks)
- **입력:** (ent-445 [US Strikes], date, 2026-05-25), (ent-438 [Doha Talks], date, 2026-05-25~26)
- **추론:** (ent-445, relatedTo, ent-438 [Doha Talks])
- **신뢰도:** 0.75 (잠정)
- **상태:** 잠정
- **근거:** 동시 발생은 '에스컬레이트 투 디에스컬레이트' 전략(협상 레버리지)이거나 현장-외교 괴리의 증거 — 인과관계 명확하지 않아 잠정 처리

---

## 2026-05-28 추론 결과

### 추론 #1: event_chain (MoU 초안 → 유가 급락)
- **입력:** (ent-451 [MoU Draft Publication], date, 2026-05-27 ~9AM ET), (ent-450 [Oil Price Crash], date, 2026-05-27)
- **추론:** (ent-450, causedBy, ent-451)
- **신뢰도:** 0.95
- **상태:** 확정
- **근거:** 이란 국영TV의 MoU 초안 공개(호르무즈 30일 복구, 미군 철수, 봉쇄 해제)가 유가 5%+ 급락을 직접 촉발. CNBC/Yahoo Finance가 시간대별 인과관계 보도.

### 추론 #2: co_participation (인터넷 복구 → MoU 초안)
- **입력:** (ent-453 [Internet Restoration], date, 2026-05-26~27), (ent-451 [MoU Draft Publication], date, 2026-05-27)
- **추론:** (ent-453, relatedTo, ent-451)
- **신뢰도:** 0.72 (잠정)
- **상태:** 잠정
- **근거:** 이란의 88일 인터넷 차단 해제와 MoU 초안 공개가 동시 발생 — 전쟁 모드에서 정상화 모드로의 이란 내부 전환 신호일 수 있으나, 직접 인과관계 불확실.

### 추론 #3: event_chain (레바논 에스컬레이션 → 펜타곤 회의)
- **입력:** (ent-452 [Lebanon 31 Killed], date, 2026-05-27), (ent-454 [Pentagon Meeting], date, 2026-05-29)
- **추론:** (ent-452, relatedTo, ent-454)
- **신뢰도:** 0.75
- **상태:** 확정
- **근거:** 이스라엘의 레바논 최대 에스컬레이션(31명 사살, 100+ 공습)이 5/29 펜타곤 군사 조정 회의와 6/2-3 워싱턴 회담 직전에 발생 — 에스컬레이트-투-네고시에이트 패턴. 이스라엘이 회담 전 최대 군사 압박을 가하는 전형적 전술.

### 추론 #4: co_participation (트럼프 → 중간선거 압박)
- **입력:** (ent-001 [Trump], participatesIn, ent-438 [Doha Talks]), (ent-455 [Midterm Pressure], relatedTo, ent-001)
- **추론:** (ent-001, relatedTo, ent-455)
- **신뢰도:** 0.80
- **상태:** 확정
- **근거:** 트럼프가 각료회의에서 명시적으로 중간선거 불영향을 선언한 것은 역설적으로 국내 정치 압박을 인지하고 있음을 시사. CNN 분석도 '좋은 출구가 없을 수 있다'고 평가.

---

## 2026-05-29

**입력:** 2026-05-29.json (16 명시적 + 3 추론 트리플)
**스키마 변경:** 없음

### 추론 #1: event_chain (IRGC 경고사격 → MoU 연관)
- **입력:** (ent-459 [IRGC Warning Shots], locatedIn, ent-008 [Hormuz]), (ent-456 [MoU], relatedTo, ent-008 [Hormuz])
- **추론:** (ent-459, relatedTo, ent-456)
- **신뢰도:** 0.72
- **상태:** 확정
- **근거:** MoU에서 호르무즈 30일 복구 개방을 합의한 시점에 IRGC가 독자적으로 4척에 경고사격을 가함 — 외교부-IRGC 이원화 구도의 전형적 이중 신호. MoU 이행에 대한 IRGC 차원의 견제 가능성.

### 추론 #2: event_chain (리타니 전투 → 펜타곤 회의 연관)
- **입력:** (ent-463 [Litani Clashes], locatedIn, ent-050 [Lebanon]), (ent-460 [Pentagon Meeting], participatesIn ← ent-050)
- **추론:** (ent-463, relatedTo, ent-460)
- **신뢰도:** 0.75
- **상태:** 확정
- **근거:** IDF가 리타니강 이북으로 진출하여 100+ 타격을 가한 것이 5/29 펜타곤 안보 트랙 회의 직전에 발생 — 5/27 31명 사살에 이어 '에스컬레이트-투-네고시에이트' 패턴 지속. 군사적 압박으로 회담 레버리지를 확보하는 이스라엘의 일관된 전략.

### 추론 #3: co_participation (바게리-카니 → 갈리바프 잠재 연관)
- **입력:** (ent-457 [Bagheri-Kani], affiliatedWith, ent-002 [Iran]), (ent-045 [Ghalibaf], affiliatedWith, ent-002 [Iran])
- **추론:** (ent-457, potentialRelation, ent-045)
- **신뢰도:** 0.80
- **상태:** 확정
- **근거:** 바게리-카니(SNSC 부비서)가 MoU를 공개 부인한 것은 갈리바프(의장)의 중재 역할과 긴장 관계를 형성. 두 인물 모두 이란 내부 권력 구조에서 MoU 관련 상반된 입장을 대표 — 바게리-카니는 강경파 라인, 갈리바프는 실용주의 라인으로 추정.

---

## 2026-05-30

**입력:** 2026-05-30.json (22 명시적 + 7 추론 트리플)
**스키마 변경:** 없음

### 추론 #1: concurrent_pressure (IRGC 보복 타격 → 상황실 결정 연관)
- **입력:** (ent-468 [IRGC Retaliatory Strike], causedBy, ent-445 [CENTCOM May 26 Bandar Abbas Strikes]), (ent-467 [Trump Situation Room], relatedTo, ent-008 [Hormuz])
- **추론:** (ent-468, relatedTo, ent-467)
- **신뢰도:** 0.80
- **상태:** 확정
- **근거:** IRGC의 4:50 AM 미 공군기지 보복 타격이 트럼프의 상황실 '최종 결정' 당일에 발생 — 이란은 군사적 압박을 통해 협상 레버리지를 유지하려는 이중 전략을 구사. IRGC '중대 경고' 발언과 '더 결정적 대응' 위협은 협상 결렬 시 에스컬레이션 비용을 명시적으로 제시한 것.

### 추론 #2: escalate_to_negotiate (IDF 리타니강 도하 → 상황실 결정 레버리지)
- **입력:** (ent-470 [IDF Litani Crossing], locatedIn, ent-050 [Lebanon]), (ent-467 [Trump Situation Room], relatedTo, ent-456 [MoU])
- **추론:** (ent-470, relatedTo, ent-467)
- **신뢰도:** 0.75
- **상태:** 확정
- **근거:** 네타냐후의 36사단 리타니강 도하 발표가 트럼프 상황실 회의와 동일 날짜에 이루어짐 — 이스라엘은 군사적 진전을 MoU 협상의 카드로 활용하는 '에스컬레이트-투-네고시에이트' 전략을 일관되게 구사(5/27 31명 사살 → 5/29 펜타곤 회의 → 5/30 도하 발표 → 상황실 결정의 연속 패턴).

### 추론 #3: parallel_tracks (이-레 군사 회담 → 미-이란 외교 병행 연관)
- **입력:** (ent-471 [Pentagon Israeli-Lebanese Talks], follows, ent-460 [Pentagon Security Track]), (ent-467 [Trump Situation Room], relatedTo, ent-456 [MoU])
- **추론:** (ent-471, relatedTo, ent-467)
- **신뢰도:** 0.80
- **상태:** 확정
- **근거:** 5/29 펜타곤 이-레 최초 군사 회담과 트럼프의 상황실 '최종 결정'은 병행 트랙으로 연동 — 레바논 안보 트랙(헤즈볼라 무장해제·IDF 철수·LAF 역할)의 진전이 미-이란 MoU 이행의 전제 조건이며, 두 트랙이 동시에 진전될 때만 포괄적 합의 가능.

### 추론 #4: UNCONFIRMED (알리 아즈마에이 사망 → Bandar Abbas 공습 연관)
- **입력:** (ent-465 [Ali Azmaei], affiliatedWith, ent-005 [IRGC]), (ent-445 [CENTCOM Bandar Abbas Strikes], date, 2026-05-26)
- **추론:** (ent-465, relatedTo, ent-445)
- **신뢰도:** 0.60 (잠정·미확인)
- **상태:** 미확인 — 공식 이란 발표 없음
- **근거:** IRGC 해군사령관의 사망 가능성은 이란 강경파 군사 리더십에 직접적 타격. 만약 확인될 경우, IRGC의 보복 타격 강도 및 이후 협상 태도에 영향. 현재 이란 국영매체 침묵 — 확인 대기.

### 주요 패턴 분석 (Day 92 종합)
- **3중 압박 수렴:** IRGC 보복 타격(군사) + 리타니강 도하(지상) + 상황실 결정(외교)이 동일 날짜에 수렴 — 5/30은 협상 결정의 임계점(critical junction)으로 기능
- **유가 신호:** 5월 -19% 월간 최대 하락은 시장이 MoU 합의를 70% 이상 확률로 가격 반영 중임을 시사. 외교 실패 시 급반전 리스크 큼
- **IRGC 이원화:** 외교부 MoU 합의 vs. IRGC 보복 타격의 동시 발생 — 이란 내부 강온파 이원화 구도가 5/29(바게리-카니 부인)에 이어 5/30에도 지속

---

## 2026-05-31 추론 결과 (Day 93)

### 추론 #1: mirrored_non_approval (거울상 비승인 → 구조적 교착)
- **입력:** (ent-472 [Trump Situation Room No-Decision], relatedTo, ent-456 [MoU]), (ent-475 [Khamenei 8/10 Breach Claim], relatedTo, ent-046 [Khamenei])
- **추론:** (ent-472, causedBy, ent-475)
- **신뢰도:** 0.75
- **상태:** 확정
- **근거:** CNN 'mirrored positions' 분석 — 트럼프와 하메네이 양쪽 모두 협상팀이 MoU에 합의했으나 최고지도자가 승인하지 않은 동일 구조. JPost 보도에 따르면 "하메네이 비승인이 트럼프도 결정하지 않은 이유"라는 직접적 인과관계 시사. 양측이 서로의 승인을 기다리는 '치킨게임' 상태.

### 추론 #2: diplomatic_stall_to_military (외교 교착 → 군사 대안 시그널)
- **입력:** (ent-472 [Trump No-Decision], date, 2026-05-30), (ent-473 [Hegseth Shangri-La], date, 2026-05-31)
- **추론:** (ent-473, follows, ent-472)
- **신뢰도:** 0.80
- **상태:** 확정
- **근거:** 트럼프가 금요일 결정을 보류한 다음 날 토요일, 헤그세스가 싱가포르 샹그릴라 대화에서 군사 재개 준비 완료를 공개 경고. "they can deal with the US military"는 외교 실패 시 군사 옵션이 즉시 활성화된다는 의도적 메시지. 2-step 시퀀스: 대통령 보류 → 국방장관 경고.

### 추론 #3: domestic_opposition_coalition (이란 내부 MoU 반대 연합 형성)
- **입력:** (ent-474 [Fars MoU Rebuttal], opposes, ent-001), (ent-475 [Khamenei Breach Claim], relatedTo, ent-046)
- **추론:** (ent-474, relatedTo, ent-475)
- **신뢰도:** 0.80
- **상태:** 확정
- **근거:** Fars(IRGC 계열)의 '진실과 거짓의 혼합' 반박과 카날리자데(국영TV 내부자)의 '8/10 조건 위반' 주장이 동시에 등장 — 이란 보수/강경 진영의 조직적 MoU 반대 캠페인. 아부토라비 의원의 '롤리팝' 발언까지 합류하여 3중 반대 전선 형성.

### 추론 #4: economic_leverage ($1B 암호화폐 압류 → MoU 협상 레버리지)
- **입력:** (ent-478 [US $1B Crypto Seizure], opposes, ent-002 [Iran]), (ent-456 [MoU], date, ongoing)
- **추론:** (ent-478, relatedTo, ent-456)
- **신뢰도:** 0.75
- **상태:** 확정
- **근거:** 베센트의 $1B 압류 공개는 MoU 협상과 동시 진행되는 경제 압박. 이란이 월 $400-500M 제재 회피 중이라는 수치를 공개함으로써 이란의 재정적 취약성을 노출하고 협상 양보 압력을 높이는 의도. MoU에서 이란이 $12B 동결자산 즉시 지급을 요구하는 맥락과 대조.

### 추론 #5: implementation_obstacle (호르무즈 기뢰 → MoU 이행 장애)
- **입력:** (ent-479 [Oman Mine Alert], locatedIn, ent-008 [Hormuz]), (ent-456 [MoU], contains, "30일 기뢰 제거")
- **추론:** (ent-479, relatedTo, ent-456)
- **신뢰도:** 0.70
- **상태:** 확정
- **근거:** MoU에 이란의 30일 이내 기뢰 제거 조건이 포함되어 있는 상황에서 오만 영해에서 부유기뢰 의심 물체가 발견됨 — 합의 이행의 물리적 난제를 시사. 기뢰의 출처와 범위가 불명확하여, 30일 이내 완전 제거가 기술적으로 가능한지 의문.

### 추론 #6: lebanon_leverage (레바논 '환상의 휴전' → 이란 MoU 레버리지)
- **입력:** (ent-480 [Lebanon Ceasefire Statistics], locatedIn, ent-050 [Lebanon]), (ent-456 [MoU], contains, "레바논 포함 요구")
- **추론:** (ent-480, relatedTo, ent-456)
- **신뢰도:** 0.70
- **상태:** 확정
- **근거:** IDF 1,600회·헤즈볼라 500회 공격 통계는 '휴전'이 명목상이라는 것을 수치적으로 증명. 이란이 MoU에 레바논 포함을 요구하는 근거로 활용 가능 — 실질적 휴전 없는 합의는 이란에게 비대칭적으로 불리.

### 주요 패턴 분석 (Day 93 종합)
- **거울상 교착 (Mirrored Deadlock):** 트럼프와 하메네이 양쪽 모두 협상팀의 합의를 승인하지 않은 동일 구조 → 어느 한쪽이 먼저 움직이지 않는 한 교착 지속. 이는 Day 92의 '3중 압박 수렴'에서 한 단계 진전된 구조적 분석.
- **2단계 시퀀스:** 대통령 결정 보류(5/30) → 국방장관 군사 경고(5/31)는 의도적 good cop/bad cop 전략일 수 있으나, 외교 실패 시 군사 대안이 즉시 활성화된다는 실질적 위협.
- **3대 해석 차이:** 통행료(Fars 부정), 핵 폐기(MoU에 미포함 주장), 동결자산 $12B(이란 측 핵심) — MoU 텍스트에 대한 양측의 공개적 해석 차이가 최초로 구체적으로 드러남.

---

## 2026-06-01 추론 결과

### 추론 #1: event_chain (상황실 보류 → 의도적 지연)
- **입력:** (ent-472 [상황실 보류], relatedTo, ent-456 [MoU]), (ent-482 [Trump 'not in a hurry'], relatedTo, ent-456)
- **추론:** (ent-482, follows, ent-472)
- **신뢰도:** 0.75
- **상태:** 확정
- **근거:** Trump의 'not in a hurry' 발언(5/31 Fox 인터뷰)은 전날 상황실 결정 보류(5/30)를 사후적으로 '의도적 전략'으로 프레이밍. 보류(indecision) → 지연(deliberate delay)으로 내러티브 전환. "If you're going to be in a hurry, you're not going to make a good deal."

### 추론 #2: military_diplomatic_leverage (Beaufort ↔ Round 4 회담)
- **입력:** (ent-483 [Beaufort 점령], locatedIn, ent-050 [Lebanon]), (ent-484 [Round 4], follows, ent-483)
- **추론:** (ent-483, opposes, ent-484)
- **신뢰도:** 0.70
- **상태:** 확정
- **근거:** 이스라엘이 6/2-3 워싱턴 회담 하루 전에 보포르 성 점령·자하라니강 대피 명령으로 최대 군사 확장을 시현. 회담장에서 '현 상태(status quo)'를 기정사실화하려는 레버리지 패턴 — 이전에도 4/14 1차 회담 전 레바논 대규모 공습, 4/23 2차 회담 전 휴전 위반 등 동일 패턴 반복.

### 추론 #3: mirrored_delay (양측 시간 무기화)
- **입력:** (ent-482 [Trump 'not in a hurry']), (ent-485 [Khamenei 비응답])
- **추론:** (ent-001 [Trump], relatedTo, ent-046 [Khamenei]) — 거울상 지연 경쟁
- **신뢰도:** 0.80
- **상태:** 확정
- **근거:** JPost가 Khamenei의 MoU+최신 제안 양쪽 모두 무응답을 확인(5/31)한 같은 날, Trump는 'not in a hurry'를 선언. 양측이 동시에 시간을 무기로 사용하는 '의도적 지연 경쟁' 구조. Day 93의 '거울상 비승인'에서 한 단계 진화: 비승인(passive) → 의도적 지연(active).

### 추론 #4: good_cop_bad_cop_reinforcement (헤그세스 경고 + 트럼프 '다른 방법')
- **입력:** (ent-473 [Hegseth 샹그릴라], follows, ent-472), (ent-482 [Trump '다른 방법'], follows, ent-472)
- **추론:** (ent-473, relatedTo, ent-482)
- **신뢰도:** 0.75
- **상태:** 확정
- **근거:** 헤그세스의 '우리가 해협을 통제한다'(5/31 싱가포르)와 트럼프의 '다른 방법으로 끝내겠다'(5/31 Fox) 동일 날짜 동시 발언 — 국방장관(military) + 대통령(political) 이중 위협의 의도적 동기화.

### 추론 #5: lebanon_mou_linkage (이스라엘 확대 → MoU 레버리지)
- **입력:** (ent-483 [Beaufort 점령], locatedIn, ent-050 [Lebanon]), (ent-456 [MoU], contains, "레바논 포함 쟁점")
- **추론:** (ent-483, relatedTo, ent-456)
- **신뢰도:** 0.70
- **상태:** 확정
- **근거:** 이스라엘의 레바논 1/5 점령 확대는 이란에게 '레바논 없는 MoU 거부' 근거를 강화. 어제 보고된 '환상의 휴전'(1,600/500 통계)에 이어 영토적 기정사실 추가. 이란이 MoU에 레바논 조항 포함을 요구하는 레버리지 증가.

### 주요 패턴 분석 (Day 94 종합)
- **의도적 지연 경쟁 (Deliberate Delay Contest):** Day 93의 '거울상 비승인'이 Day 94에는 양측의 '적극적 지연'으로 진화. Trump는 'not in a hurry'로 지연을 전략으로 프레이밍하고, Khamenei는 MoU+최신 제안 모두에 무응답으로 시간을 무기화. 누가 먼저 조급해지는지가 교착 해소의 열쇠.
- **군사-외교 레버리지 패턴:** 이스라엘의 보포르 성 점령(5/31) → 워싱턴 4차 회담(6/2-3) 시퀀스는 이전 라운드에서 반복된 '회담 전 군사 확대' 패턴의 강화. 2,000km² 점령·자하라니강 대피는 이전 어느 라운드보다 강력한 기정사실.
- **경제 구조 변형:** Lockheed $1B+ 계약과 가스 $4.56(+51%)는 전쟁이 단기 충격을 넘어 경제 구조를 변형하고 있음을 시사. 군산복합체 수혜 ↔ 소비자 부담의 이중 구조.

---

## 2026-06-03 추론 결과

### 추론 #1: co_participation (루비오 + Needham + Holler → 외교 라인 공동 활동)
- **입력:** (ent-077/Rubio, participatesIn, ent-499/Senate Nuclear Testimony), (ent-501/Round 4, follows, ent-484/Round 4 Preview)
- **추론:** (ent-077/Rubio, potentialRelation, ent-501/Round 4)
- **신뢰도:** 0.75
- **상태:** 확정
- **근거:** 루비오의 상원 핵 증언(ent-499)이 Round 4 회담(ent-501)과 동일 시간대에 진행. 상원에서 '심각하고 장기적인' 핵 제한을 요구하면서, 동시에 State Dept에서 이스라엘-레바논 정치 트랙이 진행 — 핵 압박과 레바논 외교의 이중 운용. Needham/Holler가 미국 측 수석으로 활동.

### 추론 #2: event_chain (이스라엘 레바논 공세 → 이란 협상 중단 → 트럼프 네타냐후 통화 → 레바논 휴전)
- **입력:** (ent-004/Israel, opposes, ent-050/Lebanon), (ent-492/Iran Suspends, causedBy, ent-004/Israel), (ent-494/Trump-Netanyahu Call, causedBy, ent-004/Israel), (ent-495/Lebanon Ceasefire, follows, ent-494)
- **추론:** (ent-492, follows, ent-494) — 인과 체인
- **신뢰도:** 0.80
- **상태:** 확정
- **근거:** Day 94의 이스라엘 보포르 점령(ent-483) → 이란이 협상 중단(ent-492, 6/1 Tasnim) → 트럼프가 네타냐후에 'You're f**king crazy' 통화(ent-494, 6/2) → 레바논 휴전 발표(ent-495, 6/2). 이스라엘의 군사 확대가 이란의 외교 후퇴를 촉발하고, 이것이 트럼프의 이스라엘 억제로 이어진 4단계 인과 체인. 트럼프는 이란 딜을 위해 이스라엘을 제어해야 하는 역학이 최초로 공개적으로 노출.

### 추론 #3: transitivity (갈리바프-베리 보복 위협 + 이란 협상 중단 → 이란 조율된 에스컬레이션)
- **입력:** (ent-045/Ghalibaf, participatesIn, ent-502/Retaliation Threat), (ent-044/Araghchi, participatesIn, ent-492/Iran Suspends)
- **추론:** (ent-502, relatedTo, ent-492) — 조율된 에스컬레이션 압박
- **신뢰도:** 0.80
- **상태:** 확정
- **근거:** 갈리바프(의회의장)의 베리와의 조율된 보복 위협(ent-502)이 아라그치(외무장관)의 협상 중단(ent-492)과 동일 시간대에 발생. '5월 말 이후 가장 명시적인 에스컬레이션 시그널링'이라는 평가와 일치. 정치(갈리바프)·외교(아라그치)·군사(IRGC BM 공격 ent-496) 3개 축이 동기화 — Day 93-94의 '의도적 지연'에서 '적극적 에스컬레이션'으로 이란 전략 전환 가능성.

### 추론 #4: concurrent_pressure (IRGC 걸프 BM 공격 ↔ 이란 협상 중단 동기화)
- **입력:** (ent-005/IRGC, participatesIn, ent-496/Missiles at Kuwait/Bahrain), (ent-492/Iran Suspends, opposes, ent-456/MoU)
- **추론:** (ent-496, relatedTo, ent-492) — 군사·외교 동기화
- **신뢰도:** 0.75
- **상태:** 확정
- **근거:** IRGC 쿠웨이트/바레인 BM 공격(ent-496)이 이란 협상 중단(ent-492) 같은 날 발생. 전쟁 이후 최초의 걸프 국가 기지 직접 타격으로, 미국의 중동 안보 공약을 시험. 외교 중단(아라그치) + 군사 에스컬레이션(IRGC) + 정치 위협(갈리바프) 3축 동기화 패턴의 군사 축.

### 추론 #5: escalation_ladder (Bab el-Mandeb 위협 → 호르무즈 확장)
- **입력:** (ent-500/Bab el-Mandeb, relatedTo, ent-008/Hormuz), (ent-496/IRGC Missiles, relatedTo, ent-005/IRGC)
- **추론:** (ent-500, relatedTo, ent-496) — 에스컬레이션 사다리
- **신뢰도:** 0.72
- **상태:** 확정
- **근거:** 이란의 Bab el-Mandeb 폐쇄 위협(ent-500)은 호르무즈(ent-008) 봉쇄를 넘어 홍해·수에즈까지 해양 압박을 확대하려는 전략. 글로벌 컨테이너 30%, 석유/가스 25%가 통과하는 해협으로, 호르무즈 + Bab el-Mandeb '이중 해협 봉쇄'는 세계 경제에 대한 이란의 최대 레버리지. IRGC BM 공격(ent-496)이 이 위협의 물리적 시연.

### 주요 패턴 분석 (Day 95-96 종합)
- **3축 동기화 에스컬레이션 (Triaxial Synchronized Escalation):** Day 94의 '의도적 지연'에서 Day 95-96에는 이란이 외교(협상 중단) + 정치(갈리바프-베리 위협) + 군사(IRGC 걸프 BM) 3축을 동기화하여 적극적 에스컬레이션으로 전환. 이전의 수동적 비승인(Day 93)·의도적 지연(Day 94)과 질적으로 다른 공세적 자세.
- **트럼프 딜레마 노출 (Trump Dilemma Exposed):** 이스라엘 레바논 확대(이란 딜 방해) vs 이란 딜 추진(이스라엘 억제 필요) 사이의 모순이 'You're f**king crazy' 통화로 최초 공개. 트럼프가 이란 딜과 이스라엘 지지를 동시에 추구할 수 없는 구조적 제약 확인.
- **인과 체인 실증:** 이스라엘 보포르 → 이란 중단 → 트럼프-네타냐후 → 레바논 휴전의 4단계 체인이 48시간 내 실현. 레바논 전선이 이란 핵 협상의 가장 직접적인 변수로 확인.
- **이중 해협 위협 (Dual Strait Threat):** 호르무즈에서 Bab el-Mandeb로 해양 압박 확장 시사 — 이란이 에스컬레이션 사다리의 다음 단계를 예고. 실현 시 글로벌 공급망에 대한 충격은 호르무즈 단독보다 기하급수적.

---

## 2026-06-04 추론 결과

### 추론 #1: escalation_ladder (쿠웨이트 공항 공격 → 걸프 에스컬레이션 사다리)
- **입력:** (ent-496/IRGC BM Kuwait/Bahrain, date=2026-06-01~02), (ent-505/Kuwait Airport Drone Attack, date=2026-06-03), (ent-492/Iran Talk Suspension, date=2026-06-01)
- **추론:** (ent-505, relatedTo, ent-492) — 에스컬레이션 사다리
- **신뢰도:** 0.80
- **상태:** 확정
- **근거:** 쿠웨이트 공항 드론 공격(ent-505)은 6/1-2 IRGC 쿠웨이트/바레인 BM(ent-496)에서 군사 기지→민간 인프라로 에스컬레이션한 것. 이란 협상 중단(ent-492)과 동시기에 발생하여 군사 에스컬레이션과 외교 후퇴의 동기화 패턴 지속. 전쟁 이후 최초의 중립국 민간 시설 타격은 전쟁의 성격을 질적으로 변화시키는 전환점. IRGC가 부인하면서도 CENTCOM이 '의도적·계획적·부당'이라 규정한 것은 귀속 논쟁이 국제법적 의미를 가짐.

### 추론 #2: event_chain (파일럿 존 합의 → MoU 연계)
- **입력:** (ent-506/Pilot Zones Agreement, follows, ent-495/Lebanon Ceasefire), (ent-456/MoU, contains, "레바논 포함")
- **추론:** (ent-506, relatedTo, ent-456) — 이벤트 체인
- **신뢰도:** 0.75
- **상태:** 확정
- **근거:** 이스라엘-레바논 파일럿 존 합의(ent-506)는 MoU(ent-456)와 구조적으로 연계. 이란이 레바논 전선을 MoU 조건으로 요구한 상황에서, 파일럿 존은 레바논 안정화의 첫 구체적 메커니즘. 6/22 차기 회담까지의 타임라인이 MoU 60일 프레임워크의 핵 협상 단계와 중첩 가능. 파일럿 존 성공 시 이란의 '레바논 카드' 약화.

### 추론 #3: structural_opposition (파일럿 존 ↔ 헤즈볼라 구조적 대립)
- **입력:** (ent-507/Pilot Zones, locatedIn, ent-050/Lebanon), (ent-047/Hezbollah, locatedIn, ent-050/Lebanon)
- **추론:** (ent-507, opposes, ent-047) — 구조적 대립
- **신뢰도:** 0.85
- **상태:** 확정
- **근거:** 파일럿 존(ent-507)은 LAF 독점 통제 + 비국가 행위자 배제 = 헤즈볼라(ent-047) 리타니 이남 존재의 부정. 이는 단순한 휴전 메커니즘이 아닌 헤즈볼라의 남부 레바논 군사 거점을 구조적으로 해체하는 프레임워크. 헤즈볼라 입장에서 '존재론적 위협'이며, 이란의 '저항 축' 전략에 대한 직접적 도전. 합의문에 '모든 비국가 행위자 배제'라는 표현은 헤즈볼라를 명시하지 않으면서도 사실상 헤즈볼라만을 겨냥.

### 추론 #4: message_war (트럼프 vs 아라그치 메시지 전쟁 진화)
- **입력:** (ent-001/Trump, 'this weekend' 발언), (ent-044/Araghchi, 'no progress' 발언)
- **추론:** (ent-001, opposes, ent-044) — 메시지 전쟁
- **신뢰도:** 0.72
- **상태:** 확정
- **근거:** Day 95-96의 'rapid pace vs 중단'에서 Day 96-97의 'this weekend vs no progress'로 메시지 전쟁 진화. 주목할 점: 아라그치의 톤 변화. 6/1 '협상 중단'에서 6/3 '소통은 차단되지 않았다' + '최종 공식(final formula) 작업 중'으로 미묘하게 후퇴. 이는 완전한 교착이 아닌 비공식 채널의 지속을 시사. 트럼프의 '이번 주말' 시한은 이전의 불특정 낙관('rapid pace')보다 구체적이어서, 실제 비공식 신호에 기반했을 가능성.

### 주요 패턴 분석 (Day 96-97 종합)
- **3중 전환점 (Triple Inflection Point):** 군사(쿠웨이트 민간 인프라), 정치(하원 WPR 최초 통과), 외교(파일럿 존) 3개 축에서 동시에 전환점 발생. 각각은 전쟁의 상이한 측면을 변화시킨다: (1) 민간 인프라 타격은 걸프 국가들의 전쟁 비용을 직접적으로 증가, (2) WPR은 미국 내 전쟁 피로의 제도적 표현, (3) 파일럿 존은 레바논 전선의 첫 구조적 해법.
- **메시지 전쟁 진화:** Day 95-96 'rapid pace vs 중단'에서 Day 96-97 'this weekend vs no progress + final formula'로 진화. 아라그치의 '최종 공식' 표현은 '중단'이 아닌 '교착 속 비공식 소통'임을 시사. 양측 모두 완전한 결렬을 피하면서 협상 지위를 극대화하는 포지셔닝.
- **걸프 에스컬레이션 질적 변화:** BM→드론→민간 공항으로 표적이 군사→민간으로 이동. 이는 IRGC의 전략이 '군사적 보복'에서 '심리적 압박/공포 효과'로 전환했을 가능성. 국제법적 함의가 크며, 걸프 국가들의 미국 주둔 비용-이익 계산을 변경.

---

## 2026-06-05 추론 결과

### 추론 #1: co_participation (파일럿 존 양측 거부 연동)
- **입력:** (ent-509/Hezbollah Rejects, follows, ent-506/Pilot Zones Agreement), (ent-510/Israel Continues Strikes, follows, ent-506)
- **추론:** (ent-509/Hezbollah Rejects, relatedTo, ent-510/Israel Continues Strikes)
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 헤즈볼라 거부와 이스라엘 작전 지속은 파일럿 존 합의에 대한 양측의 동시적 거부. 합의 수시간 내 양측 모두 사실상 이행을 거부함으로써 합의가 '도착 즉시 사망(DOA)' 상태. 이는 4/16 이-레 10일 휴전(ent-109) → 위반(ent-120) → 로켓(ent-161) 패턴의 반복으로, 레바논 전선의 합의-위반 순환이 구조적임을 재확인.

### 추론 #2: event_chain (쿠웨이트 외교 에스컬레이션 인과 체인)
- **입력:** (ent-505/Kuwait Airport Attack, date=2026-06-03) → (ent-511/Kuwait Expels Diplomats, date=2026-06-04)
- **추론:** (ent-511/Kuwait Expels Diplomats, relatedTo, ent-037/Kuwait)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 공항 공격 → 외교관 추방의 명확한 인과 체인. 전쟁 이후 최초의 걸프국-이란 직접 외교 조치. 단교가 아닌 축소(2명 추방)로 완전 단절은 회피하면서도 공개적 항의를 제도화.

### 추론 #3: co_participation (IRGC 가니-헤즈볼라 거부 저항 축 조율)
- **입력:** (ent-512/Ghaani, affiliatedWith, ent-005/IRGC), (ent-509/Hezbollah Rejects, participatesIn, ent-073/Qassem)
- **추론:** (ent-512/Ghaani, relatedTo, ent-509/Hezbollah Rejects)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** IRGC 쿠드스군 사령관 가니의 '이스라엘 철수 최소조건' 발언과 헤즈볼라 카셈의 파일럿 존 거부는 이란 '저항 축' 전략의 양면. IRGC가 레바논 전선을 이란 핵 협상의 레버리지로 공식 활용하는 구조를 보여줌. 쿠드스군은 역사적으로 헤즈볼라의 직접 지원 기관.

### 추론 #4: co_participation (IAEA 보고서-농축 우라늄 쟁점 연계)
- **입력:** (ent-513/IAEA Report, mentions, ent-025/Nuclear Program), (ent-064/Enriched Uranium, relatedTo, ent-025)
- **추론:** (ent-513/IAEA Report, relatedTo, ent-064/Enriched Uranium)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** IAEA 보고서의 '핵 프로그램 변동 없음'은 농축 우라늄 440.9kg(60% U-235)이 전쟁 중에도 유지됨을 시사. 1년간 사찰 접근 불가는 MoU 60일 프레임워크의 핵 단계(30-60일 차)에서 검증 메커니즘의 근본적 어려움을 예고. '최대 긴급성' 경고는 시간이 지남에 따라 검증 가능성이 감소한다는 IAEA의 우려.

### 추론 #5: event_chain (파일럿 존 거부 패턴 반복)
- **입력:** (ent-074/Hezbollah Rejects Washington Talks, date=2026-04-13), (ent-506/Pilot Zones Agreement, date=2026-06-03), (ent-509/Hezbollah Rejects Pilot Zones, date=2026-06-04)
- **추론:** (ent-506/Pilot Zones Agreement, relatedTo, ent-074/Hezbollah Rejects Talks)
- **신뢰도:** 0.78
- **상태:** 확정
- **비고:** 헤즈볼라의 워싱턴 회담 거부(4/13)와 파일럿 존 거부(6/4)는 53일 간격의 동일 패턴. 카셈과 사파의 '적과 협상하지 않는다'는 입장이 3개월간 일관되게 유지됨. 이는 헤즈볼라의 구조적 협상 거부가 전술적이 아닌 전략적 결정임을 시사. 레바논 전선의 합의는 헤즈볼라 참여 없이는 이행 불가능하며, 헤즈볼라는 이란의 핵 협상 레버리지로서 지속적 저항을 유지하려는 전략.

### 스키마 변경 없음
- 7개 새 엔티티 모두 기존 클래스(Person, Event)로 분류 가능
- 19개 새 관계(명시적) + 5개 추론 모두 기존 관계 유형(participatesIn, affiliatedWith, opposes, follows, relatedTo, mentions, locatedIn)으로 표현 가능

---

## 2026-06-06 추론 결과

### 추론 #1: event_chain (CENTCOM-IRGC 교전 → MoU 환경 악화)
- **입력:** (ent-517/CENTCOM Goruk-Qeshm Strikes, locatedIn, ent-008/Hormuz), (ent-456/MoU 60-Day Framework, relatedTo, ent-008)
- **추론:** (ent-517/CENTCOM Goruk-Qeshm Strikes, relatedTo, ent-456/MoU 60-Day Framework)
- **신뢰도:** 0.78
- **상태:** 확정
- **비고:** MoU 협상이 진행되는 와중에 CENTCOM이 4 IRGC 드론을 격추하고 이란 내 레이더 시설을 공습한 것은, 6/1 케심섬 공습, 6/3 쿠웨이트 미사일 공격에 이은 연속적 군사 에스컬레이션. '자위권 공습' 프레임은 양측 모두 유지하나, 반복적 교전은 MoU 타결 환경을 구조적으로 악화. 이란 최고지도자 고문의 'ball is in Trump's court' 발언과의 대조가 뚜렷 — 외교적 톤과 군사적 현실의 괴리.

### 추론 #2: event_chain (헤즈볼라 거부 → 렘버그 전사)
- **입력:** (ent-509/Hezbollah Rejects Pilot Zones, date=2026-06-04), (ent-519/Lemberg Death, date=2026-06-05)
- **추론:** (ent-519/Lemberg Death, causedBy, ent-509/Hezbollah Rejects Pilot Zones)
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 헤즈볼라의 파일럿 존 거부(6/4) 후 24시간 이내에 대전차 미사일로 IDF 장교를 사살한 것은 거부의 군사적 실행. 렘버그 대위는 파일럿 존 합의 이후 첫 IDF 전사자이며 29번째 남부 레바논 전사자. 합의가 무의미해졌음을 상징적으로 보여주는 사건.

### 추론 #3: co_participation (UNIFIL 사망 ↔ IDF 사망 동시기 전투 격화)
- **입력:** (ent-523/UNIFIL Jovanović Killed, date=Jun 3-4), (ent-519/Lemberg Death, date=Jun 5)
- **추론:** (ent-523, relatedTo, ent-519)
- **신뢰도:** 0.75
- **상태:** 확정
- **비고:** 48시간 내에 UNIFIL 평화유지군(세르비아)과 IDF 장교가 동시에 사망한 것은 남부 레바논의 전투가 모든 당사자에게 치명적 수준으로 격화되었음을 보여줌. UNIFIL은 7번째 사망자(3월 이후), IDF는 29번째. 파일럿 존 합의의 인적 비용이 합의 발표 48시간 만에 현실화.

### 추론 #4: event_chain (OFAC 제재 ↔ MoU 최대 압박 병행)
- **입력:** (ent-524/OFAC LPG Sanctions, date=Jun 5-6), (ent-456/MoU 60-Day Framework)
- **추론:** (ent-524, follows, ent-456)
- **신뢰도:** 0.72
- **상태:** 확정
- **비고:** MoU 협상이 교착된 상태에서 OFAC가 이란 LPG 밀수 네트워크를 제재한 것은 외교와 제재의 동시 추진(Economic Fury + MoU). UAE와 중국 프론트 기업 지정은 이란의 제재 회피 네트워크가 걸프-동아시아 축을 따라 운영됨을 공식 확인. 트럼프의 '미중 핵 협력' 시사와 동시에 중국 기업 제재라는 이중 신호는 대중국 레버리지 활용의 새로운 차원.

### 추론 #5: co_participation (트럼프-중국 핵 협력 가능성)
- **입력:** (ent-001/Trump, cooperatesWith, ent-010/China via src-1600), (ent-524/OFAC Sanctions, relatedTo, ent-010 via src-1599)
- **추론:** (ent-001/Trump, potentialRelation, ent-010/China)
- **신뢰도:** 0.70
- **상태:** 잠정
- **비고:** 트럼프의 '미국과 중국만 농축 우라늄 회수 가능' 발언은 핵 쟁점에서의 미중 협력 가능성을 시사. 그러나 동일 시기 OFAC의 중국 상하이 첸예 에너지 제재는 모순적 신호. 제재 대상이면서 핵 파트너라는 이중적 위치는 트럼프의 거래적(transactional) 외교의 특징. 신뢰도가 기준치(0.7) 경계에 있어 '잠정' 분류.

### 스키마 변경 없음
- 9개 새 엔티티 모두 기존 클래스(Person 2, Organization 1, Event 4, Location 2)로 분류 가능
- 19개 새 관계(명시적) + 5개 추론 모두 기존 관계 유형으로 표현 가능

---

## 2026-06-07 추론 결과

### 추론 #1: event_chain — IRGC BM 공격 → MoU 환경 악화
- **입력:** (ent-526 IRGC BM 공격, causedBy, ent-517 Goruk-Qeshm 공습), (ent-517, relatedTo, ent-456 MoU)
- **추론:** (ent-526, relatedTo, ent-456) — 7일간 4회 교전으로 MoU 협상 환경 추가 악화
- **신뢰도:** 0.80
- **상태:** 확정

### 추론 #2: co_participation — 동결자산 전쟁 ↔ MoU 교착
- **입력:** (ent-530 베센트 자산전용, opposes, ent-529 레자에이 $24B), (ent-529, relatedTo, ent-456 MoU)
- **추론:** (ent-530, relatedTo, ent-456) — 동일 자산을 두고 정반대 정책은 MoU 핵심 쟁점
- **신뢰도:** 0.78
- **상태:** 확정

### 추론 #3: event_chain — 150 공습 → 방어 전환 → 파일럿 존
- **입력:** (ent-534 방어전환, follows, ent-533 150곳 공습), (ent-506 Pilot Zones, relatedTo, ent-534)
- **추론:** (ent-534, relatedTo, ent-506) — 최대 화력 투사 후 방어 전환은 6/22 회담 전 de-escalation 시도
- **신뢰도:** 0.82
- **상태:** 확정

### 추론 #4: event_chain — 쿠웨이트 공항(6/3) → 알살렘 BM(6/6) 패턴
- **입력:** (ent-526 BM 공격, follows, ent-504 쿠웨이트 공항 드론), (ent-504, locatedIn, ent-037 Kuwait)
- **추론:** (ent-526, follows, ent-504) — 동일 국가(쿠웨이트) 미군 시설 대상, 드론→BM 무기 수준 격상
- **신뢰도:** 0.85
- **상태:** 확정

### 추론 #5: co_participation — 레자에이 ↔ 하메네이 내부 권력 역학
- **입력:** (ent-529 레자에이, affiliatedWith, ent-046 하메네이), (ent-529, 'first victory' 주장)
- **추론:** (ent-529, relatedTo, ent-046) — 군사고문의 서방 매체 인터뷰는 최고지도자 내부 위치 강화 시도
- **신뢰도:** 0.75
- **상태:** 잠정

---

## 2026-06-08 추론 결과

### 추론 #1: event_chain — 이란 미사일 → MoU 위기
- **입력:** (ent-537 라맛다비드 미사일, causedBy, ent-536 다히에 공습), (ent-539 '딜 불가' 선언, follows, ent-537), (ent-539, relatedTo, ent-456 MoU)
- **추론:** (ent-537, relatedTo, ent-456) — 60일 만의 이란→이스라엘 직접 미사일 공격이 MoU 프레임워크를 사실상 위기로 몰아넣음; 이란 관료가 같은 날 '딜 불가능' 선언
- **신뢰도:** 0.82
- **상태:** 확정

### 추론 #2: event_chain — 방어전환 → 다히에 공습 역설
- **입력:** (ent-534 방어전환 Jun 7, follows, ent-533 150곳 공습), (ent-536 다히에 공습, follows, ent-534)
- **추론:** (ent-536, causalChain, ent-534) — 이스라엘이 '방어 태세 전환'을 발표한 다음날 다히에를 공습한 것은 '방어'가 남부 레바논 지상전에 한정되며 공중 작전(특히 베이루트)은 별도 결심이라는 구조를 노출
- **신뢰도:** 0.78
- **상태:** 확정
- **비고:** 6/3 파일럿 존 합의 → 6/7 방어전환 → 6/8 다히에 공습. '방어'는 정치적 시그널이었을 뿐, 헤즈볼라 본부 타격 결심은 전혀 별개의 에스컬레이션 판단.

### 추론 #3: event_chain — BM 7발(걸프) → BM 10+(이스라엘) 72시간 패턴
- **입력:** (ent-526 IRGC BM 쿠웨이트/바레인 Jun 6), (ent-537 IRGC BM 라맛다비드 Jun 8)
- **추론:** (ent-537, follows, ent-526) — IRGC가 72시간 내에 2회 대규모 BM 사용(걸프 7발 → 이스라엘 10+발). 전략적 시사: BM 재고 충분하거나 억제력 계산이 변화; 다중 전선 동시 BM 투사 능력 입증
- **신뢰도:** 0.80
- **상태:** 확정

### 추론 #4: co_participation — 트럼프 'I call shots' → MoU 보존 시도
- **입력:** (ent-538 트럼프 선언, follows, ent-537 이란 미사일), (ent-001 Trump, '매우 가까운 딜' 주장)
- **추론:** (ent-538, relatedTo, ent-456) — 이란의 이스라엘 공격에도 트럼프가 이스라엘 보복을 금지한 것은 MoU 프레임워크 보존을 위한 전략적 결정; 딜 동기가 동맹국 연대보다 우선
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 4/17 'PROHIBITED' 선언의 재현이나, 이번에는 이란의 10+ BM 이후라는 점에서 더 극적. 이스라엘이 자체 보복을 자제할 수 있는 기간은 제한적.

### 추론 #5: co_participation — 이란 '딜 불가' vs 트럼프 '딜 매우 가까워'
- **입력:** (ent-539 '딜 불가', date=Jun 8), (ent-538 'I call shots'+'매우 가까운 딜', date=Jun 8)
- **추론:** (ent-539, opposes, ent-538) — 같은 날 이란과 미국이 딜 전망에 대해 정반대 평가. 이란: '불가능'; 미국: '매우 가까워'. 이는 양측의 협상 레버리지 투쟁이 공개적 메시지 전쟁으로 변환된 것이거나, 실질적 인식 차이를 반영
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 6/4 아라그치 '진전 없음' vs 트럼프 '이번 주말 딜' 패턴의 반복이나, 이번에는 이란이 '불가능'으로 격상. 미사일 공격 후의 선언이라 단순한 협상 포지셔닝이 아닌 실질적 단절 시그널일 수 있음.

### 스키마 변경 없음
- 6개 새 엔티티 모두 기존 클래스(Event 4, Location 2)로 분류 가능
- 14개 새 관계(명시적) + 5개 추론 모두 기존 관계 유형(participatesIn, locatedIn, causedBy, follows, opposes, relatedTo, causalChain)으로 표현 가능

---

## 2026-06-09 추론 결과

### 추론 #1: event_chain — 라맛다비드(6/8) → 마흐샤르(6/9) 직접 보복 체인
- **입력:** (ent-537 이란 라맛다비드 BM, date=Jun 8), (ent-542 이스라엘 마흐샤르 반격, date=Jun 9)
- **추론:** (ent-542, causalChain, ent-537) — 이란 10+ BM → 이스라엘 IAF 마흐샤르 석유화학+방공망 보복. 네타냐후가 트럼프 중단 요청을 무시하고 진행한 것은 이스라엘의 자율적 에스컬레이션 사다리를 입증
- **신뢰도:** 0.88
- **상태:** 확정
- **비고:** 4/8 이후 62일 만에 이란 에너지 인프라 직접 타격. 이는 초기 전쟁의 에너지 시설 표적 패턴(Kharg Island, 4/7-8)의 재현. 그러나 이번에는 치명적 피해 없이(15명 부상, 사망자 없음) 수행하여 에스컬레이션을 통제한 '제한적 보복' 패턴.

### 추론 #2: event_chain — 트럼프 'on your own' → 상호 중단 인과
- **입력:** (ent-545 트럼프 'on your own', date=Jun 9), (ent-544 상호 공격 중단, date=Jun 9)
- **추론:** (ent-544, causedBy, ent-545) — 트럼프의 유기 위협이 양측 정전의 직접 원인. 이스라엘은 '테헤란 대규모 공격'을 준비 중이었으나 중단; 이란은 조건부로 공세 중단
- **신뢰도:** 0.82
- **상태:** 확정
- **비고:** 4/17 'PROHIBITED' → 6/8 'I call all the shots' → 6/9 'on your own very soon'으로 3단계 격상. 유기 위협은 전례 없는 수준이며, 이스라엘이 미국 안보 보장 없이 이란과 단독 대치해야 한다는 시나리오는 네타냐후에게 수용 불가. 이 압박이 마흐샤르 이후 추가 공격 중단으로 이어짐.

### 추론 #3: event_chain — '딜 불가'(6/8) → 상호 중단(6/9) 역전
- **입력:** (ent-539 이란 '딜 불가', date=Jun 8), (ent-544 상호 중단, date=Jun 9)
- **추론:** (ent-544, follows, ent-539) — 어제 '딜 더 이상 불가능'이라 선언했던 이란이 오늘 조건부 공격 중단을 수용. 에스컬레이션이 역설적으로 디에스컬레이션을 강제하는 패턴
- **신뢰도:** 0.80
- **상태:** 확정
- **비고:** 마흐샤르 에너지 시설 타격이 이란에게 구체적 경제 비용을 상기시켜, '불가능' 포지셔닝에서 '조건부 중단'으로 후퇴. 이란의 '딜 불가'는 전날의 협상 레버리지였을 가능성이 높아짐. 다만 '레바논 휴전 조건부 평화'라는 새 조건 추가는 이란이 단순 후퇴가 아닌 협상 조건 재설정을 시도하고 있음을 시사.

### 추론 #4: event_chain — 'I call shots'(6/8) → 'on your own'(6/9) 격상
- **입력:** (ent-538 'I call shots', date=Jun 8), (ent-545 'on your own', date=Jun 9)
- **추론:** (ent-545, follows, ent-538) — 24시간 내에 통제('내가 결정')에서 유기 위협('혼자가 될 것')으로 격상. 네타냐후가 마흐샤르 공습으로 트럼프의 중지 요청을 무시한 것이 직접 원인
- **신뢰도:** 0.85
- **상태:** 확정
- **비고:** 미-이스라엘 관계의 구조적 변화. 트럼프가 동맹 유기를 공개적으로 언급한 것은 전쟁 102일 중 전례 없는 수준. 그러나 이 위협이 실행될 가능성은 낮음 — 이스라엘 로비, 의회 내 이스라엘 지지, 중동 전략 이해관계를 고려할 때. 위협 자체가 네타냐후 행동 수정의 도구로 기능.

### 추론 #5: co_participation — 항공 재개방 → MoU 환경 개선
- **입력:** (ent-546 항공 재개방, date=Jun 9), (ent-456 MoU 프레임워크)
- **추론:** (ent-546, relatedTo, ent-456) — 이란/시리아/이라크 영공 재개방은 물리적 디에스컬레이션 지표. 유가 안정화(WTI $91.32/Brent $94.63)와 함께 MoU 재개를 위한 환경이 부분적으로 조성
- **신뢰도:** 0.78
- **상태:** 잠정
- **비고:** 항공 재개방은 군사적 위협 감소의 가장 직접적 지표. 그러나 양측 모두 '재개 경고'를 병행하여 중단이 불안정. 이란의 레바논 조건 추가는 MoU 범위를 확대하여 타결을 더 어렵게 만들 수 있음. 유가 안정화는 시장이 상호 중단을 '일시적이나 긍정적'으로 해석함을 시사.

### 스키마 변경 없음
- 5개 새 엔티티 모두 기존 클래스(Event 4, Location 1)로 분류 가능
- 16개 새 관계(명시적) + 2개 업데이트 + 5개 추론 모두 기존 관계 유형(participatesIn, locatedIn, causedBy, follows, opposes, relatedTo, causalChain)으로 표현 가능
