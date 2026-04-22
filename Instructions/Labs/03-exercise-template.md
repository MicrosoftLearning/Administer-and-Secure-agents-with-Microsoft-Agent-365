---
lab:
    title: 'Observe, Alert, and Defend'
    description: 'Analyze usage and governance for agents within your organization. '
    duration: '20 minutes'
    level: 200-300
    islab: true 
---

# Lab 3 Exercise 1: Monitor agent analytics and usage

Scenario: Analyze usage and governance for agents within your organization. Your organization has deployed Agent 365 across multiple departments to automate operational tasks, support internal workflows, and improve efficiency. Finance, Customer Operations, and IT teams actively use agents, while adoption in other business units varies. Leadership wants clear visibility into agent usage, performance, risk exposure, and business value, while ensuring agents remain secure, compliant, and cost-effective. As an Admin, you are responsible for overseeing the full Agent 365 lifecycle—from usage analysis and governance to troubleshooting and retirement. 

In this exercise you will trace an agent’s actions via audit logs and dashboards, and check security alerts.

This exercise should take approximately 20 minutes to perform, however, it may take up to 24 hours for certtain policies to apply after setting them . <!-- update with estimated duration -->

## Task 1: Observe Agent Analytics from the Agent 365 dashboard

First, you need to ...

1. Navigate to https://admin.microsoft.com and login with the provided Admin credentials.
1. Navigate to **Agents** in the navigation menu on the left side on the screen. 
1. Select  **Agents** -> **Overview**
1. Scroll down to **Agent Analytics**
1. **Outcome**: You navigated to Agent Analytics within the Microsoft Admin center. 

## Task 2: Generate Audit logs with Microsoft Purview

1. Sign in to the Microsoft Purview portal and the MOD Administrator.
1. Browse to **Solutions** > **Audit** 
1. Select **Create Policy**.
1. Select **Turn On** under the Audit on solution settings. If you have to turn this setting on, it will take 24 hours for this to apply. The reccomendation is to move on to Task 3 of this lab in the meantime. 
   - **Note**: This policy may already be turned on.
   - **Note**: If this policy is already turned on, you will still need wait 24 hours before proceeding with the next step of this task. The reccomendation is to move on to Task 3 of this lab in the meantime. 
1. Under the** Date and time** range, change the Start and End date to be within 2 days of when you performed Lab 3. For example, if you performed Lab 3 on April 25th, you should set your start and end date in the filter to April 24 and April 26 respectively. 
1. Select **Search** 
1. **Outcome**: An audit log should appear with the dates as indicated

## Task 3: Generate Alert Reports with Microsoft

1. Sign in to the Microsoft Purview portal and the MOD Administrator.
1. Navigate to **Data Loss Prevention** > **Alerts**
1. **Outcome**: A log should be present with the Alert name “DLP policy match for Microsoft 365 Copilot and Copilot Chat.”  Which was generated from Lab 2 Exercise 1 Task 3. 

