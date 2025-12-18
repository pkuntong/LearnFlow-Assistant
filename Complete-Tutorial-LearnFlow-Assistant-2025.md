# Complete Tutorial: Building LearnFlow Assistant in Microsoft Copilot Studio (Late 2025)

## 🎯 What You'll Build

**LearnFlow Assistant** - An AI-powered copilot for federal employees and learners that helps with:
- Compliance and ethics training
- Career development guidance
- Performance management
- Learning platform access
- Technical tool support

**Time to Complete**: 60-90 minutes
**Experience Level**: Beginner-friendly
**Prerequisites**: Microsoft 365 account with Copilot Studio access

---

## 📚 Table of Contents

1. [Getting Started](#step-1-getting-started)
2. [Creating Your Agent](#step-2-creating-your-agent-from-scratch)
3. [Configuring the Greeting](#step-3-configuring-the-greeting-and-suggested-prompts)
4. [Creating Managed Topics](#step-4-creating-managed-topics)
   - [Topic 1: Compliance & Ethics Training](#topic-1-compliance--ethics-training)
   - [Topic 2: Learning Platforms & Access](#topic-2-learning-platforms--access)
   - [Topic 3: Career Development](#topic-3-career-development)
   - [Topic 4: Performance Management](#topic-4-performance-management)
   - [Topic 5: Technical Tools Support](#topic-5-technical-tools-support)
5. [Creating the Fallback Topic](#step-5-creating-the-fallback-topic)
6. [Adding Message Capture Action](#step-6-adding-message-capture-action)
7. [Testing Your Agent](#step-7-testing-your-agent)
8. [Publishing to Demo Channel](#step-8-publishing-to-demo-channel)
9. [Exporting for Your Portfolio](#step-9-exporting-for-your-portfolio)
10. [Federal-Specific Tips](#federal-specific-tips-and-best-practices)

---

## Step 1: Getting Started

### 1.1 Access Microsoft Copilot Studio

1. Open your web browser (Chrome, Edge, or Firefox recommended)
2. Navigate to: **https://copilotstudio.microsoft.com**
3. Sign in with your Microsoft 365 credentials
   - **Screenshot description**: *You'll see a login page with the Microsoft logo and "Sign in to Copilot Studio" header*

4. If prompted, select your organization (e.g., your federal agency)
5. Accept any terms of service if this is your first time

### 1.2 Select Your Environment

**What you'll see**: At the top-right of the page, you'll see an environment selector dropdown

1. Click the **environment dropdown** (looks like a folder icon with text)
   - **Screenshot description**: *Top-right corner, shows something like "Contoso (default)" or your agency name*
2. If you have multiple environments, select the one where you want to build
   - **Federal Tip**: Use a development or sandbox environment first, not production
3. For most users, the **default environment** is fine for learning

### 1.3 Familiarize Yourself with the Interface

**What you'll see**: The Copilot Studio home page with several sections:

- **Left Navigation Panel**:
  - Home (house icon)
  - Agents (robot icon)
  - Library (book icon)
  - Analytics
  - Settings

- **Center Area**:
  - "Create an agent" card
  - Recent agents (if any)
  - Templates and samples

- **Top Bar**:
  - Search
  - Help (? icon)
  - Settings (gear icon)
  - Your profile picture

---

## Step 2: Creating Your Agent from Scratch

### 2.1 Start Agent Creation

1. On the home page, locate the large **"+ Create"** button or **"+ New agent"** button
   - **Screenshot description**: *Usually in the top-left or center of the page, a prominent purple or blue button*
2. Click **"+ Create"** or **"+ New agent"**

3. You'll see creation options:
   - **"Create from description"** - Quick AI-powered creation (we'll use this)
   - **"Start with a template"** - Pre-built scenarios
   - **"Start from blank"** - Manual setup

4. Select **"Create from description"** (or if the interface shows "Describe your copilot", click that)

### 2.2 Describe Your Agent

**What you'll see**: A text box asking "What do you want your agent to do?"

1. In the description box, type EXACTLY:
   ```
   I'm an AI assistant that helps federal employees and learners with compliance training, career development, performance reviews, and tool access.
   ```

2. **Screenshot description**: *A large text input box with placeholder text "Describe what you want your agent to do..." and a character counter below*

3. Click **"Create"** or **"Next"** button

### 2.3 Configure Agent Details

**What you'll see**: A form with several fields to fill out

Fill in the following:

**Agent Name** (Required):
```
LearnFlow Assistant
```

**Description** (Optional but recommended):
```
AI-powered workforce learning and compliance training assistant for federal employees
```

**Instructions** (This tells the AI how to behave):
```
You are LearnFlow Assistant, a helpful and professional AI assistant supporting federal employees with:

- Compliance and ethics training requirements
- Career development and promotion pathways
- Performance review processes and timelines
- Learning platform access and technical support
- Federal workplace policies and procedures

Always:
- Be professional, clear, and encouraging
- Provide specific, actionable guidance
- Reference official policies when applicable
- Respect privacy and data sensitivity
- Escalate complex HR or legal matters appropriately

When discussing federal regulations or policies, remind users to verify information with their HR representative or supervisor for their specific agency.
```

**Screenshot description**: *Form with three text fields - "Name" (single line), "Description" (single line), and "Instructions" (large multiline box)*

**Language**:
- Select **"English"**

**Icon/Avatar** (Optional):
- Click **"Upload image"** or choose from defaults
- For LearnFlow, consider selecting a book, graduation cap, or lightbulb icon
- Recommended: Leave as default for now, customize later

4. Click **"Create"** at the bottom

### 2.4 Wait for Agent Creation

**What you'll see**:
- A loading screen with text like "Creating your agent..."
- An animation or progress indicator
- This takes 10-30 seconds

**Screenshot description**: *Loading spinner with text "Setting up LearnFlow Assistant" and a purple/blue animated background*

### 2.5 Agent Created - Overview Page

**What you'll see**: Your agent's main workspace with:

- **Top navigation tabs**:
  - Overview (you're here)
  - Topics
  - Entities
  - Analytics
  - Publish
  - Settings

- **Left side**:
  - Agent name "LearnFlow Assistant"
  - Test your agent panel (minimized or on right side)

- **Center area**:
  - Quick actions cards
  - Suggested next steps
  - Agent description

**Screenshot description**: *Clean interface with "LearnFlow Assistant" in the top-left, tabs across the top, and a "Test your agent" chat panel on the right side*

5. Click **"Topics"** tab in the top navigation to begin customization

---

## Step 3: Configuring the Greeting and Suggested Prompts

### 3.1 Navigate to System Topics

1. Click the **"Topics"** tab at the top
2. You'll see a list of topics divided into:
   - **Your topics** (custom topics you create)
   - **System topics** (pre-built by Copilot Studio)

**Screenshot description**: *Two-column layout - left sidebar shows topic list, right shows topic canvas*

3. In the topic list, find the **"System"** section (may need to scroll down)
4. Look for and click on **"Greeting"** topic
   - **Screenshot description**: *System topics have a small system icon next to them; Greeting is usually the first one*

### 3.2 Edit the Greeting Message

**What you'll see**: The topic authoring canvas with nodes connected by lines

1. You'll see the trigger node at the top: **"Greeting"**
2. Below it, a **Message node** with default greeting text

**Screenshot description**: *Flow-chart style canvas with rounded rectangle boxes connected by arrows*

3. Click on the **Message node** (the box with the greeting text)
4. The right panel opens with message editor

5. **Delete** the existing greeting text

6. **Paste this new greeting**:
   ```
   👋 Hello! I'm **LearnFlow Assistant**, your AI guide for workforce learning and development.

   I can help federal employees and learners with:

   ✅ **Compliance & Ethics Training** - Requirements, deadlines, and completion
   ✅ **Learning Platform Access** - How to log in and navigate systems
   ✅ **Career Development** - Promotion paths and skill building
   ✅ **Performance Reviews** - Process, timelines, and preparation
   ✅ **Technical Support** - M365, tools, and software help

   What would you like assistance with today?
   ```

**Screenshot description**: *Right panel shows rich text editor with formatting toolbar (bold, italic, lists) and preview of the message*

**Formatting Tips**:
- Use **bold** for emphasis (select text, click **B** button)
- Use bullet points for lists (click bullet list icon)
- Emojis are optional - you can remove them if too informal for your agency

7. Click **"Save"** in the top-right corner (floppy disk icon or "Save" button)

### 3.3 Add Suggested User Prompts (Conversation Starters)

These are clickable buttons users see to start conversations quickly.

1. While still in the Greeting topic, scroll down below the message node
2. Look for **"Add node"** button (+ icon in a circle)
3. Click **"+ Add node"**
4. Select **"Ask with adaptive card"** or look for **"Show conversation starters"**

**Note**: The interface may have changed in late 2025. If you don't see "conversation starters" in the Greeting topic:

**Alternative Method**:
1. Go to **Settings** (gear icon in top-right)
2. Find **"Conversation start"** or **"Customer engagement"** section
3. Look for **"Suggested prompts"** or **"Conversation starters"**

### 3.4 Configure 6 Suggested Prompts

Add these 6 conversation starters (exact text):

**Starter 1**:
```
How do I complete ethics training?
```

**Starter 2**:
```
What's the performance review process?
```

**Starter 3**:
```
How can I access the learning portal?
```

**Starter 4**:
```
Tell me about career advancement
```

**Starter 5**:
```
I need help with Microsoft Teams
```

**Starter 6**:
```
What are my training requirements?
```

**Screenshot description**: *Settings panel showing 6 text input boxes labeled "Suggested prompt 1" through "Suggested prompt 6"*

**How to add them**:
1. If in Settings → Find **"Add suggested prompts"** section
2. Click **"+ Add prompt"** for each one
3. Type or paste the text
4. Each prompt gets its own row with a text field

4. Click **"Save"** when done

### 3.5 Verify Your Greeting

1. Go back to **Topics** tab
2. Open the **Greeting** topic again
3. Verify your custom message appears in the message node
4. **Test it**: Open the **"Test your agent"** panel on the right
   - Type "hi" or "hello"
   - Your greeting should appear with the suggested prompts below

**Screenshot description**: *Test panel shows chat interface with your greeting message and 6 blue clickable prompt buttons*

---

## Step 4: Creating Managed Topics

Now we'll create 5 custom topics that handle specific user requests using AI-powered generative answers.

### What Are Managed Topics?

- **Topics** = Conversation pathways triggered by user phrases
- **Generative answers** = AI responses using your knowledge sources
- Each topic handles a specific category of questions

---

## Topic 1: Compliance & Ethics Training

### 4.1 Create New Topic

1. Click **"Topics"** tab
2. Click **"+ Add a topic"** or **"+ New topic"** button (top of topic list)
   - **Screenshot description**: *Purple "+ Add a topic" button at top of left sidebar*

3. Select **"From blank"** (to create manually)
   - Alternative: "Create with Copilot" if you want AI assistance

### 4.2 Name and Describe the Topic

**What you'll see**: Topic properties panel on the right

**Name** (top of the page or right panel):
```
Compliance & Ethics Training
```

**Description** (optional):
```
Helps users with federal compliance training requirements, ethics certification, and mandatory annual training
```

**Screenshot description**: *Topic name appears at top like a page title, with pencil icon to edit*

### 4.3 Add Trigger Phrases

Trigger phrases tell the agent when to activate this topic.

1. In the topic canvas, you'll see a **Trigger node** at the top
2. Click on the **Trigger node**
3. Right panel shows **"Add phrases"** section

**What you'll see**: Text box with "+ Add phrase" button

4. Add these trigger phrases (click "+ Add" after each one):

```
compliance training
ethics training
annual training requirements
mandatory training
required training courses
ethics certification
training deadlines
what training do i need
complete compliance course
federal ethics requirements
```

**Screenshot description**: *Right panel shows list of trigger phrases, each on its own row with an X button to delete*

**Federal Tip**: Include agency-specific terms like "OGE training" (Office of Government Ethics), "annual ethics briefing", or "Standards of Conduct"

### 4.4 Add Generative Answers Node

Now we'll add AI-powered responses.

1. In the topic canvas, click **"+ Add node"** below the trigger
   - **Screenshot description**: *Purple circular button with + symbol between nodes*

2. A menu appears with options:
   - Send a message
   - Ask a question
   - Add a condition
   - **Call an action**
   - **Create generative answers** ← Select this

3. Click **"Create generative answers"**

**Screenshot description**: *Node menu shows icons and labels for different node types; "Create generative answers" has a sparkle/star icon*

### 4.5 Configure Generative Answers

**What you'll see**: A new purple/blue node labeled "Create generative answers" with configuration panel on right

**Configure these settings**:

**Input (Required)**:
- This is what the AI will respond to
- Click the **Input** field
- Select **"System.Activity.Text"** from the dropdown
  - This captures the user's full message

**Screenshot description**: *Dropdown menu showing system variables like Activity.Text, User.DisplayName, Conversation.Id*

**Data source** (Where AI gets knowledge):

You have several options for late 2025 Copilot Studio:

**Option A - No data source** (Uses general AI knowledge):
- Leave data sources empty for now
- The AI will use its training data about federal compliance

**Option B - Add knowledge** (Recommended for accuracy):
1. Click **"+ Add knowledge"** or **"Edit sources"**
2. You'll see options:
   - **Upload files** (PDFs, Word docs, PowerPoint)
   - **Public websites**
   - **SharePoint** (if connected)
   - **Dataverse** (if available)

**For federal compliance topic, you could**:
- Upload your agency's annual ethics training guide (PDF)
- Add URL: `https://www.oge.gov/` (Office of Government Ethics)
- Upload compliance training slides

**Screenshot description**: *Data sources panel shows "+ Add source" button and file upload area with drag-and-drop zone*

3. If adding a public website:
   - Click **"Public websites"**
   - Paste URL: `https://www.oge.gov/web/oge.nsf/Resources`
   - Click **"Add"**

4. If uploading files:
   - Click **"Upload files"**
   - Select your PDF/Word document
   - Click **"Upload"**
   - Wait for processing (10-30 seconds)

**Content moderation**:
- Scroll down in the configuration panel
- Set to **"Medium"** or **"Strict"** for federal context
- This prevents inappropriate responses

**Additional instructions** (Optional but recommended):

Click **"Edit"** next to "How should your agent respond?"

Add custom instructions:
```
Provide accurate, official information about federal compliance and ethics training. Include:
- Training requirements and deadlines
- How to access courses
- Completion requirements
- Who to contact for questions

Remind users to verify information with their agency's ethics office or HR department.
```

**Screenshot description**: *Text box labeled "Instructions" with example text and "Add instruction" button*

### 4.6 Add Follow-up Message (Optional)

1. Below the generative answers node, click **"+ Add node"**
2. Select **"Send a message"**
3. Type:
   ```
   Was this helpful? Let me know if you need additional support with your training requirements.
   ```

### 4.7 Save the Topic

1. Click **"Save"** button (top-right corner)
2. Wait for "Saved successfully" confirmation

**Screenshot description**: *Green checkmark notification appears top-right saying "Topic saved"*

---

## Topic 2: Learning Platforms & Access

### 4.8 Create Second Topic

1. Click **"+ Add a topic"** → **"From blank"**

**Name**:
```
Learning Platforms & Access
```

**Trigger phrases**:
```
how to access learning portal
login to training system
LMS access
learning management system
learning portal login
where is the learning platform
how do i access courses
training website link
cant log into learning portal
forgot lms password
```

### 4.9 Add Information Message Node

Since this topic is about specific system access, we'll use a regular message instead of generative answers.

1. Click **"+ Add node"** below trigger
2. Select **"Send a message"**
3. Add this content (customize for your agency):

```
🌐 **Learning Platform Access**

**Primary Learning Portal:**
📍 **URL**: [Your LMS URL - e.g., agency.learn.gov]
🔑 **Login**: Use your federal PIV card or agency credentials
👤 **Username**: Your employee ID or email

**First-Time Users:**
1. Visit the portal URL above
2. Click "First Time Login" or "Register"
3. Use your PIV card or follow email instructions
4. Create security questions

**Additional Learning Platforms:**
• **OPM Training**: https://www.opm.gov/training
• **LinkedIn Learning**: Access through your agency portal
• **AgencyLearn**: [Internal system URL]

**Need Help?**
📞 IT Help Desk: [phone number]
📧 Email: learning.support@agency.gov
💬 Submit ticket: [Support portal URL]
```

**Federal Tip**: Replace bracketed items with your actual agency information.

4. Click **"+ Add node"** again
5. Add **"Create generative answers"** for follow-up questions
6. Configure:
   - **Input**: System.Activity.Text
   - **Instructions**: "Help users with specific questions about navigating learning portals, troubleshooting access, finding courses, or understanding platform features."

7. **Save** the topic

---

## Topic 3: Career Development

### 4.10 Create Third Topic

**Name**:
```
Career Development
```

**Trigger phrases**:
```
career development
promotion opportunities
career path
how to get promoted
career advancement
professional growth
career ladder
job progression
how do i move up
promotion criteria
career goals
advancement in government
federal career path
```

### 4.11 Add Personalization Question (Optional)

1. Click **"+ Add node"** below trigger
2. Select **"Ask a question"**
3. Configure:

**Question text**:
```
What's your current GS level or position? (This helps me provide relevant guidance)
```

**Identify**: Select **"User's entire response"**

**Save response as**: Create variable named `UserGSLevel`

**Screenshot description**: *Question node configuration panel with "Identify" dropdown showing options like "Multiple choice", "User's entire response", "Number", etc.*

### 4.12 Add Generative Answers for Career Guidance

1. Click **"+ Add node"**
2. Select **"Create generative answers"**
3. Configure:

**Input**:
- Use the **formula editor** (fx icon)
- Enter: `Topic.UserGSLevel & " - " & System.Activity.Text`
- This combines their GS level with their question

**Screenshot description**: *Input field with "fx" icon; clicking opens formula editor with autocomplete for variables*

**Data sources** (Recommended):
- Upload: Federal career ladder documents
- Upload: OPM position classification standards
- Add URL: `https://www.opm.gov/policy-data-oversight/classification-qualifications/`

**Instructions**:
```
Provide guidance on federal career development and advancement. Include:

- General Schedule (GS) promotion requirements and timelines
- Time-in-grade requirements for federal positions
- Skills and qualifications needed for advancement
- Training and development opportunities
- How to prepare for promotion panels
- Individual Development Plan (IDP) guidance

Encourage employees to:
- Discuss career goals with their supervisor
- Complete an IDP annually
- Take advantage of training opportunities
- Consider details and rotational assignments

Remind them that specific promotion criteria vary by agency and position.
```

4. **Save** the topic

---

## Topic 4: Performance Management

### 4.13 Create Fourth Topic

**Name**:
```
Performance Management
```

**Trigger phrases**:
```
performance review
annual review
performance evaluation
review process
how to prepare for review
self-assessment
performance feedback
review timeline
evaluation criteria
performance appraisal
midyear review
performance plan
rating criteria
```

### 4.14 Add Conditional Branch for Employees vs. Supervisors

1. Click **"+ Add node"**
2. Select **"Ask a question"**

**Question**:
```
Are you preparing for your own performance review, or are you a supervisor conducting reviews?
```

**Identify**: **Multiple choice options**

**Options**:
- `Employee - Preparing for my own review`
- `Supervisor - Conducting employee reviews`

**Save response as**: `ReviewRole`

**Screenshot description**: *Multiple choice configuration shows two option fields with radio buttons and "Add option" button*

### 4.15 Add Condition to Branch

1. Click **"+ Add node"**
2. Select **"Add a condition"**
3. Configure condition:
   - **Variable**: `Topic.ReviewRole`
   - **Operator**: `is equal to`
   - **Value**: `Employee - Preparing for my own review`

**Screenshot description**: *Condition node creates two branches - green "If yes" path and red "If no" path*

### 4.16 Add Generative Answers for Each Branch

**For "If yes" (Employee) branch**:
1. Click **"+ Add node"** under the green "Yes" path
2. Add **"Create generative answers"**
3. Instructions:
```
Help federal employees prepare for performance reviews:

- Explain the federal performance appraisal process
- Guide on writing self-assessments
- Tips for documenting accomplishments using SMART format
- How to set performance goals
- Understanding rating levels (Outstanding, Exceeds, Fully Successful, etc.)
- Preparing for appraisal meetings
- What to bring/discuss in your review

Reference the annual performance cycle and encourage reviewing their performance plan.
```

**For "If no" (Supervisor) branch**:
1. Click **"+ Add node"** under the red "No" path
2. Add **"Create generative answers"**
3. Instructions:
```
Guide supervisors on conducting effective performance reviews:

- Federal performance management system overview
- Writing clear, objective performance standards
- Documenting performance throughout the year
- Conducting fair and effective appraisal meetings
- Rating justifications and avoiding bias
- Handling difficult performance conversations
- Performance Improvement Plans (PIPs)
- Legal considerations and HR consultation

Remind supervisors to consult with HR for specific policy questions.
```

4. **Save** the topic

---

## Topic 5: Technical Tools Support

### 4.17 Create Fifth Topic

**Name**:
```
Technical Tools Support
```

**Trigger phrases**:
```
microsoft 365 help
teams support
outlook issues
technical help
software support
m365 problems
how to use teams
outlook calendar help
sharepoint access
onedrive help
email problems
teams meeting help
cant access email
software not working
```

### 4.18 Add Tool Identification Question

1. Click **"+ Add node"**
2. Select **"Ask a question"**

**Question**:
```
Which tool or application do you need help with?

Examples: Microsoft Teams, Outlook, SharePoint, OneDrive, Excel, etc.
```

**Identify**: **User's entire response**

**Save as**: `ToolName`

### 4.19 Add Generative Answers with Microsoft 365 Knowledge

1. Click **"+ Add node"**
2. Select **"Create generative answers"**

**Input**: `System.Activity.Text`

**Data sources**:
- **Public website**: `https://support.microsoft.com/en-us/office`
- Or upload your agency's IT support guides

**Instructions**:
```
Provide technical support for Microsoft 365 and common federal workplace tools:

- Step-by-step troubleshooting instructions
- How-to guidance for common tasks
- Links to official Microsoft documentation
- Workarounds for known issues

For issues you cannot resolve, direct users to:
- IT Help Desk: [phone]
- Service Desk Portal: [URL]
- Emergency IT Support: [contact]

Keep instructions simple and beginner-friendly. Ask clarifying questions if needed.
```

### 4.20 Add Escalation Message

1. Click **"+ Add node"**
2. Select **"Send a message"**

**Content**:
```
🛠️ **Still need help?**

Contact IT Support:
📞 **Help Desk**: [Your agency IT number]
💻 **Submit Ticket**: [Service desk URL]
📧 **Email**: itsupport@agency.gov

**Hours**: Monday-Friday, 7:00 AM - 6:00 PM ET

For urgent issues outside business hours, call the emergency IT line: [number]
```

3. **Save** the topic

---

## Step 5: Creating the Fallback Topic

The fallback topic catches questions that don't match your defined topics.

### 5.1 Navigate to System Fallback

1. Go to **Topics** tab
2. Scroll to **System** section
3. Click **"Fallback"** topic

**Screenshot description**: *System topics are marked with a system icon; Fallback is usually near the bottom of the system list*

### 5.2 Edit the Fallback Response

**What you'll see**: Default fallback message like "I'm sorry, I didn't understand that."

1. **Delete** the default message node (click the three dots on the node → Delete)
2. Click **"+ Add node"**
3. Select **"Create generative answers"**

### 5.3 Configure Fallback Generative Answers

**Input**: `System.Activity.Text`

**Data sources**:
- Upload: Your agency employee handbook
- Upload: Common HR policies
- Upload: Workplace resources guide
- Add public sites if applicable

**Instructions**:
```
You are LearnFlow Assistant. Answer general questions about:
- Federal workplace policies and procedures
- Employee benefits and programs
- Workplace resources and support
- Learning and development opportunities
- HR processes and guidelines

If the question is outside your scope of knowledge, politely acknowledge this and suggest:
- Contacting their supervisor
- Reaching out to HR directly: [HR contact]
- Visiting the employee portal: [URL]
- Calling the general information line: [number]

Always be helpful, professional, and encouraging. If you're unsure, it's better to direct to a human resource than provide incorrect information.
```

**Content moderation**: Set to **Medium** or **Strict**

### 5.4 Add Helpful Redirect Message

1. Click **"+ Add node"** after generative answers
2. Select **"Send a message"**
3. Content:
```
I hope that helps! If you need further assistance:

📞 **HR Contact Center**: [phone]
🌐 **Employee Portal**: [URL]
📧 **Email HR**: hr@agency.gov

Is there anything else I can help you with?
```

4. **Save** the topic

---

## Step 6: Adding Message Capture Action

This section shows how to prepare for logging user messages (you'll set up the actual Power Automate flow later).

### 6.1 Understanding Message Capture

**Purpose**: Capture every user message for:
- Analytics and improvement
- Compliance and audit trails
- Training data analysis
- User behavior insights

**Method**: We'll add a "placeholder" action that you can connect to Power Automate later.

### 6.2 Create a Global Topic for Logging (Optional Advanced Method)

If you want to log EVERY message globally:

1. Go to **Topics** tab
2. Click **"+ Add a topic"** → **"From blank"**
3. Name: `Message Logger`
4. **Important**: Remove all trigger phrases so this topic never triggers directly

5. In the canvas, add **"+ Add node"**
6. Select **"Call an action"** → **"Create a flow"**

**This will open Power Automate** - for now, we'll just note what to create later.

**What the flow will do**:
- Receive: User message, conversation ID, user ID, timestamp
- Action: Save to Dataverse or SharePoint list
- Return: Success confirmation

7. For now, click **Cancel** (we'll build this in Step 6.4)

### 6.3 Alternative: Add Logging to Each Topic

Simpler method - add logging to individual important topics:

1. Open any topic (e.g., "Compliance & Ethics Training")
2. At the end of the topic flow, click **"+ Add node"**
3. Select **"Call an action"**
4. You'll see **"Create a flow"** option

**Screenshot description**: *"Call an action" menu shows "Create a flow" with Power Automate icon and existing flows if any*

5. For now, just note this location - we'll create the flow in a moment

### 6.4 Create Simple Logging Flow (Quick Version)

Let's create a basic flow that you can expand later:

1. From any topic, click **"+ Add node"** → **"Call an action"** → **"Create a flow"**

2. **Power Automate opens in a new tab**

**What you'll see**: Flow designer with a trigger already configured

**Screenshot description**: *Power Automate interface with "Power Virtual Agents" trigger node at top*

3. Click **"+ Add an input"** under the trigger
4. Add these inputs:

**Input 1**:
- Type: **Text**
- Name: `UserMessage`
- Description: `The user's message text`

**Input 2**:
- Type: **Text**
- Name: `ConversationID`
- Description: `Unique conversation identifier`

**Input 3**:
- Type: **Text**
- Name: `UserEmail`
- Description: `User's email address`

**Screenshot description**: *Trigger node shows list of inputs with +Add button and input type dropdown*

5. Click **"+ New step"**
6. Search for: **"Compose"**
7. Select **"Compose"** action (Data Operations)
8. In the **Inputs** field, add:
```json
{
  "message": "Logged message from: @{triggerBody()['text_UserEmail']}",
  "text": "@{triggerBody()['text_UserMessage']}",
  "conversationId": "@{triggerBody()['text_ConversationID']}",
  "timestamp": "@{utcNow()}"
}
```

**Screenshot description**: *Compose action shows JSON editor with dynamic content picker on the right*

9. Click **"+ New step"**
10. Search for: **"Response"**
11. Select **"Respond to a Power Virtual Agent"** or **"Response"**
12. Add output:
    - Type: **Boolean**
    - Name: `Success`
    - Value: `true`

13. **Name your flow** (top-left): `LearnFlow - Message Logger`

14. Click **"Save"** (top-right)

**Screenshot description**: *Flow saved confirmation appears; flow name shows at top*

15. Close the Power Automate tab and return to Copilot Studio

### 6.5 Connect Flow to Topic

1. Back in Copilot Studio, refresh if needed
2. Go to your topic (e.g., Compliance topic)
3. Click **"+ Add node"** → **"Call an action"**
4. Select your newly created flow: **"LearnFlow - Message Logger"**

**Screenshot description**: *Action menu now shows your custom flow with a lightning bolt icon*

5. Map the inputs:
   - **UserMessage**: Click the field → Select `System.Activity.Text`
   - **ConversationID**: Select `System.Conversation.Id`
   - **UserEmail**: Select `System.User.Email` (if available) or `System.User.Id`

**Screenshot description**: *Input mapping shows dropdowns with system variables and custom topic variables*

6. **Save** the topic

**Federal Tip**: For actual deployment, you'd expand this flow to:
- Save to SharePoint list or Dataverse
- Include user ID and agency information
- Add data retention policies
- Ensure compliance with federal data handling requirements

---

## Step 7: Testing Your Agent

Now let's test everything you've built!

### 7.1 Open Test Panel

1. Look for **"Test your agent"** button in the bottom-left or right side
2. Click to open the test chat panel

**Screenshot description**: *Chat panel slides in from right side with "Test your agent" header and chat input box at bottom*

**Alternative**: Click the toggle switch at the top that says **"Test"**

### 7.2 Test the Greeting

1. In the test chat, type: `hi`
2. Press Enter

**What you should see**:
- Your custom greeting message appears
- 6 suggested prompts appear as clickable buttons

**Screenshot description**: *Chat shows greeting message with formatted text and 6 blue pill-shaped buttons below*

3. Click one of the suggested prompts, e.g., **"What are my training requirements?"**

**What should happen**:
- The Compliance & Ethics Training topic triggers
- Generative answer responds with training information

### 7.3 Test Each Topic Systematically

**Test 1 - Compliance Training**:
```
What compliance training do I need to complete?
```
**Expected**: Compliance topic triggers, AI provides training information

**Test 2 - Learning Portal Access**:
```
How do I log into the learning portal?
```
**Expected**: Learning Platforms topic triggers, shows portal access info

**Test 3 - Career Development**:
```
How can I get promoted from GS-9 to GS-11?
```
**Expected**: Career topic triggers, asks your GS level, provides advancement guidance

**Test 4 - Performance Review**:
```
I need to prepare for my performance review
```
**Expected**: Performance topic triggers, asks if employee or supervisor, provides relevant guidance

**Test 5 - Technical Support**:
```
I can't access my Outlook calendar
```
**Expected**: Technical Tools topic triggers, asks which tool, provides troubleshooting steps

**Test 6 - Fallback**:
```
What's the weather today?
```
**Expected**: Fallback topic triggers, politely explains scope and offers to redirect

### 7.4 Review Conversation Flow

In the test panel, you'll see:
- **Top**: Conversation history
- **Bottom**: Input box
- **Right side of each message**: Small indicator showing which topic triggered

**Screenshot description**: *Each bot response has a small tag like "Compliance & Ethics Training" showing which topic handled it*

### 7.5 Check Topic Triggering

1. Click the **three-dot menu** (⋮) in the test panel header
2. Select **"Tracking"** or **"Conversation flow"**
3. You'll see a visual flow of topics triggered

**Screenshot description**: *Dialog shows flowchart of which topics fired during conversation*

### 7.6 Test Edge Cases

Try these to ensure robustness:

**Typos**:
```
complience trainng
```
**Should still** trigger Compliance topic (AI is forgiving)

**Vague questions**:
```
I need help
```
**Should** ask clarifying questions or use fallback

**Multiple topics in one message**:
```
I need help with compliance training and my performance review
```
**Will** trigger one topic (usually the first match)

**Out of scope**:
```
Can you order me lunch?
```
**Should** trigger fallback and politely decline

### 7.7 Debug Issues

If a topic doesn't trigger:

1. Click **"Topics"** tab
2. Find the topic
3. Check trigger phrases - add more variations
4. Click **"Save"**
5. In test panel, click **"Reset"** (trash can icon) to clear conversation
6. Test again

If generative answers are off-topic:

1. Open the topic
2. Click the generative answers node
3. Review/edit the **Instructions**
4. Add more specific knowledge sources
5. Increase content moderation
6. Save and retest

**Screenshot description**: *Debug panel shows topic triggering confidence scores and matched phrases*

---

## Step 8: Publishing to Demo Channel

### 8.1 Prepare for Publishing

Before publishing, ensure:
- [ ] All 5 topics are created and tested
- [ ] Greeting is customized
- [ ] Suggested prompts are configured
- [ ] Fallback topic is set up
- [ ] Test conversations work as expected

### 8.2 Navigate to Publish

1. Click **"Publish"** tab at the top navigation
2. You'll see the publish overview page

**Screenshot description**: *Publish page shows "Latest" version on left, "Live" version on right, and a big "Publish" button in the center*

**What you'll see**:
- **Latest content**: Your current work (not live yet)
- **Published content**: What users currently see (empty if first publish)
- **Publish button**: Makes your latest work live

### 8.3 Review Changes

1. Click **"Review changes"** or scroll down
2. You'll see a list of what's new/changed:
   - New topics created
   - Modified system topics
   - Changed configurations

**Screenshot description**: *Change list shows green "+" icons for new items and yellow "~" for modified items*

3. Review to ensure everything looks correct

### 8.4 Publish Your Agent

1. Click the large **"Publish"** button
2. A confirmation dialog appears:
   ```
   Publish LearnFlow Assistant?
   This will make your changes available to users.
   ```

**Screenshot description**: *Modal dialog with "Publish" and "Cancel" buttons; may show estimated publish time*

3. Click **"Publish"** to confirm
4. Wait 1-2 minutes for publishing to complete

**What you'll see**:
- Progress indicator
- "Publishing..." message
- Green success checkmark when done: "LearnFlow Assistant published successfully"

**Screenshot description**: *Success notification with green checkmark and timestamp*

### 8.5 Configure Demo Website Channel

Now let's create a shareable demo link.

1. After publishing, click **"Channels"** in the left navigation
   - Or go to **Settings** → **Channels**

**Screenshot description**: *Channels page shows available deployment options as cards*

2. Find **"Demo website"** channel card
   - Has a globe or website icon
3. Click on **"Demo website"**

### 8.6 Enable Demo Website

**What you'll see**: Demo website configuration page

1. Toggle the switch: **"Enable demo website"** to **ON**

**Screenshot description**: *Toggle switch changes from grey to blue/purple when enabled*

2. Settings appear:
   - **Welcome message**: (optional) Customize or leave default
   - **Conversation starters**: Your 6 prompts should appear
   - **Agent name**: LearnFlow Assistant
   - **Agent icon**: Your chosen icon

3. Click **"Save"** if you made changes

### 8.7 Get Your Demo Website Link

**What you'll see**: A unique URL appears

**Screenshot description**: *Blue hyperlink displayed with copy icon next to it*

Example URL format:
```
https://copilotstudio.microsoft.com/environments/Default-xxxxx/bots/cr123_learnflowassistant/webchat
```

1. Click the **"Copy"** button next to the URL
2. **Save this link** - you'll need it for your portfolio

**Test the link**:
1. Open a new browser tab (incognito/private mode recommended)
2. Paste the URL
3. You should see your agent in a clean web interface

**Screenshot description**: *Demo website shows chat window with your agent's greeting and suggested prompts*

### 8.8 Get Embed Code for Websites

If you want to embed the agent on a webpage:

1. Still in the Demo website channel settings
2. Scroll down to find **"Embed code"** section
3. Click **"Copy"** next to the code snippet

**Screenshot description**: *Code block shows HTML iframe code with syntax highlighting*

The code looks like:
```html
<iframe
  src="https://copilotstudio.microsoft.com/environments/[env-id]/bots/[bot-id]/webchat"
  style="width: 400px; height: 600px; border: none;"
  frameborder="0">
</iframe>
```

4. Save this code - you can paste it into any HTML page

### 8.9 Customize Demo Website Appearance (Optional)

1. In Demo website settings, look for **"Customize"** or **"Appearance"**
2. You can adjust:
   - **Theme color**: Change to your agency colors
   - **Chat window size**: Default, compact, or full-screen
   - **Agent avatar**: Upload custom image
   - **Background**: Light or dark theme

**Federal Tip**: Use official agency colors (e.g., navy blue for federal government)

3. Click **"Save"** after customizing

### 8.10 Share Your Demo Link

You can now share your demo website link:
- With colleagues for testing
- In your portfolio (see Step 9)
- In presentations or documentation
- With stakeholders for review

**Federal Security Note**:
- Demo websites are PUBLIC by default
- Don't include sensitive agency information
- For production, use authenticated channels (Teams, authenticated web)
- Consider adding disclaimer: "Demo version - not official agency system"

---

## Step 9: Exporting for Your Portfolio

### 9.1 Take Screenshots for Documentation

**What to capture**:

**Screenshot 1 - Agent Overview**:
1. Go to **Overview** tab
2. Make sure agent name is visible
3. Use **Windows**: `Windows Key + Shift + S`
4. **Mac**: `Cmd + Shift + 4`
5. Capture the full page showing agent description

**Screenshot 2 - Topics List**:
1. Go to **Topics** tab
2. Expand topic list on left
3. Capture showing all 5 custom topics + system topics

**Screenshot 3 - Sample Topic Canvas**:
1. Open your best topic (e.g., Career Development)
2. Zoom out to show full flow: `Ctrl/Cmd + Mouse Wheel` or click fit-to-screen icon
3. Capture the visual flow of nodes

**Screenshot 4 - Generative Answers Configuration**:
1. Click on a generative answers node
2. Show the configuration panel on right
3. Capture showing data sources and instructions

**Screenshot 5 - Test Conversation**:
1. Open test panel
2. Have a sample conversation (3-4 exchanges)
3. Capture showing greeting, user questions, and AI responses

**Screenshot 6 - Published Demo Website**:
1. Open your demo website link in new tab
2. Capture the clean demo interface
3. Show it working with a sample question

### 9.2 Export Agent Configuration

**Export your agent as a solution** (for backup or sharing):

1. Click **Settings** (gear icon) in top-right
2. Go to **General** → **Export**
   - Or look for **"Export"** in left panel

**Screenshot description**: *Settings page with "Export agent" button*

3. Click **"Export agent"**
4. Choose export type:
   - **As a solution** (recommended) - Full export with all components
   - **As a template** - For reuse

5. Click **"Export"**
6. A `.zip` file downloads (e.g., `LearnFlowAssistant_1_0_0_0.zip`)
7. Save this file to your portfolio folder

**What's included**:
- All topics and flows
- Agent configuration
- Knowledge sources (metadata)
- Custom entities

### 9.3 Create Portfolio Documentation

Create a document summarizing your project:

**Portfolio Summary Template**:

```markdown
# LearnFlow Assistant - Microsoft Copilot Studio Project

## Project Overview
AI-powered workforce learning and compliance assistant for federal employees

**Technologies Used**:
- Microsoft Copilot Studio (2025)
- Power Automate (for logging)
- Generative AI / GPT-4
- Microsoft Dataverse

## Features Implemented

### 1. Intelligent Greeting System
- Customized welcome message
- 6 contextual conversation starters
- Professional, accessible design

### 2. Five Managed Topics with AI
1. **Compliance & Ethics Training**
   - Trigger phrases: 10+ variations
   - Generative answers using federal ethics knowledge
   - Content moderation: Medium

2. **Learning Platforms & Access**
   - Portal access instructions
   - PIV card authentication guidance
   - IT support escalation

3. **Career Development**
   - GS-level personalization
   - Promotion pathway guidance
   - OPM standards integration

4. **Performance Management**
   - Conditional logic for employees vs. supervisors
   - Federal rating system explanations
   - Self-assessment support

5. **Technical Tools Support**
   - M365 troubleshooting
   - Dynamic tool identification
   - Help desk integration

### 3. Fallback Handling
- General question support
- Graceful out-of-scope handling
- Human escalation paths

### 4. Message Logging
- Power Automate integration
- Conversation tracking for analytics
- Compliance audit trail

## Technical Highlights
- Used generative answers in all 5 topics
- Implemented conditional branching for role-based responses
- Integrated external knowledge sources (OPM, OGE websites)
- Created custom variables for personalization
- Built reusable logging flow

## Demo Links
- **Live Demo**: [Your demo website URL]
- **Screenshots**: [Link to folder or see below]
- **Video Walkthrough**: [Optional - if you create one]

## Impact & Use Cases
- Reduces HR support ticket volume by 30%+ (estimated)
- Provides 24/7 self-service for common employee questions
- Improves compliance training completion rates
- Enhances employee career development support

## Future Enhancements
- Integration with agency LMS for real-time training status
- Multi-language support (Spanish, etc.)
- Advanced analytics dashboard
- Mobile app deployment
```

Save as: `LearnFlow-Assistant-Portfolio-Summary.md`

### 9.4 Create a Demo Video (Optional)

**Using Free Tools**:

**Windows**:
1. Use **Xbox Game Bar**: `Windows Key + G`
2. Click record button
3. Navigate through your agent
4. Save video

**Mac**:
1. Use **QuickTime Player** → File → New Screen Recording
2. Record your demo
3. Export as MP4

**What to show in video** (2-3 minutes):
1. Open demo website link
2. Show greeting and conversation starters
3. Click 2-3 suggested prompts
4. Show AI responses
5. Ask a custom question
6. Demonstrate one topic's full flow
7. End with fallback handling

Save video as: `LearnFlow-Assistant-Demo.mp4`

### 9.5 Share Your Agent Link

**For Portfolio**:
- Add demo website URL to your resume/LinkedIn
- Include in project portfolio website
- Add to GitHub README if you have a projects repo

**Sample LinkedIn Post**:
```
🚀 Just built LearnFlow Assistant - an AI-powered copilot for federal workforce learning!

Built with Microsoft Copilot Studio, this agent helps employees with:
✅ Compliance training
✅ Career development
✅ Performance reviews
✅ Technical support

Features 5 intelligent topics, generative AI responses, and Power Automate integration.

🔗 Try the demo: [Your URL]

#AI #MicrosoftCopilotStudio #FederalTech #Upskilling
```

### 9.6 Get the Shareable Agent ID

For technical documentation:

1. Go to **Settings** → **General**
2. Find **"Agent ID"** or **"Environment details"**
3. Copy the ID (format: `cr123_learnflowassistant`)

**Screenshot description**: *Settings page shows Agent ID in a copyable text field*

This ID is useful if you need to reference the agent in technical docs or API calls.

### 9.7 Create Portfolio Folder Structure

Organize your files:

```
LearnFlow-Assistant-Portfolio/
├── Screenshots/
│   ├── 01-agent-overview.png
│   ├── 02-topics-list.png
│   ├── 03-topic-flow.png
│   ├── 04-generative-answers-config.png
│   ├── 05-test-conversation.png
│   └── 06-demo-website.png
├── Documentation/
│   ├── LearnFlow-Assistant-Portfolio-Summary.md
│   ├── Build-Guide-Notes.md
│   └── Technical-Specifications.md
├── Export/
│   └── LearnFlowAssistant_1_0_0_0.zip
├── Video/
│   └── LearnFlow-Assistant-Demo.mp4
└── Links.txt (contains demo URL, GitHub, etc.)
```

---

## Federal-Specific Tips and Best Practices

### 10.1 Compliance and Security

**Data Handling**:
- ⚠️ **Never include**:
  - PII (Personal Identifiable Information)
  - CUI (Controlled Unclassified Information)
  - Sensitive agency data
  - Employee SSNs, addresses, medical info

- ✅ **Use general information**:
  - Publicly available policies
  - Generic process descriptions
  - Links to official public resources

**Federal Tip**: Add this disclaimer to your greeting or settings:
```
Disclaimer: This is an informational assistant. For official policy interpretations,
please consult your HR representative, supervisor, or agency ethics office.
```

### 10.2 Accessibility (Section 508 Compliance)

Ensure your agent is accessible:

1. **Use clear language**: Write at 8th-grade reading level
2. **Avoid jargon**: Explain acronyms on first use
3. **Structured formatting**: Use headers, bullets, numbered lists
4. **Alt text**: If you add images to adaptive cards, include descriptions
5. **Color contrast**: Use high-contrast theme colors
6. **Keyboard navigation**: Test without mouse in demo website

**Test with screen reader**:
- Windows: NVDA (free) or JAWS
- Mac: VoiceOver (built-in)

### 10.3 Federal Terminology

Use appropriate federal terms:

| Instead of | Use |
|------------|-----|
| Employees | Federal employees, civil servants |
| Promotion | Advancement, career progression, grade increase |
| Review | Performance appraisal, evaluation |
| Training | Professional development, continuous learning |
| Boss | Supervisor, manager, rating official |

### 10.4 Agency-Specific Customization

**For your agency**, customize:

1. **Replace generic URLs** with actual links:
   - Learning portal: Your agency's LMS
   - HR portal: Your agency's HR system
   - Ethics office: Your ethics contact page

2. **Add agency acronyms** to trigger phrases:
   - Your agency abbreviation
   - Department-specific terms
   - Internal system names

3. **Include agency-specific policies**:
   - Upload your agency's training policy
   - Add links to internal SharePoint
   - Reference your specific GS ladder

4. **Adjust tone** to match agency culture:
   - More formal for traditional agencies
   - Friendly-professional for modern agencies

### 10.5 Knowledge Source Selection

**Best federal knowledge sources**:

**For Compliance/Ethics**:
- OGE (Office of Government Ethics): https://www.oge.gov/
- Your agency's ethics office page
- Federal ethics regulations (5 CFR)

**For Career Development**:
- OPM Classification & Qualifications: https://www.opm.gov/policy-data-oversight/classification-qualifications/
- Your agency's career development program
- Federal career ladder documents

**For Performance Management**:
- OPM Performance Management: https://www.opm.gov/policy-data-oversight/performance-management/
- Your agency's performance management handbook
- Appraisal form instructions

**For Learning Platforms**:
- Your agency's LMS documentation
- OPM Learning Portal: https://www.opm.gov/training/
- GoLearn (if applicable)

**Federal Tip**: Only use **publicly available** documents from official .gov websites for your demo. For production, use internal authenticated sources.

### 10.6 Common Federal Questions to Support

Add these scenarios to your topics:

**Compliance**:
- Annual ethics training deadline
- Financial disclosure requirements
- Hatch Act guidance
- Standards of Conduct
- Conflict of interest questions

**Career Development**:
- Time-in-grade requirements (52 weeks for 1-grade, 104 for 2-grade)
- IDP (Individual Development Plan) guidance
- Detail opportunities
- Leadership development programs
- Pathways to GS-14/15

**Performance**:
- Rating levels (Outstanding, Exceeds, Fully Successful, etc.)
- Performance Improvement Plans (PIPs)
- Probationary period evaluations
- Award nominations

**Learning Access**:
- PIV card authentication
- Remote learning access via VPN
- Training time approval
- Conference/workshop requests

### 10.7 Escalation Paths

Always provide clear escalation:

**For HR Questions**:
```
For official HR guidance, contact:
📞 HR Contact Center: [number]
📧 Email: HR@agency.gov
🌐 HR Portal: [URL]
```

**For Ethics Questions**:
```
For ethics advice, contact:
👔 Agency Ethics Office: [number]
📧 Ethics email: ethics@agency.gov
⚖️ Submit inquiry: [ethics portal]
```

**For IT Support**:
```
For technical assistance:
💻 IT Help Desk: [number]
🎫 Submit ticket: [URL]
📱 Self-service: [portal]
```

### 10.8 Testing with Federal Scenarios

Test your agent with realistic federal questions:

**Test Set 1 - Compliance**:
```
- When is the ethics training deadline?
- Do I need to file a financial disclosure?
- What's covered in the annual training?
- I missed the compliance training deadline, what now?
```

**Test Set 2 - Career (GS-specific)**:
```
- I'm a GS-9, how do I get to GS-11?
- What's time-in-grade?
- Can I apply for jobs 2 grades higher?
- How do I write an IDP?
```

**Test Set 3 - Performance**:
```
- What does "Fully Successful" mean?
- When are midyear reviews?
- How do I write a self-assessment?
- What if I disagree with my rating?
```

### 10.9 Multi-Agency Deployment Considerations

If building for multiple agencies:

1. **Use variables for agency name**:
   - Create global variable: `AgencyName`
   - Reference in messages: "Contact your `{AgencyName}` HR office"

2. **Modular contact information**:
   - Store contacts in a Dataverse table
   - Look up by agency
   - Display relevant contacts

3. **Topic variations by agency**:
   - Use conditions to branch by agency
   - Customize training requirements per agency

### 10.10 Production Deployment Checklist

Before going live agency-wide:

- [ ] Security review completed
- [ ] ATO (Authority to Operate) obtained if required
- [ ] Privacy Impact Assessment (PIA) completed
- [ ] Section 508 accessibility tested
- [ ] Content reviewed by agency ethics office
- [ ] Content reviewed by HR/OHC
- [ ] IT security review completed
- [ ] Data retention policy defined
- [ ] Incident response plan documented
- [ ] User training materials prepared
- [ ] Pilot with 50-100 users completed
- [ ] Feedback incorporated
- [ ] Analytics dashboard configured
- [ ] Support team trained
- [ ] Launch communications prepared

---

## Troubleshooting Common Issues

### Issue 1: Topics Not Triggering

**Symptom**: User types trigger phrase but wrong topic (or fallback) activates

**Solutions**:
1. Add more trigger phrase variations
2. Check for overlapping phrases between topics
3. Make phrases more specific
4. Test in incognito mode (clear test conversation)
5. Check topic is enabled and published

### Issue 2: Generative Answers Too Generic

**Symptom**: AI gives vague or incorrect responses

**Solutions**:
1. Add specific knowledge sources (upload docs)
2. Improve instructions with more context
3. Enable "Limit to data sources only"
4. Increase content moderation level
5. Provide more detailed user instructions in the prompt

### Issue 3: Demo Website Not Loading

**Symptom**: Demo link shows error or blank page

**Solutions**:
1. Ensure agent is published (check Publish tab)
2. Verify Demo website channel is enabled
3. Clear browser cache and cookies
4. Try incognito/private mode
5. Check if your organization blocks iframes
6. Wait 5-10 minutes after publishing (propagation delay)

### Issue 4: Flow Not Executing

**Symptom**: Power Automate action doesn't run or fails

**Solutions**:
1. Check flow is turned ON in Power Automate
2. Verify connection permissions
3. Test flow directly in Power Automate
4. Check run history for error messages
5. Ensure input variables are correctly mapped
6. Verify Dataverse/SharePoint permissions

### Issue 5: Knowledge Sources Not Working

**Symptom**: AI doesn't use uploaded documents

**Solutions**:
1. Verify file format (PDF, Word, PowerPoint supported)
2. Check file size (limit is typically 10MB per file)
3. Wait for indexing to complete (can take 5-10 minutes)
4. Ensure content is text-based (not scanned images)
5. Try re-uploading the document
6. Check document isn't password-protected

### Issue 6: Test Conversation Shows Old Content

**Symptom**: Changes don't appear in test panel

**Solutions**:
1. Click **Reset** (trash icon) in test panel
2. Close and reopen test panel
3. Hard refresh browser: `Ctrl+Shift+R` (Win) or `Cmd+Shift+R` (Mac)
4. Clear browser cache
5. Ensure you clicked **Save** after making changes

### Issue 7: Can't Find System Topics

**Symptom**: Don't see Greeting or Fallback topics

**Solutions**:
1. Scroll down in Topics list
2. Expand **System** section (click the header)
3. Use search box: type "greeting" or "fallback"
4. Check if filtered by status (show all topics)
5. Refresh the page

---

## Next Steps and Advanced Features

### Continue Learning

1. **Explore Entities**:
   - Create custom entities to recognize specific federal terms
   - Example: GS levels, agency names, training types

2. **Add Analytics**:
   - Go to Analytics tab
   - Review topic performance
   - Track user satisfaction
   - Identify common questions

3. **Implement Authentication**:
   - Require users to sign in
   - Personalize responses based on user profile
   - Access authenticated SharePoint sites

4. **Connect to Systems**:
   - Integrate with LMS API to show real training status
   - Connect to HR system for personalized career guidance
   - Pull data from Dataverse tables

5. **Advanced Flows**:
   - Create ticket in ServiceNow
   - Send email notifications
   - Update records in HR systems
   - Generate reports

6. **Multi-Channel Deployment**:
   - Publish to Microsoft Teams
   - Add to SharePoint pages
   - Create mobile app with Power Apps
   - Embed in your agency intranet

### Resources for Continued Learning

**Official Microsoft Documentation**:
- [Copilot Studio Documentation](https://learn.microsoft.com/microsoft-copilot-studio/)
- [Generative Answers Guide](https://learn.microsoft.com/microsoft-copilot-studio/nlu-boost-conversations)
- [Power Automate Integration](https://learn.microsoft.com/microsoft-copilot-studio/advanced-flow)

**Training Courses**:
- Microsoft Learn: "Create bots with Copilot Studio"
- LinkedIn Learning: Power Virtual Agents courses
- YouTube: Microsoft Mechanics channel

**Community**:
- [Power Platform Community](https://powerusers.microsoft.com/)
- [Copilot Studio Forum](https://powerusers.microsoft.com/t5/Microsoft-Copilot-Studio/bd-p/PVACommunity)
- Reddit: r/PowerPlatform

**Federal-Specific**:
- Federal AI Community of Practice
- Your agency's AI/RPA working group
- Government tech conferences (FOSE, ATARC, etc.)

---

## Congratulations!

You've successfully built **LearnFlow Assistant**, a production-ready AI copilot for federal workforce learning and compliance!

**What You Accomplished**:
- ✅ Created an intelligent agent from scratch
- ✅ Configured 5 managed topics with generative AI
- ✅ Set up greeting and conversation starters
- ✅ Implemented fallback handling
- ✅ Added message logging capability
- ✅ Published to demo website
- ✅ Created portfolio documentation

**Your agent can now**:
- Answer federal compliance questions 24/7
- Guide employees on career development
- Support performance review preparation
- Help with learning platform access
- Provide M365 technical support
- Escalate complex issues appropriately

---

## Appendix: Quick Reference

### Key URLs
- **Copilot Studio**: https://copilotstudio.microsoft.com
- **Power Automate**: https://make.powerautomate.com
- **Power Apps**: https://make.powerapps.com
- **OPM Resources**: https://www.opm.gov
- **OGE Resources**: https://www.oge.gov

### System Variables Cheat Sheet
```
System.Activity.Text           # User's current message
System.User.Id                 # Unique user identifier
System.User.Email              # User's email (if authenticated)
System.User.DisplayName        # User's name
System.Conversation.Id         # Unique conversation ID
System.Topic.Name              # Current topic name
```

### Common Node Types
- **Send a message**: Display text to user
- **Ask a question**: Get user input
- **Create generative answers**: AI-powered responses
- **Add a condition**: Branch conversation logic
- **Call an action**: Trigger Power Automate flow
- **Go to topic**: Redirect to another topic
- **End conversation**: Close the conversation

### Keyboard Shortcuts
- **Save**: `Ctrl/Cmd + S`
- **Find**: `Ctrl/Cmd + F`
- **Zoom in/out**: `Ctrl/Cmd + Mouse wheel`
- **Test panel**: Click **Test** toggle
- **Refresh page**: `Ctrl/Cmd + R`

---

**Version**: 1.0 (Late 2025)
**Last Updated**: December 2025
**Author**: Federal Learning Technology Team

*For questions or support, contact your agency's Power Platform administrator or submit a request to your IT service desk.*

---

**Happy Building! 🚀**
