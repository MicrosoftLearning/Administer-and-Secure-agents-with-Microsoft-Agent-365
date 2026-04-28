---
lab:
    title: 'Observe, Alert, and Defend'
    description: 'Analyze usage and governance for agents within your organization. '
    duration: '20 minutes'
    level: 100-200
    islab: true 
---

# Exercise 3: Monitor agent analytics and usage

Scenario: Analyze usage and governance for agents within your organization. Your organization has deployed Agent 365 across multiple departments to automate operational tasks, support internal workflows, and improve efficiency. Finance, Customer Operations, and IT teams actively use agents, while adoption in other business units varies. Leadership wants clear visibility into agent usage, performance, risk exposure, and business value, while ensuring agents remain secure, compliant, and cost-effective. As an Admin, you are responsible for overseeing the full Agent 365 lifecycle—from usage analysis and governance to troubleshooting and retirement. 

In this exercise, you will trace an agent’s actions via audit logs and dashboards. You will also check security alerts.

This exercise should take approximately 20 minutes to perform, however, it may take up to 24 hours for certtain policies to apply after setting them . <!-- update with estimated duration -->

## Task 1: Observe Agent Analytics from the Agent 365 dashboard

First, you need to ...

1. Navigate to https://admin.microsoft.com and login with the provided Admin credentials.
1. Navigate to **Agents** in the navigation menu on the left side on the screen. 
1. Select  **Agents** -> **Overview**.
1. Scroll down to **Agent Analytics**.
1. **Outcome**: You navigated to Agent Analytics within the Microsoft Admin center. 

## Task 2: Generate Audit logs with Microsoft Purview

1. Sign in to the Microsoft Purview portal and the MOD Administrator.
1. Browse to **Solutions** > **Audit** .
1. You should see a message at the top of the screen which reads "Sorry we're having trouble figuring out if activity is being recorded. Try refreshing the page.* This means that auditing is turned on, but will take up to 24 hours for logs to generate. The recommendation is to wait before proceeding on to the next steps.
1. Under the **Date and time** range, change the Start and End date to be within 2 days of when you performed Exercise 2 Task 3. For example, if you performed Exercise 2 Task 3 on April 25th, you should set your start and end date in the filter to April 24 and April 26 respectively. 
1. Select **Search**.
1. **Outcome**: An audit log should appear with the dates as indicated

## Task 3: Generate Alert Reports with Microsoft Purview

1. Sign in to the Microsoft Purview portal and the MOD Administrator.
1. Navigate to **Data Loss Prevention** > **Alerts**.
1. Select **Time range: Any** by **Filters** and set the start date and time to when you performed Exercise 2 Task 3.
1. **Outcome**: A log should be present with the Alert name “DLP policy match for Microsoft 365 Copilot and Copilot Chat.”  Which was generated from Exercise 2 Task 3.

