---
next:
  link: /recruit/05-using-prebuilt-agents
  text: Using a Pre-Built Agent
prev:
  link: /recruit/03-create-a-declarative-agent-for-M365Copilot
  text: Deploy a Declarative Agent for Microsoft 365 Copilot
---

# 🚨 Mission 04: 에이전트를 위한 솔루션 생성하기

## 🕵️‍♂️ CODENAME: `OPERATION CTRL-ALT-PACKAGE`

> **⏱️ Operation Time Window:** `~45 minutes`

🎥 **Watch the Walkthrough**

[![Create a solution video
thumbnail](./assets/video-thumbnail.jpg)](https://www.youtube.com/watch?v=1iATbkgfcpU "Watch the walkthrough on YouTube")

## 🎯 Mission Brief

Agent Maker, 다음 전술 작전에 오신 것을 환영합니다. 이번 미션에서는
Microsoft Copilot Studio로 구축한 IT Helpdesk Agent의 공식 배포 수단인
Solution을 구성하는 방법을 배우게 됩니다. 이는 에이전트와 관련된
아티팩트를 담는 디지털 브리프케이스를 만드는 것과 같습니다.

모든 에이전트는 잘 구조화된 공간이 필요합니다. Power Platform solution은
정리, 이식성, 그리고 프로덕션 배포 준비 상태를 제공합니다.

이제 패키징을 시작해 봅시다.

## 🔎 Objectives

이번 미션에서 배우게 될 내용:

1.  Power Platform solution이 무엇이며 에이전트 개발에서 어떤 역할을
    하는지 이해하기
2.  에이전트를 구성하고 배포하기 위해 solution을 사용하는 장점 학습하기
3.  solution publisher와 컴포넌트 관리에서의 중요성 이해하기
4.  개발부터 프로덕션까지 Power Platform solution 라이프사이클 이해하기
5.  IT Helpdesk Agent를 위한 solution publisher 및 custom solution
    생성하기

## 🕵🏻‍♀️ Solution? 그게 뭔가요?

Microsoft Power Platform에서 solution은 앱이나 에이전트의 모든 구성
요소를 담는 컨테이너 또는 패키지와 같습니다. 여기에는 테이블, 폼,
플로우, 커스텀 로직 등이 포함될 수 있습니다. Solution은 ALM(Application
Lifecycle Management)에 필수적이며, 아이디어 단계부터 개발, 테스트,
배포, 업데이트까지 앱과 에이전트를 관리할 수 있게 해줍니다.

Copilot Studio에서는 생성하는 모든 에이전트가 Power Platform solution에
저장됩니다. 기본적으로는 Default solution에 생성되지만, 새로운 custom
solution을 만들어 그 안에서 에이전트를 생성할 수도 있습니다. 이번 강의와
핸즈온 실습에서 이를 학습하게 됩니다 🤓

전통적으로 solution은 **Power Apps maker portal**에서 생성되어 왔습니다.
이 웹 기반 인터페이스에서는 앱 구축 및 커스터마이즈, Dataverse 관리,
플로우 구성, AI 컴포넌트 탐색 등을 수행할 수 있습니다.

![Solutions](./assets/4.0_01_Solutions.png)

이제 Copilot Studio에는 **Solution Explorer**가 제공되어 솔루션을 직접
관리할 수 있습니다. 더 이상 Power Apps maker portal로 이동할 필요 없이
Copilot Studio 내부에서 바로 작업할 수 있습니다 🪄

이를 통해 다음과 같은 작업을 수행할 수 있습니다:

-   **Create a solution** - custom solution을 통해 에이전트를 환경 간
    export/import 가능

-   **Set your preferred solution** - 기본적으로 생성될 솔루션 지정

-   **Add or remove components** - 환경 변수나 cloud flow 등 에이전트가
    참조하는 컴포넌트 관리

-   **Export solutions** - 다른 환경으로 이동하기 위한 export

-   **Import solutions** - 다른 곳에서 만든 솔루션 import 및 업데이트

-   **Create and manage solution pipelines** - 환경 간 자동 배포
    파이프라인 구성

-   **Git integration** - 버전 관리와 협업을 위한 Git 연결 (개발 환경
    전용)

    ![Solutions](./assets/4.0_02_CopilotStudioSolutionExplorer.png)

Solution에는 두 가지 유형이 있습니다:

-   **Unmanaged solutions** - 개발 단계에서 사용하며 자유롭게 수정 가능
-   **Managed solutions** - 테스트 또는 프로덕션 배포 시 사용되며 변경을
    제한

## 🤔 왜 내 에이전트에 Solution을 사용해야 할까요?

Solution을 하나의 \_툴박스_라고 생각해 보세요. 다른 위치(환경)에서
무언가를 구축하거나 수정해야 할 때 필요한 도구(컴포넌트)를 모아
툴박스(Solution)에 담습니다. 이후 새로운 환경으로 이동하여 작업을
수행하거나 새로운 컴포넌트를 추가해 에이전트를 확장할 수 있습니다.

> \[!NOTE\] Elaiza, 여러분의 친근한 클라우드 애드보케이트가 잠깐
> 등장합니다 🙋🏻‍♀️: 뉴질랜드에는 "Be a tidy Kiwi!"라는 표현이 있습니다 🥝.
> 이는 자신의 환경을 책임지고 깔끔하게 유지하자는 의미입니다. 에이전트
> 개발에서도 동일합니다. 관련 요소를 잘 정리하고 이동 가능하게 유지하면
> 환경 관리가 훨씬 쉬워집니다.

개발 환경에서 전용 solution 안에 에이전트를 만드는 것은 좋은 실무
습관입니다. 이유는 다음과 같습니다:

🧩 **Organized development**

-   Default solution과 분리하여 에이전트를 구성하고 모든 컴포넌트를 한
    곳에 정리할 수 있습니다 🎯
-   필요한 모든 요소가 하나의 solution 안에 있어 환경 간 이동이
    쉬워집니다 👉🏻 ALM 관점에서 좋은 습관입니다.

🧩 **Safe deployment**

-   Managed solution 형태로 export하여 다른 환경에 배포하면서도 실수로
    수정되는 것을 방지합니다.

🧩 **Version control**

-   Patch, Update, Upgrade를 통해 변경사항을 관리할 수 있습니다.
-   변경사항을 체계적으로 배포할 수 있습니다.

🧩 **Dependency management**

-   Solution은 구성 요소 간 의존성을 추적하여 변경 시 문제를 방지합니다.

🧩 **Team collaboration**

-   개발 단계에서는 unmanaged solution으로 협업하고, 배포 시 managed
    solution으로 전달할 수 있습니다.

## 🪪 Solution Publisher 이해하기

Power Platform에서 Solution Publisher는 솔루션을 만든 조직이나 소유자를
식별하는 라벨 또는 브랜드와 같습니다. 특히 팀 단위 작업이나 여러 환경 간
이동 시 중요한 요소입니다.

Solution을 생성할 때 publisher를 반드시 선택해야 하며, publisher는
다음을 정의합니다:

-   모든 커스텀 컴포넌트에 추가되는 prefix
-   솔루션 소유자의 이름 및 연락 정보

### 🤔 왜 중요할까요?

1.  **Easy identification** - prefix(`new_`, `abc_` 등)를 통해 어떤 팀
    또는 솔루션에 속하는지 빠르게 식별
2.  **Avoids conflicts** - 동일한 이름의 컬럼이 있어도 prefix로 충돌
    방지
3.  **Supports ALM** - 환경 간 이동 시 소유권 및 일관성 유지

> \[!TIP\] ✨ Example
>
> Contoso Solutions라는 publisher를 만들고 prefix를 `cts_`로 설정했다고
> 가정합니다.
>
> \_Priority_라는 커스텀 컬럼을 추가하면 `cts_Priority`로 저장됩니다.
>
> 어떤 환경에서든 해당 컬럼이 Contoso Solutions와 연관되어 있음을 쉽게
> 확인할 수 있습니다.

## 🧭 Power Platform Solution lifecycle

이제 Solution의 목적을 이해했으니 라이프사이클을 살펴보겠습니다.

**1. 개발 환경에서 Solution 생성** - Development 환경에서 새로운
solution 생성

**2. 컴포넌트 추가** - 앱, 플로우, 테이블 등 구성 요소 추가

**3. Managed solution으로 export** - 배포용 패키지 생성

**4. Test 환경 import** - Test 환경에서 동작 검증

**5. Production 환경 import** - 실제 운영 환경에 배포

**6. Patch/Update/Upgrade 적용** - 개선 및 수정 반복 🔁

> \[!TIP\] ✨ Example
>
> 직원 지원용 IT Helpdesk Agent를 만든다고 가정해 보겠습니다.
>
> -   Development 환경에서 unmanaged solution으로 시작
> -   준비가 되면 managed solution으로 export 후 UAT 환경에 import
> -   테스트 완료 후 Production 환경으로 이동

## 🧪 Lab 04: Create a new Solution

이제 다음을 학습합니다:

-   Solution publisher 생성 방법
-   Solution 생성 방법

앞서 사용했던 Copilot Studio 전용 환경에서 IT Helpdesk Agent를 위한
solution을 만들어 보겠습니다.

시작합니다!

### Prerequisites

#### Security role

Copilot Studio에서 수행 가능한 작업은 사용자 보안 역할에 따라
달라집니다. Power Apps admin center에서 solution 관리 권한이 없다면
Copilot Studio에서도 동일하게 제한됩니다.

올바른 권한이 있는지 확인하거나, 환경 관리를 담당하는 IT 관리자에게
문의하세요.

  Security role          Description
  ---------------------- ---------------------------------------------
  Environment Maker      특정 환경에서 리소스 생성 및 관리 권한 제공
  System Customizer      Environment Maker보다 넓은 권한
  System Administrator   환경 전반을 관리할 수 있는 최고 권한

#### Developer environment

전용 개발 환경으로 전환하세요. [Lesson 00 - Course Setup - Step 3:
Create new
developer](../00-course-setup/index.md#step-3-create-new-developer-environment)
참고.

1.  우측 상단 **Cog wheel** 아이콘을 선택하여 기본 환경에서 개발
    환경으로 전환합니다.

    ![Developer environment](./assets/4.0_03_DeveloperEnvironment.png)

### 4.1 Create a Solution publisher

1.  Copilot Studio 좌측 메뉴에서 **ellipsis icon (. . .)** 선택 후
    **Solutions** 클릭

    ![Solutions](./assets/4.1_01_Solutions.png)

2.  **Solution Explorer**에서 **+ New solution** 선택

    ![Solutions](./assets/4.1_02_NewSolution.png)

3.  **+ New publisher** 선택

    ![Solutions](./assets/4.1_03_NewPublisher.png)

4.  **Properties** 탭에서 다음을 입력

      Property              Description                   Required
      --------------------- ---------------------------- ----------
      Display name          Publisher 표시 이름             Yes
      Name                  Publisher 고유 이름             Yes
      Description           솔루션 목적 설명                 No
      Prefix                컴포넌트 prefix                 Yes
      Choice value prefix   옵션 추가 시 사용되는 번호      Yes

    ``` text
    Contoso Solutions
    ```

    ``` text
    ContosoSolutions
    ```

    ``` text
    Copilot Studio Agent Academy
    ```

    ``` text
    cts
    ```

    Choice value 숫자를 천 단위로 수정합니다.

    ![Solutions](./assets/4.1_04_PublisherProperties.png)

5.  필요 시 Contact 정보 입력

    ![Solutions](./assets/4.1_05_Contact.png)

6.  **Save** 선택

    ![Solutions](./assets/4.1_06_SavePublisher.png)

7.  Publisher 생성 완료

    ![Solutions](./assets/4.1_07_PublisherSelected.png)

### 4.2 Create a new Solution

1.  New solution 폼 입력

    ``` text
    Contoso Helpdesk Agent
    ```

    ``` text
    ContosoHelpdeskAgent
    ```

    기본 Version은 `1.0.0.0`

    **Set as your preferred solution** 체크

    ![Solutions](./assets/4.2_01_SolutionDetails_.png)

2.  **More options** 확장

    ![Solutions](./assets/4.2_02_MoreOptions.png)

3.  아래 항목 확인 후 비워둠

    -   Installed on
    -   Configuration page
    -   Description

    **Create** 선택

    ![Solutions](./assets/4.2_03_Create.png)

4.  Solution 생성 완료 후 back arrow 선택

    ![Solutions](./assets/4.2_04_SolutionCreated.png)

5.  Current preferred solution 표시 확인

    ![Solutions](./assets/4.2_05_CurrentPreferredSolutionSelected.png)

## ✅ Mission Complete

축하합니다! 👏🏻 Publisher를 생성하고 새로운 Solution을 만들었습니다.

정리된 디지털 구조는 엔터프라이즈 규모의 에이전트 운영을 위한 첫
단계입니다.

⏭️ [Move to **Get started quickly with pre-built agents**
lesson](../05-using-prebuilt-agents/index.md)

## 📚 Tactical Resources

🔗 [Create a
solution](https://learn.microsoft.com/power-apps/maker/data-platform/create-solution/?WT.mc_id=power-172615-ebenitez)

🔗 [Create and manage solutions in Copilot
Studio](https://learn.microsoft.com/microsoft-copilot-studio/authoring-solutions-overview/?WT.mc_id=power-172615-ebenitez)

🔗 [Share agents with other
users](https://learn.microsoft.com/microsoft-copilot-studio/admin-share-bots/?WT.mc_id=power-172615-ebenitez)

🔗 [Summary of resources available to predefined security
roles](https://learn.microsoft.com/power-platform/admin/database-security#summary-of-resources-available-to-predefined-security-roles/?WT.mc_id=power-172615-ebenitez)

🔗 [Upgrade or update a
solution](https://learn.microsoft.com/power-apps/maker/data-platform/update-solutions/?WT.mc_id=power-172615-ebenitez)

🔗 [Overview of pipelines in Power
Platform](https://learn.microsoft.com/power-platform/alm/pipelines/?WT.mc_id=power-172615-ebenitez)

🔗 [Overview of Git integration in Power
Platform](https://learn.microsoft.com/power-platform/alm/git-integration/overview/?WT.mc_id=power-172615-ebenitez)

```{=html}
<!-- markdownlint-disable-next-line MD033 -->
```
`<img src="https://m365-visitor-stats.azurewebsites.net/agent-academy/recruit/04-creating-a-solution" alt="Analytics" />`{=html}
