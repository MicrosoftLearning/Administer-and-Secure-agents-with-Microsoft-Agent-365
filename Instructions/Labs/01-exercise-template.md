---
lab:
    title: 'Discover and Govern Agents'
    description: 'Explore the Agent 365 overviewpage within the Microsoft365 Admin center. '
    duration: '20 minutes'
    level: 200-300
    islab: true 
---
<!--
Edit the metadata above to manage the list of exercises in the home page of the GitHub site that gets generated.
You can delete the module and edit index.md in the root of the repo to customize the display so that only the exercises are listed
To enable GitHub page publishing, edit the Page settings for the repo and publish from the main branch
-->

# Lab 1: Discover and Govern Agents

Scenario: As an Agent 365 administrator, you are responsible for maintaining visibility and governance across all agents in the environment. You need to identify which agents exist in the tenant, understand how they are used, and ensure they meet organizational governance requirements. 

In this exercise you will you will use Agent Registry and, optionally Agent Map to discover agents deployed in the tenant, review agent usage, and understand how agents connect to each other and to enterprise resources. During this review, you will identify an existing agent that needs an new ownership reassignment.  Using Agent 365, the admin identifies the agent, reassigns ownership. This scenario reinforces that agents are long lived digital actors that require lifecycle governance like service accounts.
By completing this lab, you will validate your ability to discover, assess, and govern agents across a Microsoft 365 tenant. 

Lab Description: Discover Microsoft-built, partner-built, and custom agents in a tenant. Additionally, use Agent Registry and Agent Map to know what agents are in use and how they connect to one another. You will also onboard a new agent. You will also identify an agent created by a user within the your organization and reassign ownership to a different user. 

This exercise should take approximately **XX** minutes to complete. <!-- update with estimated duration -->

## Before you start

<!--
Add steps to get the learner to the starting point" for the exercise. This might be cloning the repo and running a script or performing some manual steps.

Only include this section if its necessary to do some pre-exercise setup AND the same setup steps are required for self-paced (on Learn) and managed (in hosted ILT lab profiles) scenarios. Otherwise delete this section.
If self-paced /ILT-specific setup steps are required, include them in the Learn "Exercise" unit from where they open this exercise and in the Skillable lab profile instructions before this markdown file is imported.

Do not include requirements for getting an Azure (or other) subscription (write the exercise on the assumption the learner has a functioning lab environment - this section is only for exercise-specific steps to get to a starting point)

If there are complex setup steps that apply to ALL of the exercises in the repo (for example, installing and configuring client-side tools), create a separate 00-setup.md file with instructions.
 -->

Before you can start this exercise, you will need to...

1. Step 1
1. Step 2
1. etc.

## Task 1 <Discover agents across the tenant using Agent Registry>

First, you need to ...

1. Navigate to https://admin.microsoft.com and login with the provided admin credentials
1. Navigate to **Agents** on the left hand side navigation menu.
1. Select **Overview** > **Agent Registry** > **Explore all agents**. You should be able to see a list of all your agents within your organization.
1. Review the full agent inventory surfaced in the registry.
1. Next to **Filters**  you will notice options to filter the Registry view of agents by “Status”, “Publisher”, “Channel”, “Platform”, and “Data source”. Filter agents by selecting Publisher to identify the different types of agents such as:
    - Microsoft
    - External pertners
    - Crated by your org
    - Shared by creator
1. **Outcome**: You have a centralized view of all agents deployed or discovered in the tenant using Agent Registry.

    ```python
    # This is an example of an
    # indented code block.
    ```

##  Optional Task 2 <Analyze agent relationships using Agent Map>

**Note**: This is an optional task, as the ability to navigate to Agent Maps may be available only in Preview mode. You may need to join the Frontier Program by navigating to Agents> Overview> Select Try now under Do more with the Frontier program and then follow the rest of the prompts. You may get an error upon signing up. You should then close out the browser and then proceed with the steps below. If Agent Maps do not appear, proceed with the next task. 

1. Navigate to https://admin.microsoft.com and login with the provided admin credentials.
1. Navigate to Agents in the navigation menu on the left side on the screen. Select **Agents** > **All agents** select **Map**.
1. You should be able to see groups of agents. For example:
    - External partners
    - Microsoft
1. Double click on the Microsoft Group and zoom into to see the agents within the group.
1. Select the Sales Agent.
1. A pop up window should appear that reads “Sales”. This is demonstrating another way to view Agent details via the Agent Map.
1. **Outcome**: You understand how agents interact with one another and with enterprise resources, reinforcing that agents operate as part of a broader ecosystem.

## Task 3 <Review an agent's metadata>

1. In the selected Sales agent that you opened in the previous task . Review key metadata for the agent in the Overview tab: 
    - Description
    - Additional Resources
    - Published status
    - Deployment
    - Channel
    - Last Updated
    - Version
    - Publisher
    - Agent type
    - Platform
    - Sensitivity
1. Select the “x” on the pop-up window.
1. **Outcome**: You can check an Agent’s metadata.
1. etc.

## Task with subtasks
![A screenshot of an application.](./Media/edge-copilot.png) 
Sometimes you might want to break a task down into smaller chunks.

### Subtask 1

1. Step 1
1. Step 2
1. Etc.

### Subtask 2

1. Step 1
1. Step 2
1. etc.

## Clean up

<!-- Good practice - especially as self-paced learners will be using their own subscriptions -->
<!-- Delete this section if it is not needed -->

Now that you've finished the exercise, you should delete the cloud resources you've created to avoid unnecessary resource usage.

1. Step 1
2. etc.
