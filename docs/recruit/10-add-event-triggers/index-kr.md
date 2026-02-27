# 🚨 Mission 10: 이벤트 트리거 추가 - 자율 에이전트 기능 활성화

## 🕵️‍♂️ CODENAME: `OPERATION GHOST ROUTINE`

> **⏱️ Operation Time Window:** `~45 minutes`

## 🎯 Mission Brief

이제 에이전트를 단순한 대화형 도우미에서 자율적으로 동작하는 운영
자산으로 발전시킬 시간입니다. 이번 미션의 목표는 호출되지 않아도 동작할
수 있도록 에이전트를 구성하는 것입니다. 즉, 디지털 환경 전반의 신호를
감지하고 빠르고 정확하게 대응하도록 만드는 것입니다.

이벤트 트리거를 사용하면 SharePoint, Teams, Outlook과 같은 외부 시스템을
모니터링하고, 신호가 감지되는 즉시 지능형 작업을 수행하도록 에이전트를
훈련할 수 있습니다. 이 과정은 에이전트를 조용하지만 민첩하게 항상
감시하는 완전한 운영 자산으로 변화시킵니다.

성공의 기준은 단순히 요청에 응답하는 것이 아니라, 스스로 가치를
만들어내는 에이전트를 구축하는 것입니다.

## 🔎 Objectives

📖 이번 학습에서는 다음 내용을 다룹니다:

-   이벤트 트리거가 무엇이며 자율 에이전트 동작을 어떻게 가능하게 하는지
    이해하기
-   이벤트 트리거와 토픽 트리거의 차이, 트리거 워크플로우와 페이로드
    이해하기
-   일반적인 이벤트 트리거 시나리오 살펴보기
-   이벤트 기반 에이전트의 인증, 보안, 게시 시 고려사항 이해하기
-   SharePoint 이벤트에 반응하고 이메일 확인을 보내는 자율 IT Help Desk
    에이전트 구축하기

## 🤔 What is an Event Trigger?

**Event Trigger**는 외부 이벤트에 반응하여 사용자 입력 없이 에이전트가
자율적으로 동작하도록 하는 메커니즘입니다. 특정 이벤트를 "감시"하다가
발생 시 자동으로 행동하도록 만드는 기능이라고 생각하면 됩니다.

토픽 트리거가 사용자의 입력을 필요로 하는 것과 달리, 이벤트 트리거는
연결된 시스템에서 발생하는 이벤트를 기반으로 활성화됩니다. 예:

-   SharePoint 또는 OneDrive for Business에 새 파일 생성
-   Dataverse에 레코드 생성
-   Planner에서 작업 완료
-   Microsoft Form에 새 응답 제출
-   Microsoft Teams에 새 메시지 추가
-   반복 일정 기반 실행 (예: 매일 알림)

![Add Trigger](./assets/10_AddTriggerDialog.png)

### 자율 에이전트에서 이벤트 트리거가 중요한 이유

이벤트 트리거는 에이전트를 반응형 도우미에서 능동적이고 자율적인 헬퍼로
변화시킵니다:

1.  **자율 운영** - 사람의 개입 없이 24/7 동작하며 이벤트 발생 즉시
    대응합니다.
    -   *예:* 새 팀원이 추가되면 자동으로 환영 메시지 전송
2.  **실시간 반응성** - 사용자의 질문을 기다리지 않고 관련 이벤트에 즉시
    대응합니다.
    -   *예:* SharePoint 문서 수정 시 IT 팀에 알림
3.  **워크플로우 자동화** - 하나의 트리거 이벤트로 여러 작업을
    연결합니다.
    -   *예:* 지원 티켓 생성 시 작업 생성, 관리자 알림, 대시보드
        업데이트
4.  **일관된 프로세스** - 중요한 단계가 누락되지 않도록 자동화합니다.
    -   *예:* 신규 직원에게 온보딩 자료 자동 제공
5.  **데이터 기반 작업** - 트리거 페이로드 정보를 활용해 지능적인
    의사결정 수행
    -   *예:* 우선순위에 따라 긴급 티켓을 시니어 담당자에게 라우팅

## ⚙️ How do Event Triggers work?

이벤트 트리거는 외부 이벤트에 자율적으로 반응하도록 하는 3단계
워크플로우로 동작합니다:

### The trigger workflow

1.  **Event Detection** - 연결된 시스템(SharePoint, Teams, Outlook
    등)에서 특정 이벤트 발생
2.  **Trigger Activation** - 이벤트 트리거가 이를 감지하고 Power
    Automate Cloud Flow를 통해 페이로드를 에이전트에 전달
3.  **Agent Response** - 에이전트가 페이로드를 받아 정의된 작업 수행

### Event vs Topic triggers

두 트리거 유형의 차이를 이해하는 것은 매우 중요합니다:

| **Event Triggers** | **Topic Triggers** |
| :-- | :-- |
| 외부 시스템 이벤트로 활성화 | 사용자 입력/문장으로 활성화 |
| 자율 에이전트 동작 가능 | 대화형 응답 제공 |
| 제작자 인증 사용 | 사용자 인증 옵션 |
| 사용자 상호작용 없이 실행 | 사용자가 대화를 시작해야 함 |
| 예: 파일 생성, 이메일 수신 | 예: "오늘 날씨 어때?" |

## 📦 Understanding trigger payloads

이벤트가 발생하면 트리거는 이벤트 정보와 응답 지침을 포함한
**payload**를 에이전트로 전달합니다.

### Default vs custom payloads

각 트리거에는 기본 페이로드 구조가 있지만 사용자 정의가 가능합니다:

**Default payload** - `Use content from {Body}`와 같은 기본 형식 사용

-   기본 이벤트 정보 포함
-   일반적인 처리 지침 사용
-   단순한 시나리오에 적합

**Custom payload** - 구체적인 지침과 데이터 포맷 추가

-   에이전트에 상세한 방향 제시
-   사용할 데이터와 방식 명확히 지정
-   복잡한 워크플로우에 적합

### Agent instructions vs custom payload instructions

이벤트 트리거에서 에이전트 동작을 제어하는 두 가지 위치:

**Agent Instructions** (Global)

-   모든 트리거에 적용되는 전반적인 지침
-   예: "티켓 처리 시 항상 중복 여부 먼저 확인"
-   일반적인 행동 패턴에 적합

**Payload Instructions** (Trigger-specific)

-   특정 트리거에 대한 상세 지침
-   예: "이 SharePoint 업데이트는 프로젝트 채널에 요약 전송"
-   복잡한 다중 트리거 에이전트에 적합

💡 **Pro tip**: 두 레벨 간 지침이 충돌하지 않도록 주의하세요. 예상치
못한 동작이 발생할 수 있습니다.

## 🎯 Common Event Trigger scenarios

이벤트 트리거를 활용한 실제 사례:

### IT Help Desk Agent

-   **Trigger**: SharePoint 리스트 신규 항목(지원 티켓)
-   **Action**: 자동 분류, 우선순위 지정, 담당자 알림

### Employee Onboarding Agent

-   **Trigger**: Dataverse 신규 사용자 추가
-   **Action**: 환영 메시지 전송, 온보딩 작업 생성, 권한 프로비저닝

### Project Management Agent

-   **Trigger**: Planner 작업 완료
-   **Action**: 프로젝트 대시보드 업데이트, 이해관계자 알림

### Document Management Agent

-   **Trigger**: 특정 SharePoint 폴더 파일 업로드
-   **Action**: 메타데이터 추출, 태그 적용, 문서 소유자 알림

### Meeting Assistant Agent

-   **Trigger**: 일정 생성
-   **Action**: 사전 알림 및 아젠다 전송, 리소스 예약

## ⚠️ Publishing and authentication considerations

프로덕션에서 이벤트 트리거를 사용하려면 인증과 보안 영향을 이해해야
합니다.

### Maker authentication

이벤트 트리거는 **에이전트 제작자의 자격 증명**을 사용합니다:

-   에이전트는 제작자의 권한으로 시스템 접근
-   사용자가 제작자 권한으로 데이터에 접근할 가능성 존재
-   모든 작업이 제작자 계정 기준으로 수행됨

### Data protection best practices

보안을 유지하기 위한 권장 사항:

1.  **데이터 접근 검토** - 트리거가 접근 가능한 시스템과 데이터 확인
2.  **충분한 테스트** - 페이로드에 어떤 정보가 포함되는지 검증
3.  **트리거 범위 최소화** - 특정 조건으로 활성화 제한
4.  **페이로드 데이터 검토** - 민감 정보 노출 방지
5.  **사용량 모니터링** - 트리거 활동과 리소스 소비 추적

## ⚠️ Troubleshooting and limitations

이벤트 트리거 사용 시 고려 사항:

### Quota and billing impacts

-   트리거 실행마다 메시지 소비량 증가
-   잦은 트리거는 빠르게 쿼터 소모 가능
-   스로틀링 방지를 위해 사용량 모니터링 필요

### Technical requirements

-   Generative orchestration 활성화된 에이전트만 사용 가능
-   환경에서 solution-aware cloud flow 공유 필요

### Data Loss Prevention (DLP)

-   조직의 DLP 정책이 사용 가능한 트리거를 결정
-   관리자가 이벤트 트리거를 차단할 수 있음
-   예상 트리거가 보이지 않으면 관리자에게 문의

## 🧪 Lab 10 - Add Event Triggers for autonomous agent behavior

### 🎯 Use case

IT Help Desk 에이전트를 자동 응답하도록 확장합니다. SharePoint 지원 티켓
리스트에 새 항목이 생성되면:

1.  SharePoint 티켓 생성 시 자율적으로 트리거 실행
2.  티켓 정보와 수행할 작업 전달
3.  AI 생성 이메일로 제출자에게 자동 확인 메일 발송

이 실습은 이벤트 트리거가 진정한 자율 에이전트를 어떻게 만드는지
보여줍니다.

### Prerequisites

시작 전에 다음을 준비하세요:

-   ✅ 이전 실습 완료 (특히 Lab 6-8)
-   ✅ IT 지원 티켓 리스트가 있는 SharePoint 사이트 접근 권한
-   ✅ 이벤트 트리거가 활성화된 Copilot Studio 환경
-   ✅ 에이전트에 generative orchestration 활성화
-   ✅ SharePoint 및 Copilot Studio 권한

### 10.1 Enable Generative AI and create a SharePoint item creation trigger

1.  **Copilot Studio**에서 **Contoso Helpdesk agent** 열기

2.  먼저 **Generative AI** 활성화 확인:

    -   **Settings** 선택
    -   **Orchestration** 섹션에서 **Use generative AI orchestration for
        your agent's responses?** 를 **Yes**로 설정
        ![Enable Generative AI](./assets/10_EnableGenerativeAI.png)

3.  필요 시 **Save** 선택

4.  **Overview** 탭 → **Triggers** 섹션 이동

5.  **+ Add trigger** 클릭
    ![Navigate to Triggers](./assets/10_NavigateToTrigger.png)

6.  **When an item is created (SharePoint)** 선택
    ![Select SharePoint
    Trigger](./assets/10_SelectSharePointTrigger.png)

7.  트리거 이름과 연결 설정:

    -   **Trigger name:** New Support Ticket Created in SharePoint

8.  연결 구성 후 **Next** 선택
    ![Configure trigger name and
    connections](./assets/10_ConfigureTriggerNameAndConnections.png)

9.  트리거 파라미터 설정:

    -   **Site Address**: "Contoso IT" SharePoint site

    -   **List Name**: "Tickets"

    -   **Additional instructions to the agent when it's invoked by the
        trigger:**

        ``` text
        New Support Ticket Created in SharePoint: {Body}

        Use the 'Acknowledge SharePoint Ticket' tool to generate the email body automatically and respond.

        IMPORTANT: Do not wait for any user input. Work completely autonomously.
        ```

        ![Configure trigger
        parameters](./assets/10_ConfigureTriggerParams.png)

10. **Create trigger** 선택

11. **Close** 선택

### 10.2 Edit the Trigger

1.  **Overview → Triggers**에서 **New Support Ticket Created in
    SharePoint**의 **...** 선택

2.  **Edit in Power Automate** 선택
    ![Edit trigger in Power
    Automate](./assets/10_EditTriggerInPowerAutomate.png)

3.  **New designer** 활성화

4.  **Sends a prompt to the specified copilot for processing** 노드 선택

5.  **Body/message**에서 기존 Body 삭제 후 `/` 입력 → **Insert
    Expression** 선택
    ![Insert expression for
    trigger](./assets/10_InsertExpressionForTrigger.png)

6.  다음 Expression 입력:

    ``` text
    concat('Submitted By Name: ', first(triggerOutputs()?['body/value'])?['Author/DisplayName'], '\nSubmitted By Email: ', first(triggerOutputs()?['body/value'])?['Author/Email'], '\nTitle: ', first(triggerOutputs()?['body/value'])?['Title'], '\nIssue Description: ', first(triggerOutputs()?['body/value'])?['Description'], '\nPriority: ', first(triggerOutputs()?['body/value'])?['Priority/Value'],'\nTicket ID : ', first(triggerOutputs()?['body/value'])?['ID'])
    ```

7.  **Add** 선택
    ![Trigger output
    expression](./assets/10_TriggerOutputExpression.png)

8.  우측 상단 **Publish** 선택

### 10.3 Create a tool for email acknowledgment

1.  Copilot Studio의 Agent로 **Return**

2.  **Tools** 탭 이동

3.  **+ Add a tool → Connector** 선택

4.  **Send an email (V2) - Office 365 Output** 선택
    ![Select Outlook Connector](./assets/10_SelectOutlookConnector.png)

5.  연결 구성 후 **Add and configure**

6.  Tool 설정:

    -   **Name**: Acknowledge SharePoint ticket
    -   **Description**: 티켓이 접수되었음을 알리는 이메일을 전송하는
        도구

7.  Input parameter **Customize** 설정:

    **To**:

    -   **Description**: SharePoint 티켓 제출자의 이메일 주소
    -   **Identify as**: Email

    **Body**:

    -   **Description**: 티켓 접수 확인 및 3영업일 내 응답 예정 안내

    ![Configure Input
    Parameters](./assets/10_ConfigureInputParameters.png)

8.  **Save** 선택

### 10.4 Test the trigger

1.  **Help Desk Agent → Overview** 탭 선택
2.  **New Support Ticket Created in SharePoint** 옆 **Test Trigger**
    클릭
3.  새 브라우저 탭에서 **SharePoint IT Support Tickets list** 이동
4.  **+ Add new item** 클릭:
    -   **Title**: "Unable to connect to VPN"
    -   **Description**: "Unable to connect to corporate WIFI network
        after recent update"
    -   **Priority**: "Normal"
5.  SharePoint 항목 **Save**
    ![Create Test Ticket](./assets/10_CreateTestTicket.png)
6.  Copilot Studio로 돌아와 **Test your trigger** 패널 확인 (Refresh
    사용)
    ![Monitor Trigger Test](./assets/10_MonitorTriggerTest.png)
7.  트리거 표시 후 **Start testing**
8.  Activity Map 표시되면 **Allow** 선택
    ![Allow Connector](./assets/10_AllowConnector.png)
9.  에이전트 확인:
    -   트리거 페이로드 수신 여부
    -   "Acknowledge SharePoint ticket" tool 호출 여부
        ![Test trigger](./assets/10_TestTrigger.png)
10. 제출자 이메일에서 확인 메일 수신 여부 확인
    ![Test email sent](./assets/10_TestEmailSent.png)
11. Copilot Studio의 **Activity** 탭에서 전체 실행 로그 확인

## ✅ Mission Complete

🎉 **축하합니다!** 이벤트 트리거와 커넥터 도구를 성공적으로 구현하여
사용자 개입 없이 자동으로 이메일을 보내고 지원 티켓을 처리하는 자율
에이전트를 완성했습니다. 에이전트를 게시하면 자동으로 동작합니다.

🚀 **다음 단계**: 다음 학습에서는 [publish your
agent](../11-publish-your-agent/index.md) 방법을 배웁니다.

⏭️ [Move to **Publish your agent**
lesson](../11-publish-your-agent/index-kr.md)

## 📚 Tactical Resources

이벤트 트리거와 자율 에이전트를 더 깊이 학습하려면:

-   **Microsoft Learn**: [Make your agent autonomous in Copilot Studio](https://learn.microsoft.com/training/modules/autonomous-agents-online-workshop/?WT.mc_id=power-177340-scottdurow)
-   **Documentation**: [Add an event trigger](https://learn.microsoft.com/microsoft-copilot-studio/authoring-trigger-event?WT.mc_id=power-177340-scottdurow)
-   **Best Practices**: [Power Automate triggers introduction](https://learn.microsoft.com/power-automate/triggers-introduction?WT.mc_id=power-177340-scottdurow)
-   **Advanced Scenarios**: [Using Power Automate flows with agents](https://learn.microsoft.com/microsoft-copilot-studio/advanced-flow-create?WT.mc_id=power-177340-scottdurow)
-   **Security**: [Data loss prevention for Copilot Studio](https://learn.microsoft.com/microsoft-copilot-studio/admin-data-loss-prevention?WT.mc_id=power-177340-scottdurow)

<!-- markdownlint-disable-next-line MD033 -->
<img src="https://m365-visitor-stats.azurewebsites.net/agent-academy/recruit/10-add-event-triggers" alt="Analytics" />
