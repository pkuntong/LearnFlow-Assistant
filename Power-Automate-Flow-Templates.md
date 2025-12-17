# Power Automate Flow Templates - LearnFlow Assistant

This document provides detailed Power Automate flow templates for integrating LearnFlow Assistant with Dataverse and other Microsoft 365 services.

---

## 📋 Table of Contents
1. [Template 1: Save Conversation to Dataverse](#template-1-save-conversation-to-dataverse)
2. [Template 2: Email Notification for High-Priority Inquiries](#template-2-email-notification-for-high-priority-inquiries)
3. [Template 3: Log Compliance Training Inquiries to SharePoint](#template-3-log-compliance-training-inquiries-to-sharepoint)
4. [Template 4: Create Support Ticket for Escalations](#template-4-create-support-ticket-for-escalations)
5. [Template 5: Send Teams Message to Manager](#template-5-send-teams-message-to-manager)
6. [Template 6: Update User Training Status](#template-6-update-user-training-status)

---

## Template 1: Save Conversation to Dataverse

**Purpose**: Log every user interaction with LearnFlow Assistant to Dataverse for analytics, compliance, and audit trails.

### Prerequisites
- Dataverse environment set up
- Table created in Dataverse (see schema below)
- Copilot Studio copilot created

### Dataverse Table Schema

**Table Name**: `LearnFlow Conversations`

| Column Name | Data Type | Max Length | Required | Description |
|-------------|-----------|------------|----------|-------------|
| Name | Text | 100 | Yes | Auto-generated record name |
| Conversation ID | Text | 100 | Yes | Unique conversation identifier |
| User Message | Multiline Text | 5000 | Yes | User's question/message |
| Bot Response | Multiline Text | 5000 | No | Bot's response (optional) |
| User Email | Email | 100 | Yes | User's email address |
| User ID | Text | 100 | Yes | Azure AD user ID |
| Topic Name | Text | 200 | No | Topic that was triggered |
| Timestamp | Date and Time | - | Yes | When message was sent |
| Session Duration | Whole Number | - | No | Length of conversation (seconds) |
| Sentiment | Choice | - | No | Positive/Neutral/Negative |
| Was Escalated | Yes/No | - | No | Whether conversation was escalated |
| Environment | Text | 50 | No | Dev/Test/Prod |

### Power Automate Flow Steps

#### Step 1: Create New Flow
1. Go to [Power Automate](https://make.powerautomate.com)
2. Click **+ Create** → **Automated cloud flow**
3. Name: `LearnFlow - Save to Dataverse`
4. Search for trigger: **Microsoft Copilot Studio**
5. Select trigger: **When Copilot Studio calls a flow**
6. Click **Create**

#### Step 2: Configure Input Parameters
Add the following input parameters to the trigger:

```
Input Parameters:
┌─────────────────────────────────────────┐
│ Name: UserMessage                       │
│ Type: Text                              │
│ Description: The user's message         │
│ Required: Yes                           │
└─────────────────────────────────────────┘

┌─────────────────────────────────────────┐
│ Name: ConversationID                    │
│ Type: Text                              │
│ Description: Unique conversation ID     │
│ Required: Yes                           │
└─────────────────────────────────────────┘

┌─────────────────────────────────────────┐
│ Name: UserEmail                         │
│ Type: Text                              │
│ Description: User's email address       │
│ Required: Yes                           │
└─────────────────────────────────────────┘

┌─────────────────────────────────────────┐
│ Name: UserID                            │
│ Type: Text                              │
│ Description: Azure AD User ID           │
│ Required: Yes                           │
└─────────────────────────────────────────┘

┌─────────────────────────────────────────┐
│ Name: TopicName                         │
│ Type: Text                              │
│ Description: Topic that was triggered   │
│ Required: No                            │
└─────────────────────────────────────────┘

┌─────────────────────────────────────────┐
│ Name: BotResponse                       │
│ Type: Text                              │
│ Description: Bot's response (optional)  │
│ Required: No                            │
└─────────────────────────────────────────┘
```

#### Step 3: Add Dataverse Action
1. Click **+ New step**
2. Search for **Dataverse**
3. Select action: **Add a new row**
4. Configure:
   - **Environment**: Select your environment
   - **Table name**: `LearnFlow Conversations`

#### Step 4: Map Fields
Map the Dataverse fields to flow inputs:

```
Field Mappings:
├─ Name: ConversationID + "-" + formatDateTime(utcNow(), 'yyyyMMddHHmmss')
├─ Conversation ID: ConversationID (from trigger)
├─ User Message: UserMessage (from trigger)
├─ Bot Response: BotResponse (from trigger)
├─ User Email: UserEmail (from trigger)
├─ User ID: UserID (from trigger)
├─ Topic Name: TopicName (from trigger)
├─ Timestamp: utcNow()
├─ Environment: "Production"
└─ Was Escalated: No (default)
```

#### Step 5: Add Error Handling (Optional)
1. Click **+ New step**
2. Add **Condition** action
3. Configure:
   - **If yes**: Continue with success response
   - **If no**: Send email notification of failure

#### Step 6: Return Value to Copilot
1. Click **+ New step**
2. Search for **Respond to Copilot Studio**
3. Add output parameter:
   ```
   Name: SavedSuccessfully
   Type: Boolean
   Value: true
   ```

#### Step 7: Save and Test
1. Click **Save**
2. Click **Test** → **Manually**
3. Trigger from Copilot Studio
4. Verify row created in Dataverse

### Flow JSON (Import Ready)

```json
{
  "name": "LearnFlow - Save to Dataverse",
  "definition": {
    "triggers": {
      "manual": {
        "type": "Request",
        "kind": "PowerVirtualAgents",
        "inputs": {
          "schema": {
            "type": "object",
            "properties": {
              "UserMessage": {"type": "string"},
              "ConversationID": {"type": "string"},
              "UserEmail": {"type": "string"},
              "UserID": {"type": "string"},
              "TopicName": {"type": "string"},
              "BotResponse": {"type": "string"}
            },
            "required": ["UserMessage", "ConversationID", "UserEmail", "UserID"]
          }
        }
      }
    },
    "actions": {
      "Add_a_new_row": {
        "type": "OpenApiConnection",
        "inputs": {
          "host": {
            "connectionName": "shared_commondataserviceforapps",
            "operationId": "CreateRecord",
            "apiId": "/providers/Microsoft.PowerApps/apis/shared_commondataserviceforapps"
          },
          "parameters": {
            "entityName": "cr6b3_learnflowconversations",
            "item/cr6b3_conversationid": "@triggerBody()['UserMessage_Value']",
            "item/cr6b3_usermessage": "@triggerBody()['UserMessage']",
            "item/cr6b3_botresponse": "@triggerBody()['BotResponse']",
            "item/cr6b3_useremail": "@triggerBody()['UserEmail']",
            "item/cr6b3_userid": "@triggerBody()['UserID']",
            "item/cr6b3_topicname": "@triggerBody()['TopicName']",
            "item/cr6b3_timestamp": "@utcNow()"
          }
        }
      },
      "Respond_to_PowerVirtualAgents": {
        "type": "Response",
        "kind": "PowerVirtualAgents",
        "inputs": {
          "statusCode": 200,
          "body": {
            "SavedSuccessfully": true
          },
          "schema": {
            "type": "object",
            "properties": {
              "SavedSuccessfully": {"type": "boolean"}
            }
          }
        }
      }
    }
  }
}
```

### Using in Copilot Studio

1. Open your topic in Copilot Studio
2. Add node: **Call an action**
3. Select: **LearnFlow - Save to Dataverse**
4. Map inputs:
   ```
   UserMessage: Activity.Text
   ConversationID: System.Conversation.Id
   UserEmail: System.User.Email (if authenticated)
   UserID: System.User.Id
   TopicName: System.Topic.Name
   BotResponse: (leave empty or add variable)
   ```
5. Save topic

---

## Template 2: Email Notification for High-Priority Inquiries

**Purpose**: Send email alert to L&D team when urgent training questions are asked.

### Flow Steps

#### 1. Trigger: When Copilot Studio calls a flow
Input parameters:
- `UserMessage` (Text)
- `UserEmail` (Text)
- `IsUrgent` (Boolean)
- `TopicName` (Text)

#### 2. Condition: Check if urgent
```
Condition: IsUrgent equals true
```

#### 3. Action (If yes): Send email
```
To: learning-development@company.com
Subject: Urgent LearnFlow Inquiry - [TopicName]
Body:
A user has submitted an urgent inquiry through LearnFlow Assistant.

User: [UserEmail]
Topic: [TopicName]
Message: [UserMessage]
Time: [Current timestamp]

Please review and respond as needed.

View in Dataverse: [Link to record]
```

#### 4. Return to Copilot
```
Output: EmailSent (Boolean): true
```

---

## Template 3: Log Compliance Training Inquiries to SharePoint

**Purpose**: Track all compliance-related questions in a SharePoint list for audit purposes.

### SharePoint List Schema

**List Name**: `Compliance Training Inquiries`

| Column | Type | Required |
|--------|------|----------|
| Title | Single line text | Yes |
| User Email | Single line text | Yes |
| Question | Multiple lines text | Yes |
| Date Asked | Date and time | Yes |
| Topic | Choice (Ethics, Privacy, Security, Other) | Yes |
| Response Provided | Multiple lines text | No |
| Follow-up Required | Yes/No | No |
| Status | Choice (New, Reviewed, Closed) | Yes |

### Flow Steps

#### 1. Trigger: When Copilot Studio calls a flow
Inputs: UserMessage, UserEmail, TopicName

#### 2. Condition: Check if compliance topic
```
TopicName contains "Compliance" OR
TopicName contains "Ethics" OR
TopicName contains "Training"
```

#### 3. Action: Create item in SharePoint
```
Site Address: https://yourcompany.sharepoint.com/sites/LearningDev
List Name: Compliance Training Inquiries

Field mappings:
├─ Title: "Inquiry from " + UserEmail
├─ User Email: UserEmail
├─ Question: UserMessage
├─ Date Asked: utcNow()
├─ Topic: [Extract from TopicName]
├─ Status: "New"
└─ Follow-up Required: No
```

#### 4. Return to Copilot
```
Output: LoggedToSharePoint (Boolean): true
Output: ItemID (Number): [SharePoint item ID]
```

---

## Template 4: Create Support Ticket for Escalations

**Purpose**: Automatically create IT support ticket when technical issues are escalated.

### Flow Steps

#### 1. Trigger: When Copilot Studio calls a flow
Inputs:
- `UserEmail` (Text)
- `UserName` (Text)
- `IssueDescription` (Text)
- `IssueCategory` (Text) - Teams, Outlook, etc.
- `Priority` (Text) - Low, Medium, High

#### 2. Action: Send HTTP request to ticketing system
```
Method: POST
URI: https://yourcompany.service-now.com/api/now/table/incident
Headers:
├─ Content-Type: application/json
└─ Authorization: Basic [encoded credentials]

Body:
{
  "short_description": "LearnFlow Escalation - [IssueCategory]",
  "description": "[IssueDescription]\n\nReported by: [UserName] ([UserEmail])\nSource: LearnFlow Assistant",
  "caller_id": "[UserEmail]",
  "urgency": "[Priority]",
  "category": "Technical Support",
  "subcategory": "[IssueCategory]",
  "assignment_group": "IT Support"
}
```

#### 3. Parse JSON response
```
Schema:
{
  "result": {
    "sys_id": "string",
    "number": "string"
  }
}
```

#### 4. Send confirmation email to user
```
To: [UserEmail]
Subject: Support Ticket Created - [TicketNumber]
Body:
Hi [UserName],

Your technical support request has been submitted.

Ticket Number: [TicketNumber]
Issue: [IssueCategory]
Priority: [Priority]

Our IT team will respond within [SLA timeframe].

You can track your ticket at: [Ticket URL]

Thank you,
LearnFlow Assistant
```

#### 5. Return to Copilot
```
Output: TicketCreated (Boolean): true
Output: TicketNumber (Text): [Ticket number]
Output: TicketURL (Text): [Direct link to ticket]
```

---

## Template 5: Send Teams Message to Manager

**Purpose**: Notify manager when employee asks about promotion or career development.

### Flow Steps

#### 1. Trigger: When Copilot Studio calls a flow
Inputs:
- `UserEmail` (Text)
- `UserName` (Text)
- `TopicName` (Text)
- `Question` (Text)

#### 2. Get user's manager (Azure AD)
```
Action: Get manager (V2)
User (UPN): [UserEmail]
```

#### 3. Condition: Manager exists
```
If manager email is not empty
```

#### 4. Action: Post adaptive card in Teams
```
Recipient: [Manager email]
Message:

{
  "type": "AdaptiveCard",
  "body": [
    {
      "type": "TextBlock",
      "text": "Career Development Inquiry",
      "weight": "Bolder",
      "size": "Large"
    },
    {
      "type": "TextBlock",
      "text": "[UserName] has inquired about career development through LearnFlow Assistant.",
      "wrap": true
    },
    {
      "type": "FactSet",
      "facts": [
        {
          "title": "Employee:",
          "value": "[UserName]"
        },
        {
          "title": "Topic:",
          "value": "[TopicName]"
        },
        {
          "title": "Date:",
          "value": "[Current date]"
        }
      ]
    },
    {
      "type": "TextBlock",
      "text": "Question:",
      "weight": "Bolder"
    },
    {
      "type": "TextBlock",
      "text": "[Question]",
      "wrap": true
    }
  ],
  "actions": [
    {
      "type": "Action.OpenUrl",
      "title": "Schedule 1:1",
      "url": "https://outlook.office.com/calendar"
    }
  ],
  "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
  "version": "1.4"
}
```

#### 5. Return to Copilot
```
Output: ManagerNotified (Boolean): true
```

---

## Template 6: Update User Training Status

**Purpose**: Mark training as completed in HR system when user confirms completion through chatbot.

### Flow Steps

#### 1. Trigger: When Copilot Studio calls a flow
Inputs:
- `UserEmail` (Text)
- `TrainingName` (Text)
- `CompletionDate` (Text)
- `CertificationNumber` (Text)

#### 2. Update Dataverse table
```
Action: Update a row
Table: Employee Training Records
Row ID: [Lookup by UserEmail]

Fields:
├─ Training Name: [TrainingName]
├─ Completion Date: [CompletionDate]
├─ Status: "Completed"
├─ Certification Number: [CertificationNumber]
└─ Last Updated: utcNow()
```

#### 3. Send confirmation email
```
To: [UserEmail]
Subject: Training Completion Confirmed - [TrainingName]
Body:
Congratulations! Your completion of [TrainingName] has been recorded.

Completion Date: [CompletionDate]
Certificate Number: [CertificationNumber]

Your training transcript has been updated.
View your records: [Portal URL]

Thank you for staying compliant!
LearnFlow Assistant
```

#### 4. Return to Copilot
```
Output: StatusUpdated (Boolean): true
Output: ConfirmationMessage (Text): "Your training completion has been recorded!"
```

---

## 🔧 Flow Configuration Best Practices

### Security
- Use service accounts with minimum required permissions
- Store credentials in Azure Key Vault
- Enable flow connection security
- Audit flow run history regularly

### Error Handling
Always add **Configure run after** settings:
```
├─ Has failed → Send error notification
├─ Is skipped → Log skip reason
└─ Has timed out → Retry action
```

### Performance
- Use parallel branches for independent actions
- Limit loop iterations
- Use filters in Dataverse queries
- Cache frequently accessed data

### Monitoring
- Enable flow analytics
- Set up alerts for failures
- Review run history weekly
- Track average execution time

---

## 📊 Testing Flows

### Unit Testing
1. Use **Test** button in Power Automate
2. Provide sample input data
3. Verify each action executes correctly
4. Check output values

### Integration Testing
1. Call flow from Copilot Studio test panel
2. Verify end-to-end functionality
3. Check Dataverse/SharePoint records created
4. Confirm emails/notifications sent

### Load Testing
1. Simulate multiple concurrent users
2. Monitor flow throttling limits
3. Check for performance degradation
4. Verify no data loss

---

## 🚨 Troubleshooting Common Issues

| Issue | Cause | Solution |
|-------|-------|----------|
| Flow not triggering | Connection broken | Reconnect Copilot Studio |
| Dataverse insert fails | Missing required fields | Check field mappings |
| Email not sending | Invalid recipient | Verify email address |
| Timeout errors | Flow too complex | Split into multiple flows |
| Permission denied | Insufficient privileges | Grant app permissions |
| Null reference error | Optional input not provided | Add null checks |

---

## 📚 Additional Resources

- [Power Automate Documentation](https://learn.microsoft.com/power-automate/)
- [Copilot Studio Flow Integration](https://learn.microsoft.com/microsoft-copilot-studio/advanced-flow)
- [Dataverse REST API](https://learn.microsoft.com/power-apps/developer/data-platform/webapi/overview)
- [Adaptive Cards Designer](https://adaptivecards.io/designer/)

---

*Last Updated: December 2025*
*Version: 1.0*
