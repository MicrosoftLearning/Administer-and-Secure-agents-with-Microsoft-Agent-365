# Exercise 4: Observe alerts and audit logs

## Scenario
Your organization has deployed Agent 365 across multiple departments to automate operational tasks, support internal workflows, and improve efficiency. Finance, Customer Operations, and IT teams actively use agents, while adoption in other business units varies. Leadership wants clear visibility into agent usage, performance, risk exposure, and business value, while ensuring agents remain secure, compliant, and cost-effective. As an admin, you are responsible for overseeing the full Agent 365 lifecycle, from usage analysis and governance to troubleshooting and retirement. 

In this exercise, you'll trace an agent's actions via audit logs and dashboards, and check security alerts.

## Objectives

At the end of this lab exercise, you'll be able to:

- Locate and interpret key agent usage and performance indicators in the Agent Analytics dashboard.
- Generate and filter Microsoft Purview audit events to trace agent activity within a specified date range.
- Review Microsoft Purview alerts to identify and investigate DLP-related policy matches affecting Copilot and agents.

## Duration

**Estimated time:** 20 minutes

>[!Alert] Audit logs and DLP alerts may take several hours to appear. You do not need to wait for them to in order to continue or complete the lab.

## Task 1: Observe Agent Analytics from the Agent 365 dashboard

1. [] Return to the **Microsoft 365 admin center** tab in your browser.

1. [] Select **Agents** on the navigation menu on the left-hand side of the screen. 

1. [] Select **Overview**.

1. [] Scroll down to **Agent Analytics**.

**Outcome**: You viewed Agent Analytics in the Microsoft 365 admin center.. 

## Task 2: Generate audit logs with Microsoft Purview

1. [] Return to the **Microsoft Purview portal** browser tab or open a new one and connect to `purview.microsoft.com`

1. [] Select **Solutions**. 

1. [] Select **Audit**. 

1. [] You should see a message at the top of the screen that reads **"Sorry we're having trouble figuring out if activity is being recorded. Try refreshing the page."** This means that auditing is turned on, but will take up to 24 hours for logs to generate. The recommendation is to move on to the next steps.

1. [] If you see the blue bar that says **Start recording user and admin activity** , select it to enable auditing. Audit events may take several hours to appear.

	!IMAGE[rvhx8p0a.png](instructions345060/rvhx8p0a.png)

1. [] Under the **Date and time** range, change the **Start** and **End** date to be within two days of when you performed Exercise 2. For example, if you performed this exercise on April 25th, you should set your start and end date in the filter to April 24 and April 26 respectively. 

1. [] Select **Search**. 

>[!Alert] It can take several hours for the search results to appear. You do not need to wait for the results before completing the lab. The following screenshot shows an example of the results once they are available.
!IMAGE[0t9kav26.png](instructions345060/0t9kav26.png)

**Outcome**: An audit log should appear with the dates as indicated.

## Task 3: Generate alert reports with Microsoft Purview

1. [] Select **Solutions**, and then select **Data Loss Prevention**.

1. [] Select **Alerts**.

>[!Alert] It may take several hours for the alerts to appear. You do not need to wait for the results before completing the lab. 

**Outcome**: A log should be present with the Alert name "DLP policy match for Microsoft 365 Copilot and Copilot Chat", which was generated from Exercise 2, Task 3. 

