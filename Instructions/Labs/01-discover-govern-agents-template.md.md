@lab.title


This lab teaches you to discover, onboard, govern, and monitor AI agents across your Microsoft 365 tenant. You'll identify Microsoft-built, partner-built, and custom agents using Agent Registry and Agent Map, onboard new agents, and manage agent ownership. You'll then onboard an agent with Agent 365 and reassign ownership. Finally, you'll govern and monitor agents through the Agent 365 control plane, Microsoft 365 admin center, and Microsoft Purview by applying information protection and DLP policies, reviewing audit logs and dashboards, and checking security alerts to ensure compliance and visibility.

## Exercises

This lab has the following exercises:

- Exercise 1: Discover and govern agents
- Exercise 2: Secure onboarding & identity governance
- Exercise 3: Protect agent data
- Exercise 4: Monitor agent analytics and usage


# Exercise 1: Discover and govern agents

## Scenario
As an Agent 365 administrator, you're responsible for maintaining visibility and governance across all agents in the environment. You need to identify which agents exist in the tenant, understand how they're used, and ensure they meet organizational governance requirements. 
In this exercise you'll use Agent Registry and, Agent Map to discover agents deployed in the tenant, review agent usage, and understand how agents connect to each other and to enterprise resources. 
By completing this exercise, you'll validate your ability to discover, assess, and govern agents across a Microsoft 365 tenant. 

## Objectives

At the end of this lab exercise, you'll be able to:

- Use Agent Registry to locate and filter the tenant-wide inventory of agents by publisher, platform, channel, and data source.
- Interpret agent details and usage signals (for example, status, deployment, and last updated) to identify governance and lifecycle follow-up actions.
- Use Agent Map to analyze relationships between agents and connected resources to support risk assessment and governance decisions.

## Duration

**Estimated time:** 20 minutes

## Before you start

Before you can start this exercise, you'll need to...

1. [] Sign in to  the lab desktop using +++@lab.VirtualMachine(Base23B-W11-22H2).Password+++

1. [] Open a browser and connect to `https://admin.microsoft.com`. 

1. [] Sign in with the admin credentials provided.

    | Option | Value |
    | -------- | -------- |
    | Username | `@lab.CloudCredential(WWLWWLM365withCopilotA365HydratedStakeholderSteveM).AdministrativeUsername` |
    | Password | `@lab.CloudCredential(WWLWWLM365withCopilotA365HydratedStakeholderSteveM).AdministrativePassword` |

	>[!Note] In the pop-up window that says, "You need to set up multifactor authentication," select **Skip for now**.

1. [] Select the **square tile menu** option in the upper left corner of the page.

	!IMAGE[r1e214zm.png](instructions345060/r1e214zm.png)

1. [] Select **SharePoint**. The tenant's SharePoint site should open in another tab or window.

1. [] Confirm that the URL for the SharePoint site begins with **https://@lab.CloudCredential(WWLWWLM365withCopilotA365HydratedStakeholderSteveM).TenantPrefix.sharepoint.com/**

1. [] **Close the SharePoint browser tab** and return to the **Microsoft 365 Admin Center**.

1. [] In the left navigation menu, select **Users > Active users**

1. [] Select **Amber Rodriguez**, and then select **Reset password**.

    !IMAGE[m2fybagg.png](instructions345060/m2fybagg.png)

1. [] Uncheck both boxes and for the password enter `@lab.CloudCredential(WWLWWLM365withCopilotA365HydratedStakeholderSteveM).AdministrativePassword`

1. [] Select **Reset password**, and then select **Close**.

## Task 1: Discover agents across the tenant using Agent Registry

1. [] Select **Agents** on the left-hand side navigation menu.

1. [] Select **Overview**. 

1. [] On the **Agent Registry** tile, select **Explore all agents**. 

	!IMAGE[6z1kpohx.png](instructions345060/6z1kpohx.png)

    >[!Note] You should be able to review a list of all agents within your organization.

1. [] Review the full agent inventory surfaced in the registry.

    >[!Note] Next to **Filters** you'll notice options to filter the Registry view of agents by "Status", "Publisher type", "Channel", "Platform", and "Data source". 

1. [] Select **Publisher type** to filter agents and identify the different types, such as:
    - Your org
    - Your users
    - Microsoft
    - Third party

**Outcome**: You now have a centralized view of all agents deployed or discovered in the tenant using Agent Registry.

## Task 2: Analyze agent relationships using Agent Map

1. [] Select **Agents** on the left-hand side navigation menu.

1. [] Select **Overview**. 

1. [] On the Get early access to Agent 365 tile, select **Join the program**

    !IMAGE[hrati3w2.png](instructions345060/hrati3w2.png)

1. [] Select **All users**, and then select **Save**.

1. [] Select the **X** in the top right corner to close the flyout page.

1. [] On the Do more with the Frontier program tile, select **Try now**.

	!IMAGE[mr1dvs80.png](instructions345060/mr1dvs80.png)

1. [] On the Terms of Service popup, select **I agree**.

1. [] Below the Summary on the right side of the page, select **Try Now**

	!IMAGE[vc8aerxe.png](instructions345060/vc8aerxe.png)

1. [] On the You're all set! page, select **Go to Admin Home**

1. [] Select **Agents** on the left-hand side navigation menu.

1. [] Select **All agents**. 

1. [] Select **Map**.

    !IMAGE[ke95ps06.png](instructions345060/ke95ps06.png)

    >[!Note] If you don't see the Map option, refresh the browser page.

1. [] You should see groups of agents, such as:
    - External partners
    - Microsoft

1. [] Double-click the **Microsoft** group.

1. [] Zoom in to review the agents within the group.

1. [] Select the **Sales agent**.

    >[!Note] A pop-up window should appear with the title **Sales**. This demonstrates another way to view Agent details via the Agent Map.

**Outcome**: You now understand how agents interact with one another and with enterprise resources, reinforcing that agents operate as part of a broader ecosystem.

## Task 3: Review an agent's metadata

1. [] In the selected Sales agent that you opened in the previous task, review key metadata for the agent. Observe the following tabs, **Details**, **Users**, **Data & tools**, **Security**, **Permissions**, **Certification**, and **Activity**.

1. [] Select the **x** on the pop-up window to close it.

**Outcome**: You're now able to check an agent's metadata.

## Task 4: Onboard an Agent

1. [] Select **Requests**.

	!IMAGE[x4hy8dn6.png](instructions345060/x4hy8dn6.png)

1. [] Select the **IT Helpdesk Agent**.

1. [] Select **Publish to store**.

	!IMAGE[ua8wzgzl.png](instructions345060/ua8wzgzl.png)

1. [] In the Publish agent to selected users page select the following options:
    1. [] Under Select users or groups who can install the agent, select **All users**. 
    1. [] Under Select users or groups who will have the agent pre-installed (optional), select **All users**. 
 
1. [] Select **Next**.

1. [] On the Apply template page, leave all the defaults, and then select **Next**.

1. [] On the Review permissions page, select **Next**.

1. [] On the Review and finish page, select **Publish**, and then select **Done**.

1. [] On the All agents page, select **Registry**

	!IMAGE[9mibvifb.png](instructions345060/9mibvifb.png)

1. [] Select and review the **IT Helpdesk Agent**.

    >[!Note] If you do not see the IT Helpdesk Agent, ensure that you clear anything that appears in the search field.
    !IMAGE[w6344rjs.png](instructions345060/w6344rjs.png)

1. [] Select the **X** in the top right corner to close the IT Helpdesk Agent details pane.

**Outcome:** You have onboarded an agent.

## Task 5: Reassign Agent Ownership

1. [] In **Edge**, open an InPrivate window.

    !IMAGE[ap7fmvnw.png](instructions345060/ap7fmvnw.png)

1. [] In the **InPrivate** browser go to `https://m365.cloud.microsoft/chat`

1. [] Sign in as `AdilE@@lab.CloudCredential(WWLWWLM365withCopilotA365HydratedStakeholderSteveM).TenantName` with the password `@lab.CloudCredential(WWLWWLM365withCopilotA365HydratedStakeholderSteveM).UserPassword`

1. [] On the left-hand navigation panel, select **New agent**.

    >[!Note] If you see the Build an agent prompt, select **Skip to configure ->**
    !IMAGE[6wqnj3fy.png](instructions345060/6wqnj3fy.png)

1. [] Fill out the following fields under the New Agent page: 

    | Field | Value |
    | -------- | -------- |
    | Template | **None** |
    | Name | `Contoso Agent` |
    | Describe your agent | `Contoso Agent` |
    | Instructions | `Agent to help facilitate documents to the call center` |
    | Knowledge<br>Add specific websites | `https://@lab.CloudCredential(WWLWWLM365withCopilotA365HydratedStakeholderSteveM).TenantPrefix.sharepoint.com/` |

	!IMAGE[gftzp2fv.png](instructions345060/gftzp2fv.png)

1. [] Select **Create**.

	!IMAGE[ie76fgkw.png](instructions345060/ie76fgkw.png)

	> [!Alert] If the agent creation takes more than a few minutes, you may need to refresh the page and start the agent creation over.

1. [] You can close the agent created popup by selecting the **X** in the upper right corner.

	!IMAGE[j743k5oe.png](instructions345060/j743k5oe.png)

1. [] Close the InPrivate browser window and return to the **Microsoft 365 admin center as the MOD Admin**.

1. [] Select **Agents** on the left-hand side of the navigation menu, and then select **All agents**.

1. [] On the Registry tab, search for the newly created `Contoso Agent`.

1. [] Select the **Contoso Agent**.

1. [] Select **Assign new owner**.

	!IMAGE[aolfc1jx.png](instructions345060/aolfc1jx.png)

1. [] In the Search for a user text box, enter and then select `Amber Rodriguez`.

1. [] Select **Assign**.

    >[!Note] You should now see the Owner listed as Amber Rodriguez.

1. [] Select the **X** in the top right corner to close the agent.

**Outcome:** You have reassigned ownership of the Contoso Agent.