---
lab:
    title: 'Data Protection and Compliance'
    description: 'Secure the data for your agent with Agent 365 and Microsoft Purview. '
    duration: '20 minutes'
    level: 200-300
    islab: true 
---

# Exercise 2: Protect Agent data

Scenario: Security teams flag that an agent may surface sensitive content in Copilot Chat. The admin uses Purview, DLP Policies, and sensitivity labels to restrict what data the agent can process.  

In this exercise, you will manage agents through the Agent 365 control plane including the Microsoft 365 Admin Center and Purview. You will apply Microsoft Purview information protection and DLP policies to control what data the agent may process. 

This exercise should take approximately 20 minutes to perform, however, it may take up to 24 hours for certain policies to apply after setting them. <!-- update with estimated duration -->

## Task 1: Publish and apply a sensitivity label 

First, you need to ...

1. Navigate to the Microsoft Purview portal and login with the provided MOD admin credentials.
1. Navigate to **Solutions** > **Information Protection** > **Sensitivity labels**.
1. Select the checkbox **Wingtip Acquisition** > select the three elipses > select **Publish label**.
1. On **Create Policy** wizard pop click **Next** through these pages: **Labels to publish**, **Admin units**, and **Users and groups**. Leave the settings on these pages as default.
1. On the **Policy settings** page, select the check box next to **Require users to apply a label to their emails and documents**.
1. Under the  **Default settings for documents** page, set the **Default label** to **None**. Select **Next**.
1. Under the **Default settings for emails** page, leave the settings as is. Select **Next**.
1. Under the **Default settings for meeting and calendar events** page, leave the settings as is and select **Next**.
1. Under the **Default settings for sites and groups** page, leave the settings as is and select **Next**.
1. Under the **Default settings for Engage content (preview)** page, leave the settings as is and select **Next**.
1. Under the **Default settings for Fabric and Power BI content** page, leave the settings as is and select **Next**.
1. Under Name your policy page, fill in the following fields:
       - **Name**: Test for internal doc for A365 labs
       - **Description**: Test for internal doc for A365 labs
1. On the Review and finish page, select **Submit**.
1. **Outcome**: You have created a sensitivity label. 
**Note**: The sensitivity may take up 24 hours to apply. The recomendation is to move on to the next task after 24 hours has passed. 

## Task 2: Apply a DLP Policy

1. Sign in to the Microsoft Purview portal and the MOD Administrator.
1. Navigate to **Solutions** > **Data Loss Prevention** in the left hand side navigation menu.
1. Select **Policies** > **+ Create Policy**.
1. Select **Enterprise applications & devices**.
1. In the **Start with a template or create a custom policy** page, select **Custom** under **Categories**.
1. Select **Custom policy** under **Regulations**.
1. Select **Next**.
1. Under the **Name your DLP Policy**:
    - **Name**: Test for Agent 365 labs
    - **Description**: Test for Agent 365 labs
1. Select **Next** on Admin units.
1. On the Choose where to apply the policy page, scroll down to the **Microsoft 365 Copilot and Copilot Chat Location** and select the checkbox next to it. Select **Next**.
1. In the Define policy settings, select **Create or customize advanced DLP rules**. Select **Next**.
1. Select **+Create rule** and type in the following:
       - **Name**: test sensitivity label
1. Under **Conditions**, select **+Add condition** > **Content contains**, and then perform the following:
       - Leave **Group Name** and **Group Operator** in it's default settings.
       -  Select **Add** > **Sensitivity labels** > Select checkbox next to **Wingtip Acquisition**.
1. Under **Actions**, select **+ Add an action** > **Restrict Copilot from processing content** > Select the checkbox near **Accessing knowledge sources**.
1. Select **Save**.
1. Select **Next** on the **Customize advanced DLP rules** page.
1. On the **Policy mode** page select the option **Turn the Policy on immediately**. 
1. Select **Next**. Then select **Submit** > **Done**.
1. **Outcome**: You have configured a DLP Policy to apply to your agent.
**Note** this DLP Policy may take anywhere from 2-24 hours to apply. The recomendation is to wait for some time before proceeding on to the next task after 24 hours has passed. 

## Task 3: Test your DLP Policy via your agent

1. Navigate to your tenant's Sharepoint site and login as the MOD Administrator with the credentials provided.
1. In the search box, type **Sales and Marketing** and select it.
1. In the **Sales and Marketing** page, select **Documents** > **Sales** folder > open the **Annual Sales Report.docx**.
1. Press **Select label**.
1. Select **Wingtip Acquisition** > **OK**.
**Note**: the label may take a few hours to apply to this document.
1. Copy the link to the **Annual Sales Report.docx**.
1. Navigate to https://m365.cloud.microsoft/chat? and login as **Amber Rodriguez** with the password provided.

   **Note:** The provided user password may not work. If that is the case you will need to reset Amber's password by going to the Microsoft 365 admin center as the MOD Admin > **Users** > **Active Users** > Select **Amber Rodriguez** > select **Reset Password** > ensure no checkbox is selected > type in a pssword of your choosing > select **Reset Password**.
   
1. Select the **IT Helpdesk Agent** > **Open**.
1. Type in the following prompt: “Can I access this document" and paste the Sharepoint link of the **Annual Sales Report.docx** from step 6 above. Press Enter.
1. **Outcome**: Your agent should respond with a message saying the user does not have access to the document.

