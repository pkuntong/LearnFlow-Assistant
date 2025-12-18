# Azure Custom Text Classification - LearnFlow Assistant

**Project:** Workforce Learning Query Classifier  
**Model Type:** Single-label Custom Text Classification  
**Created:** December 17, 2025

---

## Table of Contents
1. [Training Dataset CSV](#training-dataset-csv)
2. [Test Examples CSV](#test-examples-csv)
3. [Azure Setup Guide](#azure-setup-guide)
4. [API Integration](#api-integration)

---

## Training Dataset CSV

Copy the content below into a file named `training_data.csv`:

```csv
Text,Class
"How do I complete my annual ethics training?","Compliance & Ethics"
"Where can I find the OGE 450 form?","Compliance & Ethics"
"Is the anti-harassment training mandatory this year?","Compliance & Ethics"
"When is the deadline for my cybersecurity awareness cert?","Compliance & Ethics"
"I need to report a conflict of interest - who do I contact?","Compliance & Ethics"
"What are the gift acceptance rules for federal employees?","Compliance & Ethics"
"Can I accept a lunch invitation from a contractor?","Compliance & Ethics"
"Where do I find the Hatch Act training module?","Compliance & Ethics"
"My annual OPSEC training is overdue - help!","Compliance & Ethics"
"How do I complete the No FEAR Act refresher?","Compliance & Ethics"
"Whats the policy on outside employment approval?","Compliance & Ethics"
"Do I need ethics approval to teach a college course?","Compliance & Ethics"
"Where can I review our agencys standards of conduct?","Compliance & Ethics"
"How often do I need to complete records management training?","Compliance & Ethics"
"I received a gift from a foreign official - what do I do?","Compliance & Ethics"
"Can you explain the post-employment restrictions?","Compliance & Ethics"
"Where is the annual privacy act training?","Compliance & Ethics"
"Is FISMA training required for all employees?","Compliance & Ethics"
"How do I file a financial disclosure report?","Compliance & Ethics"
"What training do I need for handling PII?","Compliance & Ethics"
"Need to complete mandatory training before EOY","Compliance & Ethics"
"ethics hotline number please","Compliance & Ethics"
"How do I access the LMS?","Learning Platforms & Access"
"I cant log into Cornerstone - getting an error","Learning Platforms & Access"
"Where do I find my training transcripts?","Learning Platforms & Access"
"How do I reset my learning portal password?","Learning Platforms & Access"
"Which browser works best for the online training system?","Learning Platforms & Access"
"The video wont play in my mandatory training module","Learning Platforms & Access"
"How do I access LinkedIn Learning through our agency?","Learning Platforms & Access"
"Is there a mobile app for the training platform?","Learning Platforms & Access"
"My completions arent showing up in my record","Learning Platforms & Access"
"How do I print my training certificate?","Learning Platforms & Access"
"Can I access training from home on my personal device?","Learning Platforms & Access"
"The LMS keeps timing out - is it down?","Learning Platforms & Access"
"How do I register for an instructor-led class?","Learning Platforms & Access"
"Where do I find the course catalog?","Learning Platforms & Access"
"SSO not working for training portal","Learning Platforms & Access"
"How do I get access to Skillsoft?","Learning Platforms & Access"
"my supervisor needs to approve my training request - how?","Learning Platforms & Access"
"Can I take training on my GFE while teleworking?","Learning Platforms & Access"
"Where is the FAI training portal?","Learning Platforms & Access"
"How do I transfer my training records from my old agency?","Learning Platforms & Access"
"Video buffering issue during training","Learning Platforms & Access"
"forgot my LMS username","Learning Platforms & Access"
"training page just shows a blank screen","Learning Platforms & Access"
"How do I apply for the leadership development program?","Career Development"
"What are the requirements for promotion to GS-13?","Career Development"
"Is there a mentoring program available?","Career Development"
"How do I create an Individual Development Plan?","Career Development"
"What rotational assignments are available in my series?","Career Development"
"Can I apply for a detail to another office?","Career Development"
"How do I get approved for external education?","Career Development"
"What training do I need for a supervisory position?","Career Development"
"Is tuition reimbursement available for my masters degree?","Career Development"
"How do I join the Senior Executive Service candidate program?","Career Development"
"What competencies should I focus on for advancement?","Career Development"
"Are there shadowing opportunities with senior leaders?","Career Development"
"How do I document my accomplishments for promotion?","Career Development"
"What aspiring leader programs does our agency offer?","Career Development"
"Can I participate in an interagency rotation?","Career Development"
"How do I become a certified project manager?","Career Development"
"What is the timeline for the next LDP cohort?","Career Development"
"Does the agency pay for professional certifications?","Career Development"
"How do I request a developmental assignment?","Career Development"
"Whats required for the management certificate program?","Career Development"
"career coaching - is that available?","Career Development"
"want to move from 343 to 2210 series - path?","Career Development"
"IDP template where?","Career Development"
"How do I set goals in USA Performance?","Performance Management"
"When are mid-year reviews due?","Performance Management"
"How do I give feedback to my direct reports?","Performance Management"
"Where do I find my performance plan?","Performance Management"
"What are the critical elements for my position?","Performance Management"
"How does the 5-level rating system work?","Performance Management"
"Can I update my performance objectives mid-cycle?","Performance Management"
"How do I document performance issues with an employee?","Performance Management"
"When do annual appraisals need to be completed?","Performance Management"
"How do I request a performance award nomination?","Performance Management"
"What is a Performance Improvement Plan?","Performance Management"
"My supervisor hasnt completed my review - what do I do?","Performance Management"
"How do I add accomplishments to my self-assessment?","Performance Management"
"What metrics should I track for my performance goals?","Performance Management"
"Can I see my historical performance ratings?","Performance Management"
"How do I give a time-off award to my team member?","Performance Management"
"Whats the difference between Exceeds and Outstanding?","Performance Management"
"performance appraisal portal link?","Performance Management"
"How do I challenge my performance rating?","Performance Management"
"progress review meeting - when?","Performance Management"
"PMAP system not loading","Performance Management"
"need help writing SMART objectives","Performance Management"
"How do I set up Teams for a meeting?","Technical Tools"
"OneDrive is not syncing my files","Technical Tools"
"Where do I download Microsoft Project?","Technical Tools"
"How do I use SharePoint to share documents with my team?","Technical Tools"
"My Outlook calendar invites arent working","Technical Tools"
"How do I request access to Power BI?","Technical Tools"
"Can I install Zoom on my government laptop?","Technical Tools"
"Where do I find the VPN client download?","Technical Tools"
"How do I create a shared mailbox in Outlook?","Technical Tools"
"Excel keeps crashing when I open large files","Technical Tools"
"How do I get Visio for process mapping?","Technical Tools"
"Teams showing wrong timezone for meetings","Technical Tools"
"How do I set up automatic replies in Outlook?","Technical Tools"
"Where is the ServiceNow portal for IT tickets?","Technical Tools"
"How do I add a shared drive to my computer?","Technical Tools"
"PowerPoint templates for agency presentations?","Technical Tools"
"How do I use Copilot in Word?","Technical Tools"
"My multifactor authentication isnt working","Technical Tools"
"How do I schedule a Teams Live Event?","Technical Tools"
"Need software request form for new tool","Technical Tools"
"Planner vs To Do - which should I use?","Technical Tools"
"M365 license question","Technical Tools"
"Where can I find information about our agency benefits?","Other/General"
"How do I contact HR?","Other/General"
"Whats the holiday schedule for this year?","Other/General"
"How do I submit a leave request?","Other/General"
"Where is the employee assistance program info?","Other/General"
"How do I update my emergency contact information?","Other/General"
"Whats the telework policy?","Other/General"
"How do I get a parking pass?","Other/General"
"Where do I find forms for travel reimbursement?","Other/General"
"Who handles building maintenance requests?","Other/General"
"How do I order office supplies?","Other/General"
"Whats the process for reporting a safety concern?","Other/General"
"Where can I find the organizational chart?","Other/General"
"How do I change my TSP contributions?","Other/General"
"Is there a gym in the building?","Other/General"
"What time does the cafeteria close?","Other/General"
"transit subsidy application?","Other/General"
"How do I get a new PIV card?","Other/General"
"wheres the break room","Other/General"
"snow day policy?","Other/General"
"new employee orientation schedule?","Other/General"
"union rep contact info","Other/General"
```

**Total Training Examples: 130**  
- Compliance & Ethics: 22  
- Learning Platforms & Access: 23  
- Career Development: 23  
- Performance Management: 22  
- Technical Tools: 22  
- Other/General: 18  

---

## Test Examples CSV

Copy the content below into a file named `test_data.csv` (hold out from training):

```csv
Text,Class
"What is the timeline for completing my ethics certification?","Compliance & Ethics"
"How do I report a potential bribery situation?","Compliance & Ethics"
"annual training reminder - what do I need to finish?","Compliance & Ethics"
"LMS login page wont load","Learning Platforms & Access"
"how do i see completed courses?","Learning Platforms & Access"
"Can I access training on the weekend?","Learning Platforms & Access"
"What opportunities exist for a GS-12 looking to advance?","Career Development"
"How do I find a mentor in my career field?","Career Development"
"SES CDP application deadline?","Career Development"
"How do I add evidence to my mid-year review?","Performance Management"
"when is the performance cycle end date?","Performance Management"
"My supervisor gave me a 3 but I think I deserve higher","Performance Management"
"How do I share my screen in Teams?","Technical Tools"
"OneDrive storage limit question","Technical Tools"
"ServiceNow ticket not updating","Technical Tools"
"FEHB open season dates?","Other/General"
"Where do I pick up my mail?","Other/General"
"How do I reserve a conference room?","Other/General"
"CFC campaign - how to donate?","Other/General"
"where is HR located in the building","Other/General"
```

**Total Test Examples: 20**

---

## Azure Setup Guide

### Prerequisites
- Azure subscription with Contributor or Owner role
- Azure CLI installed (optional but helpful)
- Web browser (Edge or Chrome recommended)

---

### Step 1: Create Azure AI Language Resource

1. **Navigate to Azure Portal**
   - Go to [https://portal.azure.com](https://portal.azure.com)
   - Sign in with your Azure credentials

2. **Create a new Language Resource**
   - Click **+ Create a resource**
   - Search for **"Language service"** or **"Azure AI Language"**
   - Click **Create**

3. **Configure the resource**
   | Setting | Value |
   |---------|-------|
   | Subscription | Your Azure subscription |
   | Resource Group | Create new or select existing (e.g., `rg-learnflow-ai`) |
   | Region | **East US** or **West US 2** (Custom classification supported) |
   | Name | `lang-learnflow-classifier` (must be unique) |
   | Pricing Tier | **S** (Standard) - required for custom classification |

   > ⚠️ **Important:** Free tier (F0) does NOT support custom text classification. You must use Standard (S) tier.

4. **Enable Custom Text Classification**
   - Under **Custom features** section, check:
     - ✅ Custom text classification / extraction
   - This requires a **Storage Account** - either:
     - Create new: `stlearnflowdata` (will be auto-created)
     - Or link existing storage account

5. **Review + Create**
   - Click **Review + create**
   - Click **Create**
   - Wait for deployment (2-5 minutes)

6. **Get Keys and Endpoint**
   - After deployment, click **Go to resource**
   - In left menu, click **Keys and Endpoint**
   - Copy and save:
     - **Key 1** or **Key 2**
     - **Endpoint** (e.g., `https://lang-learnflow-classifier.cognitiveservices.azure.com/`)

---

### Step 2: Prepare Training Data

1. **Create the CSV file locally**
   - Copy the Training Dataset CSV content from above
   - Save as `training_data.csv` (UTF-8 encoding, no BOM)

2. **Upload to Azure Blob Storage**
   - Go to your storage account in Azure Portal
   - Click **Containers** → **+ Container**
   - Name: `training-data`
   - Click **Create**
   - Open the container → **Upload**
   - Upload `training_data.csv`

---

### Step 3: Create Project in Language Studio

1. **Open Language Studio**
   - Go to [https://language.cognitive.azure.com](https://language.cognitive.azure.com)
   - Sign in with the same Azure account
   - Select your subscription and Language resource

2. **Create Custom Classification Project**
   - On the home page, find **Classify text**
   - Click **Custom text classification**
   - Click **Create new project**

3. **Configure Project Settings**
   | Setting | Value |
   |---------|-------|
   | Project name | `LearnFlowQueryClassifier` |
   | Description | Classifies workforce learning queries |
   | Text primary language | English |
   | Project type | **Single label classification** |
   | Enable multi-lingual | No (unless needed) |

4. **Connect Storage**
   - Select your storage account
   - Select the container: `training-data`
   - Click **Next**

5. **Review and Create**
   - Click **Create project**

---

### Step 4: Import and Label Data

#### Option A: Import Pre-labeled Data (Recommended)

1. **Create a labels file** named `labels.json`:
```json
{
  "projectFileVersion": "2022-05-01",
  "stringIndexType": "Utf16CodeUnit",
  "metadata": {
    "projectKind": "CustomSingleLabelClassification",
    "projectName": "LearnFlowQueryClassifier",
    "multilingual": false,
    "description": "Workforce learning query classifier",
    "language": "en-us"
  },
  "assets": {
    "projectKind": "CustomSingleLabelClassification",
    "classes": [
      {"category": "Compliance & Ethics"},
      {"category": "Learning Platforms & Access"},
      {"category": "Career Development"},
      {"category": "Performance Management"},
      {"category": "Technical Tools"},
      {"category": "Other/General"}
    ],
    "documents": [
      {"location": "training_data.csv", "language": "en-us", "dataset": "Train"}
    ]
  }
}
```

2. **Upload labels.json** to the same container

3. **In Language Studio:**
   - Go to **Data labeling** → **Activity** tab
   - Click **Import** → **Import labels file**
   - Select `labels.json`

#### Option B: Manual Labeling (If importing fails)

1. In Language Studio, go to **Data labeling**
2. Click **+ Add class** for each category:
   - Compliance & Ethics
   - Learning Platforms & Access
   - Career Development
   - Performance Management
   - Technical Tools
   - Other/General

3. For each document:
   - Select the text
   - Assign the appropriate class label
   - Click **Save**

> 💡 **Tip:** You can bulk-label by filtering and selecting multiple documents

---

### Step 5: Train the Model

1. **Start Training**
   - Click **Training jobs** in left menu
   - Click **Start a training job**

2. **Configure Training**
   | Setting | Value |
   |---------|-------|
   | Model name | `model-v1` |
   | Training mode | Standard training |
   | Data splitting | Auto-split (80% train / 20% test) |

3. **Start Training**
   - Click **Train**
   - Training takes **10-30 minutes** depending on data size
   - You'll receive email notification when complete

4. **Monitor Progress**
   - View status in **Training jobs** section
   - Wait for status: **Succeeded**

---

### Step 6: Evaluate Model

1. **View Evaluation Results**
   - Click on completed training job
   - Go to **Model performance** tab

2. **Review Metrics**
   - **Precision**: Correct predictions / Total predictions per class
   - **Recall**: Correct predictions / Actual instances per class
   - **F1 Score**: Harmonic mean of precision and recall

3. **Target Thresholds**
   | Metric | Minimum Target |
   |--------|----------------|
   | Overall F1 | > 0.85 |
   | Per-class F1 | > 0.80 |

4. **If Performance is Low:**
   - Add more training examples
   - Review mislabeled examples
   - Ensure class balance
   - Re-train with updated data

---

### Step 7: Deploy the Model

1. **Deploy Model**
   - Click **Deploying model** in left menu
   - Click **Add deployment**

2. **Configure Deployment**
   | Setting | Value |
   |---------|-------|
   | Deployment name | `production` |
   | Model | `model-v1` |

3. **Deploy**
   - Click **Deploy**
   - Wait for status: **Deployed** (1-2 minutes)

4. **Note Deployment Details**
   - Project name: `LearnFlowQueryClassifier`
   - Deployment name: `production`

---

## API Integration

### Endpoint Information

After deployment, your API endpoint will be:

```
POST {Endpoint}/language/analyze-text/jobs?api-version=2023-04-01
```

### Authentication
- Header: `Ocp-Apim-Subscription-Key: {your-key}`
- Content-Type: `application/json`

---

### Sample cURL Request

```bash
curl -X POST "https://lang-learnflow-classifier.cognitiveservices.azure.com/language/analyze-text/jobs?api-version=2023-04-01" \
  -H "Ocp-Apim-Subscription-Key: YOUR_API_KEY_HERE" \
  -H "Content-Type: application/json" \
  -d '{
    "displayName": "ClassifyUserQuery",
    "analysisInput": {
      "documents": [
        {
          "id": "1",
          "language": "en",
          "text": "How do I complete my annual ethics training?"
        }
      ]
    },
    "tasks": [
      {
        "kind": "CustomSingleLabelClassification",
        "taskName": "QueryClassification",
        "parameters": {
          "projectName": "LearnFlowQueryClassifier",
          "deploymentName": "production"
        }
      }
    ]
  }'
```

---

### Synchronous API (Recommended for Single Documents)

For real-time classification, use the synchronous endpoint:

```bash
curl -X POST "https://lang-learnflow-classifier.cognitiveservices.azure.com/language/:analyze-text?api-version=2023-04-01" \
  -H "Ocp-Apim-Subscription-Key: YOUR_API_KEY_HERE" \
  -H "Content-Type: application/json" \
  -d '{
    "kind": "CustomSingleLabelClassification",
    "analysisInput": {
      "documents": [
        {
          "id": "1",
          "language": "en",
          "text": "How do I complete my annual ethics training?"
        }
      ]
    },
    "parameters": {
      "projectName": "LearnFlowQueryClassifier",
      "deploymentName": "production"
    }
  }'
```

---

### Sample Response

```json
{
  "kind": "CustomSingleLabelClassificationResults",
  "results": {
    "documents": [
      {
        "id": "1",
        "classifications": [
          {
            "category": "Compliance & Ethics",
            "confidenceScore": 0.96
          }
        ],
        "warnings": []
      }
    ],
    "errors": [],
    "modelVersion": "2023-04-01"
  }
}
```

---

### Power Automate HTTP Action

For Power Automate integration, use the HTTP action with these settings:

| Setting | Value |
|---------|-------|
| Method | POST |
| URI | `https://lang-learnflow-classifier.cognitiveservices.azure.com/language/:analyze-text?api-version=2023-04-01` |
| Headers | `Ocp-Apim-Subscription-Key`: `YOUR_KEY` <br> `Content-Type`: `application/json` |
| Body | See JSON below |

**Power Automate Body (with dynamic content):**
```json
{
  "kind": "CustomSingleLabelClassification",
  "analysisInput": {
    "documents": [
      {
        "id": "1",
        "language": "en",
        "text": "@{triggerBody()?['userMessage']}"
      }
    ]
  },
  "parameters": {
    "projectName": "LearnFlowQueryClassifier",
    "deploymentName": "production"
  }
}
```

**Parse Response:**
Use "Parse JSON" action to extract:
- `body('HTTP')?['results']?['documents']?[0]?['classifications']?[0]?['category']`
- `body('HTTP')?['results']?['documents']?[0]?['classifications']?[0]?['confidenceScore']`

---

### Python SDK Example

```python
from azure.ai.textanalytics import TextAnalyticsClient
from azure.core.credentials import AzureKeyCredential

endpoint = "https://lang-learnflow-classifier.cognitiveservices.azure.com/"
key = "YOUR_API_KEY_HERE"
project_name = "LearnFlowQueryClassifier"
deployment_name = "production"

# Authenticate
client = TextAnalyticsClient(endpoint=endpoint, credential=AzureKeyCredential(key))

# Classify single document
documents = ["How do I complete my annual ethics training?"]

poller = client.begin_single_label_classify(
    documents,
    project_name=project_name,
    deployment_name=deployment_name
)

result = poller.result()
for doc, classification_result in zip(documents, result):
    if classification_result.kind == "CustomDocumentClassification":
        for classification in classification_result.classifications:
            print(f"Text: {doc}")
            print(f"Category: {classification.category}")
            print(f"Confidence: {classification.confidence_score:.2%}")
```

**Install SDK:**
```bash
pip install azure-ai-textanalytics==5.3.0
```

---

## Cost Estimation

| Resource | Pricing (East US) |
|----------|-------------------|
| Language Service (S tier) | $2.00 per 1,000 text records |
| Storage Account | ~$0.02/GB/month |
| Training | Included in tier |
| Deployment | $0.05/hour per model deployment |

**Estimated Monthly Cost:** $50-100 for moderate usage

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| "Custom classification not available" | Ensure S tier and supported region (East US, West US 2) |
| Training fails | Check CSV encoding (UTF-8), verify no empty rows |
| Low accuracy | Add more examples, check for label errors, balance classes |
| API returns 401 | Verify API key is correct and active |
| API returns 404 | Check endpoint URL, project name, deployment name |

---

## Quick Reference

| Item | Value |
|------|-------|
| Language Studio | [language.cognitive.azure.com](https://language.cognitive.azure.com) |
| API Version | 2023-04-01 |
| Project Name | LearnFlowQueryClassifier |
| Deployment Name | production |
| Model | model-v1 |
| Classes | 6 (single-label) |
| Training Examples | 130 |
| Test Examples | 20 |

---

*Document generated for LearnFlow Assistant - Azure Custom Text Classification Project*
