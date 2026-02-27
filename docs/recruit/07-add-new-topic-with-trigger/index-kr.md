# 🚨 미션 07: 트리거와 노드를 사용하여 새 토픽 추가

## 🕵️‍♂️ 코드네임: `OPERATION STAY ON TOPIC`

> **⏱️ 작업 시간:** `~60분`

## 🎯 미션 브리프

당신은 에이전트를 만들었습니다. 에이전트는 듣고, 학습하고, 질문에 답할 수 있습니다. 이제 더 전략적으로 발전시킬 차례입니다. 이번 미션에서는 내부 동작을 깊이 이해하고, 특정 프롬프트에 정확하게 반응하도록 에이전트를 학습시킵니다.

Topics와 Triggers를 사용하면 에이전트는 다음을 수행할 수 있습니다:

- 의도 인식
- 로직 기반 대화 라우팅
- 변수 수집 및 저장
- 플로우 실행 및 액션 수행

이제 단순한 대화 구성이 아니라, 의사결정 구조를 구축하는 단계입니다. Neural Nexus에 오신 것을 환영합니다.

## 🔎 목표

이번 미션에서 배우게 될 내용:

1. 토픽이 무엇이며 구조화된 대화를 만드는 역할 이해
1. 트리거 문구와 대화 노드를 포함한 토픽 구조 이해
1. 다양한 대화 노드 유형과 Power Fx를 통한 동적 로직 활용
1. 특정 요청 처리를 위한 사용자 정의 토픽 생성
1. 커넥터와 도구를 사용하여 SharePoint 데이터와 연결되는 기능성 토픽 구축

## 🤔 토픽이란?

토픽은 특정 사용자 질문이나 작업에 대응하도록 설계된 구조화된 대화입니다. 에이전트가 처리할 수 있는 미니 대화 또는 작업 단위라고 생각하면 됩니다. 각 토픽은 특정 사용자 질문이나 요청에 대응하도록 설계됩니다.

### 🌌 토픽의 목적

사용자 요구에 따라 토픽은 일반적으로 세 가지 목적을 가집니다:

**정보 제공** - 다음과 같은 질문에 답변:

- `…이 뭐예요?`    
- `…은 언제예요?`      
- `…은 왜 그래요?`    
- `…에 대해 말해줄 수 있어요?`    

**작업 수행** - 사용자가 무언가를 _하도록_ 도움:

- `저는 …하고 싶어요.`    
- `어떻게 하면 …할 수 있을까요?`    
- `저는 …이 필요해요?`    

**문제 해결** - 문제 상황 해결:

- `뭔가 제대로 작동하지 않아요…`    
- `오류 메시지가 나타납니다…`    
- `예상치 못한 상황이 발생했어요…`    

또한 `도움이 필요해요`와 같이 모호한 질문에 대해 추가 정보를 요청하는 토픽도 만들 수 있습니다.

## 🐦 토픽이 유용한 이유

토픽은 다음과 같은 도움을 줍니다:

- 에이전트 지식 구조화
- 자연스러운 대화 흐름 구현
- 사용자 문제를 효과적으로 해결

## 🪺 토픽 유형

1. **System topics** - 기본 제공되며 다음과 같은 공통 이벤트 처리:
    - 대화 시작
    - 대화 종료
    - 오류 처리
    - 로그인 요청
    - 사람 상담원 연결

1. **Custom topics** - 특정 작업 또는 질문을 위해 직접 생성:
    - 직원 휴가 요청
    - 신규 또는 교체 디바이스 요청

![Types of topics](assets/7.0_01_Topics.png)

## 🧬 토픽 구조

각 토픽은 일반적으로 다음 요소를 포함합니다.

### 🗣️ 트리거 문구

사용자가 토픽을 시작하기 위해 말할 수 있는 문장 또는 단어입니다.

**예시:**

휴가 요청 토픽:

- `휴가를 내고 싶어요`    
- `휴가 신청`    
- `휴가 신청하기`   
- `휴가 신청은 어떻게 하나요?`    

디바이스 요청 토픽:

- `새 기기가 필요해요`    
- `기기 신청할 수 있나요?`   
- `기기 신청 도와주실 수 있나요?`    

### 💬 대화 노드

토픽은 트리거 이후 에이전트가 수행하는 단계인 노드로 구성됩니다. 이러한 단계들을 연결하여 사용자와 상호작용할 때 에이전트가 따르는 대화 흐름을 만듭니다.

다음과 같은 지시 또는 액션이라고 생각하면 됩니다:

- 사용자에게 질문
- 메시지 전송
- 휴가 관리 시스템 같은 외부 서비스 호출
- 변수 설정 또는 확인
- 조건을 사용하여 대화 분기
- 다른 토픽으로 이동

![Conversation nodes](assets/7.0_03_ConversationNodes.png)

에이전트에 추가할 수 있는 주요 노드 유형은 다음과 같습니다:

#### Send a message

- **목적** - 사용자에게 메시지를 전송합니다.
- **예시** - `요청해 주셔서 감사합니다! 도와드리겠습니다.`

이 노드는 에이전트가 사용자에게 메시지를 보낼 수 있게 합니다. 단순 텍스트 또는 이미지, 비디오, 카드, 빠른 응답, 적응형 카드 같은 풍부한 콘텐츠를 포함할 수 있습니다.

변수를 사용하여 메시지를 개인화하고, 다양성을 위해 여러 메시지 변형을 추가하며, 음성 지원 채널을 위한 음성 출력도 커스터마이즈할 수 있습니다.

> [!TIP]
> 에이전트가 사용자와 명확하고 인터랙티브하게 소통하는 "말하기" 블록이라고 생각하세요.

#### Ask a question

- **목적** - 사용자에게 질문하고 답변을 기다립니다.
- **예시** - `휴가 날짜는 언제인가요?`

이 노드는 대화 중 사용자에게 특정 정보를 요청하고 응답을 변수에 저장하여 나중에 사용합니다.

질문 유형(텍스트 입력 또는 사용자가 선택하는 정의된 값 목록용 엔티티)을 커스터마이즈하고, 사용자가 잘못된 답변을 하거나 질문을 건너뛸 때 에이전트의 동작을 정의할 수 있습니다.

이미지와 빠른 응답 같은 풍부한 콘텐츠도 지원하며, 유효성 검사, 재프롬프트, 인터럽션 설정을 세밀하게 조정하여 대화 흐름을 원활하게 만들 수 있습니다.

> [!TIP]
> 에이전트가 정의한 구조화된 방식으로 사용자와 상호작용하는 "질문하고 듣기" 블록이라고 생각하세요.

#### Ask with adaptive card

- **목적** - JSON을 사용하여 풍부하고 인터랙티브한 카드를 전송합니다.
- **예시** - 사용자가 날짜를 선택할 수 있는 캘린더 날짜 선택기가 있는 카드

이 노드는 텍스트 박스, 버튼, 이미지가 포함된 폼과 같이 사용자가 작성하고 제출할 수 있는 풍부하고 인터랙티브한 카드를 표시합니다. 사용자의 입력을 캡처하여 변수에 저장하며, 에이전트가 대화 후반에 사용할 수 있습니다.

> [!TIP]
> 에이전트를 더 매력적으로 만들고 사용자로부터 상세한 정보를 수집할 수 있는 커스터마이즈 가능한 "폼 빌더" 블록이라고 생각하세요.

#### Add a condition

- **목적** - 대화에 로직을 추가합니다. 무언가를 확인하고 다음에 할 일을 결정합니다.
- **예시** - 사용자가 `Yes`라고 하면 다음 단계로 이동, `No`라면 대화를 종료합니다.

이 노드는 변수가 특정 기준을 충족하는지 확인하여 에이전트의 대화 흐름에 의사결정 지점을 만듭니다. 조건이 참인지 거짓인지에 따라 에이전트는 다른 경로를 따릅니다.

> [!TIP]
> 사용자 입력이나 변수에 저장된 데이터에 따라 에이전트가 결정을 내리는 "if-else" 블록이라고 생각하세요.

#### Variable management

- **목적** - 대화 중 정보(변수)를 저장하거나 초기화합니다.
- **예시** - Ask a question 노드에서 적응형 카드를 표시하여 사용자가 선택한 날짜를 저장합니다.

이 노드는 대화 중 정보를 저장하고 관리합니다. 사용자의 이름, 답변, 선호도 등이 될 수 있습니다. 텍스트, 숫자, 날짜 같은 다양한 변수 타입을 사용할 수 있으며, 단일 토픽 범위, 토픽 간 공유(글로벌), 시스템이나 환경에서 가져올 수 있습니다.

> [!TIP]
> 에이전트가 정보를 기억하고 대화가 계속될 때 사용할 수 있는 "메모리 박스"라고 생각하세요.

#### Topic management

- **목적** - 다른 토픽이나 토픽 내의 단계로 대화를 이동하거나, 대화를 전환하거나, 토픽이나 대화를 종료합니다.
- **예시** - "휴가 정책" 토픽으로 리디렉션

이 노드는 대화를 재시작하지 않고 하나의 토픽에서 다른 토픽으로 이동하거나, 토픽을 종료하거나, 대화를 전환/종료하거나, 같은 토픽 내의 다른 단계로 이동할 수 있게 합니다. 토픽 간 원활한 전환을 통해 사용자를 대화 흐름의 다른 부분으로 안내하며, 컨텍스트를 유지하기 위해 토픽 간 변수를 전달할 수 있습니다.

> [!TIP]
> 에이전트가 유연하게 사용자와 대화할 수 있도록 돕는 "다른 섹션/단계로 이동" 블록이라고 생각하세요.

#### Add a tool

- **목적** - 커넥터, 에이전트 플로우, 프롬프트, 커스텀 검색, 검색 쿼리, 스킬, Model Context Protocol 등의 도구에 연결합니다.
- **예시** - 사용자가 휴가 신청을 제출한 후 에이전트 플로우가 실행됩니다.

이 노드는 에이전트에게 외부 시스템과 상호작용하거나 특정 작업을 수행하는 기능을 제공합니다. 이메일 전송, 날씨 확인, 데이터베이스 접근 등을 수행합니다. 내장 커넥터, 커스텀 API, 에이전트 플로우, 프롬프트를 사용하거나 Model Context Protocol (MCP) 서버에 연결하고, 데스크톱 앱을 위한 Computer Use 도구를 통해 _GUI_ 자동화도 가능합니다.

> [!TIP]
> 도구는 API 호출, 프로세스 실행, 사용자 입력 자동 수집 등 _채팅_ 이상의 일을 에이전트에게 할 수 있게 하는 "액션 블록"이라고 생각하세요.

#### Generative answers node

- **목적** - 대규모 언어 모델을 사용해 사용자의 질문과 연결된 데이터를 기반으로 자연스럽고 사람 같은 응답을 생성합니다.
- **예시** - 휴가 관련 정보가 포함된 연결된 지식 소스를 사용하여 사용자의 휴가 요청 관련 질문에 답변합니다.

이 노드는 웹사이트, 문서, SharePoint, 커스텀 데이터 등 다양한 지식 소스의 정보를 사용하여 사용자 질문에 응답할 수 있게 합니다. 일치하는 토픽이 없을 때 폴백으로 사용하거나, 토픽 내에서 구성한 특정 소스를 기반으로 더 상세하고 동적인 답변을 제공하는 데 사용할 수 있습니다.

> [!TIP]
> 에이전트가 정의한 신뢰할 수 있는 콘텐츠를 검색하여 유용하고 정확한 응답을 제공하는 "스마트 답변 블록"이라고 생각하세요.

#### HTTP request node

- **목적** - API 호출(예: `GET` 또는 `POST`)을 전송하여 에이전트를 외부 시스템에 연결하여 데이터를 가져오거나 업데이트합니다.
- **예시** - 사용자가 남은 휴가 일수를 물으면 에이전트가 휴가 관리 시스템에 `GET` 요청을 수행하고, API 응답에서 `remainingLeaveDays`를 추출하여 사용자에게 값을 응답합니다.

이 노드는 REST API 호출(`GET` 또는 `POST` 요청 등)을 전송하여 에이전트를 외부 시스템에 연결합니다. 헤더, 바디 콘텐츠로 요청을 커스터마이즈하고, Power Fx를 사용하여 동적 데이터를 포함한 다음, 응답을 변수에 저장하여 대화 후반에 사용할 수 있습니다.

> [!TIP]
> 사용자 세부 정보 가져오기나 다른 시스템에 데이터 전송 같은 작업을 위해 에이전트가 다른 서비스와 통신하는 "외부 정보 가져오기" 블록이라고 생각하세요.

#### Send an event

- **목적** - 시스템 업데이트나 도구 트리거 같은 메시지가 아닌 액션을 클라이언트나 채널에 전송하여 에이전트가 작업을 수행하도록 돕습니다.
- **예시** - 사용자가 채팅에 참여할 때 환영 메시지를 표시하여 반응합니다.

이 노드는 에이전트가 메시지가 아닌 액션을 외부 시스템이나 채널에 전송할 수 있게 하며, 수신 측에서 응답 방법을 결정합니다. 각 이벤트에 이름을 부여하고 값을 첨부하며, 이 값은 단순 숫자나 텍스트, 변수, 또는 Power Fx 수식이 될 수 있고, JSON 객체로 전송됩니다.

> [!TIP]
> 에이전트가 사용자의 말 없이도 뒤에서 작업을 수행하거나 외부 도구와 통신하는 "무음 트리거" 블록이라고 생각하세요.

## 🏋🏻‍♀️ Using Power Fx in your nodes

Copilot Studio에서 Power Fx는 에이전트에 로직과 동적 동작을 추가하는 로우코드 프로그래밍 언어입니다. Microsoft Power Apps에서 사용하는 동일한 언어이며, Excel과 유사하게 설계되어 개발자와 비개발자 모두 쉽게 사용할 수 있습니다.

![Power Fx expression](assets/7.3_09_EnterFormula.png)

### What Power Fx can do in topics

- 변수 설정 및 조작
      - 예시: `Set(userName, "Adele Vance")`
- 조건 생성
      - 예시: `If(score > 80, "Pass", "Fail")`
- 데이터 포맷 및 변환
      - 예시: `Text(DateValue, "dd/mm/yyyy")`

### Why use Power Fx?

- **유연함:** 전체 코드를 작성하지 않고도 로직을 구축할 수 있습니다.
- **친숙함:** Excel 수식을 사용해 본 경험이 있다면 매우 유사하게 느낄 수 있습니다.
- **강력함:** 대화를 개인화하고, 입력을 검증하며, 사용자 데이터를 기반으로 에이전트 동작을 제어할 수 있습니다.

## 🏗️ 토픽을 만들고 편집하는 방법

에이전트용 토픽을 만들고 편집하는 두 가지 방법이 있습니다.

### 1. 빈 토픽에서 만들기

커스텀 대화 흐름을 처음부터 구축하며, 토픽을 편집할 때 필요에 따라 노드를 추가하거나 제거할 수 있습니다.

![Add a topic](assets/7.0_04_AddATopic.png)

#### 이 방법이 유용한 이유

- 에이전트의 응답 방식에 대한 완전한 제어가 가능합니다.
- 변수, Power Fx, 조건을 사용하여 로직을 커스터마이즈할 수 있습니다.
- 특정 비즈니스 요구에 맞는 맞춤형 경험을 구축하는 데 완벽합니다.

### 2. Copilot으로 설명에서 추가

자연어로 원하는 것을 설명하면 Copilot이 대화를 구축합니다. 토픽을 편집할 때도 마찬가지로 자연어를 사용하면 Copilot이 토픽을 검토하고 수정합니다.

#### Copilot이 지원하는 기능

- 생성 및 편집 가능:
      - 메시지 노드
      - 질문 노드
      - 조건 노드
- 사용자가 응답하지 않을 때 재프롬프트 방법이나 질문 중 인터럽션 관리와 같은 고급 설정은 지원하지 않습니다. 필요한 경우 수동으로 설정을 조정할 수 있습니다.

#### 이 방법이 유용한 이유

- AI 지원으로 개발 속도를 높여줍니다.
- 반복적인 설정 대신 로직과 사용자 경험에 집중할 수 있습니다.
- 최소한의 노력으로 대화 흐름을 반복 개선하기 쉽습니다.

#### ✨ 프롬프트 예시

- **토픽 생성**    
      - `사용자의 이름, 나이, 생년월일을 입력받아 답변을 다시 들려줍니다.`    
      - `사용자의 주소, 주, 우편번호를 수집합니다. 사용자는 각 질문에 최대 4번까지 재응답할 수 있습니다.`    

- **토픽 편집**    
      - `사용자의 생년월일을 묻는 질문을 추가하세요.`    
      - `수집된 정보를 어댑티브 카드에 요약합니다.`    

## 👩🏻‍🎨 에이전트를 위한 토픽 설계 방법

### 🧙🏻‍♂️ Step 1 - 사용자 요구 파악

사용자가 에이전트에게 물어볼 일반적인 질문이나 작업을 파악하는 것부터 시작합니다:

- 사용자가 자주 묻는 질문, 예: `병가 일수는 얼마나 되나요?`
- 사용자가 완료하고 싶은 일반적인 작업, 예: 폼 제출
- 사용자가 자주 겪는 문제, 예: 로그인 문제

### 📦 Step 2 - 시나리오 그룹화

사용자 요구를 이전에 배운 토픽의 목적에 따라 세 가지 카테고리로 정리합니다:

- 정보 제공 - 사용자가 무언가를 알고 싶음
- 작업 수행 - 사용자가 무언가를 하고 싶음
- 문제 해결 - 사용자가 문제 해결에 도움이 필요함

### 🗺️ Step 3 - 대화 흐름 매핑

에이전트가 어떻게 응답해야 하는지 간단한 대화 흐름을 스케치합니다:

- 인사 또는 확인으로 시작
- 세부 사항을 얻기 위한 후속 질문
- 답변을 제공하거나 액션을 수행

!!! tip
    대화를 짧고 집중적으로 유지하세요. 필요한 것만 질문하세요.

### 🔀 Step 4 - 다양한 대화 유형 처리

다음 두 가지를 모두 설계합니다:

- **단일 턴** - 하나의 질문, 하나의 답변

- **멀티 턴** - 후속 질문이 있는 왕복 대화

예시:

- 사용자: `휴가를 신청하고 싶습니다.`

- 에이전트: `좋습니다! 휴가 시작 날짜는 언제인가요?`

- 사용자: `7월 15일`

- 에이전트: `알겠습니다. 휴가 종료 날짜는 언제인가요?`

- 사용자: `7월 22일`

- 에이전트: `감사합니다! 휴가 사유는 무엇인가요?`

- 사용자: `가족 여행`

- 에이전트: `감사합니다! 7월 15일부터 7월 22일까지 가족 여행을 위한 휴가 요청이 제출되었습니다. 곧 확인을 받으실 것입니다.`

### 🤖 Step 5 - 예상치 못한 질문에 AI 활용

휴가 요청을 위한 토픽을 설계했더라도 사용자가 직접 다루지 않는 질문을 할 수 있습니다. 이때 _Conversational boosting_ 시스템 토픽과 같은 AI 기능이 유용합니다.

이 토픽에는 생성형 답변 노드가 포함되어 있어 에이전트가 연결된 지식 소스를 바로 사용할 수 있습니다. 에이전트 레벨에서 추가된 모든 지식 소스는 _Conversational boosting_ 시스템 토픽의 생성형 답변 노드에 자동으로 포함됩니다.

#### 예시

- 사용자: `미사용 휴가를 내년으로 이월할 수 있나요?`

이 질문은 사전 정의된 토픽 흐름에 포함되지 않을 수 있습니다. 특히 토픽이 휴가 요청 제출만 처리하는 경우에 그렇습니다.

#### AI가 도움을 주는 방식

에이전트가 회사의 HR 정책 문서나 내부 웹사이트에 연결되어 있다면, AI가 다음을 수행할 수 있습니다:

- 관련 휴가 정책 검색
- 규칙을 이해하고 요약
- 에이전트가 다음과 같이 응답: `HR 정책에 따르면, 미사용 휴가를 다음 해로 이월할 수 있습니다. 자세한 내용은 HR 포털의 휴가 정책 섹션을 확인하세요.`

#### 이것이 유용한 이유

- 모든 정책 관련 질문에 대해 수동으로 토픽을 만들 필요가 없습니다.
- AI가 신뢰할 수 있는 지식 소스에서 정확한 답변을 가져올 수 있습니다.
- 에이전트가 더 스마트하고 반응성이 좋아져 사용자 경험이 향상됩니다.

### 🔬 Step 6 - 토픽과 대화 흐름 테스트

토픽을 게시하기 전에:

- 실제 질문이나 실제 샘플 입력으로 테스트하세요.
- 자연스럽고 도움이 되는지 확인하세요.

> [!TIP]
> 테스트하면서 노드를 추가하거나, 다른 토픽으로 리디렉션하는 것으로 대체하는 등 토픽을 적절히 개선하세요.

### ⚠️ Step 7 - 웹사이트 콘텐츠 중복 방지

이미 웹사이트에 있는 내용을 복사하지 마세요.

- 사용자가 자주 묻는 토픽에 집중하세요.
- 채팅 기록이나 지원 요청을 기반으로 새 토픽을 추가하세요.

### ✨ 대화 흐름 예시

아래는 휴가 요청을 처리하는 토픽의 예시입니다.

#### Step 1: 트리거 문구

사용자가 입력합니다,

`휴가 신청을 하고 싶습니다.`

#### Step 2: 에이전트가 Adaptive card로 세부 사항 요청

에이전트가 물어봅니다,

`좋습니다! 어떤 날짜에 휴가를 원하시나요?`

Adaptive card에는 시작 날짜와 종료 날짜 캘린더 선택기 컨트롤이 있습니다.

#### Step 3: 사용자가 날짜 제공

사용자가 시작 날짜를 2025년 8월 5일, 종료 날짜를 2025년 8월 10일로 선택하고 카드를 제출합니다. 날짜 값은 adaptive card의 출력 변수로 저장됩니다.

#### Step 4: Cloud flow 실행

Power Automate 클라우드 플로우가 실행되어 휴가 관리 시스템에 새 요청을 생성하고 매니저에게 휴가 요청 이메일 알림을 전송합니다.

#### Step 5: 사용자에게 확인 메시지 전송

에이전트가 응답합니다,

`8월 5일부터 8월 10일까지의 휴가 요청이 제출되었습니다. 매니저가 검토 후 곧 연락드릴 것입니다.`

## 🧪 Lab 07 - 대화 노드를 사용한 새 토픽 추가

이제 트리거와 도구를 사용하는 새로운 토픽을 추가하는 방법을 학습합니다. 이 실습에서는 빈 토픽부터 생성하여 사용자 요구에 맞게 커스터마이즈하는 방법을 익힙니다.

### ✨ 사용 사례

**As an** employee

사용 가능한 디바이스를 확인하고, 목록을 얻고 싶습니다! :)

이제 시작합니다!

### Prerequisites

1. **SharePoint list**

    [Lesson 00 - Course Setup - Step 3: Create new SharePoint site](../00-course-setup/index.md#step-4-create-new-sharepoint-site)의 **Devices** SharePoint 리스트를 사용합니다.

    **Devices** SharePoint 리스트를 아직 설정하지 않았다면 [Lesson 00 - Course Setup - Step 3: Create new SharePoint site](../00-course-setup/index.md#step-4-create-new-sharepoint-site)로 돌아가세요.

1. **Contoso Helpdesk Agent**

    [Lesson 06 - Create a custom agent using natural language with AI and grounding it with your data](../06-create-agent-from-conversation/index.md)에서 만든 동일한 에이전트를 사용합니다.

### 7.1 빈 토픽에서 새 토픽 추가

1. 에이전트 이름 옆의 **Topics** 탭을 선택합니다. 보이지 않으면 **+6**을 선택하여 **Topics**를 찾습니다.

    ![Select Topics](assets/7.1_01_Topics.png)

1. **Topics** 탭이 로드되고 기본적으로 _Custom_ 토픽이 표시됩니다. All, Custom, System으로 토픽을 필터링할 수 있습니다. 현재 보이는 커스텀 및 시스템 토픽은 에이전트가 프로비저닝될 때 자동으로 생성된 것입니다.

    **+ Add a topic**을 선택하고 **From blank**를 선택합니다.

    ![Create topic from scratch](assets/7.1_02_FromBlank.png)

1. 토픽 이름을 입력합니다. 다음을 복사하여 붙여넣으세요.

    ```text
    사용 가능한 디바이스
    ```

    토픽이 수행하는 작업을 설명하는 트리거 설명을 입력합니다. 다음을 복사하여 붙여넣으세요.

    ```text
    이 항목은 사용자가 SharePoint 장치 목록에서 사용 가능한 장치를 찾는 데 도움이 됩니다. 사용자는 사용 가능한 장치 목록을 요청할 수 있으며, 여기에는 노트북, 스마트폰, 액세서리 등이 포함될 수 있습니다.
    ```

    ![Enter a name and description for trigger](assets/7.1_03_TopicNameAndDescription.png)

### 7.2 트리거 입출력 정의

1. 다음으로 생성형 AI가 사용자 메시지에서 디바이스 유형 값을 추출하는 오케스트레이션에 사용할 새 입력 변수를 추가합니다. 토픽의 **More ellipsis (...)**를 선택하고 **Details**를 선택하여 토픽 세부 정보 패널을 봅니다.

    ![Select Topic Details](assets/7.2_01_SelectTopicDetails.png)

1. **Topic details** 패널이 로드되었습니다. **Input** 탭을 선택합니다.

    ![Input tab](assets/7.2_02_SelectInputTab.png)

1. **Create a new variable**를 선택합니다.

    ![Create new input variable](assets/7.2_03_CreateANewVariable.png)

1. 변수 이름을 입력합니다. 다음을 복사하여 붙여넣으세요.

    ```text
    VarDeviceType
    ```

    ![Input variable name](assets/7.2_04_VariableName.png)

1. 이제 입력 및 출력 변수를 정의해야 합니다. 토픽 입출력에 대해 정의할 수 있는 속성은 다음과 같습니다.

    | 필드 | 값 |
    | ----- | ----- |
    | How will the agent fill this input? | 토픽 실행 전 에이전트가 이 변수를 어떻게 채울지 결정합니다. 기본값은 _Dynamically fill with the best option_입니다. 또는 사용자에게 묻지 않고 값으로 재정의할 수 있습니다 |
    | Variable data type | 변수의 데이터 타입. 지원되는 데이터 타입: `String`, `Boolean`, `Number`, `Date`, `DateTime`, `DateTimeNoTimeZone`, `Time`, `Record`, `Table`, `Unspecified`, `From sample data` |
    | Display name | 변수 이름 |
    | Identify as | 에이전트가 올바른 값 유형을 캡처하기 위한 엔티티 타입 |
    | Description | 에이전트가 토픽 실행 전 자동으로 입력을 채우거나 값을 요청하는 질문을 생성하는 데 도움이 되는 설명 |

    _How will the agent fill this input?_, _Variable data type_ 및 _Display name_은 기본값 그대로 둡니다. **Identify as** 속성을 **User's entire response**로 업데이트합니다.

    ![Update Identify as](assets/7.2_05_IdentifyAs.png)

1. 설명으로 다음을 복사하여 붙여넣으세요.

    ```text
    가능한 값 목록: 노트북, 데스크톱, 스마트폰
    ```

    ![Description](assets/7.2_06_InputDescription.png)

1. 다음으로 토픽의 출력을 정의합니다. **Output** 탭을 선택합니다.

    ![Select Output tab](assets/7.2_07_SelectOutputTab.png)

1. **Create a new variable**를 선택합니다.

    ![Create new output variable](assets/7.2_08_CreateANewVariable.png)

1. 다음 속성을 업데이트합니다.

    **Variable name** - 다음을 복사하여 붙여넣으세요.

    ```text
    VarAvailableDevices
    ```

    **Variable data type** - 데이터 타입으로 **Table**을 선택합니다.

    **Variable description** - 다음을 복사하여 붙여넣으세요.

    ```text
    기기 유형별 사용 가능한 기기 목록
    ```

    ![Output properties](assets/7.2_09_OutputVariable.png)

1. 토픽의 입출력 정의가 완료되었습니다. **X icon**을 선택하여 **Topic details** 패널을 닫습니다.

    ![Exit from topic details pane.](assets/7.2_10_ExitTopicDetailsPane.png)

### 7.3 커넥터를 사용한 도구 추가

1. 다음으로 **Devices** SharePoint 리스트에서 디바이스 목록을 가져오는 노드를 추가합니다. 트리거 아래의 **+ icon**을 선택합니다.

    ![Add a tool](assets/7.3_01_AddNode.png)

1. **Add a tool** 노드를 선택한 다음 **Connector** 탭을 선택합니다. `Get items`를 검색하고 **Get items** SharePoint 커넥터 액션을 선택합니다.

    ![Select get items](assets/7.3_02_GetItems.png)

1. 사용자 자격 증명이 커넥터에 사용됩니다(녹색 체크 아이콘이 표시됨). 필요한 경우 새 연결을 생성하세요.

    **Submit**을 선택하여 **Get items** SharePoint 커넥터 액션을 토픽의 노드로 추가합니다.

1. **Get items** SharePoint 커넥터 액션이 토픽에 추가되었습니다. 이제 액션의 입력 구성을 시작합니다. **ellipsis (...) icon**을 선택하고 **Properties**를 선택합니다.

    ![Select Properties](assets/7.3_04_GetItemsProperties.png)

1. **Get items** 구성 패널이 나타나며 기본적으로 **Inputs** 탭이 표시됩니다. **Initiation** 탭을 선택하고 **Usage Description** 필드에 설명을 입력합니다. 다음을 복사하여 붙여넣으세요.

    ```text
    SharePoint 목록에서 장치를 검색합니다.
    ```

    > [!NOTE]
    > 이것은 나중에 에이전트의 _Manage your connections_ 페이지를 볼 때 유용합니다. 잠시 후 다시 확인합니다.

    ![Get items description](assets/7.3_05_UpdateDescription.png)

1. **Inputs** 탭을 선택하고 [Lesson 00 - Course Setup - Step 3: Create new SharePoint site](../00-course-setup/index.md#step-4-create-new-sharepoint-site)에서 설정한 **Contoso IT** 사이트와 **Devices** 리스트를 선택합니다.

    ![Configure Get items inputs](assets/7.3_06_GetItemsInputs.png)

1. 이제 SharePoint 리스트에서 선택한 값과 상태가 _Available_인 디바이스만 표시하려면 필터를 적용해야 합니다. Power Fx의 도움으로 필터 쿼리를 입력합니다. **ellipsis (...) icon**을 선택합니다.

    ![Select ellipsis icon](assets/7.3_07_SelectVariable.png)

1. 기본적으로 **Custom** 탭에 있습니다. **Formula** 탭을 선택합니다.

    ![Select Formula tab](assets/7.3_08_SelectFormula.png)

1. **expand** 아이콘을 선택하여 **Formula** 필드를 확대합니다. 다음 Power Fx 수식을 복사하여 붙여넣으세요.

    `Concatenate` 함수를 사용하여 SharePoint의 **Status** 열이 _Available_이고 **Asset type** 열이 _질문 노드에서 선택된 디바이스_와 같은 항목을 필터링하는 수식을 만듭니다.

    ```text
    Concatenate("Status eq '사용 가능' and AssetType eq '", Topic.VarDeviceType, "'")
    ```

    **Insert**를 선택합니다.

    ![Enter Power Fx expression and select insert](assets/7.3_09_EnterFormula.png)

1. Power Fx 수식이 **Get items** 액션의 Filter Query 입력 파라미터에 적용됩니다. 다음으로 **Limit Columns by View**에서 **All items** 뷰를 선택합니다. 이렇게 하면 선택된 뷰에 기반한 리스트의 열만 가져옵니다.

    ![List Columns by View](assets/7.3_10_LimitColumnsByView.png)

1. 다음으로 출력 변수의 이름을 업데이트합니다. **Outputs** 탭을 선택하고 `GetItems` 변수를 선택합니다.

    ![Update variable](assets/7.3_11_ConfigureOutputs.png)

1. 이름을 다음으로 업데이트합니다.

    ```text
    VarDevices
    ```

    ![Update variable name](assets/7.3_12_RenameVariable.png)

1. 아래로 스크롤하여 **Usage** 섹션에서 **Global**을 선택합니다. 이렇게 하면 모든 토픽에서 변수에 접근할 수 있습니다.

    ![Update to Global variable](assets/7.3_13_UpdateToGlobalVariable.png)

1. **Variable properties** 패널을 **Close**합니다.

    ![Close Variable properties pane](assets/7.3_14_ExitVariablePropertiesPane.png)

1. **plus +** 아이콘을 선택하여 새 노드를 삽입하고, **Variable management**를 선택한 뒤 **Set a variable value**를 선택합니다.

    ![Add Set a variable value node](assets/7.3_15_AddSetAVariableValueNode.png)

1. **Set variable** 입력 파라미터의 **greater than** 아이콘을 선택합니다.

    ![Set variable](assets/7.3_16_SelectAVariable.png)

1. 앞서 생성한 토픽 출력 변수인 **VarAvailableDevices**를 선택합니다.

    ![Save topic](assets/7.3_17_SelectVarAvailableDevices.png)

1. 다음으로 변수의 값을 정의합니다. **ellipsis (...) icon**을 선택합니다.

    ![Select variable value](assets/7.3_18_SelectVariable.png)

1. **Formula** 탭을 선택하고 **expand** 아이콘을 선택하여 **Formula** 필드를 확대합니다.

    ![Select Formula tab and select expand icon](assets/7.3_19_SelectFormulaTab.png)

1. 이제 PowerFx 수식을 사용하여 **Get items** 응답에서 반환된 `value` 속성을 변수 값으로 설정하고, `Global` 접두사를 추가하여 [변수의 범위](https://learn.microsoft.com/microsoft-copilot-studio/advanced-power-fx?WT.mc_id=power-172618-ebenitez)를 글로벌로 만듭니다.

    **Insert**를 선택합니다.

    ![Power Fx formula for variable value](assets/7.3_20_EnterFormula.png)

1. 이제 **To value** 필드에 Power Fx 수식이 설정된 것을 볼 수 있습니다.

    ![To value field](assets/7.3_21_Formula.png)

1. 다음으로 에이전트 지침을 업데이트해야 합니다. **Overview** 탭을 선택하고 **Edit**를 선택합니다.

    ![Edit instructions](assets/7.3_22_EditInstructions.png)

1. **디바이스 지원** 관련 **헤더** 아래의 다음 지침을 강조 표시하고 삭제합니다.

    ![Add instructions](assets/7.3_23_ClearInstructions.png)

1. 지침에 새 줄을 추가하고 다음을 복사하여 붙여넣으세요.

    ```text
    1. [사용 가능한 장치]를 사용하여 사용 가능한 장치를 찾고 자세한 정보를 제공합니다. 입력값에서 항상 VarDeviceType을 추출합니다. 장치 정보를 제공한 후, 사용자에게 사용 가능한 장치 목록에서 장치를 요청할지 묻습니다.
    ```

    이 지침은 생성형 AI가 **Available devices** 트리거를 호출하여 **Devices** SharePoint 리스트에서 사용 가능한 디바이스 목록을 표시하도록 안내합니다.

    ![Update instructions](assets/7.3_24_UpdateInstructions.png)

1. 대괄호 안의 전체 토픽 플레이스홀더를 선택합니다.

    ![Highlight placeholder](assets/7.3_25_HighlightPlaceholder.png)

1. 슬래시 문자 `/`를 입력하면 토픽 목록이 나타납니다. **Available devices** 토픽을 선택합니다.

    ![Reference trigger](assets/7.3_26_SelectAvailableDevicesTopic.png)

1. 이제 사용 가능한 디바이스에 대해 질문하면 에이전트가 토픽을 호출합니다. 업데이트된 지침을 **Save**합니다.

    ![Save instructions](assets/7.3_27_SaveUpdatedInstructions.png)

1. 이제 업데이트된 에이전트를 테스트합니다. 오른쪽 상단의 **Test**를 선택하여 테스트 패널을 표시하고 테스트 패널을 **refresh**합니다. 에이전트에 다음 메시지를 입력합니다.

    ```text
    I need a laptop
    ```

    ![Test](assets/7.3_28_NewTestSession.png)

1. 에이전트가 진행하기 전에 사용자의 연결 사용을 확인해야 합니다. **Allow**를 선택합니다.

    ![Select allow](assets/7.3_29_SelectAllow.png)

1. 에이전트가 Power Fx 수식을 사용하여 디바이스 유형이 "laptop"이고 상태가 "available"인 필터링된 디바이스 목록을 검색하는 SharePoint 도구를 실행합니다. 사용자가 읽을 수 있도록 글머리 기호 형식으로 응답이 반환됩니다.

    ![Response of test](assets/7.3_30_TestResponse.png)

1. 마지막으로 에이전트의 _Manage your connections_ 페이지를 통해 사용 중인 연결을 확인하는 방법을 알아봅니다. **ellipsis (...)**를 선택하고 **Manage Connection**을 선택합니다.

    ![Manage connection](assets/7.3_31_ManageConnections.png)

1. 이 페이지에서 에이전트가 사용하는 모든 연결을 볼 수 있습니다. 현재 토픽에 추가된 SharePoint 도구와 연관된 하나의 연결만 나열됩니다. **Used By** 열의 **1 tool**을 선택합니다.

    ![Used By](assets/7.3_32_UsedBy.png)

1. Get items 액션의 세부 정보를 볼 수 있으며, 앞서 입력한 _usage description_이 여기에 표시됩니다. **Close**를 선택합니다.

    > [!NOTE]
    > 이를 통해 어떤 액션이 사용되고 있는지와 그 목적을 알 수 있습니다. 연결을 체계적으로 관리할 수 있습니다 📁.

    ![Usage description](assets/7.3_33_UsedByInformation.png)

1. Copilot Studio가 열린 브라우저 탭으로 돌아가서 테스트 패널을 **refresh**하여 테스트를 클리어합니다.

## ✅ 미션 완료

축하합니다! 👏🏻 빈 토픽에서 새 토픽을 만드는 방법, Get items SharePoint 커넥터 액션을 호출하는 도구 추가, Power Fx를 활용하여 상태가 available이고 디바이스 타입이 laptop인 항목만 반환하도록 필터링하는 방법을 배웠습니다. 🙌🏻

이것으로 **Lab 07 - 대화 노드를 사용한 새 토픽 추가**가 끝났습니다. 아래 링크를 선택하여 다음 레슨으로 이동하세요. 다음 레슨의 랩에서 이번 랩의 유스케이스를 확장합니다.

⏭️ [Move to **Enhance user interactions with Adaptive Cards** lesson](../08-add-adaptive-card/index-kr.md)

## 📚 참고 자료

🔗 [Use system topics](https://learn.microsoft.com/microsoft-copilot-studio/authoring-system-topics?mc_id=power-172618-ebenitez)

🔗 [Topics in Microsoft Copilot Studio](https://learn.microsoft.com/microsoft-copilot-studio/guidance/topics-overview?WT.mc_id=power-172618-ebenitez)

🔗 [Set topic triggers](https://learn.microsoft.com/microsoft-copilot-studio/authoring-triggers?WT.mc_id=power-172618-ebenitez)

🔗 [Defining agent topics](https://learn.microsoft.com/microsoft-copilot-studio/guidance/defining-chatbot-topics?WT.mc_id=power-172618-ebenitez)

🔗 [Create expressions using Power Fx](https://learn.microsoft.com/microsoft-copilot-studio/advanced-power-fx?WT.mc_id=power-172618-ebenitez)

📺 [Author topics using natural language](https://aka.ms/ai-in-action/copilot-studio/ep6)

📺 [Add actions to agents using connectors](https://aka.ms/ai-in-action/copilot-studio/ep4)

<!-- markdownlint-disable-next-line MD033 -->
<img src="https://m365-visitor-stats.azurewebsites.net/agent-academy/recruit/07-add-new-topic-with-trigger" alt="Analytics" />
