---
title: Features
---

### Send notifications from Jira to Mattermost

Notify your team of the latest updates by sending notifications from your Jira projects to Mattermost channels.

![image](https://user-images.githubusercontent.com/13119842/59113100-6cd7a800-8912-11e9-9e23-3639c0eb9c4d.png)

![image](https://user-images.githubusercontent.com/13119842/59113138-7f51e180-8912-11e9-9fc5-3077ba90a8a8.png)





#### Create Jira issues

Create Jira issues from a Mattermost message by clicking the **More Actions** (...) option of any message in the channel (available when you hover over a message), then selecting **Create Jira Issue**.

Then, on the resulting issue creation dialog, select the project, issue type and enter other fields to create the issue.

![image](https://user-images.githubusercontent.com/13119842/59113188-985a9280-8912-11e9-9def-9a7382b4137e.png)

Click **Create** and the Jira issue is now created, including any file attachments part of the Mattermost message.

![image](https://user-images.githubusercontent.com/13119842/59113219-a4deeb00-8912-11e9-9741-5ddc8a4b51fa.png)



#### Attach Messages to Jira Issues

Keep all information in one place by attaching parts of Mattermost conversations in Jira issues as comments. 


#### Transition Jira issues

Transition issues without the need to switch to your Jira project. To transition an issue, use the `/jira transition <issue-key> <state>` command.

For instance, `/jira transition EXT-20 done` transitions the issue key **EXT-20** to **Done**.

![image](https://user-images.githubusercontent.com/13119842/59113377-dfe11e80-8912-11e9-8971-f869fa123366.png)

Note that states and issue transitions are based on your Jira project workflow configuration. If an invalid state is entered, an ephemeral message is returned mentioning that the state couldn't be found.