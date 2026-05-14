# Exercise 3: Protect agent data

## Scenario
The Security team flags that an agent may surface sensitive content in Copilot Chat. The admin uses Purview, DLP, and sensitivity labels to restrict what data the agent can process. 

In this exercise, you'll manage agents through the Agent 365 control plane, including the Microsoft 365 admin center, and Microsoft Purview. You'll apply Microsoft Purview information protection and data loss prevention (DLP) policies to control what data the agent may process. 

## Objectives

At the end of this lab exercise, you'll be able to:

- Publish a sensitivity label and configure label policy settings.
- Create and scope a DLP policy for Microsoft 365 Copilot and Copilot Chat that restricts Copilot from processing content with a specified sensitivity label.
- Validate policy effectiveness by testing agent access to labeled SharePoint content and confirming the expected restriction behavior.

## Duration

**Estimated time:** 20 minutes

>[!Alert] It may take up to 2 hours to apply after the policies configured. You do not need to wait for them to complete in order to continue or complete the lab.

## Task 1: Publish and apply a sensitivity label 

1. [] In a new browser tab, go to the Microsoft Purview portal at `purview.microsoft.com`

1. [] If prompted, sign in with the admin credentials provided.

    | Option | Value |
    | -------- | -------- |
    | Username | `@lab.CloudCredential(WWLWWLM365withCopilotA365HydratedStakeholderSteveM).AdministrativeUsername` |
    | Password | `@lab.CloudCredential(WWLWWLM365withCopilotA365HydratedStakeholderSteveM).AdministrativePassword` |

1. [] On the pop-up window, select **Get Started**.

1. [] In the left menu, select **Solutions**, and then select **Information Protection**. 

    !IMAGE[2ni6bb9g.png](instructions345060/2ni6bb9g.png)

1. [] Select **Sensitivity labels**.

    !IMAGE[e843u9ly.png](instructions345060/e843u9ly.png)

1. [] Select the **Wingtip Acquisition** checkbox.

1. [] Select the vertical ellipsis **(…)**.

1. [] Select **Publish label**.

	!IMAGE[c42l9ext.png](instructions345060/c42l9ext.png)

1. [] On the Choose sensitivity labels to publish page, select **Next**.

1. [] On the Assign admin units page, select **Next**.

1. [] On the Publish to users and groups page, select **Next**.

1. [] On the Policy settings page, select the **Require users to apply a label to their emails and documents** checkbox, and then select **Next**.

1. [] Under Default settings for documents, select **None**, and then select **Next**.

1. [] On the Default settings for emails page, select **Next**.

1. [] On the Default settings for meeting and calendar events page, leave the settings as they are and select **Next**.

1. [] Leave the settings on the Default settings for sites and groups page unchanged and select **Next**.

1. [] Leave the settings on the Default settings for Engage content (preview) page unchanged and select **Next**.

1. [] Leave the settings on the Default settings for Fabric and Power BI content page unchanged and select **Next**.

1. [] On the **Name your policy** page, fill in the following fields:

    | Field           | Value                               |
    |-----------------|-------------------------------------|
    | **Name**        | `Test for internal doc for A365 labs` |
    | **Description** | `Test for internal doc for A365 labs` |

1. [] Select **Next**.

1. [] On the **Review and finish** page, review the settings and then select **Submit**.

    !IMAGE[1609pen3.png](instructions345060/1609pen3.png)

1. [] On the New Policy Created page, select **Done**.

**Outcome**: You have published a sensitivity label by creating a label policy. 


## Task 2: Apply a DLP policy

>[!Alert] It may take up to 2 hours to apply after the policies configured. You do not need to wait for them to complete in order to continue or complete the lab.


1. [] In the left menu, select **Solutions**, and then select **Data Loss Prevention**. 

	!IMAGE[jt22y518.png](instructions345060/jt22y518.png)

    >[!Note] If you are prompted to turn on always-on diagnostics for devices, select **Turn on**.

1. [] Select **Policies** in the left-hand side navigation menu, and then select **+ Create policy**.

	!IMAGE[46n003i6.png](instructions345060/46n003i6.png)

1. [] Select **Enterprise applications & devices**.

	!IMAGE[bxw4tjle.png](instructions345060/bxw4tjle.png)

1. [] Select **Custom** under **Categories**.

1. [] Select **Custom policy** under **Regulations**.

1. [] Select **Next**.

	!IMAGE[2ngpxad1.png](instructions345060/2ngpxad1.png)

1. [] Fill in the fields under the **Name your DLP policy**:

    | Field           | Value                   |
    |-----------------|-------------------------|
    | **Name**        | `Test for Agent 365 labs` |
    | **Description** | `Test for Agent 365 labs` |

1. [] Select **Next**.

1. [] Select **Next** on the Admin units page.

1. [] On the Choose where to apply the policy page, scroll down to **Microsoft 365 Copilot and Copilot Chat**, and then select the checkbox next to it.

1. [] Select **Next**.

1. [] On the Define policy settings page, ensure that **Create or customize advanced DLP rules** is selected, and then select **Next**.

1. [] Select **+ Create rule**.

1. [] On the **Create rule** page, enter `test sensitivity label` in the **Name** field.

1. [] Under Conditions, select **+ Add condition**, and then select **Content contains**.

1. [] Select **Add > Sensitivity labels**. 

1. [] Select the checkbox next to **Wingtip Acquisition**, and then select **Add**.

1. [] Under Actions, select **+ Add an action**, and then select **Restrict Copilot from processing content**. 

1. [] Select the checkbox next to **Accessing knowledge sources**.

1. [] Select **Save**.

1. [] On the Customize advanced DLP rules page, select **Next**.

1. [] On the Policy mode page, select **Turn the policy on immediately**.

1. [] Select **Next**, and then select **Submit**.

1. [] Select **Done**.

1. [] On the left, under Data Loss Prevention, select **Recommendations**

1. [] Under Not Started select **Protect items with sensitivity labels from Microsoft 365 Copilot and agent processing**.

1. [] Select **Get started**.

1. [] Select **+ Add**.

1. [] Select **Wingtip Acquisition**, and then select **Add (1)**

1. [] Select **Create policy**.

1. [] Select the **X** in the top right corner to close the flyout.

1. [] On the left, under Data Loss Prevention, select **Policies**

1. [] Select the checkbox next to **DSPM for AI - Protect sensitive data from Copilot processing**

	>[!Note] If you do not see the policy, refresh the page.

1. [] Select the **pencil icon** to edit the policy.

1. [] Select **Next** four (4) times until you reach the **Policy mode** page.

1. [] On the policy mode page, select **Turn the policy on immediately**, and then select **Next**.

1. [] Select **Submit**, and then select **Done**.

    >[!Note] You will see the DLP policies status as **Sync in progress**

	!IMAGE[1q5uk47z.png](instructions345060/1q5uk47z.png)

**Outcome:** You have configured a DLP Policy to apply to your agent. 

>[!Note] These DLP Policies may take up to 2 hours for them to sync and apply. Once the sync is complete you will see the status change.
!IMAGE[p67gyjol.png](instructions345060/p67gyjol.png)


## Task 3: Test your DLP Policy via your agent

1. [] In a new browser tab, go to your tenant's SharePoint site at: `https://@lab.CloudCredential(WWLWWLM365withCopilotA365HydratedStakeholderSteveM).TenantPrefix.sharepoint.com/sites/SalesandMarketing` 

1. [] If prompted, sign in with the admin credentials provided.

    | Option | Value |
    | -------- | -------- |
    | Username | `@lab.CloudCredential(WWLWWLM365withCopilotA365HydratedStakeholderSteveM).AdministrativeUsername` |
    | Password | `@lab.CloudCredential(WWLWWLM365withCopilotA365HydratedStakeholderSteveM).AdministrativePassword` |

1. [] On the **Sales and Marketing** page, select **Documents**. 

	!IMAGE[qa4fe8v2.png](instructions345060/qa4fe8v2.png)

1. [] Select the **Sales** folder.

1. [] Open the **Annual Sales Report.docx**.

1. [] Select **Select label**.

	!IMAGE[0w8iyp2a.png](instructions345060/0w8iyp2a.png)

    >[!Note] If you do not see the Select label option, select the Sensitivity label dropdown <br>!IMAGE[8q0fd2du.png](instructions345060/8q0fd2du.png)

1. [] Select **Wingtip Acquisition** > **OK**. Then refresh the page.

	> [!note] You may not be prompted to press **OK**. 


1. [] Copy the link to the **Annual Sales Report.docx** (The complete URL at the top of the browser tab)

1. [] **Close** the Annual Sales Report.docx browser tab.

1. [] In Edge, open an new **InPrivate** window.

    !IMAGE[ap7fmvnw.png](instructions345060/ap7fmvnw.png)

1. [] In the InPrivate browser connect to `https://m365.cloud.microsoft/chat`

1. [] Sign in as Amber Rodriguez with the following credentials:

	| Option | Value |
    | -------- | -------- |
    | Username | `amberr@@lab.CloudCredential(WWLWWLM365withCopilotA365HydratedStakeholderSteveM).TenantName` |
    | Password | `@lab.CloudCredential(WWLWWLM365withCopilotA365HydratedStakeholderSteveM).AdministrativePassword` |

1. [] On the left navigation pane, select **...All agents**.

1. [] Select the **IT Helpdesk Agent**.

1. [] Type in the following prompt and do not select Enter yet: `Can I access this document:`.

1. [] **Paste the SharePoint** link that you copied earlier to the end of the prompt. 

	>[!Note] You can safely ignore and additional characters that appear in the paster URL.

1. [] Select **Enter**.

	>[!Note] You should see a notification that the user does not have access to the document
	!IMAGE[659ffbn8.png](instructions345060/659ffbn8.png)

1. [] Close the InPrivate browser.

**Outcome**: Your agent should respond with a message saying the user does not have access to the document.
