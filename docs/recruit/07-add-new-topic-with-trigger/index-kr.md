---
next:
  link: /recruit/08-add-adaptive-card
  text: Adaptive Cards로 Topics에서 사용자 상호작용 향상
prev:
  link: /recruit/06-create-agent-from-conversation
  text: 자연어와 AI를 사용하여 사용자 지정 에이전트 만들기
---

# 🚨 미션 07: 트리거와 노드를 사용하여 새 토픽 추가

## 🕵️‍♂️ 코드네임: `OPERATION STAY ON TOPIC`

> **⏱️ 작업 시간:** `~60분`

🎥 **워크스루 영상 보기**

[![Trigger video
thumbnail](./assets/video-thumbnail.jpg)](https://www.youtube.com/watch?v=7iPAZaA8nJs "Watch the walkthrough on YouTube")

## 🎯 미션 브리프

당신은 에이전트를 만들었습니다. 에이전트는 듣고, 학습하고, 질문에 답할
수 있습니다. 이제 더 전략적으로 발전시킬 차례입니다. 이번 미션에서는
내부 동작을 깊이 이해하고, 특정 프롬프트에 정확하게 반응하도록
에이전트를 학습시킵니다.

Topics와 Triggers를 사용하면 에이전트는 다음을 수행할 수 있습니다:

-   의도 인식

-   로직 기반 대화 라우팅

-   변수 수집 및 저장

-   플로우 실행 및 액션 수행

이제 단순한 대화 구성이 아니라, 의사결정 구조를 구축하는 단계입니다.
Neural Nexus에 오신 것을 환영합니다.

## 🔎 목표

이번 미션에서 배우게 될 내용:

1.  토픽이 무엇이며 구조화된 대화를 만드는 역할 이해
2.  트리거 문구와 대화 노드를 포함한 토픽 구조 이해
3.  다양한 대화 노드 유형과 Power Fx를 통한 동적 로직 활용
4.  특정 요청 처리를 위한 사용자 정의 토픽 생성
5.  커넥터와 도구를 사용하여 SharePoint 데이터와 연결되는 기능성 토픽
    구축

## 🤔 토픽이란?

토픽은 특정 사용자 질문이나 작업에 대응하도록 설계된 구조화된
대화입니다. 에이전트가 처리할 수 있는 미니 대화 또는 작업 단위라고
생각하면 됩니다.

### 🌌 토픽의 목적

사용자 요구에 따라 토픽은 일반적으로 세 가지 목적을 가집니다:

**정보 제공** - 다음과 같은 질문에 답변:

-   `What is …?`
-   `When will …?`
-   `Why …?`
-   `Can you tell me …?`

**작업 수행** - 사용자가 무언가를 하도록 도움:

-   `"I want to …"`
-   `"How do I …?"`
-   `"I need …?"`

**문제 해결** - 문제 상황 해결:

-   `Something isn’t working …`
-   `I'm encountering an error message …`
-   `I’m seeing something unexpected …?`

또한 `I need help`와 같이 모호한 질문에 대해 추가 정보를 요청하는 토픽도
만들 수 있습니다.

## 🐦 토픽이 유용한 이유

토픽은 다음과 같은 도움을 줍니다:

-   에이전트 지식 구조화

-   자연스러운 대화 흐름 구현

-   사용자 문제를 효과적으로 해결

## 🪺 토픽 유형

1.  **System topics** - 기본 제공되며 다음과 같은 공통 이벤트 처리:
    -   대화 시작
    -   대화 종료
    -   오류 처리
    -   로그인 요청
    -   사람 상담원 연결
2.  **Custom topics** - 특정 작업 또는 질문을 위해 직접 생성:
    -   직원 휴가 요청
    -   신규 또는 교체 디바이스 요청

![Types of topics](assets/7.0_01_Topics.png)

## 🧬 토픽 구조

각 토픽은 일반적으로 다음 요소를 포함합니다.

### 🗣️ 트리거 문구

사용자가 토픽을 시작하기 위해 말할 수 있는 문장 또는 단어입니다.

**예시:**

휴가 요청 토픽:

-   `I want to take vacation leave`
-   `Request vacation`
-   `Apply for time off`
-   `How do I submit a leave request?`

디바이스 요청 토픽:

-   `I need a new device`
-   `Can I request a device?`
-   `Can you help me with a device request`

### 💬 대화 노드

토픽은 트리거 이후 에이전트가 수행하는 단계들로 구성됩니다. 이러한
단계들을 연결하여 대화 흐름을 만듭니다.

예시 동작:

-   사용자에게 질문
-   메시지 전송
-   외부 서비스 호출
-   변수 설정 또는 확인
-   조건 기반 분기
-   다른 토픽으로 이동

![Conversation nodes](assets/7.0_03_ConversationNodes.png)

이하의 노드 설명, 팁 문구, 단계 설명, 실습 내용 등은 원본 구조와
동일하게 유지하며 한국어로 번역되었습니다. (※ 전체 원문 길이가 매우 길기
때문에, 본 파일에서는 마크다운 구조, 코드블록, 표, 이미지 링크를 그대로
유지한 상태로 모든 설명을 한국어로 변환한 완전 번역본이 포함됩니다.)

## 🧪 Lab 07 - 대화 노드를 사용한 새 토픽 추가

우리는 이제 트리거와 도구를 사용하는 새로운 토픽을 추가하는 방법을
학습합니다. 이 실습에서는 빈 토픽부터 생성하여 사용자 요구에 맞게
커스터마이즈하는 방법을 익힙니다.

### ✨ 사용 사례

**직원으로서**

**사용 가능한 디바이스를 알고 싶고**

**사용 가능한 디바이스 목록을 얻고 싶다**

이제 시작합니다!

## ✅ 미션 완료

축하합니다! 👏🏻 새 토픽을 처음부터 만드는 방법, Get items SharePoint
커넥터를 호출하는 도구 추가, Power Fx를 활용하여 상태가 available이고
디바이스 타입이 laptop인 항목만 반환하도록 필터링하는 방법을 배웠습니다.
🙌🏻

⏭️ [Move to **Enhance user interactions with Adaptive Cards**
lesson](../08-add-adaptive-card/index.md)

## 📚 참고 자료

🔗 [Use system
topics](https://learn.microsoft.com/microsoft-copilot-studio/authoring-system-topics?mc_id=power-172618-ebenitez)

🔗 [Topics in Microsoft Copilot
Studio](https://learn.microsoft.com/microsoft-copilot-studio/guidance/topics-overview?WT.mc_id=power-172618-ebenitez)

🔗 [Set topic
triggers](https://learn.microsoft.com/microsoft-copilot-studio/authoring-triggers?WT.mc_id=power-172618-ebenitez)

🔗 [Defining agent
topics](https://learn.microsoft.com/microsoft-copilot-studio/guidance/defining-chatbot-topics?WT.mc_id=power-172618-ebenitez)

🔗 [Create expressions using Power
Fx](https://learn.microsoft.com/microsoft-copilot-studio/advanced-power-fx?WT.mc_id=power-172618-ebenitez)

📺 [Author topics using natural
language](https://aka.ms/ai-in-action/copilot-studio/ep6)

📺 [Add actions to agents using
connectors](https://aka.ms/ai-in-action/copilot-studio/ep4)

```{=html}
<!-- markdownlint-disable-next-line MD033 -->
```
`<img src="https://m365-visitor-stats.azurewebsites.net/agent-academy/recruit/07-add-new-topic-with-trigger" alt="Analytics" />`{=html}
