# Lab : Azure Sentinel
# Student lab manual

## Lab scenario

You have been asked to create a proof of concept of Azure Sentinel-based threat detection and response. Specifically, you want to:

- Start collecting data from Azure Activity and Security Center.
- Add built in and custom alerts 
- Review how Playbooks can be used to automate a response to an incident.

> For all the resources in this lab, we are using the **East US** region. Verify with your instructor this is the region to use for class. 

## Lab objectives

In this lab, you will complete the following exercise:

- Exercise 1: Implement Azure Sentinel

### Exercise 1: Implement Azure Sentinel

### Estimated timing: 30 minutes

In this exercise, you will complete the following tasks:

- Task 1: On-board Azure Sentinel
- Task 2: Connect Azure Activity to Sentinel
- Task 3: Create a rule that uses the Azure Activity data connector. 


#### Task 1: On-board Azure Sentinel

In this task, you will on-board Azure Sentinel and connect the Log Analytics workspace. 

1. Sign-in to the Azure portal **`https://portal.azure.com/`**.

    >**Note**: Sign in to the Azure portal using an account that has the Owner or Contributor role in the Azure subscription you are using for this lab.

1. In the Azure portal, in the **Search resources, services, and docs** text box at the top of the Azure portal page, type **Azure Sentinel** and press the **Enter** key.

1. On the **Azure Sentinel** blade, click **Connect workspace**.

1. On the **Choose a workspace to add to Azure Sentinel** blade, select the Log Analytics workspace you created in the Azure Monitor lab and click **Add**.

    >**Note**: Azure Sentinel has very specific requirements for workspaces. For example, workspaces created by Azure Security Center can not be used. Read more at [Quickstart: On-board Azure Sentinel](https://docs.microsoft.com/en-us/azure/sentinel/quickstart-onboard)
	
#### Task 2: Configure Azure Sentinel to use the Azure Activity data connector. 

In this task, you will configure Sentinel to use the Azure Activity data connector.  

1. In the Azure portal, on the **Azure Sentinel \| Overview** blade, in the **Configuration** section, click **Data connectors**. 

1. On the **Azure Sentinel \| Data connectors** blade, review the list of available connectors, click the entry representing the **Azure Activity** connector (scroll to the right if needed), review its description, and then click **Open connector page**.

1. On the **Azure Activity** blade, click the **Configure Azure Activity logs** link.

1. On the **Azure Activity log** blade, click the entry representing the Azure subscription you are using in this lab and then click **Connect**.

1. Navigate back to the **Azure Sentinel \| Data connectors** blade and click **Refresh**.

1. On the **Azure Sentinel \| Data connectors** blade, click **Azure Activity**. 

1. Verify that the **Azure Activity** pane displays the **Data received** graph (you might have to refresh the browser page). 

    >**Note**: It may take over 5 minutes before the graph will reflect the any events included in the Azure Activity logs.

#### Task 3: Create a rule that uses the Azure Activity data connector. 

In this task, you will review and create a rule that uses the Azure Activity data connector. 

1. On the **Azure Sentinel \| Configuration** blade, click **Analytics**. 

1. On the **Azure Sentinel \| Analytics** blade, click the **Rule templates** tab. 

    >**Note**: Review the types of rules you can create. Each rule is associated with a specific Data Source.

1. In the listing of rules, type **Suspicious** into the search bar form and click the **Suspicious number of resource creation or deployment** entry associated with the **Azure Activity** data source. And then, in the pane displaying the rule template properties, click **Create rule** (scroll to the right of the page if needed).

    >**Note**: This rule has the medium severity. 

1. On the **General** tab of the **Analytic rule wizard - Create new rule from template** blade, accept the default settings and click **Next: Set rule logic >**.

1. On the **Set rule logic** tab of the **Analytic rule wizard - Create new rule from template** blade, accept the default settings and click **Next: Incident settings >**.

1. On the **Incident settings** tab of the **Analytic rule wizard - Create new rule from template** blade, accept the default settings and click **Next: Automated response >**. 

    >**Note**: This is where you can add a playbook, implemented as a Logic App, to a rule to automate the remediation of an issue.

1. On the **Automated response** tab of the **Analytic rule wizard - Create new rule from template** blade, accept the default settings and click **Next: Review >**. 

1. On the **Review and create** tab of the **Analytic rule wizard - Create new rule from template** blade, click **Create**.

    >**Note**: You now have an active rule.

