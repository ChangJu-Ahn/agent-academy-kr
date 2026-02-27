# 🚨 Mission 08: Adaptive Cards로 Topics에서 사용자 상호작용 향상

## 🕵️‍♂️ CODENAME: `OPERATION INTERFACE UPLIFT`

> **⏱️ Operation Time Window:** `~45 minutes`

## 🎯  Mission Brief

요원 여러분, 이번 임무는 정적인 사용자 경험에 침투하여 풍부하고 동적이며 실행 가능한 Adaptive Cards로 대체하는 것입니다. JSON 페이로드와 Power Fx 수식을 배포하여 Copilot Studio 대화를 기본적인 Q&A에서 완전히 인터랙티브한 경험으로 변환하게 됩니다. 목표는 사용자 입력을 수집하고, 데이터를 아름답게 표시하며, 정밀하고 세련된 방식으로 대화를 이끄는 것입니다. 적응하지 못하면 사용자들은 덜 지능적인 인터페이스로 이탈할 수 있습니다.

## 🔎 Objectives

이번 미션에서 배우게 될 내용:

1. Adaptive Cards가 무엇이며 Copilot Studio에서 사용자 상호작용을 어떻게 향상시키는지 이해하기
1. JSON과 Power Fx 수식을 사용해 동적 콘텐츠를 위한 인터랙티브 카드 제작하기
1. Adaptive Card Designer와 시각적 카드 제작을 위한 주요 구성 요소 탐색하기
1. 에이전트 토픽 내에서 풍부한 인터랙티브 폼 및 데이터 수집 경험 만들기
1. 반응형이며 사용자 친화적인 Adaptive Cards 설계를 위한 모범 사례 적용하기

## 🤔 What is an Adaptive Card?

**Adaptive Card**는 Microsoft Teams, Microsoft Outlook 또는 에이전트 같은 앱에 포함할 수 있는 인터랙티브하고 시각적으로 풍부한 UI 요소를 만드는 방법입니다. 카드의 레이아웃과 콘텐츠를 정의하는 구조화된 JSON 객체입니다:

- 카드에 표시될 요소 - 텍스트, 이미지, 버튼
- 요소가 배치되는 방식
- 폼 제출이나 링크 열기와 같은 사용자 액션

    ![Adaptive Card](assets/8.0_01_AdaptiveCard.png)

### Copilot Studio에서 Adaptive Cards가 중요한 이유

사용자의 이름, 이메일 또는 피드백을 요청하는 에이전트를 만든다고 상상해 보세요. 단순 텍스트만 사용하면 대화가 지루하거나 따라가기 어려울 수 있습니다. 이때 Adaptive Cards가 필요합니다!

1. **대화를 인터랙티브하게 만듦** - 단순 메시지 대신 버튼, 폼, 이미지 등을 표시할 수 있습니다.
    - 예: 카드에서 깔끔한 폼으로 이름과 이메일을 입력받을 수 있습니다.

1. **어디서나 잘 보이는 디자인** - Adaptive Cards는 Microsoft 365 Copilot 채팅이나 Microsoft Teams와 같은 앱 스타일에 자동으로 맞춰집니다. 다크 모드, 글꼴, 레이아웃을 따로 신경 쓸 필요가 없습니다.

1. **JSON으로 쉽게 제작** - JSON 코드(UI를 위한 _레시피_)로 카드를 정의합니다. Copilot Studio에서는 토픽에 추가하기 전에 미리보기를 제공합니다.

1. **데이터 수집 및 활용** - 질문을 하고 답변을 수집하며 대화 흐름에 활용할 수 있습니다.
    - 예: 사용자 전화번호를 받은 뒤 확인 카드를 표시.

1. **사용자 경험 향상** - 더 깔끔하고 클릭 가능한 인터페이스로 에이전트를 더욱 인터랙티브하게 만듭니다.

## 🐱 _JSON_은 사람 이름인가요?

발음은 "Jason"이지만 사람이 아닙니다 😅

JSON(_JavaScript Object Notation_)은 데이터를 구조화하는 경량 포맷입니다. 읽고 쓰기 쉬우며 {} 안의 키-값 쌍으로 구성됩니다.

토픽에 adaptive card를 추가할 때 사용할 수 있는 옵션 중 하나입니다.

![Adaptive card node properties](assets/8.0_02_AdaptiveCardPropertiesPane.png)

## 👀 _formula_를 이용해 adaptive card를 만드는 또 다른 방법

[Mission 07 - Using Power Fx in your nodes](../07-add-new-topic-with-trigger/index.md#what-power-fx-can-do-in-topics)에서 Power Fx를 배웠던 것을 기억하시나요? Copilot Studio의 Adaptive Cards에서도 동일하게 사용할 수 있습니다.

요약하면,

> [!NOTE]
> Power Fx는 에이전트에 로직과 동적 동작을 추가하는 로우코드 프로그래밍 언어입니다. Microsoft Power Apps에서 사용하는 동일한 언어이며 Excel과 유사해 쉽게 사용할 수 있습니다.

### Adaptive Cards에서 Power Fx가 동작하는 방식

Adaptive Card를 디자인할 때 Power Fx 수식을 사용하여:

- 사용자 이름, 날짜, 상태 등 동적 값 삽입
- 통화 표시 또는 숫자 반올림과 같은 텍스트/숫자 포맷
- 조건에 따른 요소 표시/숨김
- 사용자 입력, 변수, 노드 출력 기반으로 응답 커스터마이즈

예시:

"`Hello`" & `System.User.DisplayName`

이 수식은 "Hello"와 사용자 이름을 동적으로 결합합니다.

### 유용한 이유

1. **개인화**

    사용자별로 메시지를 맞춤화하여 자연스럽고 관련성 높은 상호작용을 제공합니다.

1. **동적 콘텐츠**

    변수와 노드 출력에서 실제 데이터를 표시할 수 있습니다.

1. **스마트 로직**

    조건 기반으로 사용자에게 보일 요소를 제어하여 사용성을 높이고 오류를 줄입니다.

1. **로우코드 친화적**

    Excel 수식과 유사한 직관적인 언어입니다.

## 👷🏻‍♀️ Adaptive Card Designer로 제작하기

**Adaptive Card Designer**는 텍스트, 이미지, 버튼, 입력 요소 등을 드래그 앤 드롭으로 추가하여 인터랙티브 메시지 카드를 만드는 시각적 도구입니다. 복잡한 코드를 작성하지 않고도 사용자 친화적인 인터페이스를 설계할 수 있습니다.

디자이너는 시각적으로 카드를 만들지만, 내부적으로는 JSON 객체를 생성합니다. 또한 _formula_ 모드로 전환하면 Power Fx 표현식을 사용하여 외부 데이터 표시가 가능합니다.

## 🎨 Adaptive Card Designer 이해하기

![Adaptive Card Designer](assets/8.0_03_AdaptiveCardPropertiesPane.png)

### A) Card Elements

Adaptive card의 구성 요소입니다. 다음 요소를 드래그 앤 드롭으로 추가할 수 있습니다:

- **TextBlock**: 텍스트 표시
- **Image**: 이미지 표시
- **FactSet**: 키-값 쌍 표시
- **Input fields**: 텍스트 박스, 날짜 선택 등 입력 요소
- **Actions**: _Submit_, _Open URL_, _Show Card_ 버튼

각 요소는 고유 목적과 스타일 옵션을 가집니다.

### B) Card Viewer

실시간으로 카드 모습을 확인하는 **Preview** 영역입니다. 요소를 추가하거나 수정하면 즉시 반영됩니다.

### C) Card Structure

카드의 **계층 구조와 레이아웃**을 보여줍니다. 예:

- 제목용 **TextBlock**
- 이미지와 텍스트가 포함된 **ColumnSet**
- **FactSet**과 **Action buttons**

요소의 중첩 구조를 이해하는 데 도움을 줍니다.

### D) Element Properties

카드 요소를 클릭하면 설정을 변경할 수 있습니다:

- 텍스트 크기, 굵기, 색상 변경
- 이미지 URL 및 alt 텍스트 설정
- 입력 옵션 설정

### E) Card Payload Editor

카드의 **raw JSON 코드** 영역입니다. 고급 사용자는 다음 작업을 할 수 있습니다:

- 템플릿 기능 사용
- 카드 정의 복사/붙여넣기

> [!TIP] Tip - Adaptive Card 샘플 확인
>
> 1. [https://adaptivecards.microsoft.com/designer](https://adaptivecards.microsoft.com/designer) 이동
> 1. **New card** 선택 후 샘플 확인
> 1. 웹 기반 디자이너에서 JSON을 복사
> 1. Copilot Studio 에이전트의 adaptive card에 붙여넣기

![Adaptive Card Designer Samples](assets/8.0_04_AdaptiveCardDesignerSamples.png)

## 🌵 Common use cases

Copilot Studio의 **Send a message** 또는 **Ask a question** 노드에서 Adaptive Cards의 일반적인 활용 사례입니다.

1. **폼 및 데이터 수집**

    - 휴가 신청
    - 피드백 폼
    - 연락처 정보
    - 일정 예약

1. **동적 정보 표시**

    ServiceNow, SAP, Dynamics 365, SharePoint 등의 데이터를 표시

    - 주문 요약
    - 계정 잔액
    - 티켓 상태
    - 예정 일정

1. **인터랙티브 선택**

    - 옵션 선택
    - 작업 확인/취소
    - 서비스 평가

1. **액션 트리거**

    - "Submit request"
    - "View details"

## ⭐ Best practices

1. **단순하고 명확하게 유지**

    - 목적이 분명한 카드 설계
    - 간결한 텍스트와 직관적인 레이아웃 사용

1. **입력 요소는 의도적으로 구성**

    - 필요한 입력만 포함
    - 명확한 라벨 사용

1. **가독성 있는 구조**

    - 제목은 **TextBlocks**
    - 관련 요소는 **Containers** 또는 **ColumnSets**로 그룹화

1. **Action 요소 명확히 표시**

    - **Action.Submit**, **Action.OpenUrl** 사용
    - "Click here" 같은 모호한 라벨 피하기

1. **반응형 디자인 고려**

    - 다양한 화면 크기 가정
    - 고정 폭 대신 **ColumnSets** 활용

1. **가능하면 동적 콘텐츠 사용**

    - Power Fx로 변수 및 노드 출력 연결
    - 사용자 이름, 상태 등 표시

## 🧪 Lab 08 - Adaptive Cards 추가 및 토픽 기능 강화

이제 adaptive cards와 고급 토픽 기능을 사용해 토픽을 개선합니다.

### ✨ Use case

**As an** employee

**I want to** request a device

**So that I** can request a device from the list of available devices

Let's begin!

### Prerequisites

1. **SharePoint list**

    [Lesson 00 - Course Setup - Step 3: Create new SharePoint site](../00-course-setup/index.md#step-4-create-new-sharepoint-site)의 **Devices** 리스트 사용

1. **Contoso Helpdesk Copilot**

    [Lesson 06 - Create a custom agent using natural language with AI and grounding it with your data](../06-create-agent-from-conversation/index.md)에서 만든 에이전트 사용

### 8.1 사용자 요청 제출용 adaptive card 토픽 생성

새로운 토픽을 생성하여 사용자의 디바이스 요청을 처리합니다.

1. **Topics** 탭 → **+ Add a topic from blank** 선택

    ![Select Topics tab](assets/8.1_01_NewTopic.png)

1. 토픽 이름:

    ```text
    Request device
    ```

    트리거 설명:

    ```text
    This topic helps users request a device when they answer yes to the question that asks the user if they would like to request one of these devices.
    ```

    ![Topic Name and trigger Description](assets/8.1_02_TopicNameAndTriggerDescription.png)

1. **Ask with adaptive card** 노드 추가

    ![Select Ask with adaptive card node](assets/8.1_03_AddAskWithAdaptiveCard.png)

1. **Edit adaptive card** 선택

    ![Edit adaptive card](assets/8.1_04_EditAdaptiveCard.png)

1. Adaptive Card Designer에서 TextBlock과 FactSet을 추가해보며 구조 변화를 확인

    ![Drag and drop card elements](assets/8.1_05_DragAndDropCardElements.png)

1. **Preview** 선택

    ![Select preview](assets/8.1_06_PreviewAdaptiveCard.png)

1. 다양한 폭에서 카드 미리보기 확인

    ![Preview card at different widths](assets/8.1_07_PreviewCardWidths.png)

1. Preview 종료 후 Undo

    ![Undo](assets/8.1_08_Undo.png)

1. Card payload editor 전체 삭제 후 JSON 붙여넣기

    ![Clear card payload editor](assets/8.1_09_SelectAll.png)

1. 카드 미리보기 확인 후 **Save → Close**

    ![Select Save](assets/8.1_10_DeviceRequestCard.png)

1. Adaptive Card Node properties 닫기

    ![Close Adaptive Card Node properties panel](assets/8.1_11_ExitAdaptiveCardNodeProperties.png)

1. authoring canvas에서 adaptive card 확인

    ![Device request adaptive card](assets/8.1_12_DeviceRequestCard.png)

1. output variables 확인

    ![Node variable outputs](assets/8.1_13_DeviceRequestCardOutputs.png)

1. JSON → Formula 변경

    ![Change to formula](assets/8.1_14_ChangeToFormula.png)

1. expand 아이콘 선택

    ![Click on expand icon](assets/8.1_15_SelectExpand.png)

1. payload editor 전체 삭제

    ![Click into payload card editor](assets/8.1_16_SelectAll.png)

    Formula 붙여넣기

1. Power Fx 설명 후 카드 모달 닫기

    ![Power Fx Formula](assets/8.1_17_PowerFxFormula.png)

1. Adaptive Card Node properties 닫기

1. 토픽 저장

    ![Save topic](assets/8.1_18_SaveTopic.png)

### 8.2 Request device 토픽 호출을 위한 에이전트 지침 업데이트

1. **Overview → agent instructions → Edit**

    ![Edit instructions](assets/8.2_01_EditInstructions.png)

1. 새 줄 추가:

    ```text
    2. If the user answers yes to the question of requesting a device, trigger [Request device]. Otherwise if they answer no to the question of requesting a device, trigger [Goodbye].
    ```

    ![Request device placeholder](assets/8.2_02_ReplaceRequestDevicePlaceholder.png)

1. `/Req` 입력 후 **Request devices** 선택

    ![Redirect to Request devices topic](assets/8.2_03_ReferenceRequestDeviceTopic.png)

1. `[Goodbye]`도 동일하게 설정

    ![Redirect to Goodbye topic](assets/8.2_04_ReferenceGoodbyeTopic.png)

1. 테스트 진행

    ```text
    I need a laptop
    ```

    ![Test agent](assets/8.2_05_TestAgent.png)

1. 다음 입력:

    ```text
    yes please
    ```

    ![Test Request device](assets/8.2_06_TestRequestDeviceTopic.png)

1. adaptive card 표시 확인

    ![Question node](assets/8.2_07_AdaptiveCardQuestion.png)

1. 테스트 창 새로고침

    ![Refresh test pane](assets/8.2_08_RefreshTestPane.png)

## ✅ Mission Complete

축하합니다! 👏🏻 Power Fx를 사용해 변수 데이터를 표시하는 adaptive card를 추가하고, 토픽 간 리디렉션 방법을 학습했습니다. 작은 단위의 토픽을 구성하면 에이전트 구조가 더 체계적으로 정리되고 사용자 대화 흐름을 더 잘 안내할 수 있습니다.

⏭️ [Move to **Add an agent flow to your Topic for automation** lesson](../09-add-an-agent-flow/index.md)

## 📚 Tactical Resources

🔗 [Using Adaptive Cards in Copilot Studio](https://learn.microsoft.com/microsoft-copilot-studio/guidance/adaptive-cards-overview?WT.mc_id=power-172619-ebenitez)

🔗 [Add an adaptive card in Send a message node](https://learn.microsoft.com/microsoft-copilot-studio/authoring-send-message#add-an-adaptive-card?WT.mc_id=power-172619-ebenitez)

🔗 [Create expressions using Power Fx](https://learn.microsoft.com/microsoft-copilot-studio/advanced-power-fx?WT.mc_id=power-172619-ebenitez)

📺 [Building Adaptive Cards with Power FX](https://aka.ms/ai-in-action/copilot-studio/ep8)

<!-- markdownlint-disable-next-line MD033 -->
<img src="https://m365-visitor-stats.azurewebsites.net/agent-academy/recruit/08-add-adaptive-card" alt="Analytics" />
