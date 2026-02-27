# 🚨 Mission 11: 에이전트 게시하기

## 🕵️‍♂️ CODENAME: `OPERATION PUBLISH PUBLISH PUBLISH`

> **⏱️ 작업 예상 시간:** `~30 minutes`

## 🎯 미션 개요

여러 개의 도전적인 모듈을 완료한 Agent Maker 여러분, 이제 가장 중요한 단계인 에이전트 게시를 진행할 준비가 되었습니다. Microsoft Teams와 Microsoft 365 Copilot 전반의 사용자에게 여러분의 에이전트를 제공할 시간입니다.
명확한 미션과 강력한 도구, 핵심 지식 소스에 대한 접근 권한을 갖춘 여러분의 에이전트는 이제 실제 사용자에게 서비스를 제공할 준비가 되었습니다. Microsoft Copilot Studio를 사용하여 에이전트를 배포하면, 사용자가 실제 업무 환경에서 바로 도움을 받을 수 있습니다.

이제 에이전트를 실제로 실행해 봅시다.

## 🔎 목표

📖 이번 학습에서는 다음 내용을 다룹니다:

1.  에이전트를 게시하는 것이 왜 중요한지
2.  에이전트를 게시하면 어떤 일이 발생하는지
3.  채널을 추가하는 방법 (Microsoft Teams & Microsoft 365 Copilot)
4.  Microsoft Teams에서 에이전트를 추가하는 방법
5.  조직 전체에서 Microsoft Teams를 통해 에이전트를 사용할 수 있게 하는 방법

## 🚀 에이전트 게시하기

Copilot Studio에서 에이전트를 작업할 때마다 지식이나 도구를 추가하며 업데이트할 수 있습니다. 모든 변경 사항을 완료하고 충분히 테스트했다면 이제 게시할 준비가 된 것입니다. 게시를 하면 최신 업데이트가 실제 환경에 반영됩니다. 새로운 도구를 추가했더라도 게시 버튼을 누르지 않으면 최종 사용자에게는 아직 제공되지 않습니다.

사용자에게 업데이트를 배포하려면 항상 게시 버튼을 눌러야 합니다. 에이전트에는 여러 채널이 추가되어 있을 수 있으며, 게시를 하면 추가된모든 채널에서 업데이트가 적용됩니다.

!!! important
    ❗ 최근 Copilot Studio Trial 환경에는 에이전트 게시를 제한하는 변경 사항이 적용되었습니다. Trial 환경에서는 이 모듈을 완료하여 에이전트를 게시할 수 없습니다. 에이전트를 게시하려면 유료 환경이 필요합니다. 단, 배지를 받기 위해 게시가 필수는 아닙니다.

## ⚙️ 채널 구성하기
채널은 사용자가 어디에서 에이전트에 접근하고 상호작용할 수 있는지를 결정합니다. 에이전트를 게시한 후 여러 채널에서 사용할 수 있도록 설정할 수 있습니다. 각 채널은 에이전트 콘텐츠를 서로 다른 방식으로 표시할 수 있습니다.

다음 채널에 에이전트를 추가할 수 있습니다:

-   **Microsoft Teams and Microsoft 365 Copilot** - Teams 채팅과 회의, Microsoft 365 Copilot 환경에서 에이전트를 사용할 수 있게 합니다 ([Learn more](https://learn.microsoft.com/microsoft-copilot-studio/publication-add-bot-to-microsoft-teams))
-   **Demo website** - Copilot Studio에서 제공하는 데모 웹사이트에서 에이전트를 테스트합니다 ([Learn more](https://learn.microsoft.com/microsoft-copilot-studio/publication-connect-bot-to-web-channels))
-   **Custom website** - 자체 웹사이트에 에이전트를 직접 임베드합니다 ([Learn more](https://learn.microsoft.com/microsoft-copilot-studio/publication-connect-bot-to-web-channels))
-   **Mobile app** - 사용자 지정 모바일 앱에 에이전트를 통합합니다 ([Learn more](https://learn.microsoft.com/microsoft-copilot-studio/publication-connect-bot-to-custom-application))
-   **SharePoint** - SharePoint 사이트에 에이전트를 추가하여 문서 및 사이트 지원을 제공합니다 ([Learn more](https://learn.microsoft.com/microsoft-copilot-studio/publication-add-bot-to-sharepoint))
-   **Facebook Messenger** - Facebook 메시징 플랫폼을 통해 사용자와 연결합니다 ([Learn more](https://learn.microsoft.com/microsoft-copilot-studio/publication-add-bot-to-facebook))
-   **Power Pages** - Power Pages 웹사이트에 에이전트를 통합합니다 ([Learn more](https://learn.microsoft.com/microsoft-copilot-studio/publication-add-bot-to-power-pages))
-   **Azure Bot Service channels** - Slack, Telegram, Twilio SMS 등 추가
    채널에 접근합니다 ([Learn more](https://learn.microsoft.com/microsoft-copilot-studio/publication-connect-bot-to-azure-bot-service-channels))

채널을 추가하려면 에이전트의 **Channels** 탭으로 이동한 뒤 구성하려는 채널을 선택하세요. 각 채널은 별도의 설정 요구 사항이 있으며 추가 인증이나 구성이 필요할 수 있습니다.

![Channels tab in agent](./assets/channels.png)

## 📺 채널 경험

각 채널마다 사용자 경험이 다릅니다. 여러 채널을 대상으로 에이전트를 만들
때는 채널별 차이를 반드시 고려해야 합니다. 다양한 채널에서 테스트하여
의도한 대로 동작하는지 확인하는 것이 좋은 전략입니다.

| Experience | Website | Teams and Microsoft 365 Copilot | Facebook | Dynamics Omnichannel for Customer Service |
| :-- | :-- | :-- | :-- | :-- |
| Customer satisfaction survey | Adaptive card | Text-only | Text-only | Text-only |
| Multiple-choice options | Supported | [Supported up to six (as hero card)][1] | [Supported up to 13][3] | [Partially Supported][5] |
| Markdown | Supported | [Partially Supported][2] | [Partially supported][4] | [Partially Supported][6] |
| Welcome message | Supported | Supported | Not supported | Supported for [Chat][7]. Not supported for other channels. |
| Did-You-Mean | Supported | Supported | Supported | Supported for [Microsoft Teams][8], [Chat][7], Facebook, and text-only channels (short message service (SMS) via [TeleSign][9] and [Twilio][10], [WhatsApp][11], [WeChat][12], and [Twitter][13]). Suggested actions are presented as a text-only list; users must retype an option to respond. |

[1]: https://learn.microsoft.com/microsoftteams/platform/concepts/cards/cards-reference#hero-card
[2]: https://learn.microsoft.com/microsoftteams/platform/bots/how-to/format-your-bot-messages#text-only-messages
[3]: https://developers.facebook.com/docs/messenger-platform/send-messages/quick-replies/
[4]: https://www.facebook.com/help/147348452522644?helpref=related
[5]: https://learn.microsoft.com/dynamics365/customer-service/asynchronous-channels#suggested-actions-support
[6]: https://learn.microsoft.com/dynamics365/customer-service/asynchronous-channels#preview-support-for-formatted-messages
[7]: https://learn.microsoft.com/dynamics365/customer-service/set-up-chat-widget
[8]: https://learn.microsoft.com/dynamics365/customer-service/configure-microsoft-teams
[9]: https://learn.microsoft.com/dynamics365/customer-service/configure-sms-channel
[10]: https://learn.microsoft.com/dynamics365/customer-service/configure-sms-channel-twilio
[11]: https://learn.microsoft.com/dynamics365/customer-service/configure-whatsapp-channel
[12]: https://learn.microsoft.com/dynamics365/customer-service/configure-wechat-channel
[13]: https://learn.microsoft.com/dynamics365/customer-service/configure-twitter-channel

> [!NOTE]
> 채널별로 다른 로직을 사용할 수 있는 예시가 있습니다. Power Platform Snippets 저장소에서 예제를 확인할 수 있습니다:
>
> Henry Jammes가 Microsoft Teams 채널일 때 다른 adaptive card를 표시하는 방법을 공유했습니다. ([Link to example](https://github.com/pnp/powerplatform-snippets/blob/main/copilot-studio/multiple-topics-matched-topic/source/multiple-topics-matched.yaml#L40))

## 🧪 Lab 11: Teams 및 Microsoft 365 Copilot에 에이전트 게시하기

### 🎯 사용 사례

Contoso IT Help Desk 에이전트는 이제 강력한 기능으로 완전히 구성되었습니다. SharePoint 지식 소스 접근, 지원 티켓 생성, 사전 알림 전송, 사용자 질의에 대한 지능적인 응답이 가능합니다. 하지만 현재 이러한 기능은 개발 환경에서만 사용할 수 있습니다.

**문제:** 에이전트를 실제 채널에 게시하지 않으면 최종 사용자는 이 기능을 사용할 수 없습니다.

**해결 방법:** 에이전트를 게시하면 최신 버전(새 토픽, 개선된 지식 소스,구성된 플로우 포함)이 실제 사용자에게 제공됩니다. 게시하지 않으면 사용자는 여전히 이전 버전을 사용하게 됩니다.

Teams 및 Microsoft 365 Copilot 채널을 추가하는 것도 중요한 이유는 다음과 같습니다:

-   **Teams 통합**: 직원들은 협업과 회의를 위해 대부분의 시간을 Microsoft Teams에서 보냅니다. Teams에 에이전트를 추가하면 별도 환경 이동 없이 IT 지원을 받을 수 있습니다.

-   **Microsoft 365 Copilot**: 사용자는 Office 앱 전반의 Copilot 경험 안에서 IT 헬프데스크 에이전트를 바로 사용할 수 있습니다.

-   **중앙화된 접근**: 별도의 웹사이트를 기억할 필요 없이 기존 업무 플랫폼에서 지원을 받을 수 있어 도입 장벽이 줄어듭니다.

이 미션은 개발 환경에서 만든 결과물을 실제 운영 환경에서 가치를 제공하는
솔루션으로 전환합니다.

### 사전 준비 사항

이 랩을 시작하기 전에 다음을 확인하세요:

-   ✅ 이전 랩을 완료하고 Contoso Helpdesk Agent가 완전히 구성되어 있어야 합니다
-   ✅ 에이전트 테스트가 완료되어 운영 준비가 되어 있어야 합니다
-   ✅ Copilot Studio 환경에서 에이전트를 게시할 권한이 있어야 합니다
-   ✅ 조직의 Microsoft Teams 접근 권한이 있어야 합니다

### 11.1 에이전트 게시하기

이제 에이전트 작업이 완료되었으므로 최종 사용자가 사용할 수 있도록 게시해야 합니다.

1.  Copilot Studio에서 Contoso Helpdesk Agent로 이동합니다 (via the
    [Copilot Studio maker portal](https://copilotstudio.microsoft.com))

    Copilot Studio에서는 에이전트 개요 상단의 publish 버튼을 선택하면
    쉽게 게시할 수 있습니다.

    ![Publish Agent overview](./assets/publish.png)

2.  에이전트에서 **Publish** 버튼을 선택합니다

    게시 확인 팝업이 열립니다.

    ![Publish confirmation](./assets/publish-popup.png)

3.  **Publish**를 선택하여 게시를 확정합니다

    에이전트가 게시 중이라는 메시지가 표시됩니다.

    ![Agent is publishing](./assets/publishing.png)

    게시가 완료되면 에이전트 페이지 상단에 알림이 표시됩니다.

    ![Notification publish done](./assets/publish-notification.png)

하지만 아직 채널에 추가하지 않았으므로 다음 단계에서 진행합니다!

### 11.2 Teams 및 Microsoft 365 Copilot 채널 추가하기

1.  에이전트 상단 탐색 메뉴에서 **Channel**을 선택합니다

    ![Channels tab](./assets/channels-tab.png)

2.  **Teams and Microsoft 365**를 선택합니다

    ![Select Teams and Microsoft 365](./assets/teams-m365-copilot.png)

3.  **Add channel**을 선택하여 채널을 추가합니다

    ![Select add channel](./assets/add-channel.png)

    추가가 완료되면 사이드바 상단에 녹색 알림이 표시됩니다.

    ![Channel added](./assets/channel-added.png)

4.  **See agent in Teams**를 선택하여 새 탭을 엽니다

    ![See agent in Teams](./assets/see-agent-teams.png)

5.  **Add**를 선택하여 Contoso Helpdesk Agent를 Teams에 추가합니다

    ![Add agent to Teams](./assets/add-teams.png)

    완료되면 다음 화면이 표시됩니다:

    ![Agent added successfully](./assets/teams-added.png)

6.  **Open**을 선택하여 Teams에서 에이전트를 엽니다

    ![Agent open in Microsoft Teams](./assets/agent-teams-open.png)

이제 Microsoft Teams에서 사용할 수 있도록 게시되었습니다.

### 11.3 테넌트 전체 사용자에게 에이전트 제공하기

1.  Contoso Helpdesk Agent가 열린 브라우저 탭을 닫습니다

2.  **Edit details**를 선택합니다

    ![Edit details](./assets/m365-teams-edit-details.png)

    아이콘, 설명, Teams 설정 등을 변경할 수 있습니다.

    ![Edit details pane](./assets/edit-details.png)

3.  **Cancel**을 선택합니다

4.  **Availability options**를 선택합니다

    ![Availability options](./assets/m365-teams-availability-options.png)

5.  **Show to everyone in my org**를 선택합니다

    ![Availability options](./assets/availability-options.png)

6.  **Submit for admin approval**을 선택합니다

    ![Submit for approval](./assets/submit-for-approval.png)

    관리자는 Teams Admin Center에서 앱을 승인해야 합니다.

    ![Teams app pending approval](./assets/pending-approval.png)

    관리자는 *Publish*를 선택하여 조직 전체에 배포할 수 있습니다.

    ![Teams app publish](./assets/teams-apps-publish.png)

    승인 후 Copilot Studio에서 *available in app store* 배너를 확인할 수 있습니다.

    ![Available in App Store](./assets/available-in-app-store.png)

## ✅ 미션 완료

🎉 **축하합니다!** 에이전트를 성공적으로 게시하고 Teams 및 Microsoft 365 Copilot에 추가했습니다! 다음 단계는 라이선스 이해입니다.

⏭️ [Move to the **Understanding licensing** mission](../12-understanding-licensing/index-kr.md)

## 📚 참고 자료

🔗 [Publish channels documentation](https://learn.microsoft.com/microsoft-copilot-studio/publication-fundamentals-publish-channels)

<!-- markdownlint-disable-next-line MD033 -->
<img src="https://m365-visitor-stats.azurewebsites.net/agent-academy/recruit/11-publish-your-agent" alt="Analytics" />
