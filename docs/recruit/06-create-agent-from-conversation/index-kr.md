---
next:
  link: /recruit/07-add-new-topic-with-trigger
  text: Add new topic with trigger and nodes
prev:
  link: /recruit/05-using-prebuilt-agents
  text: Using a Pre-Built Agent
---

# 🚨 Mission 06: 자연어와 AI를 사용하여 커스텀 에이전트 생성 및 데이터로 그라운딩하기

## 🕵️‍♂️ CODENAME: `OPERATION AGENT FORGE`

> **⏱️ Operation Time Window:** `~75 minutes`

🎥 **Watch the Walkthrough**

[![Create custom agent video
thumbnail](./assets/video-thumbnail.jpg)](https://www.youtube.com/watch?v=qZTtQVncGFg "Watch the walkthrough on YouTube")

## 🎯 Mission Brief

다시 오신 것을 환영합니다, Agent Maker. 이번 미션에서는 Copilot Studio의
가장 강력한 기능인 자연어만으로 완전히 새로운 커스텀 에이전트를 만드는
과정을 진행합니다... 그리고 여러분의 데이터로 더욱 강력하게 만들
것입니다.

이것은 단순한 챗봇이 아닙니다. 실제 기업 정보를 기반으로 추론하고,
응답하고, 참조할 수 있는 지식 기반 디지털 동료를 구축하게 됩니다.

여러분의 무기는 자연어입니다. 여러분의 임무는 SharePoint, 업로드 파일,
회사 URL을 사용해 IT 질문에 답변하는 완전 맞춤형 헬프데스크 에이전트를
설계하고, 학습시키고, 테스트하는 것입니다.

이제 처음부터 에이전트를 만들어 봅시다.

## 🔎 Objectives

이번 미션에서 배우게 될 내용:

1.  커스텀 에이전트가 무엇이며 사전 빌드된 템플릿과 어떻게 다른지
    이해하기
2.  자연어 프롬프트와 AI를 활용해 에이전트 생성하기
3.  SharePoint, 문서, 웹사이트 등 엔터프라이즈 지식 소스로 에이전트
    그라운딩하기
4.  생성형 오케스트레이션 개념과 여러 데이터 소스를 활용한 동적 응답
    방식 이해하기
5.  자체 데이터를 활용해 질문에 답변하는 완전한 IT 헬프데스크 에이전트
    구축 및 테스트

## 🤔 What is a *custom* agent?

커스텀 에이전트는 Copilot Studio에서 특정 작업이나 질문을 돕기 위해 직접
생성하고 설계하는 챗봇 또는 가상 비서입니다. 커스텀이라고 부르는 이유는
다음과 같습니다:

-   **목적을 직접 결정합니다** - 휴가 요청 지원, 주문 상태 확인, IT 관련
    질문 지원 등
-   **대화를 직접 정의합니다** - 에이전트가 무엇을 말하고 어떻게
    응답할지 설정
-   **자신의 데이터로 그라운딩합니다** - 기본 제공 지식 리소스를 통해
    엔터프라이즈 데이터 연결
-   **자신의 시스템이나 앱과 연결합니다** - 커넥터, 플로우, REST API,
    MCP 서버 활용 가능

> \[!NOTE\] 즉, 사용자와 대화하고 질문에 답변하거나 정보를 수집하고
> 엔터프라이즈 데이터와 연결되는 디지털 도우미를 만드는 것입니다.

### 🤖 What can a custom agent do?

커스텀 에이전트는 다음을 수행할 수 있습니다:

-   이름, 날짜, 선호도 등의 정보를 사용자에게 질문
-   해당 정보를 데이터베이스나 테이블에 저장
-   질문 기반으로 데이터를 조회하고 답변 제공
-   사용자 상호작용 없이 자동으로 동작
-   이메일 전송, 레코드 생성 등 액션을 직접 또는 자동으로 트리거

### 👩🏻‍💻 Why use a custom agent?

-   반복 작업 자동화로 시간 절약
-   사용자에게 친숙하고 가이드된 경험 제공
-   비즈니스 또는 프로젝트 요구사항에 맞춤화 가능

### ✨ Example

직원이 휴가를 신청하도록 돕는 커스텀 에이전트를 만든다고 가정해
보겠습니다.

이 에이전트는 이름, 휴가 날짜, 매니저 이름을 묻고 SharePoint 목록 같은
휴가 관리 시스템에 저장합니다.

이제 직원은 SharePoint로 이동해 항목을 직접 생성할 필요 없이 에이전트와
대화만 하면 됩니다.

## 🗣️ Use natural language to create agents

이전 레슨에서는 [Lesson 05 - Get started quickly with pre-built
agents](../05-using-prebuilt-agents/index.md)에서 사전 빌드된 템플릿으로
빠르게 에이전트를 만드는 방법을 배웠습니다. 이번 레슨에서는 AI 기반
대화형 작성 경험을 살펴봅니다. Copilot Studio에서는 코드를 작성하지
않아도 자연어 설명만으로 에이전트를 만들 수 있습니다.

자연어로 에이전트를 설명하면 AI가 자동으로 이름, 설명, 지침을 생성하고
트리거, 채널, 지식 소스, 도구까지 제안합니다. 이러한 제안은 현재
세션에서만 유지됩니다.

## 🌱 But I'm new to "describing what I want" - what do I do?

자연어로 에이전트를 설명하는 것이 처음일 수 있습니다. Microsoft 제품
전반의 Copilot을 사용할 때 여러분은 이미 프롬프트라는 형태로 자연어를
사용하고 있습니다.

프롬프트는 AI 에이전트에게 무엇을 해야 하는지 전달하는 메시지입니다. 즉,
비서에게 명확한 지시를 내리는 것과 같습니다.

### 🪄 Why Prompts matter

-   에이전트의 동작을 안내합니다.
-   어떤 대화를 해야 하는지 이해하도록 돕습니다.
-   좋은 프롬프트는 더 정확한 응답을 만듭니다.

### 📝 Tips for writing a good prompt

-   명확하고 구체적으로 작성하세요.
-   사용자 관점에서 생각하세요.
-   가능하면 예시를 포함하세요.

> \[!TIP\] ✨ Example
>
> HR 팀이 휴가 요청을 돕는 에이전트를 만든다고 가정합니다.
>
> 프롬프트 예시:
>
> `I want to build an agent that helps users submit a vacation request. When a user says they want to request time off, the agent should ask for their name, the start date of their vacation, the end date of their vacation, and their manager’s name. Once the user provides this information, the agent should save it to a SharePoint list called 'Vacation Requests' and post a notification in a dedicated Microsoft Teams channel.`
>
> 이 프롬프트가 좋은 이유:
>
> -   **목표가 명확함**
> -   **사용자 상호작용 설명**
> -   **필수 데이터 명시**
> -   **데이터 저장 위치 명확**

## 🔮 OK, I've created my agent... how do I next ground it with knowledge?

Copilot Studio에서 지식 소스는 에이전트가 더 나은 답변을 하기 위해
정보를 가져오는 위치입니다. Power Platform, Dynamics 365, 웹사이트 등
다양한 엔터프라이즈 데이터를 사용할 수 있습니다.

이 과정은 **generative orchestration**을 통해 이루어집니다.

### 🌿 What is generative orchestration in the context of agents?

생성형 오케스트레이션이란 AI가 질문에 답변하기 위해 언어 능력과 추가된
지식 소스를 결합하는 방식입니다.

사용자가 질문하면 에이전트는:

-   AI로 질문 이해
-   필요한 정보가 없으면 추가 질문 생성
-   관련 지식 소스 선택
-   소스 검색
-   자연스럽고 유용한 답변 생성

### 🏦 Why knowledge sources matter?

1.  **더 스마트한 답변**
2.  **수동 작성 감소**
3.  **신뢰 가능한 정보 사용**
4.  **생성형 AI와 결합**
5.  **확장 가능**

> \[!TIP\] ✨ Example
>
> HR 정책 문서와 SharePoint를 추가하면 직원이 "휴가 일수는 얼마나
> 되나요?"라고 물을 때 정책을 자동으로 찾아 답변합니다.

## Types of knowledge sources that can be added

1.  **Public websites**
    -   **기능:** Bing을 사용해 특정 웹사이트 검색
    -   **장점:** FAQ나 제품 정보 활용
2.  **Documents**
    -   **기능:** 업로드한 PDF, Word 문서 활용
    -   **장점:** 내부 가이드 기반 답변 가능
3.  **SharePoint**
    -   **기능:** SharePoint 파일 연결
    -   **장점:** 팀 문서 접근
4.  **Dataverse**
    -   **기능:** 구조화 데이터 사용
    -   **장점:** 고객 정보 조회 가능
5.  **Real-time knowledge with connectors**
    -   **기능:** Salesforce, ServiceNow 등 실시간 데이터 접근
    -   **장점:** 최신 정보 제공
6.  **Azure AI Search**
    -   **기능:** 시맨틱/벡터 검색 활용
    -   **장점:** 대규모 문서 기반 정확한 답변

## 🔒 Note on security

### Knowledge source authentication

일부 소스는 인증이 필요하며 사용자가 접근 가능한 데이터만 참조됩니다.

## Improving your agent's responses in Copilot Studio

에이전트 생성 후에는 응답 품질을 개선해야 합니다.

1.  **지침 개선**
2.  **톤 조정**
3.  **지식 소스 업데이트**
4.  **Topics & Triggers 사용**
5.  **실제 질문으로 테스트**
6.  **반복 개선**

## 🧪 Lab 06: Create a custom agent in Copilot Studio

이제 데이터를 기반으로 대화하는 커스텀 에이전트를 만들어 봅니다.

### ✨ Use case

[Lesson 03 - Create a declarative agent for Microsoft 365
Copilot](../03-create-a-declarative-agent-for-M365Copilot/index.md#use-case-scenario)과
동일한 시나리오를 사용합니다.

**As an** employee

**I want to** IT 헬프데스크 에이전트로부터 빠르고 정확한 지원을 받고

**So that I can** 생산성을 유지하고 문제를 빠르게 해결하기

Let's begin!

### ✨ Prerequisites

-   **SharePoint site**
-   **Solution**

(설정이 안 되어 있다면 해당 레슨으로 돌아가세요.)

### 6.1 Use natural language to create an agent with AI

> \[!WARNING\] AI generated instructions may differ across sessions

1.  Copilot Studio Home에서 다음 프롬프트 입력

``` text
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

![Enter prompt](./assets/6.1_01_Prompt.png)

(이후 단계 설명은 UI 조작 안내이므로 동일하게 진행)

![View of Agent Settings](./assets/6.1_02_AgentSettings.png) ![Setting
up agent](./assets/6.1_03_AgentProvisioned.png) ![Knowledge sources and
tools sections with suggestions from
AI](./assets/6.1_04_KnowledgeAndTools.png) ![Connected Agents, Topics
and Suggested Prompts
sections](./assets/6.1_05_ConnectedAgentsTopicsSuggestedPrompts.png)
![Select Settings](./assets/6.1_06_AgentSettings.png) ![Solution created
in Contoso Helpdesk Agent
solution](./assets/6.1_07_AdvancedSettings.png) ![Select Edit in Details
section](./assets/6.1_08_EditDetails.png)

``` text
Contoso Helpdesk Agent
```

![Update agent name](./assets/6.1_09_AgentName.png) ![Select add for the
suggested website URL](./assets/6.1_10_AddSuggestedWebsite.png) ![Select
add](./assets/6.1_11_AddWebsite.png)

``` text
https://learn.microsoft.com/troubleshoot/
```

![Add second website URL](./assets/6.1_12_AddAdditionalWebsite.png)
![Select Dismiss](./assets/6.1_13_SelectDismiss.png) ![Disable Web
Search](./assets/6.1_14_DisableWebSearch.png) ![Select start new test
session in testing pane](./assets/6.1_15_StartNewTestSession.png)

``` text
How can I check the warranty status of my Surface?
```

![Test newly created agent](./assets/6.1_16_EnterQuestion.png)
![References in response](./assets/6.1_17_References.png)

축하합니다! Copilot Studio에서 자연어 설명만으로 첫 커스텀 에이전트를
만들었습니다 🙌🏻

### 6.2 Add an internal knowledge source using a SharePoint site

![Select SharePoint](./assets/6.2_01_SelectSharePoint.png) ![Update
SharePoint site name and select Add to
agent](./assets/6.2_02_AddSharePointSite.png) ![SharePoint site
status](./assets/6.2_03_SharePointSiteAdded.png)

### 6.3 Add an internal knowledge source by uploading a document

![Select upload files](./assets/6.3_01_SelectUploadFile.png)

Download this [sample
file](https://raw.githubusercontent.com/microsoft/agent-academy/refs/heads/main/docs/recruit/06-create-agent-from-conversation/assets/Contoso_Guest_WiFi_Connection_Guide.docx)

![Select document](./assets/6.3_02_SelectWordFile.png) ![Select Add to
Agent](./assets/6.3_03_SelectAddToAgent.png) ![Document
added](./assets/6.3_04_FileAdded.png) ![File
status](./assets/6.3_05_FileStatus.png)

### 6.4 Test agent

``` text
How can I find the serial number on my Surface device?
```

![Select start a new test session
icon](./assets/6.4_01_EnterQuestion1.png) ![Question 1
response](./assets/6.4_02_Question1Response.png) ![Knowledge sources
referenced and searched](./assets/6.4_03_OtherSourcesSearchedOver.png)

``` text
How can I access our company's Contoso VPN from my device? How do guests connect to the Contoso Guest wifi?
```

![Test SharePoint and document knowledge
sources](./assets/6.4_04_EnterQuestion2Question3.png) ![Knowledge
sources referenced for Question 1 and Question
2](./assets/6.4_05_Question2Response.png) ![Question 3
response](./assets/6.4_06_Question3Response.png) ![Activity modal of
other sources searched
over](./assets/6.4_07_OtherSourcesSearchedOver.png) ![Review
document](./assets/6.4_08_VerifyDocument.png)

## ✅ Mission Complete

축하합니다 👏🏻 Copilot Studio에서 자연어 설명으로 커스텀 에이전트를
생성하는 방법을 배웠습니다. 이제 에이전트는 네 가지 지식 소스를 기반으로
대화할 수 있습니다 🙌🏻

⏭️ [Move to **Add a new Topic with trigger**
lesson](../07-add-new-topic-with-trigger/index.md)

이제 여러분은 데이터와 대화하는 디지털 에이전트를 만들 수 있습니다. 다음
미션으로 계속 진행하세요.

## 📚 Tactical Resources

🔗 [Quickstart: Create and deploy an
agent](https://learn.microsoft.com/microsoft-copilot-studio/fundamentals-get-started?context=%2Fmicrosoft-365-copilot%2Fextensibility%2Fcontext/?WT.mc_id=power-172617-ebenitez)

🔗 [Create and delete
agents](https://learn.microsoft.com/microsoft-copilot-studio/authoring-first-bot?WT.mc_id=power-172617-ebenitez)

🔗 [Key concepts - Authoring
agents](https://learn.microsoft.com/microsoft-copilot-studio/authoring-fundamentals/?WT.mc_id=power-172617-ebenitez)

📺 [Create a custom agent using natural
language](https://aka.ms/ai-in-action/copilot-studio/ep1)

📺 [Add knowledge to your
agents](https://aka.ms/ai-in-action/copilot-studio/ep2)

```{=html}
<!-- markdownlint-disable-next-line MD033 -->
```
`<img src="https://m365-visitor-stats.azurewebsites.net/agent-academy/recruit/06-create-agent-from-conversation" alt="Analytics" />`{=html}
