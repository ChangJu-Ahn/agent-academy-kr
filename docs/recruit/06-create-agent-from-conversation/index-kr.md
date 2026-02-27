# 🚨 Mission 06: 자연어와 AI를 사용하여 커스텀 에이전트 생성 및 데이터로 그라운딩하기

## 🕵️‍♂️ CODENAME: `OPERATION AGENT FORGE`

> **⏱️ Operation Time Window:** `~75 minutes`

## 🎯 Mission Brief

다시 오신 것을 환영합니다, Agent Maker. 이번 미션에서는 Copilot Studio의 가장 강력한 기능인 자연어만으로 완전히 새로운 커스텀 에이전트를 만드는 과정을 진행합니다. 그리고 여러분의 데이터로 더욱 강력하게 만들 것입니다.

이것은 단순한 챗봇이 아닙니다. 실제 기업 정보를 기반으로 추론하고, 응답하고, 참조할 수 있는 지식 기반 디지털 동료를 구축하게 됩니다.

여러분의 무기는 자연어입니다. 여러분의 임무는 SharePoint, 업로드 파일, 회사 URL을 사용해 IT 질문에 답변하는 완전 맞춤형 헬프데스크 에이전트를 설계하고, 학습시키고, 테스트하는 것입니다.

이제 처음부터 에이전트를 만들어 봅시다.

## 🔎 Objectives

이번 미션에서 배우게 될 내용:

1. 커스텀 에이전트가 무엇이며 사전 빌드된 템플릿과 어떻게 다른지 이해하기
1. 자연어 프롬프트와 AI를 활용해 에이전트 생성하기
1. SharePoint, 문서, 웹사이트 등 엔터프라이즈 지식 소스로 에이전트 그라운딩하기
1. 생성형 오케스트레이션 개념과 여러 데이터 소스를 활용한 동적 응답 방식 이해하기
1. 자체 데이터를 활용해 질문에 답변하는 완전한 IT 헬프데스크 에이전트 구축 및 테스트

## 🤔 What is a _custom_ agent?

커스텀 에이전트는 Copilot Studio에서 특정 작업이나 질문을 돕기 위해 직접 생성하고 설계하는 챗봇 또는 가상 비서입니다. 커스텀이라고 부르는 이유는 다음과 같습니다:

- **목적을 직접 결정합니다** - 휴가 요청 지원, 주문 상태 확인, IT 관련 질문 지원 등
- **대화를 직접 정의합니다** - 에이전트가 무엇을 말하고 어떻게 응답할지 설정
- **자신의 데이터로 그라운딩합니다** - 기본 제공 지식 리소스를 통해 엔터프라이즈 데이터 연결
- **자신의 시스템이나 앱과 연결합니다** - 커넥터, 플로우, REST API, MCP 서버 활용 가능

> [!NOTE]
> 즉, 사용자와 대화하고 질문에 답변하거나 정보를 수집하고 엔터프라이즈 데이터와 연결되는 디지털 도우미를 만드는 것입니다.

### 🤖 What can a custom agent do?

커스텀 에이전트는 다음을 수행할 수 있습니다:

- 이름, 날짜, 선호도 등의 정보를 사용자에게 질문
- 해당 정보를 데이터베이스나 테이블에 저장
- 질문 기반으로 데이터를 조회하고 답변 제공
- 사용자 상호작용 없이 자동으로 동작
- 이메일 전송, 레코드 생성 등 액션을 직접 또는 자동으로 트리거

### 👩🏻‍💻 Why use a custom agent?

- 반복 작업 자동화로 시간 절약
- 사용자에게 친숙하고 가이드된 경험 제공
- 비즈니스 또는 프로젝트 요구사항에 맞춤화 가능

### ✨ Example

직원이 휴가를 신청하도록 돕는 커스텀 에이전트를 만든다고 가정해 보겠습니다.

이 에이전트는 이름, 휴가 날짜, 매니저 이름을 묻고 SharePoint 목록 같은 휴가 관리 시스템에 저장합니다.

이제 직원은 SharePoint로 이동해 항목을 직접 생성할 필요 없이 에이전트와 대화만 하면 됩니다.

## 🗣️ Use natural language to create agents

이전 레슨에서는 [Lesson 05 - Get started quickly with pre-built agents](../05-using-prebuilt-agents/index.md)에서 사전 빌드된 템플릿으로 빠르게 에이전트를 만드는 방법을 배웠습니다. 이번 레슨에서는 AI 기반 대화형 작성 경험을 살펴봅니다. Copilot Studio에서는 코드를 작성하지 않아도 자연어 설명만으로 에이전트를 만들 수 있습니다.

자연어로 에이전트를 설명하면 AI가 자동으로 이름, 설명, 지침을 생성하고 트리거, 채널, 지식 소스, 도구까지 제안합니다. 이러한 제안은 수락하거나 무시할 수 있지만, 현재 세션에서만 유지되며 저장되지 않습니다.

## 🌱 But I'm new to "describing what I want" - what do I do?

자연어로 에이전트를 설명하는 것이 처음일 수 있습니다. Microsoft 제품 전반의 Copilot을 사용할 때 여러분은 이미 _프롬프트_라는 형태로 자연어를 사용하고 있습니다.

프롬프트는 AI 에이전트에게 무엇을 해야 하는지 전달하는 메시지 또는 지시입니다. 비서에게 명확한 지시를 내리는 것과 같다고 생각하면 됩니다. 지시가 명확할수록 AI가 이해하고 실행하기가 쉬워집니다.

### 🪄 Why Prompts matter

- 에이전트의 동작을 안내합니다.
- 어떤 대화를 해야 하는지 이해하도록 돕습니다.
- 좋은 프롬프트는 더 정확한 응답을 만듭니다.

### 📝 Tips for writing a good prompt

- 명확하고 구체적으로 작성하세요 - 에이전트가 해야 할 일을 정확히 말하세요.
- 사용자 관점에서 생각하세요 - 사용자가 무엇을 말할까? 에이전트는 무엇을 응답해야 할까?
- 가능하면 예시를 포함하세요 - 샘플 상호작용을 제공하세요.

> [!TIP] ✨ Example
>
> HR 팀이 휴가 요청을 돕는 에이전트를 만든다고 가정합니다.
>
> 프롬프트 예시:
>
> `**사용자가 휴가 신청을 제출할 수 있도록 도와주는 에이전트를 만들고 싶습니다. 사용자가 휴가 신청을 하면, 에이전트는 사용자의 이름, 휴가 시작일, 휴가 종료일, 그리고 직속 상사의 이름을 입력받아야 합니다. 사용자가 이 정보를 제공하면, 에이전트는 해당 정보를 '휴가 신청'이라는 SharePoint 목록에 저장하고, Microsoft Teams의 특정 채널에 알림을 게시해야 합니다.**`
>
> 이 프롬프트가 좋은 이유:
>
> - **목표가 명확함** - 휴가 요청 제출
> - **사용자 상호작용 설명** - 사용자가 말하는 것과 에이전트가 물어야 하는 것
> - **필수 데이터 명시** - 이름, 시작일, 종료일, 매니저
> - **데이터 저장 위치 명확** - Vacation Requests라는 SharePoint 목록

## 🔮 OK, I've created my agent... how do I next ground it with knowledge?

Copilot Studio에서 지식 소스는 에이전트가 더 나은 답변을 하기 위해 정보를 가져오는 위치입니다. 이러한 소스를 추가하면 Power Platform, Dynamics 365, 웹사이트 및 회사에서 사용하는 기타 시스템이나 서비스에서 엔터프라이즈 데이터를 가져올 수 있습니다.

이러한 소스는 AI와 함께 작동하여 에이전트가 사용자 질문에 더 정확하게 응답하도록 도와주며, 이 과정은 **generative orchestration**을 통해 이루어집니다.

### 🌿 What is generative orchestration in the context of agents?

생성형 오케스트레이션이란 에이전트가 AI를 사용하여 내장된 언어 능력과 추가된 지식 소스를 결합해 질문에 동적으로 답변하는 방식을 의미합니다.

사용자가 질문하면 에이전트는:

- AI로 질문을 이해합니다.
- 필요한 정보가 없으면 즉석에서 질문을 생성하여 사용자에게 추가 정보를 요청합니다.
- 가장 관련성 높은 지식 소스를 선택합니다.
- 해당 소스를 검색하여 답변을 찾습니다.
- 찾은 정보를 활용해 자연스럽고 유용한 답변을 생성합니다.

### 🏦 Why knowledge sources matter?

1. **더 스마트한 답변** - 지식 소스를 추가하면 에이전트가 조직의 실제 데이터를 사용해 더 정확한 답변을 제공할 수 있습니다.

1. **수동 작성 감소** - 모든 가능한 응답을 직접 작성할 필요가 없습니다. 에이전트가 추가된 소스를 검색하고 자동으로 응답합니다.

1. **신뢰할 수 있는 정보 사용** - Dataverse, SharePoint 또는 회사 웹사이트와 같이 이미 사용 중인 시스템에서 답변을 가져오므로 신뢰할 수 있는 정보를 제공합니다.

1. **생성형 AI와 결합** - 지식 소스와 AI가 함께 작동하여 에이전트가 사전 프로그래밍되지 않은 질문도 이해하고 자연스럽게 응답할 수 있습니다.

1. **유연하고 확장 가능** - 설정 시 또는 나중에 언제든지 지식 소스를 추가할 수 있으며, 요구사항이 변경되면 에이전트가 더 스마트해집니다.

> [!TIP] ✨ Example
>
> 직원의 HR 질문을 돕는 에이전트를 만든다고 상상해 보세요. 회사의 HR 정책 문서와 SharePoint 사이트를 지식 소스로 추가합니다.
>
> 직원이 _"휴가 일수는 얼마나 되나요?"_ 라고 물으면, 에이전트가 생성형 오케스트레이션을 사용해 해당 소스를 검색하고 올바른 정책으로 답변합니다. 직원이 물어볼 수 있는 모든 질문에 대한 답변을 직접 작성할 필요가 없으므로 시간을 절약할 수 있습니다.

## Types of knowledge sources that can be added

1. **Public websites**
    - **기능:** Bing을 사용해 특정 웹사이트(회사 사이트 등)를 검색합니다.
    - **장점:** FAQ나 제품 정보 같은 공개 정보를 가져오는 데 유용합니다.

1. **Documents**
    - **기능:** PDF나 Word 파일 같은 문서를 에이전트에 직접 업로드합니다. 업로드된 파일은 Dataverse에 안전하게 저장됩니다.
    - **장점:** 내부 가이드, 매뉴얼 또는 정책을 기반으로 질문에 답변할 수 있습니다.

1. **SharePoint**
    - **기능:** [Work IQ](https://www.microsoft.com/en-us/microsoft-365/blog/2025/11/18/microsoft-ignite-2025-copilot-and-agents-built-to-power-the-frontier-firm/#microsoft-365-copilot-with-work-iq-ai-built-for-work)로 구동되는 SharePoint 폴더 또는 파일에 연결합니다.
    - **장점:** SharePoint에 저장된 팀 문서, HR 정책 또는 프로젝트 파일에 접근하는 데 이상적입니다.

1. **Dataverse**
    - **기능:** Dataverse 환경의 테이블과 행에서 구조화된 데이터를 사용하며, 에이전트 응답 개선을 위해 테이블과 열에 동의어 및 용어집 정의를 적용할 수 있습니다.
    - **장점:** 고객 정보 같은 엔터프라이즈 데이터를 조회해야 할 때 유용합니다.

1. **Real-time knowledge with connectors**
    - **기능:** 사용자의 권한을 사용하여 대화 중에 Salesforce, ServiceNow, Dynamics 365, AzureSQL, Databricks 등의 엔터프라이즈 시스템에서 실시간 데이터에 접근합니다.
    - **장점:** 데이터를 저장하거나 복제하지 않고 최신의 안전하고 정확한 응답을 제공하여 에이전트를 더 스마트하고 안전하게 만듭니다.

1. **Azure AI Search**
    - **기능:** Azure에 저장된 대규모 문서 세트를 시맨틱 및 벡터 검색을 사용하여 사용자 질문을 이해하고 검색합니다.
    - **장점:** 복잡한 데이터 소스에서 정확하고 신뢰할 수 있는 답변을 제공하며, 인용을 지원하고, 안전한 접근 제어로 대규모 문서 컬렉션에 대해 잘 확장됩니다.

## 🔒 Note on security

### Knowledge source authentication

SharePoint와 Dataverse 같은 일부 소스는 사용자 인증이 필요합니다. 즉, 에이전트는 사용자가 볼 수 있는 데이터만 응답에 참조합니다. 반면 Azure AI Search와 같은 다른 소스는 Azure 계정과 인증 유형 지정이 필요한 추가 구성이 필요할 수 있습니다.

## Improving your agent's responses in Copilot Studio

대화형 작성 경험에서 에이전트가 프로비저닝된 후에는 프롬프트로부터 AI가 생성한 지침에 대해 에이전트를 테스트해야 합니다. Copilot Studio에서 에이전트의 응답을 개선하는 것은 에이전트가 목표를 명확히 이해하고 올바른 정보를 활용하도록 하는 것입니다.

1. **지침 개선** - 에이전트의 행동 방식을 알려주는 곳입니다. 명확하고 구체적인 언어를 사용하세요.

    예시:

    ✅ "친절한 고객 지원 에이전트처럼 행동하며 쉽게 설명하세요."

    ❌ "도움이 되세요." (너무 모호함)

1. **톤과 언어 확인** - 에이전트의 톤이 대상 사용자에게 맞는지 확인하세요.

    다음과 같이 설정할 수 있습니다:

    - 친근하고 캐주얼하게
    - 전문적이고 간결하게
    - 지원적이고 인내심 있게

1. **지식 소스 추가 또는 업데이트** - 에이전트가 특정 주제에 대해 답변해야 한다면 올바른 정보에 접근할 수 있는지 확인하세요.

    - 웹사이트, 문서 또는 FAQ 링크를 추가하세요.
    - 콘텐츠를 최신 상태로 유지하세요.
    - 명확하고 잘 구조화된 정보를 사용하세요.

1. **Topics & Triggers 사용** - 에이전트가 특정 작업이나 대화를 처리해야 한다면 트리거 문구가 포함된 토픽을 만들 수 있습니다. 이렇게 하면 대화를 더 정확하게 안내할 수 있습니다. 다음 레슨에서 더 자세히 배웁니다.

1. **실제 질문으로 테스트** - 사용자가 물어볼 수 있는 유형의 질문을 에이전트에게 해보세요.

    답변이 좋지 않다면:

    - 시스템 지침을 조정하세요.
    - 더 많은 예시나 지식을 추가하세요.
    - 질문을 다시 표현하여 어떻게 응답하는지 확인하세요.

1. **검토 및 반복 개선** - 에이전트 개선은 지속적인 과정입니다!

    게시 후:

    - 사용자로부터 피드백을 수집하세요.
    - 일반적인 질문이나 혼란을 관찰하세요.
    - 에이전트 설정을 계속 개선하세요.

## 🧪 Lab 06: Create a custom agent in Copilot Studio

이제 데이터를 기반으로 대화하는 커스텀 에이전트를 만드는 방법을 배워보겠습니다.

### ✨ Use case

[Lesson 03 - Create a declarative agent for Microsoft 365 Copilot](../03-create-a-declarative-agent-for-M365Copilot/index.md#use-case-scenario)과 동일한 시나리오를 사용합니다.

**As an** employee

**I want to** 디바이스 문제, 네트워크 트러블슈팅, 프린터 설정 같은 문제에 대해 IT 헬프데스크 에이전트로부터 빠르고 정확한 지원을 받고

**So that I can** 생산성을 유지하고 기술 문제를 지연 없이 해결하기

Let's begin!

### ✨ Prerequisites

- **SharePoint site**

    [Lesson 00 - Course Setup - Step 3: Create new SharePoint site](../00-course-setup/index.md#step-4-create-new-sharepoint-site)에서 만든 **Contoso IT** SharePoint 사이트를 사용합니다.

    **Contoso IT** SharePoint 사이트를 아직 설정하지 않았다면 [Lesson 00 - Course Setup - Step 3: Create new SharePoint site](../00-course-setup/index.md#step-4-create-new-sharepoint-site)로 돌아가세요.

- **Solution**

    [Lesson 04 - Creating a Solution for your agent](../04-creating-a-solution/index.md#41-create-a-solution-publisher)에서 만든 **Contoso Helpdesk Agent** 솔루션을 사용합니다.

    **Contoso Agent** 솔루션을 아직 설정하지 않았다면 [Lesson 04 - Creating a Solution for your agent](../04-creating-a-solution/index.md#41-create-a-solution-publisher)로 돌아가세요.

### 6.1 Use natural language to create an agent with AI

> [!WARNING] AI generated instructions may differ across sessions
>
> 자연어로 에이전트를 설명하면 AI가 생성하는 이름, 설명, 지침은 세션마다 다를 수 있습니다. 제안되는 트리거, 채널, 지식 소스, 도구도 마찬가지입니다.

1. Copilot Studio 홈 페이지로 이동하여 필드에 IT 헬프데스크 에이전트를 설명하는 다음 프롬프트를 입력합니다.

    ```text
    You are an IT Help Desk assistant that helps employees resolve common IT issues and find available devices. Be polite, concise, and helpful. Use Microsoft Support as the primary source: https://support.microsoft.com (and Microsoft Learn troubleshooting if needed: https://learn.microsoft.com/en-us/troubleshoot/). Do not invent steps - if you can't verify official guidance, say so and offer safe diagnostics + escalation.

    For troubleshooting:
    1) Ask ONE focused question if details are missing (goal, symptom/error, app/device).
    2) Try quick fixes first (restart, connectivity, sign-in, service status).
    3) Provide numbered step-by-step instructions (short, actionable).
    4) If not resolved, offer 1-2 alternative branches.
    5) After 2-3 branches, recommend escalation and provide a "ticket summary" of symptoms + error + device/app + what was tried.

    For devices:
    1) Ask what type of device do they need

    Never ask for passwords/OTP. Refuse requests to bypass security.
    Include relevant Microsoft Support links and preserve URLs.
    ```

    이 프롬프트에는 다음이 포함됩니다:

    - **역할 및 목표:** IT Help Desk 비서
    - **주요 지식 소스** (웹사이트 지식 소스의 우선순위 포함)
    - **응답 스타일:** 정중하고, 간결하고, 도움이 되게
    - **트러블슈팅 흐름:** 질문 > 빠른 수정 > 단계 > 대안 > 에스컬레이션
    - **에스컬레이션 산출물:** 티켓 요약
    - **디바이스 지원 (기본)**
    - **보안 경계:** 비밀번호 없음, 보안 우회 없음
    - **링크 처리:** URL 유지, Microsoft Support 인용

    ![Enter prompt](./assets/6.1_01_Prompt.png)

1. 에이전트가 생성될 솔루션이 [Lesson 04 - Create a new solution](../04-creating-a-solution/index.md#42-create-a-new-solution)에서 만들고 기본 솔루션으로 선택한 솔루션인지 확인합니다.

    **톱니바퀴** 아이콘을 선택하면 **Agent Settings** 모달이 나타나며 이전에 만든 솔루션이 기본으로 선택된 것을 확인할 수 있습니다. 이는 [Lesson 04 - Create a new solution](../04-creating-a-solution/index.md#42-create-a-new-solution)에서 기본 솔루션으로 선택했기 때문입니다.

    ![View of Agent Settings](./assets/6.1_02_AgentSettings.png)

1. **Cancel**을 선택합니다. 프롬프트 설명을 제출하면 Copilot Studio가 에이전트 프로비저닝을 시작합니다.

1. 에이전트가 프로비저닝되면 확인 메시지가 나타납니다. AI가 자동으로 에이전트의 **이름**, **설명** 및 **지침**을 생성한 것을 확인하세요. 오케스트레이션 모드는 기본적으로 활성화되어 있으며(**Settings**에서 확인 가능), 에이전트의 응답 모델로 기본 모델이 사용됩니다.

    > [!WARNING] 참고: AI 생성 지침은 세션마다 다를 수 있습니다
    >
    > 자연어로 에이전트를 설명하면 AI가 생성하는 이름, 설명, 지침은 세션마다 다를 수 있습니다. 제안되는 트리거, 채널, 지식 소스, 도구도 마찬가지입니다.

    ![Setting up agent](./assets/6.1_03_AgentProvisioned.png)

1. 아래로 스크롤하여 AI가 제안한 지식 소스, 도구 및 트리거를 확인합니다.

    ![Knowledge sources and tools sections with suggestions from AI](./assets/6.1_04_KnowledgeAndTools.png)

   만약 Instruction의 한글 버전이 필요하면 다음을 참고합니다.

   ```
        # 목적
        이 상담원의 목적은 공식 Microsoft 자료를 기반으로 정확하고 간결하며 정중한 안내를 제공하여 직원들이 일반적인 IT 문제를 해결하고 사용 가능한 장치를 찾도록 돕는 것입니다.
        
        # 일반 지침
        - 항상 정중하고 간결하며 도움이 되는 답변을 제공하십시오.
        - Microsoft 지원 및 Microsoft Learn 문제 해결 가이드와 같은 공식 Microsoft 자료를 주요 정보원으로 활용하십시오.
        - 임의로 해결책을 만들지 마십시오. 공식 안내를 제공할 수 없는 경우, 그 사실을 명확히 밝히고 안전한 다음 단계를 제안하십시오.
        - 암호 또는 일회용 암호를 절대 요구하지 마십시오. 보안을 우회하려는 모든 요청은 거부하십시오.
        
        # 기술
        - 일반적인 IT 문제 해결
        - 정보가 불충분할 경우 명확한 질문을 통해 문제 해결
        - 단계별 지침 제공
        - 첫 번째 시도가 실패할 경우 다른 해결 방법 제안
        - 해결되지 않은 문제는 요약하여 상위 담당자에게 보고
        
        # 단계별 지침
        
        ## 초기 평가
        1. 목표: 사용자의 문제 파악
        2. 조치: 세부 정보가 누락된 경우, 핵심 질문 하나를 하세요(예: "정확한 오류 메시지는 무엇인가요?" 또는 "어떤 장치나 앱에 문제가 발생했나요?").
        
        ## 빠른 해결 방법
        1. 목표: 먼저 간단한 해결 방법을 시도합니다.
        2. 조치: 장치 재시작, 네트워크 연결 확인, 로그인 자격 증명 확인, 서비스 상태 확인과 같은 기본적인 단계를 제안합니다.
        
        ## 공식 지침 제공
        1. 목표: 정확한 문제 해결 단계를 제공합니다.
        2. 조치: Microsoft 지원 및 Microsoft Learn의 문제 해결 가이드를 활용하여 명확하고 단계별 지침을 제공합니다.
        
        ## 대체 해결 방법
        1. 목표: 첫 번째 해결 방법이 실패하면 1~2가지 추가적인 공식 해결 방법을 제공합니다.
        2. 조치: 각 방법에 대한 공식 문서 링크를 제공합니다.
        
        ## 지원팀에 문의
        1. 목표: 2~3회 시도 후에도 문제가 지속되면 IT 지원팀에 문의하도록 권장합니다.
        2. 조치: "티켓 요약"에 다음 내용을 포함하여 문제를 요약합니다.
        
        - 증상 및 오류 메시지
        - 관련 장치 또는 앱
        - 이미 시도한 단계
        
        # 오류 처리 및 제한 사항
        - 공식적인 지침이 없는 경우, 사용자에게 알리고 IT 지원팀에 문의하도록 안내합니다.
        
        # 상호 작용 예시
        사용자: "Outlook이 열리지 않습니다."
        상담원: "데스크톱 버전의 Outlook을 사용하시는지, 웹 버전의 Outlook을 사용하시는지 확인해 주시겠습니까?"
        사용자: "데스크톱 버전입니다."
        상담원: "컴퓨터를 다시 시작하고 업데이트를 확인해 보세요. 그래도 문제가 해결되지 않으면 다음 단계를 따르세요. [Microsoft 지원 링크]"
        
        # 후속 조치 및 종료
        - 해결 방법을 안내한 후 문제가 해결되었는지 확인합니다.
        - 문제가 해결되지 않은 경우, 다른 해결 방법을 시도하거나 IT 지원팀에 보고합니다.
        
        # 비표준 용어
        - "티켓 요약": IT 지원팀에 보고하기 위해 해결되지 않은 문제를 간략하게 요약한 보고서입니다.
   ```

1. 더 아래로 스크롤하여 Connected Agents, Topics 및 Suggested Prompts 섹션을 확인합니다.

    ![Connected Agents, Topics and Suggested Prompts sections](./assets/6.1_05_ConnectedAgentsTopicsSuggestedPrompts.png)

1. 에이전트가 `Contoso Helpdesk Agent` 솔루션에 올바르게 생성되었는지 확인합니다. 오른쪽 상단의 **Settings**를 선택합니다.

    ![Select Settings](./assets/6.1_06_AgentSettings.png)

1. **Advanced**에서 에이전트가 `Contoso Helpdesk Agent` 솔루션에 생성된 것을 확인할 수 있습니다. 설정을 닫습니다.

    ![Solution created in Contoso Helpdesk Agent solution](./assets/6.1_07_AdvancedSettings.png)

1. 이제 에이전트 이름을 업데이트합니다. **Details** 섹션에서 **Edit**를 선택합니다.

    ![Select Edit in Details section](./assets/6.1_08_EditDetails.png)

1. 에이전트 이름으로 다음을 입력하고 업데이트된 세부 정보를 **Save**합니다.

    ```text
    Contoso Helpdesk Agent
    ```

    ![Update agent name](./assets/6.1_09_AgentName.png)

1. 이제 제안된 지식 소스를 추가합니다. **Knowledge** 섹션에서 `https://support.microsoft.com` 웹사이트 URL에 대해 **+ Add**를 선택합니다.

    ![Select add for the suggested website URL](./assets/6.1_10_AddSuggestedWebsite.png)

1. **Add public websites** 모달이 웹사이트 URL과 함께 나타납니다. **Add**를 선택합니다.

    ![Select add](./assets/6.1_11_AddWebsite.png)

1. 아래 URL을 사용하여 다른 웹사이트를 추가하고 **Add to agent**를 선택합니다.

    ```text
    https://learn.microsoft.com/troubleshoot/
    ```

    ![Add second website URL](./assets/6.1_12_AddAdditionalWebsite.png)

1. 두 웹사이트 URL이 에이전트의 지식 소스로 추가되었습니다. **X Dismiss**를 선택하여 AI의 두 번째 제안을 제거합니다.

    ![Select Dismiss](./assets/6.1_13_SelectDismiss.png)

1. 기본적으로 **Web Search** 설정이 활성화되어 있습니다. 우리가 정의한 지식 소스만 에이전트가 사용하도록 **토글**을 선택하여 **Web Search** 기능을 비활성화합니다.

    ![Disable Web Search](./assets/6.1_14_DisableWebSearch.png)

1. 이제 새로 만든 에이전트를 테스트합니다. 오른쪽의 **Testing** 패널에서 **new test session** 아이콘을 선택합니다.

    ![Select start new test session in testing pane](./assets/6.1_15_StartNewTestSession.png)

1. **Testing** 패널에 다음 질문을 입력합니다.

    ```text
    내 Surface의 보증 상태는 어떻게 확인할 수 있나요?
    ```

    ![Test newly created agent](./assets/6.1_16_EnterQuestion.png)

1. 에이전트가 처리하는 경로를 실시간으로 보여주는 Activity map이 로드됩니다. 이 시나리오에서 에이전트는 질문을 이해하고 두 웹사이트 URL을 사용하여 지식 소스를 검색합니다.

    에이전트는 지침에 정의된 대로 번호가 매겨진 단계별 지침으로 답변합니다. 응답에는 에이전트가 답변을 형성한 [https://support.microsoft.com](https://support.microsoft.com) 웹사이트에 대한 참조가 포함됩니다. 이를 통해 사용자가 답변의 출처를 확인할 수 있습니다.

    ![References in response](./assets/6.1_17_References.png)

축하합니다! Copilot Studio에서 자연어 설명으로 첫 커스텀 에이전트를 만들었습니다 🙌🏻

### 6.2 Add an internal knowledge source using a SharePoint site

이전에는 대화형 생성 경험 중에 공개 웹사이트를 에이전트의 외부 지식 소스로 추가했습니다. 이제 SharePoint 사이트를 사용하여 내부 지식 소스를 추가하겠습니다. 이것은 [Lesson 00 - Course Setup](../00-course-setup/index.md#step-4-create-new-sharepoint-site)에서 만든 SharePoint 사이트입니다.

1. **Knowledge** 섹션에서 **+ Add knowledge**를 선택하고 **SharePoint**를 선택합니다.

    ![Select SharePoint](./assets/6.2_01_SelectSharePoint.png)

1. SharePoint URL 필드에 [Lesson 00 - Course Setup](../00-course-setup/index.md#step-4-create-new-sharepoint-site)에서 만든 **SharePoint 사이트 주소**를 붙여넣고 **Add**를 선택합니다.

    SharePoint 사이트의 **이름**을 `Contoso IT`로 업데이트하고 **Add to agent**를 선택합니다.

    ![Update SharePoint site name and select Add to agent](./assets/6.2_02_AddSharePointSite.png)

1. SharePoint 사이트가 _Ready_ 상태의 지식 소스로 추가되었습니다. Status 열은 지식 소스가 성공적으로 로드/연결되었는지 또는 문제가 있는지 표시합니다.

    ![SharePoint site status](./assets/6.2_03_SharePointSiteAdded.png)

### 6.3 Add an internal knowledge source by uploading a document

이제 문서를 에이전트에 직접 업로드하여 다른 내부 지식 소스를 추가하겠습니다.

1. **Knowledge** 섹션에서 **+ Add knowledge**를 선택하고 **Upload file** 또는 **select to browse**를 선택합니다.

    ![Select upload files](./assets/6.3_01_SelectUploadFile.png)

1. 이 [샘플 파일](https://raw.githubusercontent.com/microsoft/agent-academy/refs/heads/main/docs/recruit/06-create-agent-from-conversation/assets/Contoso_Guest_WiFi_Connection_Guide-kr.docx)을 다운로드하고 파일 탐색기에서 선택합니다. **Open**을 선택합니다.

    ![Select document](./assets/6.3_02_SelectWordFile.png)

1. 업로드할 파일이 선택되었습니다. 다음으로 **Add to agent**를 선택합니다.

    ![Select Add to Agent](./assets/6.3_03_SelectAddToAgent.png)

1. 문서가 에이전트에 추가되는 중입니다. 업로드가 완료될 때까지 기다리세요. 브라우저 창을 닫지 마세요.

    ![Document added](./assets/6.3_04_FileAdded.png)

1. 문서 상태는 처음에 _In progress_로 표시됩니다. 에이전트를 테스트하기 전에 상태가 **Ready**로 업데이트될 때까지 기다리세요.

    ![File status](./assets/6.3_05_FileStatus.png)

이제 에이전트를 테스트해 봅시다!

### 6.4 Test agent

네 가지 지식 소스를 통해 Contoso Helpdesk Agent에 질문하여 테스트합니다.

1. 테스트 패널에서 **new test session** 아이콘을 선택합니다.

    공개 웹사이트(외부) 지식 소스를 테스트하기 위해 다음 질문을 입력합니다.

    ```text
    내 서피스 기기의 일련번호는 어떻게 찾을 수 있나요?
    ```

    ![Select start a new test session icon](./assets/6.4_01_EnterQuestion1.png)

1. 에이전트가 지식 소스를 검토하고 웹사이트 지식 소스를 사용하여 응답을 제공하는 것을 볼 수 있습니다.

    응답이 반환되며, 답변을 형성한 웹 페이지에 대한 참조가 포함된 것을 확인하세요.

    ![Question 1 response](./assets/6.4_02_Question1Response.png)

1. Activity map의 지식 모달을 아래로 스크롤하면 에이전트가 검색한 다른 지식 소스를 볼 수 있습니다(다른 웹사이트 URL, SharePoint 사이트, 업로드된 파일).

    그러나 **Referenced sources** 섹션에서 첫 번째 웹사이트 지식 소스만 참조된 것을 확인할 수 있습니다. 답변은 첫 번째 웹사이트 지식 소스를 사용하여 그라운딩되었습니다. 참조를 선택하면 해당 웹 페이지로 이동합니다.

    ![Knowledge sources referenced and searched](./assets/6.4_03_OtherSourcesSearchedOver.png)

1. 이제 하나의 메시지에서 SharePoint 사이트 지식 소스와 문서 지식 소스를 함께 테스트합니다. 다음 질문을 입력합니다.

    ```text
    내 기기에서 회사 Contoso VPN에 어떻게 접속할 수 있나요? 게스트는 Contoso 게스트 Wi-Fi에 어떻게 연결하나요?
    ```

    ![Test SharePoint and document knowledge sources](./assets/6.4_04_EnterQuestion2Question3.png)

1. 에이전트가 네 가지 지식 소스를 모두 검토하여 하나의 메시지에 제출된 두 질문에 대한 응답을 생성합니다. 에이전트는 단일 메시지로 두 질문에 모두 답변하며, 각각 어디에서 응답을 생성했는지에 대한 별도의 참조를 제공합니다.

    Activity map의 지식 모달에서 Contoso VPN 접근 관련 질문 1에 대해 SharePoint 사이트가 참조된 것을 볼 수 있습니다. Activity 모달에서 두 질문에 답변하는 데 사용된 지식 소스를 완전히 파악할 수 있습니다.

    ![Knowledge sources referenced for Question 1 and Question 2](./assets/6.4_05_Question2Response.png)

1. Contoso Guest wifi에 관한 질문 2의 응답을 아래로 스크롤합니다. 마찬가지로 세부 정보가 포함된 업로드 파일을 사용하여 그라운딩된 응답을 볼 수 있습니다.

    ![Question 3 response](./assets/6.4_06_Question3Response.png)

1. Activity 모달에서 두 번째 웹사이트 URL도 참조되었지만 참조 소스로는 사용되지 않았음을 확인하세요.

    ![Activity modal of other sources searched over](./assets/6.4_07_OtherSourcesSearchedOver.png)

1. 생성된 응답이 정확한지 항상 확인하는 것이 좋습니다. 문서 참조를 선택하면 답변을 반영하는 문서의 텍스트가 포함된 모달이 나타납니다.

    ![Review document](./assets/6.4_08_VerifyDocument.png)

에이전트는 단일 메시지에서 여러 질문에 답변하고, 지식 소스를 검색하며 응답에 지식 소스를 참조할 수 있습니다. 항상 참조를 검토하여 응답이 정확한지 확인하세요.

## ✅ Mission Complete

축하합니다! 👏🏻 자연어 설명으로 나만의 커스텀 에이전트를 만드는 방법을 배웠습니다. 커스텀 에이전트는 네 가지 서로 다른 지식 소스의 데이터를 기반으로 대화할 수 있습니다 🙌🏻

이것으로 **Lab 06 - AI로 에이전트 만들기**가 끝났습니다. 아래 링크를 선택하여 다음 레슨으로 이동하세요. 이 랩에서 만든 커스텀 에이전트는 다음 레슨의 랩에서 사용됩니다.

⏭️ [Move to **Add a new Topic with trigger** lesson](../07-add-new-topic-with-trigger/index-kr.md)

이제 여러분은 데이터와 대화하는 디지털 에이전트를 만들 수 있습니다. 다음 미션으로 계속 진행하세요.

## 📚 Tactical Resources

🔗 [Quickstart: Create and deploy an agent](https://learn.microsoft.com/microsoft-copilot-studio/fundamentals-get-started?context=%2Fmicrosoft-365-copilot%2Fextensibility%2Fcontext/?WT.mc_id=power-172617-ebenitez)

🔗 [Create and delete agents](https://learn.microsoft.com/microsoft-copilot-studio/authoring-first-bot?WT.mc_id=power-172617-ebenitez)

🔗 [Key concepts - Authoring agents](https://learn.microsoft.com/microsoft-copilot-studio/authoring-fundamentals/?WT.mc_id=power-172617-ebenitez)

📺 [Create a custom agent using natural language](https://aka.ms/ai-in-action/copilot-studio/ep1)

📺 [Add knowledge to your agents](https://aka.ms/ai-in-action/copilot-studio/ep2)

<!-- markdownlint-disable-next-line MD033 -->
<img src="https://m365-visitor-stats.azurewebsites.net/agent-academy/recruit/06-create-agent-from-conversation" alt="Analytics" />
