---
lab:
    title: 'Observe, Alert, and Defend'
    description: 'Analyze usage and governance for agents within your organization. '
    duration: '20 minutes'
    level: 200-300
    islab: true 
---

# Lab 2 Exercise 1: Monitor agent analytics and usage

Scenario: Security teams flag that an agent may surface sensitive content in Copilot Chat. The admin uses Purview, DLP, and sensitivity labels to restrict what data the agent can process.  

In this exercise you will manage agents through the Agent 365 control plane, including the Microsoft 365 Admin Center, and Purview. Apply Microsoft Purview information protection and DLP policies to control what data the agent may process. 

Lab Description: Discover Microsoft-built, partner-built, and custom agents in a tenant. Additionally, use Agent Registry and Agent Map to know what agents are in use and how they connect to one another. You will also onboard a new agent. You will also identify an agent created by a user within the your organization and reassign ownership to a different user. 

This exercise should take approximately 20 minutes to perform, however, it may take up to 24 hours for certtain policies to apply after setting them . <!-- update with estimated duration -->

## Task 1: Publish and apply a sensitivity label 

First, you need to ...

1. Navigate to the Microsoft Purview portal and login with the provided admin credentials
1. Navigate to **Solutions** > **Information Protection** > **Sensitivity labels**
1. Select **Publish labels**
1. Select the checkbox **Wingtip Acquisition** > select the three elipses > select **Publish label**
1. On Create Policy wizard pop click “Next” through all pages **Labels to publish**, **Admin units**, and **Users and groups** leaving the settings as default.
1. On the Policy settings page, select the check box next to **Require users to apply a label to their emails and documents**.
1. Under Default settings for documents, set the Default label to All Employees. Press **Next**.
1. Click the check box next to **Require users to apply a label to their emails** to ensure that checkbox is selected. Select **Next**.
1. Leave the settings under Apply label inheritance as is. Select **Next**.
1. Under the Default settings for meeting and calendar events page leave the settings as is and select **Next**.
1. Under the Default settings for Engage content (preview) page leave the settings as is and select **Next**.
1. Under the Default settings for Fabric and Power BI content page leave the settings as is and select **Next**.
1. Under Name your policy page, fill in the following fields:
       - **Name**: Test for internal doc for A365 labs
       - **Description**: Test for internal doc for A365 labs
1. On the Review and finish page, select **Submit**.
1. **Outcome**: You have created a sensitivity label. 
**Note**: The sensitivity may take up 24 hours to apply. The recomendation is to move on to the next task after 24 hours has passed. 

## Task 2: Apply a DLP Policy

1. Sign in to the Microsoft Purview portal and the MOD Administrator.
1. Navigate to **Solutions** > **Data Loss Prevention** > **Policies** in the left hand side navigation menu.
1. Select **Create Policy**.
1. Select **Enterprise applications & devices**
1. Select **Custom policy** under Regulations.
1. Select **Custom** under Categories.
1. Select **Next**.
1. Under the **Name your DLP Policy**:
    - **Name**: Test for Agent 365 labs
    - **Description**: Test for Agent 365 labs
1. Select Next on Admin units.
1. On the Choose where to apply the policy page, scroll down to the **Microsoft 365 Copilot and Copilot Chat Location** and select the checkbox next to it.
1. In the Define policy settings select “Create or customize advanced DLP rules”. Select Next.
1. Select **+Create rule**
       - Name: test sensitivity label
1. Under Conditions select **Add** > **Sensitivity labels** > Select checkbox next to **Wingtip Acquisition**.
1. Select **+ Add an action** > **Restrict Copilot from processing content** > Select the checkbox near **Accessing knowledge sources**.
1. Select **Save**
1. Select **Next**
1. Select **Submit**
1. **Outcome**: You have configured a DLP Policy to apply to your agent
**Note** this DLP Policy may take anywhere from 2-24 hours to apply. The recomendation is to move on to the next task after 24 hours has passed. 

## Task 3: Test your DLP Policy via your agent

1. Navigate to your tenant's Sharepoint site and login as the MOD Administrator with the credentials provided.
1. In the searchbox, type **Sales and Marketing** and select it.
1. In the **Sales and Marketing** page, select **Documents** > **Sales** folder > open the **Annual Sales Report.docx**.
1. Press **Select label**.
1. Select **Wingtip Acquisition** > OK
**Note**: the label may take a few hours to apply to this document.
1. Copy the link to the Annual Sales Report.docx
1. Navigate to https://m365.cloud.microsoft/chat? and login as a non admin user with the crednetials provided.
1. Select the **IT Support Assistant** Agent > **Open**
1. Type in the following prompt: “Can I access this document" and paste the Sharepoint link from step 6 above. Press Enter.
1. **Outcome**: Your agent should respond with a message saying it cannot provide that information.

