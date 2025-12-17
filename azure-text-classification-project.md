# Azure Custom Text Classification: Workforce Learning Query Categorization

## Project Overview

This document provides a complete implementation guide for building an Azure AI Language Custom Text Classification model to automatically categorize workforce learning and development queries. This solution is designed for federal agencies and large organizations managing employee learning programs.

### Taxonomy Categories

| Category | Description |
|----------|-------------|
| **Compliance & Ethics** | Mandatory training, annual certifications, ethics requirements, security clearances |
| **Learning Platforms & Access** | LMS access issues, course enrollment, technical problems, account management |
| **Career Development** | Professional growth, certifications, mentorship, leadership programs |
| **Performance Management** | Reviews, goals, IDPs, feedback, performance improvement |
| **Technical Tools** | Software training, systems access, IT applications, productivity tools |
| **Other** | General inquiries, miscellaneous requests, unclassifiable queries |

---

## Section 1: Training Dataset

Save the following content as `training_data.csv`. This dataset contains 85 labeled examples of realistic federal workforce learning queries.

```csv
text,category
"When is my annual cybersecurity awareness training due?",Compliance & Ethics
"I haven't completed my No FEAR Act training yet. Is there a deadline?",Compliance & Ethics
"How do I access the ethics training for new supervisors?",Compliance & Ethics
"My security clearance renewal requires additional training. What courses do I need?",Compliance & Ethics
"Where can I find the mandatory anti-harassment training module?",Compliance & Ethics
"Is the Privacy Act training required for all GS employees?",Compliance & Ethics
"I need to complete my HIPAA compliance certification before my TDY assignment.",Compliance & Ethics
"What are the annual training requirements for contracting officer representatives?",Compliance & Ethics
"How often do I need to renew my records management training?",Compliance & Ethics
"The OGE 450 filers training is showing as incomplete. How do I verify completion?",Compliance & Ethics
"I'm a new federal employee. What mandatory trainings must I complete in my first 90 days?",Compliance & Ethics
"Does the whistleblower protection training count toward my annual compliance hours?",Compliance & Ethics
"My supervisor says I need Controlled Unclassified Information training. Where is it?",Compliance & Ethics
"Is there a religious freedom and accommodation training available?",Compliance & Ethics
"I can't log into the Learning Management System. My PIV card isn't working.",Learning Platforms & Access
"How do I reset my password for the agency LMS portal?",Learning Platforms & Access
"The course video won't play on my government laptop. I'm getting a codec error.",Learning Platforms & Access
"Can I access training courses from my personal device while teleworking?",Learning Platforms & Access
"My training transcript is missing three courses I completed last quarter.",Learning Platforms & Access
"How do I register for an instructor-led training session in the catalog?",Learning Platforms & Access
"The system keeps timing out when I try to launch the Adobe Connect session.",Learning Platforms & Access
"I need to enroll my team members in a group training. How do I do bulk enrollment?",Learning Platforms & Access
"Why does my SF-182 keep getting rejected when I submit it through the portal?",Learning Platforms & Access
"The mobile app for our learning portal doesn't sync with the desktop version.",Learning Platforms & Access
"I transferred from another agency. How do I get my training records migrated?",Learning Platforms & Access
"Can I get a certificate of completion for external training I took through Coursera?",Learning Platforms & Access
"The course I need says 'enrollment closed.' When will it open again?",Learning Platforms & Access
"My supervisor needs to approve my training request but can't find it in the system.",Learning Platforms & Access
"How do I request access to the leadership development track in the LMS?",Learning Platforms & Access
"What professional certifications are reimbursable under the agency's tuition assistance program?",Career Development
"I'm interested in the Presidential Management Fellows program. What's the application process?",Career Development
"How do I find a mentor through the agency's mentorship program?",Career Development
"Are there any rotational opportunities for GS-12 employees looking to broaden their experience?",Career Development
"I want to develop my project management skills. Is there a PMP prep course available?",Career Development
"What leadership development programs are available for aspiring supervisors?",Career Development
"Can I use my training budget for a conference registration fee?",Career Development
"How do I create an Individual Development Plan that aligns with my career goals?",Career Development
"Is there a succession planning program for senior-level positions?",Career Development
"What skills should I develop to qualify for a GS-14 position in my series?",Career Development
"I'm interested in the Senior Executive Service Candidate Development Program. Am I eligible?",Career Development
"Does the agency offer coaching for employees transitioning to leadership roles?",Career Development
"Are there cross-training opportunities between different divisions?",Career Development
"How do I apply for the emerging leaders program?",Career Development
"What graduate degree programs does the agency support through academic partnerships?",Career Development
"Can I shadow someone in a different role to explore career options?",Career Development
"How do I set performance goals in the new performance management system?",Performance Management
"When is the mid-year performance review period?",Performance Management
"My supervisor hasn't acknowledged my self-assessment. How do I follow up?",Performance Management
"How do I document a developmental opportunity in my performance plan?",Performance Management
"What's the difference between the 'Meets Expectations' and 'Exceeds Expectations' ratings?",Performance Management
"I disagree with my annual rating. What's the reconsideration process?",Performance Management
"How do I request 360-degree feedback as part of my performance evaluation?",Performance Management
"When should I update my performance elements after a position change?",Performance Management
"My performance improvement plan expires next month. What happens next?",Performance Management
"Can I add stretch goals to my performance plan mid-cycle?",Performance Management
"How do I give feedback to a colleague using the peer recognition tool?",Performance Management
"What training is available to help supervisors conduct effective performance conversations?",Performance Management
"My EPAP isn't showing my updated critical elements. How do I fix this?",Performance Management
"How do I link my IDP goals to my annual performance objectives?",Performance Management
"Where can I find training on Microsoft Teams advanced features?",Technical Tools
"I need to learn Power BI for my new data analysis responsibilities.",Technical Tools
"Is there training available for the new financial management system rollout?",Technical Tools
"How do I get access to the Tableau visualization software?",Technical Tools
"I want to learn Python for automating reports. Are there courses available?",Technical Tools
"Where's the training for the new human capital management system?",Technical Tools
"Is there a SharePoint administrator training track?",Technical Tools
"I need to learn advanced Excel for budget forecasting.",Technical Tools
"How do I request access to Power Automate for workflow automation?",Technical Tools
"Are there any Salesforce training modules for the CRM implementation?",Technical Tools
"I want to learn SQL for database queries. What courses are recommended?",Technical Tools
"Where can I find training on the new document management system?",Technical Tools
"Is there a course on using Microsoft Copilot for productivity?",Technical Tools
"How do I get certified in ServiceNow for IT service management?",Technical Tools
"I need training on the new grants management system before the fiscal year ends.",Technical Tools
"Who do I contact about a billing issue for a conference I attended?",Other
"Can I transfer unused training hours to the next fiscal year?",Other
"What's the process for requesting training funds from a different budget code?",Other
"I'm retiring next year. Can I still take career development courses?",Other
"How do I nominate a colleague for a training excellence award?",Other
"Is there a way to rate the quality of a course I completed?",Other
"What's the maximum number of training hours allowed per quarter?",Other
"Can contractors access the same training catalog as federal employees?",Other
"I'm looking for training on public speaking for an upcoming presentation.",Other
"Are there any wellness or mindfulness courses available through the LMS?",Other
"How do I provide feedback on the new learning management system?",Other
```

### Dataset Statistics

| Category | Count | Percentage |
|----------|-------|------------|
| Compliance & Ethics | 14 | 16.5% |
| Learning Platforms & Access | 16 | 18.8% |
| Career Development | 16 | 18.8% |
| Performance Management | 14 | 16.5% |
| Technical Tools | 15 | 17.6% |
| Other | 10 | 11.8% |
| **Total** | **85** | **100%** |

---

## Section 2: Azure Language Studio Project Setup

### Prerequisites

Before starting, ensure you have:
- An active Azure subscription
- Azure AI Language resource created in a supported region (East US, West US 2, West Europe, etc.)
- Storage account with a blob container for training data
- Contributor role or higher on the resource

### Step 2.1: Create Azure AI Language Resource

1. Navigate to [Azure Portal](https://portal.azure.com)
2. Click **Create a resource** → Search for **Language Service**
3. Click **Create** and configure:
   - **Subscription**: Select your subscription
   - **Resource Group**: Create new or select existing
   - **Region**: `East US` (or nearest supported region)
   - **Name**: `workforce-learning-language`
   - **Pricing Tier**: `S` (Standard) for production workloads
4. Review and Create the resource
5. Once deployed, navigate to the resource and note down:
   - **Endpoint URL**: `https://workforce-learning-language.cognitiveservices.azure.com/`
   - **API Key**: Found under **Keys and Endpoint**

### Step 2.2: Create Storage Account and Upload Data

1. In Azure Portal, create a **Storage Account**:
   - **Name**: `workforcelearningdata`
   - **Region**: Same as your Language resource
   - **Performance**: Standard
   - **Redundancy**: LRS (Locally-redundant storage)

2. After creation, navigate to the storage account:
   - Go to **Containers** → **+ Container**
   - Name: `training-data`
   - Access: Private

3. Upload the `training_data.csv` file to this container

4. **Configure CORS and Role Assignment**:
   - Go to your Language resource
   - Navigate to **Access control (IAM)**
   - Add role assignment: **Storage Blob Data Contributor**
   - Assign to the Language resource's managed identity

### Step 2.3: Create Custom Text Classification Project in Language Studio

1. Navigate to [Language Studio](https://language.cognitive.azure.com/)

2. Sign in with your Azure credentials

3. Select your Language resource:
   - Subscription: `[Your Subscription]`
   - Resource: `workforce-learning-language`

4. Under **Classify text**, select **Custom text classification**

5. Click **Create new project** and configure:

   | Field | Value |
   |-------|-------|
   | **Project name** | `WorkforceLearningClassifier` |
   | **Description** | `Classifies employee learning queries into predefined categories for intelligent routing` |
   | **Text primary language** | `English` |
   | **Classification type** | `Single label classification` |
   | **Storage container** | Select your `training-data` container |

6. Click **Create project**

### Step 2.4: Import and Label Training Data

1. In your project, go to **Data labeling**

2. Click **Import** → **Import from CSV**

3. Configure import settings:
   - **CSV file**: Select `training_data.csv`
   - **Text column**: `text`
   - **Label column**: `category`
   - **Separator**: Comma

4. Click **Import**

5. Verify imported data:
   - All 85 documents should appear
   - Each document should be labeled with one of the 6 categories

6. **Review class distribution** to ensure balanced representation

### Step 2.5: Train the Model

1. Navigate to **Training jobs**

2. Click **Start a training job**

3. Configure training:

   | Setting | Value |
   |---------|-------|
   | **Model name** | `workforce-classifier-v1` |
   | **Training mode** | `Standard training` |
   | **Data splitting** | `Automatic split` (80% training, 20% testing) |

4. Click **Train** and wait for completion (typically 15-30 minutes)

5. After training completes, review **Model performance**:
   - Overall F1 Score
   - Per-class precision, recall, and F1
   - Confusion matrix

### Expected Model Performance

Based on the training data provided, expect approximately:

| Category | Precision | Recall | F1 Score |
|----------|-----------|--------|----------|
| Compliance & Ethics | 0.90+ | 0.85+ | 0.87+ |
| Learning Platforms & Access | 0.88+ | 0.90+ | 0.89+ |
| Career Development | 0.85+ | 0.88+ | 0.86+ |
| Performance Management | 0.90+ | 0.85+ | 0.87+ |
| Technical Tools | 0.92+ | 0.90+ | 0.91+ |
| Other | 0.75+ | 0.80+ | 0.77+ |

---

## Section 3: Deploy the Model

### Step 3.1: Create a Deployment

1. In Language Studio, navigate to **Deploying a model**

2. Click **Add deployment**

3. Configure deployment:

   | Setting | Value |
   |---------|-------|
   | **Deployment name** | `workforce-learning-prod` |
   | **Model** | `workforce-classifier-v1` |

4. Click **Deploy**

5. Deployment typically completes in 5-10 minutes

### Step 3.2: Note Deployment Details

After deployment, record these values for API calls:

```
Endpoint: https://workforce-learning-language.cognitiveservices.azure.com/
API Key: [Your API Key from Azure Portal]
Project Name: WorkforceLearningClassifier
Deployment Name: workforce-learning-prod
API Version: 2023-04-01
```

### Step 3.3: Test the Deployment

1. In Language Studio, go to **Testing deployments**

2. Select your deployment: `workforce-learning-prod`

3. Enter test queries:

   ```
   Test 1: "How do I complete my annual ethics certification?"
   Expected: Compliance & Ethics
   
   Test 2: "I can't log into the learning portal with my CAC card"
   Expected: Learning Platforms & Access
   
   Test 3: "What certifications should I pursue for a promotion to GS-14?"
   Expected: Career Development
   ```

4. Verify predictions match expected categories

---

## Section 4: Power Automate Integration

### HTTP POST Endpoint Code

Use the following HTTP action configuration in Power Automate to call the classification API.

#### Option A: HTTP Action (Premium Connector)

**HTTP Action Configuration:**

```json
{
  "method": "POST",
  "uri": "https://workforce-learning-language.cognitiveservices.azure.com/language/analyze-text/jobs?api-version=2023-04-01",
  "headers": {
    "Content-Type": "application/json",
    "Ocp-Apim-Subscription-Key": "@{variables('ApiKey')}"
  },
  "body": {
    "displayName": "WorkforceLearningClassification",
    "analysisInput": {
      "documents": [
        {
          "id": "1",
          "language": "en",
          "text": "@{triggerBody()?['query']}"
        }
      ]
    },
    "tasks": [
      {
        "kind": "CustomSingleLabelClassification",
        "taskName": "ClassifyQuery",
        "parameters": {
          "projectName": "WorkforceLearningClassifier",
          "deploymentName": "workforce-learning-prod"
        }
      }
    ]
  }
}
```

#### Option B: Complete Power Automate Flow (Step-by-Step)

**Flow Name**: `Classify Learning Query`

**Trigger**: When a new email arrives / When an HTTP request is received / When a SharePoint item is created

---

**Step 1: Initialize Variables**

Add a **Initialize Variable** action for each:

| Variable Name | Type | Value |
|---------------|------|-------|
| `ApiEndpoint` | String | `https://workforce-learning-language.cognitiveservices.azure.com` |
| `ApiKey` | String | `[Your API Key - Store in Azure Key Vault for production]` |
| `ProjectName` | String | `WorkforceLearningClassifier` |
| `DeploymentName` | String | `workforce-learning-prod` |

---

**Step 2: Submit Classification Job (HTTP Action)**

```
Method: POST
URI: @{variables('ApiEndpoint')}/language/analyze-text/jobs?api-version=2023-04-01

Headers:
  Content-Type: application/json
  Ocp-Apim-Subscription-Key: @{variables('ApiKey')}

Body:
{
  "displayName": "QueryClassification_@{utcNow()}",
  "analysisInput": {
    "documents": [
      {
        "id": "1",
        "language": "en",
        "text": "@{triggerBody()?['userQuery']}"
      }
    ]
  },
  "tasks": [
    {
      "kind": "CustomSingleLabelClassification",
      "taskName": "ClassifyUserQuery",
      "parameters": {
        "projectName": "@{variables('ProjectName')}",
        "deploymentName": "@{variables('DeploymentName')}"
      }
    }
  ]
}
```

---

**Step 3: Parse Operation-Location Header**

The response will include an `Operation-Location` header with the job status URL.

Add a **Compose** action:
```
Name: GetOperationLocation
Inputs: @{outputs('HTTP')['headers']['operation-location']}
```

---

**Step 4: Delay for Processing**

Add a **Delay** action:
- Count: `5`
- Unit: `Second`

---

**Step 5: Get Classification Results (HTTP Action)**

```
Method: GET
URI: @{outputs('GetOperationLocation')}

Headers:
  Ocp-Apim-Subscription-Key: @{variables('ApiKey')}
```

---

**Step 6: Parse JSON Response**

Add a **Parse JSON** action:

```json
{
  "type": "object",
  "properties": {
    "jobId": { "type": "string" },
    "status": { "type": "string" },
    "tasks": {
      "type": "object",
      "properties": {
        "completed": { "type": "integer" },
        "items": {
          "type": "array",
          "items": {
            "type": "object",
            "properties": {
              "results": {
                "type": "object",
                "properties": {
                  "documents": {
                    "type": "array",
                    "items": {
                      "type": "object",
                      "properties": {
                        "id": { "type": "string" },
                        "class": {
                          "type": "array",
                          "items": {
                            "type": "object",
                            "properties": {
                              "category": { "type": "string" },
                              "confidenceScore": { "type": "number" }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
}
```

---

**Step 7: Extract Classification Result**

Add a **Compose** action to get the predicted category:
```
Name: PredictedCategory
Inputs: @{body('Parse_JSON')?['tasks']?['items']?[0]?['results']?['documents']?[0]?['class']?[0]?['category']}
```

Add another **Compose** action for confidence score:
```
Name: ConfidenceScore
Inputs: @{body('Parse_JSON')?['tasks']?['items']?[0]?['results']?['documents']?[0]?['class']?[0]?['confidenceScore']}
```

---

**Step 8: Route Based on Category (Switch/Condition)**

Add a **Switch** control:

Control Value: `@{outputs('PredictedCategory')}`

| Case | Action |
|------|--------|
| `Compliance & Ethics` | Send to Compliance Team channel/email |
| `Learning Platforms & Access` | Create IT Support ticket |
| `Career Development` | Forward to HR Development team |
| `Performance Management` | Route to Performance Management mailbox |
| `Technical Tools` | Create IT Training request |
| `Other` | Send to general Learning inbox |

---

### Synchronous API Alternative (Simpler Integration)

For immediate response without job polling, use the synchronous endpoint:

```json
{
  "method": "POST",
  "uri": "https://workforce-learning-language.cognitiveservices.azure.com/language/:analyze-text?api-version=2023-04-01",
  "headers": {
    "Content-Type": "application/json",
    "Ocp-Apim-Subscription-Key": "@{variables('ApiKey')}"
  },
  "body": {
    "kind": "CustomSingleLabelClassification",
    "parameters": {
      "projectName": "WorkforceLearningClassifier",
      "deploymentName": "workforce-learning-prod"
    },
    "analysisInput": {
      "documents": [
        {
          "id": "1",
          "language": "en",
          "text": "@{triggerBody()?['userQuery']}"
        }
      ]
    }
  }
}
```

**Response Format:**

```json
{
  "kind": "CustomSingleLabelClassificationResults",
  "results": {
    "documents": [
      {
        "id": "1",
        "class": [
          {
            "category": "Compliance & Ethics",
            "confidenceScore": 0.95
          }
        ]
      }
    ]
  }
}
```

---

## Section 5: Production Considerations

### Security Best Practices

1. **Store API Keys in Azure Key Vault**
   - Create a Key Vault secret for the API key
   - Use Power Automate's Key Vault connector to retrieve secrets

2. **Use Managed Identities** where possible
   - Eliminates need for API keys in automation flows

3. **Implement Rate Limiting**
   - Standard tier: 1,000 requests per minute
   - Add retry logic for 429 responses

### Monitoring and Logging

1. **Enable Diagnostic Settings** on the Language resource:
   - Log to Log Analytics workspace
   - Track request metrics, errors, and latency

2. **Set Up Alerts**:
   - High error rate (>5%)
   - Latency degradation (>2s average)
   - Quota usage warnings

### Model Maintenance

1. **Regularly Review Misclassifications**
   - Export logs of low-confidence predictions
   - Add corrected examples to training data

2. **Retrain Periodically**
   - Quarterly retraining recommended
   - Incorporate new query patterns
   - Test new model version before swapping deployment

3. **Version Control**
   - Name models with version numbers (v1, v2, etc.)
   - Maintain rollback capability with multiple deployments

---

## Appendix A: Sample Test Queries

Use these queries to validate your deployment:

```
1. "My annual cyber awareness training is overdue by 3 weeks."
   Expected: Compliance & Ethics

2. "The LMS keeps showing an error when I try to launch courses."
   Expected: Learning Platforms & Access

3. "I want to get my PMP certification this fiscal year."
   Expected: Career Development

4. "How do I add my supervisor's comments to my mid-year review?"
   Expected: Performance Management

5. "Is there a Power Automate training track for citizen developers?"
   Expected: Technical Tools

6. "Can I donate my unused training hours to another employee?"
   Expected: Other
```

---

## Appendix B: Troubleshooting

| Issue | Solution |
|-------|----------|
| 401 Unauthorized | Verify API key is correct and active |
| 404 Not Found | Check project/deployment names match exactly |
| 400 Bad Request | Validate JSON body structure |
| Low Confidence Scores | Add more training examples for that category |
| Slow Response Times | Use synchronous endpoint for single documents |

---

## Appendix C: Cost Estimation

| Component | Pricing (as of 2024) |
|-----------|---------------------|
| Custom Text Classification Training | $3 per 1,000 training characters |
| Hosted Model (S tier) | ~$25/month per deployed model |
| API Calls | $0.50 per 1,000 text records |

**Estimated Monthly Cost** (1,000 queries/month): **~$25-30**

---

*Document Version: 1.0*  
*Last Updated: December 17, 2024*  
*Author: Azure AI Implementation Team*
