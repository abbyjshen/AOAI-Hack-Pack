# Preparation (edits in progress)
Preparation enables you to prepare your Azure Enviornment in time for the Hackathon. The steps to prepare the enviornment are:  

* [Identify the preparation owner](#identify-the-preparation-owner-from-the-partnercustomer) 
* [Define/ Create the Azure Subscription for the hackathon](#definecreate-the-azure-subscriptions-for-the-hackathon)
* [Request Access to Azure OpenAI Service for All Subscriptions](#request-access-to-azure-openai-service-for-all-subscriptions)
* [Create Shared Azure OpenAI Service Resources](#create-shared-azure-openai-service-resources)
* [Deploy Models with Tokens Per Minute (TPM) Limits](#deploy-models-with-tokens-per-minute-tpm-limits)
* [Grant RBAC Roles on the AOAI Service](#grant-rbac-roles-on-the-aoai-service)
* [Prepare and Assign Data](#prepare-and-assign-data)


### Identify the Preparation Owner from the Partner/Customer:
- Determine who the responsible party is on the customer/partner side.
- Ensure they possess:
    - Knowledge and experience of managing and deploying Azure resources via the Portal, at least AZ-900 level knowledge.
    - Authorization to configure subscriptions:
        - If sandbox subscription exists, the responsible person should have owner/ contributor role
        - If the subscription does not already exist, then they need to create a new subscription and therefore, privledges for it. 

### Define/Create the Azure Subscriptions for the Hackathon:
**Warning**: Costs may incur for resource usage. [Monitor/manage expenses](https://learn.microsoft.com/en-us/azure/cost-management-billing/cost-management-billing-overview).
    - Given the increased access for participants, ensure you use [sandbox subscriptions](https://learn.microsoft.com/en-us/azure/architecture/guide/azure-sandbox/azure-sandbox).  
    **Note**: A new Entra ID tenant is not required. Create a new subscription within the existing tenant.  
- Identify hackathon participants. Determine:
        - Existing subscriptions
        - Visual Studio subscriptions
        - Existing dev/test (sandbox) subscriptions
        - Current skill set of participants and if they require additional knowledge to prepare for the hackathon
- Collaborate with the preparation owner to determine the number of subscriptions required. Considerations:
    - Number of teams or resources 
    - **Recommendation**: Use a single sandbox subscription for all participants. Benefits of this approach include:
        - Consistent Monitoring: Easier to track usage and costs across the board.
        - Simplified Management: Reduces the administrative overhead of managing multiple subscriptions.
        - Shared Resources: Facilitates seamless sharing of resources and information among teams.
        - Cost Efficiency: Potentially lower costs as there are volume-based price benefits.
- Based on the chosen approach, define AD groups per team and create separate resource groups for each.
- Ensure participants have contributor access within their [specific resource groups](https://learn.microsoft.com/en-us/azure/role-based-access-control/quickstart-assign-role-user-portal).

### Request Access to Azure OpenAI Service for All Subscriptions
- Visit [https://aka.ms/oai/access](https://aka.ms/oai/access). Submit details for each subscription.
    - Monitor request status.   
    **Note:** If your team requires other [limited access services](https://learn.microsoft.com/en-us/azure/ai-services/cognitive-services-limited-access) for the hack, you will need to request access for them.
### Create Shared Azure OpenAI Service Resources
- Initialize Azure OpenAI resources within each subscription
- Provision necessary resources (e.g., computation, storage)
- Document resource specifics for team access

### Deploy Models with Tokens Per Minute (TPM) Limits
- Ascertain model requirements for each team.
- [Deploy models](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/create-resource?pivots=web-portal) via Azure OpenAI Service, setting [TPM to prevent overuse](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/quota?tabs=rest#assign-quota).
    **Note on TPM:** AOAI has limits on tokens per minutes for each subcription. These tokens are shared across all models of similar types in a region. Learn more about the limits [here](https://learn.microsoft.com/en-us/azure/ai-services/openai/quotas-limits). This limit is crucial for hackathons with multiple teams. If one team consumes the entire quota, others will be left without access. Therefore:
- [Even Distribution](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/quota?tabs=rest#assign-quota): Consider dividing the TPM evenly among teams to ensure fair use.
- Monitoring: Regularly monitor token consumption to avoid any team exhausting the entire limit.
- Alerts: Set up notifications when a certain percentage of the TPM is reached to ensure corrective actions can be taken in time.  

### Grant [RBAC Roles](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/role-based-access-control) on the AOAI Service:
- In the Azure portal, access the Azure OpenAI Service resource
- Assign ['Cognitive Services OpenAI User'](https://learn.microsoft.com/en-us/azure/role-based-access-control/quickstart-assign-role-user-portal) roles to appropriate participants. You may explore [other available roles](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/role-based-access-control#azure-openai-roles) to determine the most suitable role. 
- If working within a single subscription, ensure that the resource groups are clearly defined and that teams are informed about the shared TPM restrictions.

### Configure [Diagnostic Logging](https://learn.microsoft.com/en-us/azure/dev-box/how-to-configure-dev-box-azure-diagnostic-logs):
- Within the Azure portal, access the Azure OpenAI Service resource's 'Diagnostic settings'.
- Monitor service metrics, setting optional alerts for thresholds.
    
### Prepare and Assign Data:
- Establish data requirements
- Source data:
- Create data sets using GPT
- Use sales data, or data from support tickets to create data sets. **Note:** Ensure that personally identifiable data is not used for training models
- [Azure's Open Datasets](https://learn.microsoft.com/en-us/azure/open-datasets/dataset-catalog)
- Select where to [save the data](https://learn.microsoft.com/en-us/azure/machine-learning/how-to-datastore?view=azureml-api-2&tabs=sdk-identity-based-access%2Csdk-adls-identity-access%2Csdk-azfiles-accountkey%2Csdk-adlsgen1-identity-access)
- Use the data in [Azure Open AI Studio](https://learn.microsoft.com/en-us/azure/ai-services/openai/use-your-data-quickstart?tabs=command-line&pivots=programming-language-studio#add-your-data-using-azure-openai-studio) to be consumed by AI models
- If data preprocessing is part of preparations, ensure it's executed appropriately.
- Provide access details to teams, upholding data privacy and security
- Region Considerations:
    - Compliance: Adhere to regulations like GDPR for EU data. **Note:** This is only applicable if PII data is being used.
    - Latency: Choose regions close to most participants.
    - Service Availability: Verify the selected region supports Azure services.
    - Cost: Be aware of potential regional price variations.


### Checklist

- List all hackathon participants.
- make a list of all the required subscriptions
- Define AD groups/team
    - Create separate resource groups/team.
- Ensure contributor access for participants.
- Request Access to Azure OpenAI Service:
- Monitor approval status.
- Grant RBAC Roles on the AOAI Service & Manage TPM
- Set up monitoring for token usage.
 - Set up TPM consumption alerts.
 - Configure Diagnostic Logging
- Prepare and Assign Data

# Capability

1. Create a schedule of learning events including some of these topics, leading up to hackathon start:​


    - **[Azure Fundamentals](https://github.com/PlagueHO/AzureOpenAIDemo/blob/main/prompt-examples/README.md)** (Recommended for newcomers to Azure)
    - **[Azure OpenAI Service L100](https://github.com/PlagueHO/AzureOpenAIDemo/blob/main/prompt-examples/README.md)**:
      - Intended audience: C-level and all roles
      - Includes [simple prompt demos](https://github.com/PlagueHO/AzureOpenAIDemo/blob/main/prompt-examples/README.md)
    - **Innovating beyond Chat with [Azure OpenAI Service](https://github.com/PlagueHO/AzureOpenAIDemo/blob/main/prompt-examples/README.md)**:
      - Intended audience: Technical roles
      - **Note**: Do not use L200/L300 deck; it contains Microsoft Confidential information.
    - **[Copilots](https://github.com/PlagueHO/AzureOpenAIDemo/blob/main/prompt-examples/README.md) & [Plugins](https://github.com/PlagueHO/AzureOpenAIDemo/blob/main/prompt-examples/README.md) with [Semantic Kernel](https://github.com/PlagueHO/AzureOpenAIDemo/blob/main/prompt-examples/README.md)**:
      - Intended audience: Technical roles
    - **[Azure AI services](https://github.com/PlagueHO/AzureOpenAIDemo/blob/main/prompt-examples/README.md)**:
      - Comprehensive overview of Azure AI services
      - Intended audience: Technical roles
1. Self-Paced Learning Plan

    Recommend teams complete the following learning pathways:
    
    - **[Azure OpenAI Service](https://github.com/PlagueHO/AzureOpenAIDemo/blob/main/prompt-examples/README.md)**
    - **[Responsible AI](https://github.com/PlagueHO/AzureOpenAIDemo/blob/main/prompt-examples/README.md)**
    - **[Responsible Conversational AI](https://github.com/PlagueHO/AzureOpenAIDemo/blob/main/prompt-examples/README.md)**
    
