
# Exercise 2: Secure onboarding & identity governance

Scenario: A department submits a request to deploy an internal HR agent. The admin reviews the agent approval workflow, applies the Entra access packages and permission scopes, and configures lifecycle and expiration policies. The admin publishes the agent, and ensures it runs within approved runtime boundaries-without modifying how the agent was built. 

In this exercise, you will apply an access package to a secuirty template for your organiztion's agent.

This exercise should take approximately 20 minutes to perform.

## Task 1: Create an access package for agent identities

First, you need to ...


1. [] in a new browser tab, go to `https://entra.microsoft.com`.

1. [] If prompted, sign in with the admin credentials provided.

    | Option | Value |
    | -------- | -------- |
    | Username | `@lab.CloudCredential(WWLWWLM365withCopilotA365HydratedStakeholderSteveM).AdministrativeUsername` |
    | Password | `@lab.CloudCredential(WWLWWLM365withCopilotA365HydratedStakeholderSteveM).AdministrativePassword` |


    >[!Alert] You will have to setup your login with the Authenticator app. Please follow the prompts on screen to do so. 

1. [] Navigate to **Entra ID** in the navigation menu on the left side on the screen. 

1. [] Select  **Groups** -> **New Group**.

1. [] In the **New Group** page, fill out the following fields:
    1. [] Group Type: **Security**
    1. [] Group Name: `agent 365-test group`
    1. [] Group description: `test group for labs`
 
1. [] Select **Create**. 

1. [] On the left hand side of the navigation menu, select **ID Governance** (you may need to scroll down)

1. [] Select **Entitlement Management**.

1. [] On the center menu, under Catalogs, select **Catalogs**.

1. [] Select the **Agent 365 Governance** catalog.

1. [] Select **Resources**.

1. [] Select **+ Add Resources** 

1. [] Select **+ Groups and Teams**.

1. [] Search for and then select `agent365-test group` that was created in step 4 
 
1. [] Select **Select**, and then select **Add**.

1. [] On the left menu under ID Governance, select **Access Reviews**.

1. [] In the center menu under Entitlement management, select **Access Packages**.

1. [] Select **+ New access package**.

1. [] Under the **Basics** tab fill out the following fields:
    1. [] Name: `Agent 365 New Access Package`.
    1. [] Description: `Access package for lab`.
    1. [] Catalog: Select **Agent 365 Governance** (the Catalog we modified in above) .

1. [] Select **Next: Resource roles >**.

1. [] Under the Resource roles tab, select **+ Groups and Teams**.

	!IMAGE[ky37bpe0.png](instructions346133/ky37bpe0.png)

1. [] In the pop window ,select the checkbox **See all Group and Team(s) not in the 'Agent 365 Governance' catalog. You must have the correct permissions to add them in this access package.** 

1. [] Select the **agent-365-test-group**, and then select **Select**.

1. [] Select **+ SharePoint sites**. 

	!IMAGE[qhamjmnp.png](instructions346133/qhamjmnp.png)

1. [] In the pop window ,select the checkbox **See SharePoint Site(s) not in the 'Agent 365 Governance' catalog. You must have the correct permissions to add them in this access package.** 

1. [] Search for and then select `Operations Department` site, and then select **Select**.

1. [] Back under the Resource roles tab, you should see Resource agent-365-test-group in the main grid.  In the grid, select the drop down for the field Role. Select **Member**.

1. [] Back under the Resource roles tab, you should see resource 'Operations Department' in the main grid.  In the grid, select the drop down for the field Role. Select **Operations Department Members**.

1. [] Select **Next: Requests >**.

1. [] Under the field Who can get access select **For users, service, principals, and agent identities in your directory**.

1. [] In the field Select specific scope select **All agents**.

1. [] Under **Who can request access** leave the default Admin as selected.

1. [] Scroll down to Approval and set **Require approval** to **No**. 

1. [] Select **Next: Requester Information >**.

1. [] Under the Requester information tab, leave all default values and then select **Next: Lifecycle**.

1. [] Under Lifecycle tab, ensure that  the checkbox for **Require access reviews** under Access Reviews is **NOT selected**.

1. [] Select **Next: Rules >**.

1. [] Under the Custom extensions tab, leave all default values and then select, and then select **Next: Review + create >**.

1. [] Under the Review and Create tab, select the **Create**. 

**Outcome**: You have created an access package. 

## Task 2: Configure Conditional Access Policies

1. [] In the left menu under Entra ID, select **Conditional Access**.

1. [] In the center menu select **Policies**.

	!IMAGE[4ey5j9nr.png](instructions346133/4ey5j9nr.png)

1. [] Under **Policy name**, select the **CA: Block High-Risk Agent Identities**.

1. [] Under **Users or agents (Preview)**, select the link **0 users or agents (Preview) selected**.

1. [] In the dropdown for What does this policy apply to?, select **Agents (Preview)**.

1. [] Under Include, select **All agent identities (Preview)**.

1. [] Under Conditions, select the link **0 conditions selected**.

1. [] Under Agent risk (Preview), select **Not configured**.

1. [] In the Agent risk (Preview) flyout, set **Configure** to **Yes**, and select the checkbox for **High**. 

1. [] Select **Done**, and then select **Save**.

1. [] Under **Policy name**, select the **CA: Block Unapproved Agent Identities**.

1. [] Under **Users or agents (Preview)**, select the link **0 users or agents (Preview) selected**.

1. [] In the dropdown for What does this policy apply to?, select **Agents (Preview)**.

1. [] Under Include, select **All agent identities (Preview)**.

1. [] Under Conditions, select the link **0 conditions selected**.

1. [] Under Agent risk (Preview), select **Not configured**.

1. [] In the Agent risk (Preview) flyout, set **Configure** to **Yes**, and select the checkbox for **High**. 

1. [] Select **Done**, and then select **Save**.

**Outcome**: You have configured conditional access policies.

## Task 3: Configure Custom security attributes


1. [] In the left menu under Entra ID, select **Users**, and then select **All Users**

1. [] Search for and then select `MOD Administrator`

1. [] Select the number next to **Assigned roles**.

	!IMAGE[07jrn6v9.png](instructions346133/07jrn6v9.png)

1. [] Select **+ Add assignments**

1. [] In the dropdown for **Select role**, search for and then select the role `Attribute Assignment Administrator`

1. [] Select **Next**.

1. [] Under assignment type, select **Active**

1. [] Under Enter justification, enter `to access custom security attributes`.

1. [] Select **Assign**.

1. [] Select **+ Add assignments**

1. [] In the dropdown for **Select role**, search for and then select the role `Attribute Assignment Reader`

1. [] Select **Next**.

1. [] Under assignment type, select **Active**

1. [] Under Enter justification, enter `to access custom security attributes`.

1. [] Select **Assign**.

1. [] Select **+ Add assignments**

1. [] In the dropdown for **Select role**, search for and then select the role `Attribute Definition Administrator`

1. [] Select **Next**.

1. [] Under assignment type, select **Active**

1. [] Under Enter justification, enter `to access custom security attributes`.

1. [] Select **Assign**.

1. [] Select **+ Add assignments**

1. [] In the dropdown for **Select role**, search for and then select the role `Attribute Definition Reader`

1. [] Select **Next**.

1. [] Under assignment type, select **Active**

1. [] Under Enter justification, enter `to access custom security attributes`.

1. [] Select **Assign**.

1. [] Select **Refresh** to confirm the assignments were added.

1. [] In the left menu under Entra ID, select **Custom security attributes**.

1. [] Select the **AgentGovernance** security attribute.

1. [] Select **Department** 

1. [] Select the **ellipses** **…** on the right and then select **Edit attribute**.

1. [] Ensure **Compliance** is listed under **Predefined values**.

1. [] Select the **x** at the top right of the window.

**Outcome**: You have configured a custom security attirbute.

## Task 4: Create a new security template for Agents

1. [] Return to the **Microsoft 365 admin center** browser tab.

1. [] Select **Agents**, and then select **Settings**.

1. [] Select **Templates**.

1. [] Select **+ Add a new template**.

1. [] For Template name, enter `HR Helper agent template`.

1. [] For Template description, enter `Test template for labs`.

1. [] Select **Next**.

1. [] Under the **Security policies and protections** page, select the following checkboxes: 
    1. [] **Conditional Access**: ensure the **CA: Block High-Risk Agent Identities**, and **CA: Block Unapproved Agent Identities** are selected and grayed out. 
    1. [] **Access Packages**: set the drop down to **Agent 365 New Access Package**, which you created in Task 1 of this exercise.
    1. [] **Custom Security Attribute**: set the drop down fields to **Department** and **Compliance**.

1. [] Select **Next**.

1. [] Select **Save template**.

1. [] Select **Finish**.

**Outcome**: You have configured a custom security attirbute.


## Task 5: Assign an agent identity to the access package

1. [] Select **Agents**, and then select **All agents**.

1. [] Select **Requests**.

	!IMAGE[3zgrhcby.png](instructions346133/3zgrhcby.png)

1. [] Select the **HR Helper Agent**.

1. [] Select **Publish to store**.

	!IMAGE[n6v4thek.png](instructions346133/n6v4thek.png)

1. [] In the Publish agent to selected users page select the following options:
    1. [] Under Select users or groups who can install the agent, select **All users**. 
    1. [] Under Select users or groups who will have the agent pre-installed (optional), select **All users**. 
 
1. [] Select **Next**.

1. [] In the Template dropdown, select **HR Helper agent template**

1. [] Review all the policies in the **Default** section to learn more about which policies can be managed in different platforms, and then select **Next**.

1. [] Select **Next**.

1. [] Select **Publish**.

1. [] Select **Done**.

**Outcome**: You have applied the agent identity to the access package.

##  Optional Task 6: Test your agent's access

<!--

1. [] In the top left corner of the Microsoft 365 admin center, select the **app launcher**, and then select **SharePoint**.

	!IMAGE[rmy73whe.png](instructions346133/rmy73whe.png)

1. [] Select the **Operations Depeartment Group** tile.

	!IMAGE[5a3iczdk.png](instructions346133/5a3iczdk.png)

1. [] Select **Documents** > open the folder **Human Resources** > open the **Contoso Ltd. Open Poitions.docx**.

	!IMAGE[dludgrkz.png](instructions346133/dludgrkz.png)

1. [] Select **Select label**.

	!IMAGE[0w8iyp2a.png](instructions345060/0w8iyp2a.png)

    >[!Note] If you do not see the Select label option, select the Sensitivity label dropdown <br>!IMAGE[8q0fd2du.png](instructions345060/8q0fd2du.png)

1. [] Select **Public** > **OK**.

-->

1. [] In a new browser tab connect to `https://m365.cloud.microsoft/chat`.

1. [] On the left navigation pane, select **…All agents**.

1. [] In the search box search for and then select the **HR Helper Agent**,

1. [] Type the following prompt and select enter: `What can you do for me?` wait for the agent to respond and then type in any other prompt. For example, `What can you tell me about Contoso Ltd.'s open positions?`

**Outcome**: Your agent should respond with tasks it can do for you. 
