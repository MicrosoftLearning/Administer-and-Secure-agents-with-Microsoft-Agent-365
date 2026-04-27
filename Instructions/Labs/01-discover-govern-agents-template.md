---
lab:
    title: 'Discover and Govern Agents'
    description: 'Explore the Agent 365 overviewpage within the Microsoft365 Admin center. '
    duration: '20 minutes'
    level: 200-300
    islab: true 
---


# Exercise 1: Discover and Govern Agents

Scenario: As an Agent 365 administrator, you are responsible for maintaining visibility and governance across all agents in the environment. You need to identify which agents exist in the tenant, understand how they are used, and ensure they meet organizational governance requirements. 

In this exercise, you will you will use Agent Registry and, optionally, Agent Map to discover agents deployed in the tenant. You will review agent usage, and understand how agents connect to each other and to enterprise resources. During this review, you will identify an existing agent that needs new ownership reassignment. This scenario reinforces that agents are long lived digital actors that require lifecycle governance like service accounts.

By completing this exercise, you will validate your ability to discover, assess, and govern agents across a Microsoft 365 tenant. 

Lab Exercise: Discover Microsoft-built, partner-built, and custom agents in a tenant. Additionally, use Agent Registry and Agent Map to know what agents are in use and how they connect to one another. You will onboard a new agent. You will also identify an agent created by a user within the your organization and reassign ownership to a different user. 

This exercise should take approximately **20** minutes to complete. <!-- update with estimated duration -->

## Before you start

Before you can start this exercise, you will need to...

1.  Navigate to https://admin.microsoft.com and login with the provided admin credentials.
1.   On the pop up window **You need to set up multifactor authentication**, select **Skip for now**
1.  Click on the squre tile menu option at the top left corner.
1.  Select Sharepoint. The tenant's Sharepoint site should open in another tab/window.
1.  Take note of the Sharepoint site as you will need it during the lab. For example,  https://wwlcpxxxxx.sharepoint.com/.


## Task 1: Discover agents across the tenant using Agent Registry

First, you need to ...

1. Navigate to https://admin.microsoft.com and login with the provided admin credentials.
1. Navigate to **Agents** on the left hand side navigation menu.
1. Select **Overview** > **Agent Registry** > **Explore all agents**. You should be able to see a list of all your agents within your organization.
1. Review the full agent inventory surfaced in the registry.
1. Next to **Filters**, you will notice options to filter the Registry view of agents by “Status”, “Publisher Type”, “Channel”, “Platform”, and “Data source”. Filter agents by selecting Publisher to identify the different types of agents such as:
    - Your org
    - Your users
    - Microsoft 
    - Third party
1. **Outcome**: You have a centralized view of all agents deployed or discovered in the tenant using Agent Registry.

##  Optional Task 2: Analyze agent relationships using Agent Map

**Note**: This is an optional task, as the ability to navigate to Agent Maps may be available only in Preview mode. You may need to join the Frontier Program by navigating to Agents> Overview. Then, select 'Join the program' under 'Get early access to Agent 365'. On the pop up window, seelct 'All users'. Then select 'Try now. You may get an error upon signing up. You should then close out the browser and then proceed with the steps below. If Agent Maps do not appear, proceed with the next task. 

1. Open up a browser window and navigate to https://admin.microsoft.com. Login with the provided admin credentials.
1. Navigate to Agents in the navigation menu on the left side on the screen. Select **Agents** > **All agents** select **Map**.
1. You should be able to see different groups of agents. For example:
    - External partners
    - Microsoft
1. Double click on the Microsoft Group and zoom in to see the agents within the group.
1. Select the Sales Agent.
1. A pop up window should appear that reads “Sales”. This is demonstrating another way to view Agent details via the Agent Map.
1. **Outcome**: You understand how agents interact with one another and with enterprise resources, reinforcing that agents operate as part of a broader ecosystem.

## Task 3: Review an agent's metadata

1. In the selected Sales agent that you opened in the previous task. Review key metadata for the agent in the Overview tab:
   **Note**: If you were unable to complete the previous task, Navigate to the **Overview** > **Agent Registry** > **Explore all agents** section within the Microsoft 365 Admin center and search and Select the "Sales" Agent.
1. You should be able to see the following information related to the "Sales" Agent. This appears in a pop up window:
    - Description
    - Published status
    - Availability
    - Deployment
    - Channel
    - Last Updated
    - Version
    - Publisher
    - Agent type
    - Platform
    - Sensitivity
1. Select the **x** on the pop-up window to close out the winow.
1. **Outcome**: You can check an Agent’s metadata.

# Exercise 1a: Manage Agents with Agent 365

## Task 1: Onboard an Agent

1. Navigate to https://admin.microsoft.com and login with the provided admin credentials. Select **Agents** on the left hand side of the navigation menu. 
1. Select **All agents** > **Requests**.
1. Select the **IT Helpdesk Agent**.
1. Select **Publish to store**.
1. In the **Publish agent to selected users** page select the following options:
       - Under **Select users to groups who can install the agent**, select **All users**.
       - Under the **Select users or groups who will have the agent pre-installed (optional)**, select **All users**. The select **Next**.
1. On the Apply security template page select the following option:
       - In the dropdown list for **Template**, leave the default option as is. Leave the rest of the page as is and select **Next**.
1. On the **Review permissions** page, select **Next**.
1. On the **Review and finish** page, select **Publish**. Select **Done**.
1. Navigate back to **Agents**> **All Agents** > **Registry**.
1. Select the  **IT Helpdesk Agent**.
1. **Outcome**: You have onboarded an agent.

## Task 2: Reassign Agent Ownership

1.Navigate to the Microsoft 365 Admin portal as the MOD Admin. Select **Users** from the left hand side navigation menu. Select the user **Adil Eli**.
1. In Adil Eli's account page, copy Adil's username which is located in the **Username and email** field.
1. Navigate to https://m365.cloud.microsoft/chat? and login as Adil Eli with the username you copied in the step above. The password has been provided to you under the "Resource" tab.
1. On the left hand navigation side, select **New agent**.
1. Fill out the following fields under the New Agent page:
       - **Template**: None
       - **Name**: Contoso Agent
       - **Description**: Contoso Agent
       - **Instructions**: Agent to help facilitate documents to the call center
       - **Knowledge**: Add specific websites: Add the link to the Sharepoint site that you retrieved at the start of the lab.
1. Select **Create**.
1. Navigate to https://admin.microsoft.com and login with as the MOD Administrator.
1. Select **Agents** on the left hand side of the navigation menu. Then select **All agents**.
1. Under the **Registry** tab you should now see the newly created Contoso Agent.
1. Select the Contoso Agent.
1. Select **Assign new owner**.
1. In the Search for a user text box, select Amber Rodriguez.
1. Select **Assign**.
1. You may receive an error that the assignment was unsuccessful. Close out the agent reassignment window.
1. Back on the Agent registry page, refresh the web page.
1. Select the Contoso Agent.
1. You should now the Owner listed as Amber Rodriguez.
1. **Outcome**: You have reassigned the owner of an agent.

