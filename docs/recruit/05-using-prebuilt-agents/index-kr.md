# 🧰 Mission 05: Using a Pre-Built Agent

## 🕵️‍♂️ CODENAME: `OPERATION SAFE TRAVELS`

> **⏱️ Operation Time Window:** `~30 minutes`

## 🎯 Mission Brief

Copilot Studio Agent Academy의 다음 미션에 오신 것을 환영합니다. 이제 **pre-built agents**의 세계를 살펴보게 됩니다. 이는 Microsoft에서 제공하는 목적 중심의 지능형 에이전트로, 배포 속도를 높이고 Time‑to‑Value를 줄이도록 설계되었습니다.

처음부터 새로 구축하는 대신, pre-built agents(또는 **agent templates**)는 즉시 사용 가능한 시나리오를 제공하여 몇 분 안에 커스터마이즈하고 배포할 수 있도록 도와줍니다.

이번 미션에서는 사용자의 출장 준비를 돕고, 회사 정책을 이해하며, 계획을 간소화하는 **Safe Travels** 에이전트를 배포합니다.

## 🧭 Objectives

이번 미션의 목표는 다음과 같습니다:

1.  pre-built agents가 무엇이며 왜 중요한지 이해
2.  **Safe Travels** agent template 배포
3.  에이전트의 응답과 콘텐츠 커스터마이즈
4.  에이전트 테스트 및 게시

## 🧠 What Are Pre-Built Agents?

Pre-built agents는 Microsoft에서 제공하는 turnkey AI agents로 다음을 포함합니다:

-   출장, HR, IT 지원과 같은 일반적인 비즈니스 요구사항 해결
-   완전히 동작하는 topics, trigger phrases, instructions, sample knowledge 포함
-   조직 데이터로 수정, 확장, grounding 가능

빠르게 시작하거나 에이전트 구조를 학습할 때 매우 적합합니다.

## 🧪 Lab 05: Quickly get started with a pre-built agent

이제 pre-built agent를 선택하고 커스터마이즈하는 방법을 학습합니다.

앞서 예제와 동일하게, 전용 Copilot Studio 환경에서 IT helpdesk agent를 구축하기 위한 solution을 생성하는 흐름을 유지합니다.

이제 시작합니다.

### 5.1 Launch Copilot Studio

1.  <https://copilotstudio.microsoft.com> 로 이동

2.  Microsoft 365 회사 또는 학교 계정으로 로그인

> [!WARNING]
> Copilot Studio가 활성화된 tenant에서 작업해야 합니다. Copilot Studio가 보이지 않는다면 [Mission 00](../00-course-setup/index.md)로 돌아가 설정을 완료하세요.

### 5.2 Choose the Safe Travels Agent Template

1.  Copilot Studio homepage에서 **+ Create** 클릭 ![Create an agent](./images/create.png)

2.  **Start with an agent template** 섹션까지 스크롤

3.  **Safe Travels** 선택

    ![Choose safe travels template](./images/choose_template.png)

4.  템플릿에 description, instructions, knowledge가 미리 포함된 것을 확인

    ![Review the template](./images/template-setup.png)

5.  **Create** 클릭

    ![Create an agent](./images/create-agent-setup.png)

이 단계에서 Safe Travels 구성을 기반으로 새로운 agent가 생성됩니다.

### 5.3 Customize the Agent

이제 조직에 맞게 agent를 조정합니다:

1.  template에 제공된 instructions를 활용하도록 **Enabled generative AI** 선택

    ![Enable Generative Answers](./images/gen-answers.png)

2.  유럽 여행 관련 질문에 답할 수 있도록 추가 knowledge source를 연결합니다. **knowledge** 섹션에서 **Add knowledge** 선택

    ![Add Knowledge](./images/knowledge.png)

3.  **Public websites** 선택

    ![Add a public website](./images/public-website.png)

4.  입력창에 **<https://european-union.europa.eu/>** 입력 후 **Add** 선택

    ![Add the website](./images/paste-add.png)

5.  **Add to agent** 선택

    ![Add to Agent](./images/add-to-agent.png)

### 5.4 Test and Publish

1.  우측 상단 **Test** 클릭하여 테스트 창 실행

2.  다음 문장을 입력해 테스트:

    -   `미국에서 암스테르담으로 여행하려면 비자가 필요한가요?`
    -   `미국 여권을 발급받는 데 얼마나 걸리나요?`
    -   `스페인 발렌시아에서 가장 가까운 미국 대사관은 어디에 있나요?`

3.  agent가 정확한 답변을 제공하는지 확인하고 Activity Map에서 정보 출처 확인

    ![Add to Agent](./images/response-passport.png)

4.  준비가 되면 **Publish** 클릭

    ![Add to Agent](./images/publish-1.png)

5.  대화 상자에서 다시 **Publish** 선택 

    ![Add to Agent](./images/publish-2.png)

6.  필요 시 **Channels** 기능을 사용하여 Microsoft Teams에 agent 추가 가능

> [!NOTE]   
> 🧳 Bonus Objective SharePoint site 또는 FAQ 파일을 grounding하여 조직의 출장 정책에 맞게 Safe Travels agent를 확장해 보세요.

## ✅ Mission Complete

다음을 완료했습니다:

-   Microsoft pre-built agent 배포
-   agent 커스터마이즈
-   Safe Travels agent template 테스트 및 게시

⏭️ [Move to **Creating a custom agent from scratch** lesson](../06-create-agent-from-conversation/index-kr.md).

<!-- markdownlint-disable-next-line MD033 -->
<img src="https://m365-visitor-stats.azurewebsites.net/agent-academy/recruit/05-using-prebuilt-agents" alt="Analytics" />
