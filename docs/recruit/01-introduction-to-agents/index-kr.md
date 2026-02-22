---
prev:
  text: 'Course Setup'
  link: '/recruit/00-course-setup'
next:
  text: 'Copilot Studio Fundamentals'
  link: '/recruit/02-copilot-studio-fundamentals'
---

# 🚨 Mission 01: 에이전트 소개

## 🕵️‍♂️ CODENAME: `OPERATION AI AGENT DECODE`

> **⏱️ Operation Time Window:** `~30분 – 개념 이해 중심, 실습 없음`

🎥 **워크스루 영상 보기**

[![Introduction to Agents video thumbnail](./images/video-thumbnail.jpg)](https://www.youtube.com/watch?v=BhPz_zicUnM "Watch the walkthrough on YouTube")

## 🎯 Mission Brief

환영합니다, 리크루트. 에이전트를 직접 만들기 전에, 이를 구동하는 AI 개념을 확실히 이해해야 합니다. 이번 미션에서는 대화형 AI, 대형 언어 모델(LLM), 검색 증강 생성(RAG), 그리고 Copilot Studio에서 만들 수 있는 다양한 에이전트 유형에 대한 기초 지식을 익히게 됩니다.

## 🔎 Objectives

이번 미션에서 배우게 될 내용:

1.  대화형 AI란 무엇인지
2.  대형 언어 모델(LLM)이 채팅 경험을 어떻게 구현하는지
3.  검색 증강 생성(RAG)이 제공하는 가치
4.  대화형 에이전트와 자율형 에이전트의 차이
5.  Copilot Studio 에이전트가 이러한 개념을 어떻게 활용하는지

이제 시작해 봅시다!

## What Is Conversational AI?

대화형 AI는 인간의 언어(텍스트 또는 음성)를 자연스럽게 이해하고 처리하며 응답할 수 있는 시스템을 의미합니다. 예를 들어 웹사이트에서 주문 상태를 알려주는 챗봇이나, 앱 안에서 동작하는 가상 개인 비서가 이에 해당합니다. 대부분의 최신 대화형 AI는 내부적으로 대형 언어 모델(LLM)에 의존합니다.

## Large Language Models (LLMs) 101

대부분의 대화형 AI 시스템의 핵심에는 **대형 언어 모델(Large Language Models)** 이 있습니다. 이는 방대한 텍스트로 학습된 신경망으로, 언어의 통계적 패턴을 학습하여 자연스러운 문장을 생성하고 질문에 답하거나 아이디어를 브레인스토밍하고 콘텐츠를 생성할 수 있습니다. 핵심 포인트:

1.  **Training Data:** LLM은 웹페이지, 책, 시, 기사 등 테라바이트 단위의 텍스트를 학습합니다. 이러한 "세계 지식"을 통해 다양한 주제에 대응할 수 있습니다.
2.  **Tokenization:** 텍스트는 토큰(단어, 부분 단어, 문자 등)이라는 작은 단위로 나뉘며, 모델은 한 번에 하나의 토큰을 예측합니다.
3.  **Context Window:** 각 LLM은 한 번에 처리할 수 있는 토큰 수 제한이 있으며, 이를 초과하면 이전 내용은 요약되거나 잘립니다.
4.  **Prompting:** 사용자는 프롬프트(질문이나 요청 텍스트)를 보내 LLM과 상호작용합니다. 프롬프트가 명확할수록 더 정확하고 관련성 높은 응답을 얻을 수 있습니다.

> [!TIP]
> LLM은 흔히 "초고성능 자동완성"에 비유됩니다. 인간처럼 의미를 완전히 이해하는 것은 아니지만, 다음에 올 가장 적절한 단어나 문장을 매우 잘 예측합니다.

## Retrieval-Augmented Generation (RAG)

LLM이 학습 데이터에만 의존하면 환각(hallucination)이 발생하거나 최신 정보가 반영되지 않을 수 있습니다. RAG는 모델이 답변을 생성하기 전에 최신 정보를 조회하도록 하여 이를 보완합니다. 개념적으로 RAG는 다음과 같이 동작합니다:

1.  **User Query:** 사용자가 질문을 입력합니다 (예: "Contoso의 최신 분기 실적은?")
2.  **Retriever Step:** 시스템이 문서, 웹사이트, 내부 데이터베이스, SharePoint 등에서 관련 정보를 검색합니다.
3.  **Augmentation:** 검색된 데이터를 LLM에 보내기 전에 프롬프트에 추가합니다.
4.  **Generation:** LLM은 사용자 질문과 검색된 컨텍스트를 함께 활용하여 최신 정보 기반의 응답을 생성합니다.

RAG를 사용하면 에이전트가 내부 위키, API, FAQ 지식 베이스 등을 조회하여 정적 학습 데이터에만 의존하지 않는 답변을 제공할 수 있습니다.

## Conversational vs. Autonomous Agents

Copilot Studio에서 **에이전트**라는 용어는 여러 유형의 AI 도우미를 의미합니다. 크게 다음 두 가지로 나눌 수 있습니다:

**Conversational Agents:**

-   텍스트 또는 음성 기반의 양방향 대화가 필요합니다.
-   여러 턴의 대화에서 컨텍스트를 유지합니다.
-   외부 도구 또는 API와 연동할 수 있습니다 (예: Power Automate 호출, 일정 초대 전송, Dataverse 데이터 조작).
-   고객 지원, FAQ, 가이드형 상호작용, 간단한 Q&A에 적합합니다.
    -   예시:
        -   HR 정책 질문에 답하는 Microsoft Teams 에이전트
        -   제품 관련 질문에 답하는 웹사이트 에이전트

**Autonomous Agents:**

-   단순한 대화를 넘어 사용자를 대신해 **행동을 수행**합니다.
-   "계획 → 실행 → 관찰 → 재계획"과 같은 LLM 추론 루프를 활용합니다.
-   외부 도구 또는 API와 연동할 수 있습니다.
-   지속적인 사용자 입력 없이도 동작하며, 트리거되면 여러 단계를 자율적으로 수행합니다.
    -   예시:
        -   여행 요청이 입력되면 일정 생성, 항공권 예약, 이메일 발송까지 수행하는 에이전트
        -   Teams 회의에 참여해 실시간 전사 후 OneNote에 요약을 작성하는 회의 요약 에이전트

> [!IMPORTANT]    
> Key Difference
> 대화형 에이전트는 사용자 입력이 있어야 동작합니다. 자율형 에이전트는 외부 트리거를 기반으로 사람의 개입 없이도 작업을 수행할 수 있습니다.

## Agents in Copilot Studio

**Copilot Studio**는 대화형 및 자율형 시나리오를 하나의 프레임워크로 통합합니다. 주요 기능:

1.  **Visual Agent Designer:** 드래그 앤 드롭 방식으로 에이전트를 설계, 테스트, 배포할 수 있는 캔버스.
2.  **Model (LLM) Selection:** OpenAI, Anthropic, Custom 모델 등 다양한 AI 모델 선택 가능.
3.  **Knowledge:** SharePoint, OneDrive, Dataverse 등 기본 연동을 통해 RAG를 쉽게 구성.
4.  **Tools:** 외부 도구 또는 API와 연결하여 행동 수행 가능.
5.  **Multi-Modal Support:** 파일 업로드 및 음성 대화를 지원.
6.  **Publishing & Distribution:** Microsoft 365 Copilot, 웹사이트 임베드 등 다양한 채널로 배포 가능.

## 🎉 Mission Complete

이제 에이전트와 핵심 AI 개념에 대한 소개를 완료했습니다. 정리하면:

1.  **LLMs = 에이전트의 두뇌**
    -   언어 이해와 생성 담당
2.  **RAG = 실시간 지식 통합**
    -   정적인 LLM과 변화하는 데이터 사이의 간극을 연결
    -   관련 문서를 프롬프트에 주입
3.  **Conversational vs. Autonomous**
    -   **Conversational:** 대화 중심
    -   **Autonomous:** 외부 트리거 기반 자율 실행

다음 단계에서는 [Copilot Studio 기초](../02-copilot-studio-fundamentals/index.md)를 살펴봅니다!

계속 집중하세요, 이제 AI 여정이 시작됩니다.

## 📚 Tactical Resources

🔗 [Copilot Studio Documentation Home](https://learn.microsoft.com/microsoft-copilot-studio/)

<!-- markdownlint-disable-next-line MD033 -->
<img src="https://m365-visitor-stats.azurewebsites.net/agent-academy/recruit/01-introduction-to-agents" alt="Analytics" />
