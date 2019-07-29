---
Title: Transition Jira Issues
---

Transition issues without the need to switch to your Jira project. To transition an issue, use the `/jira transition <issue-key> <state>` command.

For instance, `/jira transition EXT-20 done` transitions the issue key **EXT-20** to **Done**.

![image](https://user-images.githubusercontent.com/13119842/59113377-dfe11e80-8912-11e9-8971-f869fa123366.png)

Note that states and issue transitions are based on your Jira project workflow configuration. If an invalid state is entered, an ephemeral message is returned mentioning that the state couldn't be found.