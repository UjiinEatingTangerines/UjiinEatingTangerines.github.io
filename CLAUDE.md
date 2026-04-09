# Resume Project — Base Rules

This is a multilingual (KO/EN/JA) resume website for a backend engineer targeting big-tech payment/settlement positions.

## Target Companies
- Primary: LINE
- Secondary: Olive Young, Toss Bank

## File Structure
- `index.html` — Main resume (KO/EN/JA trilingual, PDF export)
- `tossbank.html` — Toss Bank targeted version (KO only)
- `style.css` — Shared styles

## Resume Writing Rules

These rules are distilled from reviewer feedback (Ted, Jude, and senior engineers) and must be applied to ALL resume edits.

### 1. Trade-offs > Actions (최우선)
- "X를 했다"가 아닌 "Y 대신 X를 선택한 이유"를 서술
- 아키텍처 결정의 근거와 대안 비교를 반드시 포함
- 읽는 사람이 "왜?"라고 물을 만한 부분을 선제적으로 설명
- Bad: "Kafka DLQ로 실패 건을 격리했습니다"
- Good: "스케줄러 재폴링 대비 Kafka DLQ가 실패 격리와 순서 보장에 유리해 선택. 단, consumer lag 모니터링이 추가로 필요"

### 2. 마이그레이션 스토리 = 최고 소재
- "무엇을 만들었는가"보다 "어떻게 전환했는가"가 더 매력적
- 무중단 전환, 데이터 정합성 검증, 롤백 전략 등 전환 과정의 기술적 깊이를 강조
- 새 시스템 구축보다 레거시 → 신규 전환 과정에 집중

### 3. 도메인 종속 표현 최소화
- 정산/결제 팀만 이해할 수 있는 용어를 범용 기술 문제로 번역
- Bad: "48시간 보류 규칙과 회원 유형별 단가를 분리"
- Good: "시간 기반 상태 전이와 동적 가격 정책을 결제 로직에서 분리해 독립 모듈화"
- 단, 도메인 키워드(결제, 정산, 원장, 대사)는 JD 매칭용으로 유지

### 4. 기술 키워드는 문맥 속에서
- Redis, Kafka 등 핵심 기술은 반드시 노출하되, 나열이 아닌 문제 해결 맥락에서 등장
- "어떤 문제를 이 기술의 어떤 특성으로 풀었는가"가 드러나야 함
- 기술을 쓴 이유가 없으면 오히려 감점 — "정말 이게 필요했나?"에 답할 수 있어야 함

### 5. 정량 수치 필수
- Before → After 형식 선호 (936초 → 1~2초)
- 트래픽이 낮더라도 건수, 시간, 비율로 표현
- 데이터 규모(테이블 행 수, 일일 처리량)를 반드시 언급
- 퍼센트만으로는 불충분 — 절대 수치를 병기

### 6. 표준 용어만 사용
- 자체 조어 금지 (예: "배치 슬라이스" → Spring Batch의 chunk/step/partition 등 공식 용어)
- 기술 면접에서 질문받았을 때 표준 문서를 참조해 설명할 수 있는 용어만 사용
- 불확실한 용어는 공식 문서에서 확인 후 사용

### 7. 아키텍처 과잉 경계
- 기술 도입의 필요성에 의문을 제기할 수 있어야 함
- "SQS로 배치 트리거?" → "직접 호출 후 실패 시 큐" 같은 더 단순한 대안 검토
- 복잡한 아키텍처를 자랑하는 것보다, 적절한 복잡도를 선택한 판단력이 더 가치 있음

### 8. 섹션 역할 분리
- **Experience**: HR이 읽는 비즈니스 성과 요약 — 1~2줄, 함축적, 숫자 포함
- **Problem Solving**: 기술 면접관이 읽는 문제-해결-성과 — 깊이 있게, trade-off 포함
- Experience가 뚱뚱해지면 안 됨 — Problem Solving에서 빼낸 것을 Experience에 넣지 말 것

### 9. 프로젝트 3~5개만
- 읽는 사람은 위에서 2~3개만 읽음
- 가장 매력적인 프로젝트를 최상단에 배치
- 임팩트가 약한 것(JIRA 티켓 감소, 단순 CRUD API)은 과감히 제거

### 10. JD 기반 키워드 정렬
- 지원 대상 JD를 먼저 분석하고, JD 핵심 키워드가 이력서에 매핑되어야 함
- 같은 경험도 JD에 따라 강조점이 달라져야 함
- 새 타겟 회사 추가 시 해당 JD 키워드 분석부터 시작

### 11. 프로젝트는 문제에서 시작
- 기능 나열이 아닌, "어떤 불편/문제가 있었고 → 그래서 이렇게 설계했다"로 시작
- "왜 이 기능을 먼저 만들었는가"에 답할 수 있어야 함
- AI 시대에 구현은 평준화 — 문제를 정의하고 우선순위를 판단하는 능력이 차별화
- 실사용자 검증 경험(배포 후 피드백, 예상과 다른 결과)이 있으면 최우선으로 부각
- Bad: "캘린더 기능 구현, 알림 기능 구현, 소셜 로그인 구현"
- Good: "기존 앱의 개인 기록 중심 한계를 파악하고, 일정 조율 경험에 초점을 맞춰 기능 우선순위를 재설계"

## Trilingual Consistency
- KO를 먼저 작성하고, EN/JA는 KO의 의미를 정확히 반영
- 기술 용어(Kafka, Redis, Saga 등)는 3개 언어 모두 동일하게 유지
- 수치와 결과는 3개 언어 모두 동일
