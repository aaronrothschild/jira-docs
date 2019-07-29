---
title: Installation
sections:
  - Step One
  - Step Two
  - Step Three
---

### Step One 
- Configure plugin in Mattermost

1. Go to **System Console > Plugins > Jira**, select the username that this plugin is attached to, generate a **Secret** and hit **Save**.
   - You may optionally create a new user account for your Jira plugin, which acts as a bot account posting Jira updates to Mattermost channels.
2. Go to **System Console > Plugins > Management** and click **Enable** to enable the Jira plugin.

### Step Two 
- Configure webhooks in Jira

If you want to [send notifications from Jira to Mattermost](#11-send-notifications-from-Jira-to-Mattermost), link a Jira project to a Mattermost channel via webhooks.

1. As a Jira System Administrator, go to **Jira Settings > System > WebHooks**.
  - For older versions of Jira, click the gear icon in bottom left corner, then go to **Advanced > WebHooks**.

2. Click **Create a WebHook** to create a new webhook. Enter a **Name** for the webhook and add the JIRA webhook URL https://SITEURL/plugins/jira/webhook?secret=WEBHOOKSECRET&team=TEAMURL&channel=CHANNELURL as the **URL**.
  - Replace `TEAMURL` and `CHANNELURL` with the Mattermost team URL and channel URL you want the JIRA events to post to. The values should be in lower case.
  - Replace `SITEURL` with the site URL of your Mattermost instance, and `WEBHOOKSECRET` with the secret generated in Mattermost via **System Console > Plugins > Jira**.

  For instance, if the team URL is `contributors`, channel URL is `town-square`, site URL is `https://community.mattermost.com`, and the generated webhook secret is `5JlVk56KPxX629ujeU3MOuxaiwsPzLwh`, then the final webhook URL would be

  ```
  https://community.mattermost.com/plugins/jira/webhook?secret=5JlVk56KPxX629ujeU3MOuxaiwsPzLwh&team=contributors&channel=town-square
  ```

3. (Optional) Set a description and a custom JQL query to determine which tickets trigger events. For more information on JQL queries, refer to the [Atlassian help documentation](https://confluence.atlassian.com/jirasoftwarecloud/advanced-searching-764478330.html).

4. Finally, set which issue events send messages to Mattermost channels, then hit **Save**. The following issue events are supported:
     - Issue Created; Issue Deleted
     - Issue Updated, including when an issue is reopened or resolved, or when the assignee is changed. Optionally send notifications for comments, see below.

**Note**: You can send notifications for comments by selecting **Issue Updated**, then adding `&updated_comments=1` to the end of the webhook URL, such as 

```
https://community.mattermost.com/plugins/jira/webhook?secret=5JlVk56KPxX629ujeU3MOuxaiwsPzLwh&team=contributors&channel=town-square&updated_comments=1
```

This sends all comment notifications to a Mattermost channel, including public and private comments, so be cautious of which channel you send these notifications to.

### Step Three
- Install the plugin as an application in Jira

If you want to allow users to [create and manage Jira issues across Mattermost channels](#11-create-and-manage-jira-issues-in-mattermost), install the plugin as an application in your Jira instance. For Jira Server or Data Center instances, post `/jira install server <your-jira-url>` to a Mattermost channel as a Mattermost System Admin, and follow the steps posted to the channel. For Jira Cloud, post `/jira install cloud <your-jira-url>`.

### If you need Help
If you face issues installing the plugin, see our [Frequently Asked Questions](#5-frequently-asked-questions-faq) for troubleshooting help, or open an issue in the [Mattermost Forum](http://forum.mattermost.org).

**Note**: If you experience problems with Jira-related user interactions in Mattermost such as creating issues, disable these features by setting **Allow users to connect their Mattermost accounts to Jira** to false in **System Console > Plugins > Jira**. This setting does not affect Jira webhook notifications. After changing this setting to false, disable, then re-enable this plugin in **System Console > Plugins > Plugin Management** to reset the plugin state for all users.

