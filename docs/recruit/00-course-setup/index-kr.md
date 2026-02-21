# 🚨 Mission 00: Course Setup

## 🕵️‍♂️ CODENAME: `OPERATION DEPLOYMENT READY`

> **⏱️ Operation Time Window:** `~30 minutes`

## 🎯 Mission Brief

Copilot Studio Agent로서의 트레이닝 첫 번째 미션에 오신 것을
환영합니다.\
첫 번째 AI 에이전트를 구축하기 전에 **실전에 바로 사용할 수 있는 개발
환경**을 준비해야 합니다.

이 브리핑에서는 Microsoft 365 생태계에서 성공적으로 작업하기 위해 필요한
시스템, 접근 권한, 그리고 설정 단계를 안내합니다.

## 🔎 Objectives

이번 미션에는 다음이 포함됩니다:

1.  Microsoft 365 계정 생성\
2.  Microsoft Copilot Studio 접근 권한 획득\
3.  (선택 사항) 프로덕션 배포를 위한 Microsoft 365 Copilot 라이선스 확보
4.  Copilot Studio에서 사용할 개발자 환경 생성\
5.  이후 미션에서 데이터 소스로 사용할 SharePoint 사이트 생성

> \[!IMPORTANT\] **이미 Microsoft 365, Power Platform, Copilot Studio에
> 접근할 수 있나요?** 아래 Step 1--4는 **완전히 새로운 체험 환경을
> 처음부터 생성하는 과정**입니다. 이미 Power Platform과 Copilot Studio에
> 접근 가능한 Microsoft 365 비즈니스 테넌트가 있다면 **[Step 5: Create
> new SharePoint site](#step-5-create-new-sharepoint-site)** 로 바로
> 이동할 수 있습니다. Step 1--4는 별도의 테스트용 환경을 만들고 싶을
> 때만 필요합니다.

## 🔍 Prerequisites

시작하기 전에 다음 사항을 준비하세요:

1.  **회사 또는 학교 이메일 주소** (@outlook.com, @gmail.com 등의 개인
    이메일은 지원되지 않음)
2.  인터넷 접속 및 최신 브라우저 (Edge, Chrome, Firefox 권장)\
3.  Microsoft 365 기본 사용 경험 (예: Office 앱 또는 Teams 로그인)\
4.  (선택 사항) 유료 라이선스를 구매할 계획이라면 신용카드 또는 결제
    수단

------------------------------------------------------------------------

## 🧪 Trial Environment Setup (Steps 1--4)

## Step 1: Get a Microsoft 365 Account

Copilot Studio는 Microsoft 365 내부에서 동작하므로, 먼저 Microsoft 365
계정이 필요합니다. 기존 계정을 사용하거나 아래 단계에 따라 적절한
라이선스를 생성할 수 있습니다:

1.  **유료 Microsoft 365 Business 구독 생성**
    1.  [Microsoft 365 Business Plans and Pricing
        Page](https://www.microsoft.com/microsoft-365/business/microsoft-365-plans-and-pricing)
        로 이동
    2.  시작하기에 가장 저렴한 옵션은 Microsoft 365 Business Basic
        플랜입니다. `Try for free` 를 선택하고 안내되는 양식에 따라 구독
        및 계정 정보를 입력합니다. ![Microsoft 365
        Signup](./images/m365-freetrial.png)
    3.  새 계정이 생성되면 로그인합니다.

> \[!TIP\] Microsoft 365 Copilot Chat에 에이전트를 게시하거나 조직
> 데이터(SharePoint, OneDrive, Dataverse)에 연결하려면 Microsoft 365
> Copilot 라이선스가 필요합니다. 이는 추가 라이선스이며 자세한 내용은
> [on the licensing
> site](https://www.microsoft.com/microsoft-365/copilot#plans) 에서
> 확인할 수 있습니다.

## Step 2: Start a Copilot Studio Trial

Microsoft 365 테넌트를 준비했다면 Copilot Studio 접근 권한을 받아야
합니다. 다음 단계에 따라 30일 무료 체험을 시작할 수 있습니다:

1.  [aka.ms/TryCopilotStudio](https://aka.ms/TryCopilotStudio) 로 이동\

2.  이전 단계에서 생성한 이메일 주소를 입력하고 `Next` 선택

    ![Microsoft 365 Signup](./images/mcs-trial-screen.png)

3.  계정이 인식되면 `Sign In` 선택

    ![Microsoft 365 Signup](./images/mcs-trial-signin.png)

4.  `Start Free Trial` 선택

    ![Microsoft 365 Signup](./images/mcs-start-trial.png)

> \[!INFO\] Trial Notes
>
> 1.  무료 체험에서는 **Copilot Studio의 전체 기능**을 사용할 수
>     있습니다.
> 2.  체험 만료 전에 이메일 알림을 받게 되며, 30일 단위로 연장(최대
>     90일)할 수 있습니다.\
> 3.  테넌트 관리자가 셀프 서비스 가입을 비활성화한 경우 오류가
>     표시되며, Microsoft 365 관리자에게 문의해야 합니다.

## Step 3: Create new developer environment

### Sign up for a Power Apps Developer Plan

Step 1에서 사용한 동일한 Microsoft 365 테넌트로 Power Apps Developer
Plan에 가입하여 Copilot Studio 개발 및 테스트용 무료 환경을 생성합니다.

1.  [Power Apps Developer Plan website](https://aka.ms/PowerAppsDevPlan)
    에서 가입

    -   이메일 주소 입력
    -   체크박스 선택
    -   **Start free** 선택

    ![Sign up for Power Apps Developer Plan](images/0.3_01_SignUp.png)

2.  Developer Plan 가입 후 [Power Apps](https://make.powerapps.com/) 로
    이동합니다. 환경 이름은 예를 들어 **Adele Vance's environment** 와
    같이 생성됩니다. 동일 이름이 이미 존재하면 **Adele Vance's (1)**
    환경으로 생성됩니다.

    실습 진행 시 이 개발자 환경을 Copilot Studio에서 사용하세요.

> \[!NOTE\] 기존 Microsoft 365 계정을 사용하는 경우, 예를 들어 회사 조직
> 계정을 사용하는 경우에는 IT 관리자에 의해 가입 기능이 비활성화되어
> 있을 수 있습니다. 이 경우 관리자에게 문의하거나 Step 1을 참고해 테스트
> 테넌트를 생성하세요.

## Step 4: Enable Ability to Publish with the Copilot Studio Trial

최근 Copilot Studio 체험판에서는 기본적으로 에이전트 게시가 비활성화되어
있습니다. 게시 기능을 활성화하려면 Power Platform Admin Center에서
Copilot Studio Authors 역할에 자신을 추가해야 합니다.

먼저 게시 권한을 부여할 사용자들을 포함할 보안 그룹을 생성해야 합니다.
이 그룹을 Copilot Studio Authors 역할과 연결하게 됩니다.

1.  [admin.cloud.microsoft](https://admin.cloud.microsoft) 이동

2.  **Teams & groups** 확장 후 **Active teams & groups** 선택

    ![Teams and groups](images/admin-teams-groups.png)

3.  **Security groups** 탭 선택 후 **Add a security group** 선택

    ![Security Group](images/admin-securitygroup-tab.png)

4.  보안 그룹 이름을 **AgentCreators** 등으로 지정 후 **Next** 선택

    ![Security Group Name](images/admin-securitygroup-name.png)

5.  이름 확인 후 **Create group** 선택

    ![Create group](images/admin-creategroup.png)

6.  생성한 보안 그룹 선택

    ![Select group](images/admin-selectgroup.png)

7.  **members** 탭 → **view all and manage members** 선택

    ![Add members](images/admin-viewmembers.png)

8.  **add members** 선택

    ![Add members](images/admin-addmember.png)

9.  목록에서 본인 이름 선택 후 **Add** → **Add**

    ![Select yourself](images/admin-selectname.png)

10. **admin.powerplatform.com** 이동

11. **manage** 탭 선택

    ![Manage](images/pp-admin-managetab.png)

12. **tenant settings** 탭 선택

    ![Tenant Settings](images/pp-admin-tenantsettings.png)

13. \***copilot studio authors** 옵션 선택

    ![Authors](images/pp-authors.png)

14. **pencil icon** 선택

    ![Pencil](images/pp-pencil.png)

15. 생성한 보안 그룹 선택 후 **Done**

    ![Select Security Group](images/pp-securitygroup.png)

16. 보안 그룹이 추가되었는지 확인 후 **Save**

    ![Save](images/pp-save.png)

------------------------------------------------------------------------

## 🔧 Required Setup (Everyone)

다음 단계는 체험 환경 또는 기존 환경 여부와 관계없이 모두 수행해야
합니다.

## Step 5: Create new SharePoint site

[Lesson
06](../06-create-agent-from-conversation/index.md#62-add-an-internal-knowledge-source-using-a-sharepoint-site)
에서 사용할 새로운 SharePoint 사이트를 생성해야 합니다.

1.  Microsoft Copilot Studio 좌측 상단의 waffle 아이콘을 선택하고
    SharePoint 선택

    ![Select SharePoint](images/0.4_01_SelectSharePoint.png)

2.  SharePoint가 열리면 **+ Create site** 선택

    ![Create site](images/0.4_02_CreateSite.png)

3.  생성 마법사에서 **Team site** 선택

    ![Team site](images/0.4_03_SelectTeamOrCommunicationSite.png)

4.  템플릿 목록에서 아래로 스크롤하여 **IT help desk** 템플릿 선택

    ![IT help desk template](images/0.4_04_SelectITHelpDeskTemplate.png)

5.  **Use template** 선택

    ![Use template](images/0.4_05_SelectUseTemplate.png)

6.  사이트 정보 입력 예시:

      Field              Value
      ------------------ ------------------------------
      Site name          Contoso IT
      Site description   Copilot Studio for Beginners
      Site address       ContosoIT

    ![Site information](images/0.4_06_SiteDetails.png)

7.  언어는 기본값 **English** 그대로 두고 **Create site** 선택

    ![Language and other
    options](images/0.4_07_LanguageOtherOptions.png)

8.  사이트 생성이 진행되는 동안 **Add members** 에 사용자 추가 가능.
    완료 후 **Finish** 선택

    ![Select finish](images/0.4_08_SelectFinish.png)

9.  SharePoint 홈 화면이 열리면 사이트 URL을 **복사**

10. 이 템플릿에는 IT 정책 예제 데이터와 두 개의 샘플 리스트(Tickets,
    Devices)가 포함되어 있습니다.

### Use Devices SharePoint list

Mission 07에서 **Devices** 리스트를 사용합니다.

### Add new column

리스트 우측 끝에서 **+ Add column** → **hyperlink** 타입 선택 후 컬럼
이름을 **Image** 로 입력하고 추가

### Create sample data in Devices SharePoint list

최소 4개의 샘플 데이터를 추가하고 추가 컬럼을 생성해야 합니다.

샘플 데이터 입력 시 다음 필드를 반드시 채우세요:

-   Device photo - [device images
    folder](https://github.com/microsoft/agent-academy/tree/main/docs/recruit/00-course-setup/images/device-images)
    이미지 사용
-   Title
-   Status
-   Manufacturer
-   Model
-   Asset Type
-   Color
-   Serial Number
-   Purchase Date
-   Purchase Price,
-   Order \#
-   Image - 아래 링크 사용

  --------------------------------------------------------------------------------------------------------------------------------------------------------------| Device | URL |
| ------ | --- |
| Surface Laptop 13 | [https://raw.githubusercontent.com/microsoft/agent-academy/refs/heads/main/docs/recruit/00-course-setup/images/device-images/Surface-Laptop-13.png](https://raw.githubusercontent.com/microsoft/agent-academy/refs/heads/main/docs/recruit/00-course-setup/images/device-images/Surface-Laptop-13.png) |
| Surface Laptop 15 | [https://raw.githubusercontent.com/microsoft/agent-academy/refs/heads/main/docs/recruit/00-course-setup/images/device-images/Surface-Laptop-15.png](https://raw.githubusercontent.com/microsoft/agent-academy/refs/heads/main/docs/recruit/00-course-setup/images/device-images/Surface-Laptop-15.png) |
| Surface Pro | [https://raw.githubusercontent.com/microsoft/agent-academy/refs/heads/main/docs/recruit/00-course-setup/images/device-images/Surface-Pro-12.png](https://raw.githubusercontent.com/microsoft/agent-academy/refs/heads/main/docs/recruit/00-course-setup/images/device-images/Surface-Pro-12.png) |
| Surface Studio | [https://raw.githubusercontent.com/microsoft/agent-academy/refs/heads/main/docs/recruit/00-course-setup/images/device-images/Surface-Studio.png](https://raw.githubusercontent.com/microsoft/agent-academy/refs/heads/main/docs/recruit/00-course-setup/images/device-images/Surface-Studio.png) |


## ✅ Mission Complete

다음 작업을 성공적으로 완료했습니다:

-   Microsoft 365 개발 환경 구성\
-   Copilot Studio 체험판 활성화\
-   에이전트 grounding을 위한 SharePoint 사이트 생성\
-   이후 미션에서 사용할 Devices 리스트 데이터 입력

이제 [Lesson 01](../01-introduction-to-agents/index.md) 에서 **Recruit
레벨 에이전트 트레이닝**을 시작할 준비가 완료되었습니다.
