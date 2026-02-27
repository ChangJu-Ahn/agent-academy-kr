# 🚨 미션 09: 자동화를 위해 Topic에 에이전트 플로우 추가하기

## 🕵️‍♂️ 코드네임: `OPERATION AUTOMATION POWERHOUSE`

> **⏱️ 작업 시간:** `~30 minutes`  

## 🎯 미션 브리프

이제 에이전트는 사용자와 대화하고 정보를 제공할 수 있지만, 진정한 운영 역량을 위해서는 에이전트가 실제로 **행동**할 수 있어야 합니다. 이 미션에서는 에이전트 플로우를 장착해 대화형 에이전트를 자동화의 강자로 바꿉니다.

미션이 끝나면, Adaptive Card로 사용자 입력을 수집하고, SharePoint에서 데이터를 조회하고, 이메일로 관리자에게 알림을 보내며, 사용자에게 자연스럽게 피드백까지 제공하는 **엔드-투-엔드 디바이스 요청 자동화**를 완성하게 됩니다. 이 모든 과정은 지능형 워크플로 자동화를 통해 에이전트가 오케스트레이션합니다.

## 🔎 목표

이번 미션에서 배우는 내용:

1. 자동화를 위해 에이전트 플로우가 무엇이며 Power Automate 클라우드 플로우와 어떻게 다른지 이해하기
1. AI 액션과 자연어 작성 기능 등 에이전트 플로우를 강력하게 만드는 핵심 기능 이해하기
1. 에이전트 플로우 디자이너 탐색 및 동적 데이터 처리를 위한 식(Expression) 사용 방법 알아보기
1. SharePoint 데이터와 이메일 알림을 통합한 완전한 디바이스 요청 자동화 만들기

## 🤔 에이전트 플로우란?

에이전트 플로우는 반복 작업을 자동화하고 앱/서비스를 통합하는 강력한 방법입니다. 에이전트가 실행할 수 있는 **구조화된 단계별 워크플로**라고 생각하면 됩니다. 예를 들어, 알림을 보내거나, 레코드를 업데이트하거나, 이벤트에 응답하는 작업을 에이전트가 수행하도록 도와주는 “미니 워크플로”입니다.

AI가 상황에 따라 즉석에서 의사결정을 하는 자율 에이전트와 달리, 에이전트 플로우는 **결정론적(deterministic) 워크플로**입니다. 즉, 동일한 입력이 주어지면 매번 동일한 경로를 따라 실행되어 일관되고 신뢰할 수 있는 결과를 보장합니다.

간단히 말하면:

- 사용자에게 _말만 하는 것_이 아니라, 에이전트가 _무언가를 하게_ 해줍니다.
- 토픽과 에이전트 전반에서 재사용 가능하며, 사용자 메시지/이벤트/다른 앱 및 서비스에 의해 트리거될 수 있습니다.

## 🙋🏽 그런데 Power Automate 클라우드 플로우와는 무엇이 다른가요?

에이전트 플로우와 Power Automate 클라우드 플로우는 모두 작업 자동화를 돕지만, 목적과 동작 방식이 다릅니다.

### 🤖 Copilot Studio의 에이전트 플로우

**용도:**

- Copilot Studio의 대화형/자율 에이전트(에이전트 지침을 통해)용으로 설계됨
- 비즈니스 시스템과 상호작용하는 스마트한 AI 기반 자동화에 초점

**장점:**

- Copilot Studio 내에서 직접 쉽게 만들고 관리 가능
- 사용자와의 _대화 중_ 발생하는 작업(예: 휴가 신청 제출) 자동화에 적합
- Copilot Studio 내부 사용량 기반 과금이므로 별도의 Power Automate 라이선스가 필요하지 않음(엔터프라이즈 팀의 시간/비용 절감 가능)

**제한 사항:**

- 공유, 복사, 공동 소유자(co-owner) 지정이 불가
- Copilot Studio 안에서만 보이고 사용할 수 있음
- 현재 에이전트의 이벤트 트리거는 Power Automate maker 포털에서 편집 가능

### ☁️ Power Automate 클라우드 플로우

**용도:**

- 다양한 앱과 서비스 전반에서 범용 자동화를 위해 설계됨
- 독립적으로 실행되거나, 에이전트 플로우와 함께 동작할 수 있음

**장점:**

- 매우 다양한 커넥터 제공
- 에이전트 외부 프로세스 자동화에 이상적
- 팀 차원에서 공유/재사용/관리 가능

**요구 사항:**

- 사용을 위해 Power Automate 라이선스가 필요

### 📗 요약

| 이것을 사용 | 이런 경우에 |
| :- | :- |
| 에이전트 플로우 | 에이전트 내부에서 작업을 자동화하고, AI를 활용하며, 모든 것을 Copilot Studio 안에서 유지하고 싶을 때 |  
| Power Automate 클라우드 플로우 | 여러 앱/서비스 전반을 자동화하거나, 에이전트 밖에서 워크플로를 구축하고 싶을 때 |

## 👍🏻 왜 에이전트 플로우를 사용하나요

에이전트 플로우는 고정된 경로를 항상 따릅니다. 동일한 입력이면 매번 동일하게 동작합니다.

따라서 다음과 같은 특성이 있습니다:

- **신뢰성** - 항상 같은 방식으로 동작한다고 믿을 수 있음
- **예측 가능성** - 플로우 실행 결과를 예상할 수 있음
- **규칙 기반** - 정의한 단계대로 실행됨

추가 장점:

- **자동화** - 폼 제출, 알림 발송 같은 반복 작업을 처리
- **연결성** - ServiceNow, SharePoint, Salesforce 등 1400+ 커넥터와 연결(또는 커스텀 커넥터 제작 가능)
- **강한 통합** - 에이전트 로직의 일부로서, 대화 중 사용자 메시지/액션으로 직접 트리거됨
- **확장성** - 여러 에이전트/시나리오에서 재사용 가능
- **노코드/로우코드** - 자연어 또는 비주얼 디자이너로 구축
- **올인원 플랫폼** - Copilot Studio 한 곳에서 설계/테스트/배포 가능(플랫폼 전환 불필요)

## 🏄🏻‍♂️ 에이전트 플로우는 에이전트를 어떻게 강화하나요?

에이전트 플로우는 단순히 사용자와 “채팅”하는 것을 넘어, 실제로 행동하고 시스템과 상호작용할 수 있게 해줍니다.

예를 들어 재무 부서에서 벤더로부터 많은 인보이스를 받는다고 가정해봅시다. 보통은 누군가가 인보이스를 읽고, 금액/날짜/발신자 같은 핵심 정보를 추출한 다음, 기록과 대조해 맞는지 확인하고, 승인 담당자에게 전달합니다. 시간과 노력이 많이 들고 실수도 생길 수 있습니다.

Copilot Studio의 에이전트 플로우를 사용하면, 인보이스가 들어오는 즉시 에이전트가 다음을 자동으로 수행할 수 있습니다:

1. 지능형 문서 처리를 통해 문서를 읽고 핵심 정보를 찾음
1. 엔터프라이즈 데이터와 대조해 내용이 올바른지 확인
1. 적절한 담당자에게 승인 요청 라우팅

이로 인해 시간을 절약하고 실수를 줄이며 전체 프로세스를 훨씬 매끄럽게 만들 수 있습니다.

### 이렇게 생각해보세요

- **에이전트(Agents)**: 똑똑한 의사결정자
- **에이전트 플로우(Agent flows)**: 신뢰할 수 있는 실행자

### 왜 중요한가요

- 신뢰성 있는 자동화와 유연한 AI를 동시에 얻을 수 있습니다.
- 비즈니스 요구가 바뀌어도 플로우를 쉽게 만들고 업데이트할 수 있습니다.
- 팀 전반에 걸쳐 자동화를 확장할 수 있습니다.

## 🔌 에이전트 플로우를 강력하게 만드는 핵심 기능

1. **자연어 작성(Natural language authoring)**
    - 플로우가 해야 할 일을 평문 영어로 설명하면 됨
    - Copilot이 의도를 이해하고 플로우를 구성
    - 코드 작성 없이 아이디어를 설명

1. **AI 액션(AI actions)**

    AI로 다음을 수행할 수 있습니다:

    - 문서나 이미지를 읽고 이해
    - 긴 내용을 짧고 유용한 답으로 요약
    - 스마트한 추천 또는 의사결정

1. **생성형 액션(Generative actions)**
    - 플로우가 실시간으로 적응할 수 있게 함
    - 변화하는 정보에 맞춰 단계들을 계획/조정 가능

1. **통합 액션(Integration actions)**
    - Outlook, Microsoft Teams, ServiceNow, SharePoint 등 다양한 앱/서비스와 연결(+1400 기본 커넥터 또는 커스텀 커넥터)
    - 팀이 이미 사용하는 앱과 함께 에이전트를 동작시키는 데 유리

1. **휴먼 인 더 루프(Human in the loop)**
    - 사람이 검토하거나 확인해야 하는 승인 단계를 추가
    - [고급 승인](https://learn.microsoft.com/microsoft-copilot-studio/flows-advanced-approvals?WT.mc_id=power-172621-ebenitez)은 리마인더, 위임, 다단계 승인 등을 지원

## ⚙️ 동작 방식

1. **트리거(Trigger)**

    사용자 질문, 토픽에서 플로우 호출, 예약 시간, 또는 다른 시스템에서의 이벤트 발생 등 어떤 이벤트가 플로우를 시작합니다.

1. **액션(Actions)**

    이후 에이전트가 따라가는 단계들입니다. 예: 이메일 전송, API 호출, ServiceNow 티켓 업데이트 등.

## 🧶 에이전트 플로우 만들기

1. **자연어**: 에이전트가 해야 할 일을 설명하면 Copilot이 플로우를 생성
1. **디자이너 캔버스**: 에이전트 플로우 디자이너에서 액션/조건/루프를 드래그 앤 드롭으로 구성

## 🎨 에이전트 플로우 디자이너란?

Copilot Studio의 비주얼 도구로, 에이전트가 작업을 완료하기 위해 따라야 하는 단계별 지침을 제공하는 에이전트 플로우를 만들고/편집하고/관리할 수 있습니다. 에이전트 플로우가 처음이어도 쉽게 사용할 수 있도록 설계되었습니다.

### 에이전트 플로우 디자이너의 주요 기능

1. **비주얼 캔버스**
    - 전체 플로우를 다이어그램처럼 한눈에 확인
    - 줌 인/아웃, 화면 맞춤, 미니맵으로 큰 플로우도 탐색 가능

1. **액션 추가/제거**
    - _플러스(+) 버튼_으로 메시지 전송, SharePoint 리스트 항목 업데이트 같은 액션 추가
    - 커넥터 액션을 검색하고 설정에서 구성 가능
    - 삭제하려면 _세 점(⋮)_을 클릭하고 _Delete_ 선택

1. **파라미터 확인**
    - 액션을 클릭해 설정(= _parameters_)을 확인/편집
    - 값을 직접 입력하거나 _expressions_로 동적 처리 가능

1. **버전 기록(Version history)**
    - 저장할 때마다 버전이 기록됨
    - 필요 시 이전 버전 보기/복원 가능

1. **오류 검사(Error checking)**
    - _Flow Checker_가 오류를 하이라이트
    - 플로우 게시 전 모든 오류를 해결해야 함

1. **게시 및 테스트(Publish and test)**
    - 오류가 없으면 게시하여 라이브로 전환
    - _Test_ 기능으로 수동/자동 실행 후 정상 동작 확인

### 왜 에이전트 플로우 디자이너를 사용하나요?

- **비주얼하고 직관적** - 드래그/클릭으로 플로우 구성
- **안전하게 실험 가능** - 버전 기록으로 변경 사항 되돌리기 가능
- **내장 테스트** - 실제 배포 전에 동작 확인

## 🔤 _expressions_를 언급했는데, expressions는 무엇인가요?

Expressions는 에이전트 플로우가 데이터를 다루도록 돕는 작은 수식/명령입니다. 값 계산, 텍스트 포맷, 의사결정, 입력에서 특정 정보 추출 등에 사용합니다.

### 왜 expressions를 사용하나요?

Expressions로 다음이 가능합니다:

- **데이터 처리 커스터마이징** - 이름 결합, 날짜 형식 지정
- **의사결정** - 값이 10보다 크면 특정 동작 수행
- **데이터 변환** - 소문자로 변환, 문자열 일부 추출
- **로직 자동화** - 전체 코드를 쓰지 않고도 로직 구현

### expressions는 어떤 형태인가요?

Expressions는 함수(function)를 사용합니다. 전 Microsoft MVP Jerry Weinstock의 함수 설명을 일부 빌려 설명하겠습니다.

표현식은 함수를 사용합니다. 전 Microsoft MVP Jerry Weinstock의 함수 설명 일부를 설명하겠습니다.

!!! 인용문
함수는 표현식에서 간단하거나 복잡한 연산을 통해 데이터를 변환하는 내장 논리입니다.

함수를 사용하면 코드를 작성하지 않고도 표현식을 만들 수 있습니다.

제가 좋아하는 설명 방식은 에이전트 흐름의 함수가 Excel 함수와 유사하다는 것입니다. 데이터에 연산을 수행하여 원하는 출력으로 변환할 수 있습니다. Excel에서 수식을 만들 때는 표 또는 범위의 셀에서 입력 값을 선택한 다음 함수를 적용하여 데이터 출력을 조작합니다. 예를 들어 `COUNT` 함수를 사용하여 범위에서 숫자가 포함된 셀의 수를 계산할 수 있습니다.

에이전트 흐름에서는 표의 셀에서 데이터를 참조하는 대신 표현식을 만들 때 트리거 또는 작업의 데이터 출력을 참조합니다. 이전 예제를 계속해서 `length` 함수를 사용하여 SharePoint 커넥터 작업인 '항목 가져오기'에서 반환된 항목 수를 가져올 수 있습니다.

### 왜 함수가 중요한가요?

함수를 사용하면 에이전트 플로우는:

- **더 똑똑해집니다** - 다양한 입력/조건에 반응 가능
- **더 유연해집니다** - 데이터 처리 방식을 커스터마이징
- **더 효율적입니다** - 로직을 자동화해 수작업을 줄임

### 가장 유용한 함수들

아래는 에이전트 플로우에서 자주 쓰는 함수들입니다. 전체 목록은 [레퍼런스 가이드](https://learn.microsoft.com/azure/logic-apps/workflow-definition-language-functions-reference?WT.mc_id=power-172621-ebenitez)를 참고하세요.

#### 🔡 텍스트

- `concat()` - 두 개 이상의 텍스트 조각을 결합합니다.
      - 예: `concat('Hello ', firstName)` → “Hello John”

- `toLower()` / `toUpper()` - 텍스트를 소문자/대문자로 변경합니다.
      - 입력 표준화에 유용합니다.

- `substring()` - 문자열의 일부를 추출합니다.
      - 예: 이름의 첫 3글자 가져오기

- `trim()` - 텍스트 앞뒤 공백을 제거합니다.

#### 🔢 수학/숫자

- `add()`, `sub()`, `mul()`, `div()` - 기본 수학 연산.
      - 예: `add(5, 3)` - 결과는 8

#### 📅 날짜/시간

- `utcNow()` - UTC 기준 현재 날짜/시간을 가져옵니다.
      - 타임스탬프에 유용합니다.

- `addDays()`, `addHours()` - 날짜에 시간을 더합니다.
      - 예: `addDays(utcNow(), 7)` 결과는 7일 후

- `formatDateTime()` - 날짜를 읽기 쉬운 문자열로 포맷합니다.
      - 예: Monday, July 7, 2025

#### ✅ 논리

- `if()` - true면 한 값을, false면 다른 값을 실행합니다.
      - 예: `if(score > 50, 'Pass', 'Fail')`

- `equals()` - 두 값이 같은지 확인합니다.

- `and()`, `or()`, `not()` - 여러 조건을 결합합니다.

#### 🪣 기타 유용한 함수

- `coalesce()` - 비어있지 않은 첫 값을 반환합니다.
      - 기본값/대체값 처리에 유용합니다.

- `guid()` - 고유 ID를 생성합니다.
      - 추적/로깅에 유용합니다.

- `length()` - 문자열 또는 배열의 문자/아이템 개수를 셉니다.

## ⭐ 모범 사례

Copilot Studio에서 에이전트 플로우를 만들 때의 모범 사례입니다.

1. **단순하게 시작하고 점진적으로 확장**

    - 메시지 전송 같은 작고 명확한 작업부터 시작
    - 자동화의 기본을 테스트한 뒤 단계 추가

1. **명확하고 설명적인 액션 이름 사용**

    - 각 단계를 명확히 라벨링해 자신과 팀이 쉽게 이해하도록 함
    - 예: SharePoint 커넥터의 기본 "Update item" 대신, "Update device status"처럼 무엇을 업데이트하는지 이름 변경

1. **게시 전에 오류 확인**

    - **flow checker**로 이슈를 찾고 수정
    - 오류가 있으면 게시할 수 없으므로 발생 시 해결

1. **충분히 테스트**

    - 저장/게시가 된다고 해서 기대대로 동작한다는 뜻은 아님
    - _Test_ 기능으로 수동/자동 실행 후 결과 확인

1. **버전 기록 사용**

    - 자주 저장해 필요 시 이전 버전으로 되돌릴 수 있게 함
    - _Version History_ 패널에서 이전 버전 보기/복원 가능

1. **파라미터와 expressions를 현명하게 사용**

    - 액션 구성 시 파라미터로 플로우를 동적으로 만들기
    - 값을 직접 입력하거나 expressions로 계산/결합(상위 액션의 값은 _dynamic content_ picker로 추가)

1. **사용하지 않는 액션 삭제**

    - 불필요해진 액션은 삭제해 플로우를 깔끔하게 유지

## 🧪 Lab 09 - 자동화를 위한 에이전트 플로우 추가 및 토픽 기능 강화

이제 Adaptive Cards와 토픽/노드의 고급 기능을 활용해 토픽을 강화하는 방법을 배웁니다.

### ✨ 유스케이스

**As a** 관리자(직원의)

**I want to** 디바이스 요청을 받기

**So that I** 직원이 요청한 디바이스를 검토할 수 있다.

시작해봅시다!

### 사전 준비 사항

1. **SharePoint 리스트**

    [Lesson 00 - Course Setup - Step 3: Create new SharePoint site](../00-course-setup/index.md#step-4-create-new-sharepoint-site)에서 만든 Contoso IT SharePoint 사이트의 **Devices** SharePoint 리스트를 사용합니다.

    **Devices** 리스트를 아직 만들지 않았다면, 위 레슨으로 돌아가 설정을 완료하세요.

1. **Contoso Helpdesk Agent**

    이전에 [Lesson 06 - Create a custom agent using natural language with AI and grounding it with your data](../06-create-agent-from-conversation/index.md)에서 만든 동일한 에이전트를 사용합니다.

### 9.1 에이전트 플로우 만들기

이 실습에서는 선택된 디바이스의 SharePoint 항목을 가져오고, 디바이스 상세 정보를 담아 관리자에게 이메일을 보내는 에이전트 플로우를 만듭니다.

1. **Request device** 토픽에서 **Ask with adaptive card** 노드까지 스크롤한 뒤 새 노드를 추가합니다. **Add a tool**을 선택하고, **Basic tools** 탭의 플라이아웃에서 **New Agent flow**를 선택합니다.

    ![새 Agent flow 추가](./assets/9.1_01_AddNewAgentFlow.png)

1. Agent flows **Designer**가 트리거와 액션이 포함된 상태로 로드됩니다.

    - **Trigger** - When an agent calls the flow
        - Copilot Studio 에이전트에서 플로우를 트리거합니다.

    - **Action** - Respond to the agent
        - Copilot Studio 에이전트로 다시 전달될 수 있는 출력 값을 포함한 응답을 보냅니다.

    트리거를 선택합니다.

    ![트리거 선택](./assets/9.1_02_SelectTrigger.png)

1. 이제 에이전트 플로우에 여러 입력을 추가합니다.

    - `DeviceSharePointId` - SharePoint 항목의 ID 값을 저장합니다. 이 값은 사용자가 디바이스를 선택한 **Ask with adaptive card** 노드의 출력입니다.

    - `User` - 에이전트의 시스템 변수에서 가져오는 사용자 이름입니다.

    - `AdditionalComments` - 사용자가 입력한 코멘트로, **Ask with adaptive card** 노드의 출력입니다.

    먼저 트리거 입력으로 `DeviceSharePointId`를 추가합니다. **+ Add an input**을 선택합니다.

    ![입력 추가](./assets/9.1_03_AddInput.png)

1. 사용자 입력 타입으로 **Text**를 선택합니다.

    ![Text 선택](./assets/9.1_04_SelectText.png)

1. 입력 이름으로 아래를 입력합니다.

    ```text
    DeviceSharePointId
    ```

    ![DeviceSharePointId 입력](./assets/9.1_05_DeviceSharePointIdInput.png)

1. 두 번째 입력 `User`를 추가합니다. 동일한 단계로 **+ Add an input**을 선택하고 **Text**를 선택합니다.

    ![입력 추가](./assets/9.1_06_AddInput.png)

1. 입력 이름으로 아래를 입력합니다.

    ```text
    User
    ```

    ![User 입력](./assets/9.1_07_UserInput.png)

1. 세 번째 입력 `AdditionalComments`를 추가합니다. 동일한 단계로 **+ Add an input**을 선택하고 **Text**를 선택합니다.

    ![입력 추가](./assets/9.1_08_AddInput.png)

1. 입력 이름으로 아래를 입력합니다.

    ```text
    AdditionalComments
    ```

    ![AdditionalComments 입력](./assets/9.1_09_AdditionalComments.png)

1. `AdditionalComments` 입력을 선택적으로 만들기 위해 **ellipsis (...) icon**을 선택하고 **Make the field optional**을 선택합니다.

    ![선택 입력으로 변경](./assets/9.1_10_Optional.png)

1. 훌륭합니다! 트리거 구성이 완료되었습니다. 이제 트리거 아래의 **plus + icon**을 선택해 새 액션을 삽입합니다.

    ![액션 추가](./assets/9.1_11_AddAction.png)

1. **Actions pane**가 나타나며 1400+ 기본 커넥터의 액션을 볼 수 있습니다. **search field**에 아래를 입력합니다.

    ```text
    Get item
    ```

    검색 결과에서 **SharePoint connector**의 **Get item** 액션을 선택합니다.

    ![Get item 액션](./assets/9.1_12_AddGetItemAction.png)

1. 이제 **Get item** 액션을 구성합니다.

    **Get item** 액션의 **Ellipsis (...)** 아이콘을 선택합니다.

    ![ellipsis 선택](./assets/9.1_13_SelectEllipsis.png)

1. **Rename**을 선택합니다.

    ![Rename 선택](./assets/9.1_14_SelectRename.png)

1. 액션 이름을 아래처럼 변경합니다.

    ```text
    Get Device
    ```

    ![액션 이름 변경](./assets/9.1_15_RenameAction.png)

1. **Site Address** 필드에서 [Lesson 00 - Course Setup - Step 3: Create new SharePoint site](../00-course-setup/index.md#step-4-create-new-sharepoint-site)에서 만든 Contoso IT SharePoint 사이트의 **Site address**를 선택합니다.

    **List Name** 필드에서 **Devices** SharePoint 리스트를 선택합니다.

    ![입력 파라미터](./assets/9.1_16_SharePointSiteAndListParameters.png)

1. **Id** 필드 오른쪽의 **lightning bolt icon** 또는 **fx icon**을 선택합니다.

    ![동적 콘텐츠 선택기](./assets/9.1_17_InsertExpressionIcon.png)

1. 플라이아웃의 **Dynamic content** 탭에서 아래를 입력합니다.

    ```text
    id
    ```

    검색 결과에서 트리거의 **DeviceSharePointId** 파라미터를 선택합니다.

    다음으로 **Add**를 선택하여 **Id** 파라미터에 동적 콘텐츠 입력을 추가합니다.

    ![DeviceSharePointId 입력 선택](./assets/9.1_18_DeviceSharePointId.png)

1. 트리거의 동적 콘텐츠 입력이 **Id** 파라미터에 참조되었습니다. 이제 고급 파라미터를 하나 업데이트합니다. **Show all**을 선택해 고급 파라미터를 표시합니다.

    ![고급 파라미터 보기](./assets/9.1_19_AdvancedParameters.png)

1. **Limit Columns by View** 파라미터가 표시되며 기본값은 **Use all columns (Do not limit)** 입니다. 반환되는 컬럼을 제한하기 위해 뷰를 선택하도록 변경합니다. **Limit Columns by View** 파라미터를 선택해 뷰 목록을 엽니다.

    ![파라미터 선택](./assets/9.1_20_LimitColumnsByView.png)

1. **All Items** 뷰를 선택합니다.

    ![All Items 뷰 선택](./assets/9.1_21_SelectView.png)

1. _Get Device_ 액션 아래의 **plus + icon**을 선택해 새 액션을 삽입합니다.

    ![새 액션 추가](./assets/9.1_22_AddAnAction.png)

1. **search field**에 아래를 입력합니다.

    ```text
    send an email
    ```

    검색 결과에서 **Office 365 Outlook connector**의 **Send an email (V2)** 액션을 선택합니다.

    ![Send an email 액션](./assets/9.1_23_SendAnEmail.png)

1. 커넥터 연결이 없다면 **Sign in**을 선택해 로그인된 계정을 사용하여 연결을 생성합니다.

    액션 이름을 아래로 변경합니다.

    ```text
    Send an email to manager
    ```

    이제 액션의 입력 파라미터를 정의합니다.

    **To** 입력 파라미터에는 본인을 선택합니다. 일반적으로는 관리자이거나 Entra ID 프로필에서 관리자를 가져오는 다른 액션을 사용하겠지만, 이 레슨에서는 본인을 선택합니다.

    **Subject** 입력 파라미터에는 아래를 입력합니다.

    ```text
    요청 타입: 신규 디바이스
    ```

    **Body** 입력 파라미터에는 아래를 입력합니다.

    ```text
    안녕하세요,
    다음 업체에서 새 장치를 요청했습니다.
    
    제조사:
    
    모델명:
    
    SharePoint의 해당 항목 링크
    추가 의견:
    
    이 이메일은 Contoso 헬프데스크 담당자가 자동으로 발송한 메시지입니다.
    ```

    ![액션 이름 변경 및 입력 구성](./assets/9.1_24_RenameAndConfigureParameters.png)

1. 이제 **Body** 입력 파라미터를 트리거 또는 **Get item** 액션의 동적 콘텐츠 참조로 업데이트합니다. 두 번째 줄 뒤에 공백을 하나 입력한 뒤, 트리거 입력 **User**의 사용자 이름을 삽입합니다.

    오른쪽의 **lightning bolt icon** 또는 **fx icon**을 선택합니다.

    ![User 입력을 동적 콘텐츠로 추가](./assets/9.1_25_AddUserInput.png)

1. 플라이아웃의 **Dynamic content** 탭에서 트리거의 **User** 입력을 선택합니다. **Add**를 선택해 **Body** 파라미터에 **User** 입력을 추가합니다.

    ![User 입력 선택](./assets/9.1_26_SelectUserInput.png)

1. 트리거의 동적 콘텐츠 입력이 **Body** 파라미터에 참조되었습니다. 이메일 본문의 나머지 줄도 동일하게 반복합니다.

    ![User 입력 추가됨](./assets/9.1_27_UserInputAdded.png)

1. `Manufacturer:` 옆의 빈칸을 클릭합니다. 오른쪽의 **lightning bolt icon** 또는 **fx icon**을 선택합니다.

    플라이아웃의 **Dynamic content** 탭에서 검색창에 아래를 입력합니다.

    ```text
    manufacturer
    ```

    트리거의 **Manufacturer value** 입력을 선택하고 **Add**를 선택합니다.

    ![Manufacturer value 입력을 동적 콘텐츠로 추가](./assets/9.1_28_ManufacturerValueAdded.png)

1. `Model:` 옆의 빈칸을 클릭합니다. 오른쪽의 **lightning bolt icon** 또는 **fx icon**을 선택합니다.

    플라이아웃의 **Dynamic content** 탭에서 검색창에 아래를 입력합니다.

    ```text
    model
    ```

    **Get item** 액션의 **Model** 입력을 선택하고 **Add**를 선택합니다.

    ![Model 입력을 동적 콘텐츠로 추가](./assets/9.1_29_ModelAdded.png)

1. `Link to item in SharePoint` 텍스트는 이메일 본문에서 하이퍼링크로 바꿉니다.

1. **&lt;/&gt;** 아이콘을 선택해 HTML 편집기로 전환합니다.

    ![코드 뷰 전환](./assets/9.1_30_ToggleCodeView.png)

1. HTML 편집기가 활성화되었습니다. `Link to item in SharePoint` 텍스트 앞을 클릭한 뒤, 하이퍼링크 생성을 위해 HTML 앵커 태그를 추가합니다. 아래를 복사해 붙여넣습니다.

    ```text
    <a href="
    ```

    ![HTML 태그](./assets/9.1_31_AddHTMLTag.png)

1. HTML 앵커 태그(`<a href="`) 뒤를 클릭하고 오른쪽의 **lightning bolt icon** 또는 **fx icon**을 선택합니다.

    플라이아웃의 **Dynamic content** 탭에서 검색창에 아래를 입력합니다.

    ```text
    link to item
    ```

    **Get item** 액션의 **Link to item** 입력을 선택하고 **Add**를 선택합니다.

    ![Link to item을 동적 콘텐츠로 추가](./assets/9.1_32_AddLinkToItem.png)

1. 이제 **Link to item** 동적 콘텐츠 입력이 **Body** 파라미터에 참조되었습니다.

    ![Link to item 파라미터 추가됨](./assets/9.1_33_LinkToItemAdded.png)

1. **Link to item** 입력 뒤를 클릭하고 아래를 복사해 붙여넣습니다.

    ```text
    ">
    ```

    ![HTML 태그](./assets/9.1_34_AddHTMLTag.png)

1. `Link to item in SharePoint` 텍스트 뒤를 클릭합니다.

    ![텍스트 뒤 클릭](./assets/9.1_35_ClickAfterText.png)

1. 하이퍼링크를 마무리하려면 HTML 앵커 태그를 닫아야 합니다. 아래를 복사해 붙여넣습니다.

    ```text
    </a>
    ```

    ![앵커 태그 닫기](./assets/9.1_36_ClosingAnchorTag.png)

1. 이메일 본문에 하이퍼링크 추가가 완료되었습니다 😎 **&lt;/&gt;** 아이콘을 선택해 코드 뷰를 다시 전환합니다.

    ![코드 뷰 전환](./assets/9.1_37_ToggleCodeView.png)

1. `Additional comments from` 텍스트에서 콜론(`:`) 앞을 클릭하고 오른쪽의 **lightning bolt icon** 또는 **fx icon**을 선택합니다.

    ![User 파라미터 추가](./assets/9.1_38_AddUserInput.png)

1. 플라이아웃의 **Dynamic content** 탭에서 검색창에 아래를 입력합니다.

    ```text
    user
    ```

    트리거의 **User** 파라미터를 선택하고 **Add**를 선택합니다.

    ![User 파라미터를 동적 콘텐츠로 추가](./assets/9.1_39_AddUserDynamicContent.png)

1. 이제 사용자에게 Additional Comments가 제공되었으면 그 값을 표시하고, 코멘트가 없으면 "None"을 표시하는 expression을 삽입합니다.

    콜론 뒤를 클릭하고 오른쪽의 **lightning bolt icon** 또는 **fx icon**을 선택합니다.

    ![expression 추가](./assets/9.1_40_AddExpression.png)

1. 플라이아웃의 **Function** 탭에서 위 expression 입력 필드에 아래를 입력합니다.

    ```text
    if(empty())
    ```

    이 expression은 `if` 함수를 사용한 if-else 문입니다.

    다음으로 `empty` 함수는 문자열 파라미터에 값이 있는지 여부를 확인합니다. 참조할 문자열 파라미터는 트리거의 `AdditionalComments` 입력 파라미터 값입니다.

    ![If empty](./assets/9.1_41_IfEmptyFunctions.png)

1. 다음으로 `empty` 함수 뒤의 **괄호 안**을 클릭합니다. 트리거의 `AdditionalComments` 입력 파라미터를 삽입합니다.

    **Dynamic content** 탭을 선택하고 검색창에 아래를 입력합니다.

    ```text
    Additional
    ```

    패널을 아래로 스크롤해 트리거의 **AdditionalComments** 입력을 선택합니다. 파라미터가 expression의 문자열 파라미터로 추가됩니다.

    ![AdditionalComments를 동적 콘텐츠로 추가](./assets/9.1_42_AdditionalCommentsDynamicContent.png)

1. 이제 **_true_** 로직을 정의합니다. `AdditionalComments` 문자열 파라미터가 비어 있으면 `None` 문자열을 표시합니다.

    문자열 파라미터를 감싸는 괄호 뒤에 아래를 입력합니다.

    ```text
    , 'None',
    ```

    ![True 로직](./assets/9.1_43_None.png)

1. 마지막으로 **_false_** 로직을 정의합니다. `AdditionalComments` 문자열 파라미터가 비어 있지 않으면 트리거의 **AdditionalComments** 입력 파라미터 값을 표시합니다.

    > [!NOTE]
    > 이 값은 **Request device** 토픽의 **Ask with adaptive card** 노드에서 Adaptive Card의 Additional Comments 필드에서 가져옵니다.

    **_true_** 로직 뒤의 콤마 다음에서 **Dynamic content** 탭을 선택하고 검색창에 아래를 입력합니다.

    ```text
    Additional
    ```

    패널을 아래로 스크롤해 트리거의 **AdditionalComments** 입력을 선택합니다. 파라미터가 expression의 문자열 파라미터로 추가됩니다.

    이제 **Add**를 선택해 **Body** 파라미터에 추가합니다.

    ![False 로직](./assets/9.1_44_AdditionalCommentsDynamicContent.png)

1. 훌륭합니다. expression이 완성되었습니다! 이제 expression이 **Body** 파라미터에 추가되었습니다. 마지막으로 마지막 줄을 이탤릭체로 포맷합니다.

    ![이탤릭](./assets/9.1_45_Italics.png)

1. 이제 **Respond to the agent** 액션을 업데이트하여 **Get item** 액션의 **Model value** 파라미터 값을 에이전트로 되돌려 보내겠습니다.

    마우스 왼쪽 버튼을 누른 채 디자이너에서 위로 이동해 **Respond to the agent** 액션이 보이도록 합니다.

    **Respond to the agent** 액션을 선택하고 출력 타입으로 **Text**를 선택합니다.

    ![Text 출력 선택](./assets/9.1_46_RespondToTheAgentAction.png)

1. 출력 이름으로 아래를 입력합니다.

    ```text
    ModelValue
    ```

    ![ModelValue 출력](./assets/9.1_47_ModelValueInput.png)

1. 값 필드를 선택하고 오른쪽의 **lightning bolt icon** 또는 **fx icon**을 선택합니다.

    플라이아웃의 **Dynamic content** 탭에서 검색창에 아래를 입력합니다.

    ```text
    model
    ```

    **Get item** 액션의 **Model** 파라미터를 선택하고 **Add**를 선택합니다.

    ![Model 파라미터를 동적 콘텐츠로 추가](./assets/9.1_48_InsertModelDynamicContent.png)

1. 이제 **Model** 파라미터가 텍스트 출력의 값이 되었습니다. **Save draft**를 선택해 에이전트 플로우를 저장합니다.

    에이전트 플로우를 완료했습니다 👏🏻

    ![Save draft 선택](./assets/9.1_49_SaveDraftAgentFlow.png)

1. 게시 전에 에이전트 플로우를 한 번 더 업데이트합니다. **Overview** 탭에서 **Edit**를 선택합니다.

    ![Edit 선택](./assets/9.1_50_EditAgentFlowDetails.png)

1. **Flow name**에 아래를 복사해 붙여넣습니다.

    ```text
    Send device request email
    ```

    **Description**에는 아래를 복사해 붙여넣습니다.

    ```text
    This flow starts when an agent manually triggers it and provides device and user details. It retrieves device information from a SharePoint list using the provided device ID. After successfully getting the device details, it sends an email to a manager with the request information, and sends a value back to the agent.
    ```

    **Save**를 선택해 플로우 이름/설명 업데이트를 저장합니다.

    ![이름 변경, 설명 추가, 세부 정보 저장](./assets/9.1_51_RenameAndDescription.png)

1. **Designer** 탭으로 돌아가 **Publish**를 선택해 에이전트 플로우를 게시합니다. 게시된 플로우는 **Request device** 토픽에서 노드로 추가할 수 있습니다.

    ![Publish](./assets/9.1_52_Publish.png)

1. 잠시 후 에이전트 플로우가 게시되었다는 확인 메시지가 표시됩니다.

    ![확인 메시지](./assets/9.1_53_Confirmation.png)

### 9.2 토픽에 에이전트 플로우 추가

이제 **Request device** 토픽에 에이전트 플로우를 추가합니다.

1. 왼쪽 메뉴에서 **Agents**를 선택하고 **Contoso Helpdesk Agent**를 선택합니다.

    ![Agents 선택](./assets/9.2_01_SelectAgent.png)

1. **Topics** 탭을 선택합니다.

    ![Topics 탭 선택](./assets/9.2_02_SelectTopics.png)

1. 다음으로 **Request device** 토픽을 선택합니다.

    ![Request device 토픽 선택](./assets/9.2_03_SelectRequestDevice.png)

1. **Ask with adaptive card** 노드까지 스크롤한 뒤 새 노드를 추가합니다.

    **Add a tool**을 선택하고, 플라이아웃의 **Basic tools** 탭에서 방금 생성/게시한 **Send device request email** 에이전트 플로우를 선택합니다. 앞서 입력한 설명도 함께 표시되는 것을 확인하세요(노란색 하이라이트).

    ![에이전트 플로우 선택](./assets/9.2_04_SelectAgentFlow.png)

1. 에이전트 플로우의 트리거 입력에는 **Ask with adaptive card** 노드의 변수 출력값을 연결해야 합니다.

    **DeviceSharePointId** 입력의 **ellipsis (...) icon**을 선택합니다.

    ![변수 선택](./assets/9.2_05_SelectVariable.png)

1. **Ask with adaptive card** 노드에서 정의된 출력 중 하나인 **deviceSelectionId** 변수를 선택합니다.

    ![deviceSelectionId 선택](./assets/9.2_06_SelectdeviceSelectionIdVariable.png)

1. 다음으로 **User** 입력의 **ellipsis (...) icon**을 선택합니다.

    ![변수 선택](./assets/9.2_07_SelectVariable.png)

1. 플라이아웃 변수 패널에서 **System** 탭을 선택하고 **User.DisplayName** 변수를 선택합니다. 이 변수는 에이전트와 상호작용하는 내부 사용자의 표시 이름을 저장합니다.

    ![User.DisplayName 시스템 변수 선택](./assets/9.2_08_SelectUser.DisplayNameVariable.png)

1. 다음으로 **Advanced inputs**의 **greater than icon**을 선택해 확장하고 **AdditionalComments** 입력을 표시합니다.

    ![고급 입력 확장](./assets/9.2_09_ExpandAdvancedInputs.png)

1. AdditionalComments 입력의 **ellipsis (...) icon**을 선택합니다.

    ![변수 선택](./assets/9.2_10_SelectVariable.png)

1. 플라이아웃 변수 패널에서 **Formula** 탭과 확장 아이콘을 선택합니다. Power Fx expression을 사용할 것입니다.

    ![Formula 탭 및 확장 아이콘 선택](./assets/9.2_11_SelectFormulaAndExpandIcon.png)

1. 에이전트 플로우에서의 _if_ 함수 조건 검사와 유사하지만 이번에는
    - Power Fx 함수를 사용하고,
    - **Ask with adaptive card** 노드의 `commentsId` 출력 변수가 비어있으면 값 없음, 비어있지 않으면 해당 값을 삽입합니다.

    Power Fx 필드에 아래 함수를 입력합니다.

    ```text
    If(IsBlank())
    ```

    이 expression은 `If` 함수를 사용한 if-else 문입니다.

    다음 `IsBlank` 함수는 문자열 파라미터에 값이 존재하는지 여부를 확인합니다. 참조할 문자열 파라미터는 **Ask with adaptive card** 노드의 `commentsId` 출력 변수입니다.

    ![If 및 IsBlank 함수](./assets/9.2_12_IfIsBlank.png)

1. 다음으로 `IsBlank` 함수 뒤 괄호 안을 클릭합니다. **Ask with adaptive card** 노드의 `commentsId` 출력 변수를 삽입합니다.

    괄호 안에 아래를 입력합니다.

    ```text
    Topic.commentsId
    ```

    그리고 괄호 뒤에 콤마를 추가합니다.

    ![commentsId 출력 참조](./assets/9.2_13_Topic.commentsId.png)

1. 이제 로직을 정의합니다.

    - **_true_** - `Topic.commentsId` 문자열 파라미터가 비어 있으면 아무 값도 삽입하지 않음
    - **_false_** - 비어 있지 않으면 `commentsId` 변수 값을 삽입

    문자열 파라미터를 감싸는 괄호 뒤에 아래를 입력합니다.

    ```text
    "", Topic.commentsId)
    ```

    ![Power Fx expression](./assets/9.2_14_PowerFxExpression.png)

    Power Fx expression은 아래와 같아야 합니다.

    ```text
    If(IsBlank(Topic.commentsId), "", Topic.commentsId)
    ```

    훌륭합니다! expression이 완성되었습니다 🙌🏻 이제 **Insert**를 선택해 에이전트 플로우 입력 파라미터에 Power Fx expression을 설정합니다.

1. 이제 **AdditionalComments** 입력에 Power Fx expression이 표시됩니다.

    ![AdditionalComments 입력에 Power Fx expression 표시](./assets/9.2_15_PowerFxExpressionForAdditionalCommentsInput.png)

1. 토픽을 **Save**합니다.

### 9.3 더 나은 사용자 경험을 위해 Request device 토픽에 여러 노드 추가

이제 두 개의 노드를 더 추가합니다:

- **Send a message** - 사용자가 선택한 디바이스를 참조해 요청이 제출되었음을 확인하는 메시지
- **Topic management** - 대화를 종료하기 위해 **End of conversation** 노드로 리디렉션

시작해봅시다!

1. 에이전트 플로우 노드 아래의 **plus + icon**을 선택하고 **Send a message** 노드를 선택합니다.

    ![Send a message 노드 추가](./assets/9.3_01_AddSendAMessageNode.png)

1. 메시지 필드에 아래를 입력합니다.

    ```text
    Thanks
    ```

    그리고 사용자 이름을 참조하기 위해 **Insert variable** 아이콘을 선택합니다.

    ![변수 삽입](./assets/9.3_02_InsertVariable.png)

1. **System** 탭을 선택하고 검색창에 `User`를 입력합니다. **User.DisplayName** 변수를 선택합니다.

    ![시스템 변수 선택](./assets/9.3_03_SelectSystemVariable.png)

1. 시스템 변수가 추가된 뒤, 메시지 필드에 아래를 입력합니다.

    ```text
    . Your selected device,
    ```

    그 다음 **Insert variable**을 선택하고, 이번에는 **Custom** 탭에서 검색창에 `Model`을 입력합니다. **ModelValue** 변수를 선택합니다.

    ![커스텀 변수 선택](./assets/9.3_04_SelectCustomVariable.png)

1. 메시지를 완성하기 위해 아래를 추가로 입력합니다.

    ```text
    , has been submitted and will be reviewed by your manager.
    ```

    메시지는 아래처럼 보일 것입니다.

    ![메시지 전송](./assets/9.3_05_SendAMessage.png)

1. 마지막으로 **Send a message** 노드 아래의 **plus + icon**을 선택하고 **Topic management**를 선택한 뒤, **Go to another topic**을 선택하고 **End of Conversation**을 선택합니다.

    ![Topic management](./assets/9.3_06_EndOfConversation.png)

1. 토픽을 **Save**합니다.

    ![토픽 저장](./assets/9.3_07_SaveTopic.png)

### 9.4 여러 시나리오로 에이전트 테스트

수고하셨습니다!!! 😁 이제 에이전트를 테스트해볼 수 있습니다.

#### 9.4.1 디바이스 요청 + Adaptive Card에 코멘트 입력

1. 테스트 패널에서 **new test session**을 시작하고, **ellipsis (. . .)** 아이콘을 선택한 뒤 **Track between topics**를 선택합니다. 토픽이 다른 토픽으로 리디렉션되는 순간을 실시간으로 확인할 수 있습니다.

    ![토픽 간 추적 활성화](./assets/9.4_01_EnableTrackBetweenTopics.png)

1. 첫 번째 유스케이스를 테스트합니다. 사용자가 디바이스를 선택하고 추가 코멘트를 입력하는 시나리오입니다. 에이전트에 아래 메시지를 입력합니다.

    ```text
    I need a laptop
    ```

    ![첫 번째 유스케이스 테스트](./assets/9.4_02_TestAgent_RequestDevice_Yes.png)

1. 에이전트가 **Available devices**를 트리거하고 사용 가능한 디바이스 목록을 응답합니다. 디바이스 요청 여부 질문에 아래처럼 답합니다.

    ```text
    yes please
    ```

    ![Yes](./assets/9.4_03_RequestDevice_Yes.png)

1. 에이전트 지침에 따라 **Request device**가 호출되고, 에이전트 메시지에 Adaptive Card가 표시되는 것을 확인합니다.

    **Surface Laptop 13** 디바이스를 선택하고 아래 코멘트를 추가합니다.

    ```text
    I need 16GB of RAM please
    ```

    ![디바이스 선택 및 코멘트 입력](./assets/9.4_04_SelectDeviceAndEnterComment.png)

1. 아래로 스크롤하여 **Submit Request** 버튼을 선택해 Adaptive Card를 에이전트에 제출합니다.

    ![요청 제출](./assets/9.4_05_SubmitRequest.png)

1. 두 커넥터 액션의 연결 인증을 위해 에이전트가 자격 증명 사용을 요청하면 **Allow**를 선택합니다.

    ![Allow 선택](./assets/9.4_06_SelectAllow.png)

1. 에이전트가 확인 메시지를 표시합니다. 메시지에는 사용자 표시 이름과 선택된 모델이 포함되며, 이후 **End of Conversation** 토픽으로 리디렉션됩니다. 좋습니다!

    ![요청 제출 완료](./assets/9.4_07_RequestSubmitted.png)

1. **End of Conversation** 토픽의 나머지를 확인하기 위해 **Yes**를 선택합니다.

    ![Yes 선택](./assets/9.4_08_RedirectNode.png)

1. 다음으로 별점 카드에서 어떤 별이든 선택해 경험을 평가합니다.

    이후 토픽은 **End of Conversation** 토픽의 마지막 **Question** 노드로 진행합니다. **No**를 선택합니다.

    ![대화 종료 토픽](./assets/9.4_09_EndOfConversation.png)

1. 마지막으로 **End of Conversation** 토픽에서 최종 메시지가 테스트 패널에 표시되며 토픽이 완료됩니다.

    ![대화 종료 토픽](./assets/9.4_10_EndOfConversation.png)

1. 이메일 인박스를 확인하여 에이전트 플로우가 관리자에게 보낸 이메일을 검토합니다. 선택한 디바이스 상세 정보와 Adaptive Card에 입력한 메모가 포함되어 있습니다.

    ![이메일 수신](./assets/9.4_11_ReviewEmailMessageWithComment.png)

1. 하이퍼링크를 클릭하면 브라우저에서 디바이스의 SharePoint 항목이 열립니다. 훌륭합니다!

    ![이메일의 하이퍼링크 클릭](./assets/9.4_12_SelectLinkInEmail.png)

#### 9.4.2 디바이스 요청 + Adaptive Card에 코멘트 미입력

이번에는 코멘트를 입력하지 않는 두 번째 시나리오를 테스트합니다.

1. 아래 단계를 동일하게 반복합니다.

    - 테스트 패널을 **Refresh**하고 **activity map** 아이콘 선택
    - 메시지 `I need a laptop` 입력
    - 디바이스 요청 여부 질문에 `yes please`로 응답

    ![디바이스 요청](./assets/9.4_13_RequestDevice_Yes.png)

1. 이번에는 **Surface Laptop 15**를 선택하고 코멘트를 입력하지 않습니다.

    ![디바이스 선택](./assets/9.4_14_SelectDevice.png)

1. **Submit Request** 버튼을 선택해 요청을 **Submit**합니다.

    ![Submit Request](./assets/9.4_15_SubmitRequest.png)

1. 이번에는 이메일에서 코멘트가 **None**으로 표시됩니다.

    ![이메일 수신](./assets/9.4_16_ReviewEmailMessage.png)

#### 9.4.3 디바이스를 요청하지 않음

마지막 시나리오는 디바이스를 요청하지 않는 경우이며, 에이전트 지침에 따라 **Goodbye** 토픽이 호출되어야 합니다.

1. 아래 단계를 동일하게 반복합니다.

    - 테스트 패널을 **Refresh**하고 **activity map** 아이콘 선택
    - 메시지 `I need a laptop` 입력
    - 이번에는 디바이스 요청 여부 질문에 `No`로 응답

    ![에이전트 테스트](./assets/9.4_17_TestAgent_RequestDevice_No.png)

1. 에이전트가 **Goodbye** 토픽을 호출하고 토픽에 정의된 질문이 표시됩니다.

    ![Goodbye 토픽 호출됨](./assets/9.4_18_Goodbye.png)

## ✅ 미션 완료

축하합니다! 👏🏻 에이전트 플로우를 만들고 기존 **Request device** 토픽에 추가했으며, 에이전트를 다른 토픽으로 리디렉션하는 방법까지 학습했습니다.

이로써 **Lab 09 - 자동화를 위한 에이전트 플로우 추가 및 토픽 기능 강화**가 끝났습니다. 다음 레슨으로 이동하려면 아래 링크를 선택하세요. 다음 레슨의 Lab에서는 이번 Lab의 유스케이스를 확장합니다.

⏭️ [**Add Event Triggers - Enable autonomous agent capabilities** 레슨으로 이동](../10-add-event-triggers/index.md)

## 📚 참고 자료

🔗 [Introducing agent flows: Transforming automation with AI-first workflows](https://www.microsoft.com/microsoft-copilot/blog/copilot-studio/introducing-agent-flows-transforming-automation-with-ai-first-workflows/)

🔗 [Agent flows overview](https://learn.microsoft.com/microsoft-copilot-studio/flows-overview?WT.mc_id=power-172621-ebenitez)

🔗 [Use agent flows with your agent](https://learn.microsoft.com/microsoft-copilot-studio/advanced-flow?WT.mc_id=power-172621-ebenitez)

🔗 [List of functions in the reference guide](https://learn.microsoft.com/azure/logic-apps/workflow-definition-language-functions-reference?WT.mc_id=power-172621-ebenitez)

📺 [Agent Flows in Copilot Studio](https://www.youtube.com/watch?v=VJTKyk3Pr7s)

<!-- markdownlint-disable-next-line MD033 -->
<img src="https://m365-visitor-stats.azurewebsites.net/agent-academy/recruit/09-add-an-agent-flow" alt="Analytics" />
