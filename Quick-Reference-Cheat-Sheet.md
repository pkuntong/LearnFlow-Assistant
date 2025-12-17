# LearnFlow Assistant - Quick Reference Cheat Sheet

## 🚀 Quick Start Checklist

### Initial Setup (15 min)
- [ ] Create new copilot: **+ Create** → **New copilot**
- [ ] Name: `LearnFlow Assistant`
- [ ] Add instructions about workforce learning
- [ ] Customize greeting topic
- [ ] Click **Save**

### Create Topics (30-45 min)
- [ ] Topic 1: Annual Ethics/Compliance Training
- [ ] Topic 2: Access Internal Learning Portals
- [ ] Topic 3: Career Development
- [ ] Topic 4: Performance Review Process
- [ ] Topic 5: Technical Tool Support
- [ ] Configure Fallback topic

### Configure Features (15 min)
- [ ] Enable Dataverse logging
- [ ] Test all topics
- [ ] Publish copilot
- [ ] Get embed code or Teams link

---

## 📍 Navigation Quick Reference

| Action | Path |
|--------|------|
| Create new topic | **Topics** → **+ Add** → **Topic** → **From blank** |
| Add trigger phrases | In topic → **Phrases** section at top |
| Add generative answers | **+ Add node** → **Advanced** → **Generative answers** |
| Add message | **+ Add node** → **Send a message** |
| Add question | **+ Add node** → **Ask a question** |
| Add condition | **+ Add node** → **Add a condition** |
| Call Power Automate | **+ Add node** → **Call an action** |
| Test copilot | **Test** button (bottom-left) |
| Publish | **Publish** button (top-right) |
| Get embed code | **Channels** → **Custom website** → **Copy** |
| View analytics | **Analytics** (left navigation) |
| Settings | **Gear icon** (top-right) |

---

## 🎯 Essential Topic Components

### Basic Topic Structure
```
1. Trigger Phrases (5-10 variations)
2. Optional: Ask clarifying question
3. Generative Answers node
   - Input: Activity.Text
   - Data source: Upload docs or add URLs
   - Custom instructions: Guide the AI
4. Follow-up message
5. Save topic
```

### Generative Answers Setup
```
Input: Activity.Text (user's message)
Data Sources:
  ✓ Upload company PDFs/Word docs
  ✓ Add SharePoint/OneDrive links
  ✓ Public website URLs
  ✓ No source (uses AI knowledge)

Content Moderation: Medium or High
☑ Limit to data sources only (for accuracy)
```

---

## 🔧 Common Node Types

| Node Type | When to Use | Key Settings |
|-----------|-------------|--------------|
| **Send a message** | Display info, links, instructions | Use markdown, keep concise |
| **Ask a question** | Get user input | Save response as variable |
| **Generative answers** | AI-powered responses | Configure data sources |
| **Add a condition** | Branch conversation | Check variable values |
| **Call an action** | Trigger Power Automate | Map input/output parameters |
| **Topic management** | Redirect to another topic | Select target topic |
| **End conversation** | Close conversation | With/without survey |

---

## 💡 Power Fx Quick Reference

### Common Variables
```
Activity.Text              # User's current message
System.User.Id            # User's unique ID
System.Conversation.Id    # Conversation ID
System.User.DisplayName   # User's name
Topic.VariableName        # Topic variable you created
```

### Useful Expressions
```
# Combine text
Topic.UserRole & " - " & Activity.Text

# Current date/time
Text(Now(), "yyyy-MM-dd HH:mm:ss")

# Conditional text
If(Topic.IsManager = "Yes", "Manager content", "IC content")

# Check if text contains
Contains(Activity.Text, "urgent")
```

---

## 📊 Testing Checklist

### Pre-Launch Testing
- [ ] Test greeting appears correctly
- [ ] Each topic triggers with trigger phrases
- [ ] Generative answers are relevant
- [ ] Links and URLs work
- [ ] Fallback provides helpful response
- [ ] Dataverse logging works (if enabled)
- [ ] Conversation flows naturally
- [ ] Variables save correctly
- [ ] Adaptive cards display properly
- [ ] Power Automate flows execute

### Test Phrases
**Compliance**: `what compliance training do I need`
**Portal**: `how do I access learning portal`
**Career**: `how can I get promoted`
**Review**: `performance review process`
**Tech**: `I need help with Teams`
**Fallback**: `random unrelated question`

---

## 🚢 Publishing & Deployment

### Publishing Steps
1. **Test thoroughly** in test panel
2. Click **Publish** (top-right)
3. Review changes
4. Confirm publish
5. Wait for completion (~2 min)

### Get Access Links

**Demo Website** (Quick start)
```
Channels → Demo website → Toggle ON → Copy link
Share: https://copilotstudio.microsoft.com/...
```

**Embed Code** (Website integration)
```
Channels → Custom website → Copy code
Paste iframe in your HTML
```

**Microsoft Teams** (Internal deployment)
```
Channels → Microsoft Teams → Turn on Teams
Add to Teams or share app link
```

**SharePoint**
```
Channels → SharePoint → Add to SharePoint
Use PVA web part on SharePoint pages
```

---

## 🎨 Customization Options

### Branding
- **Bot icon**: 192x192 px PNG (Settings → Details)
- **Theme color**: Hex code for company brand
- **Bot name**: Display name in chat
- **Conversation starters**: Quick action buttons

### Greeting Message Template
```
Hello! I'm [Bot Name], your guide for [purpose].

I can help you with:
• Topic 1
• Topic 2
• Topic 3
• Topic 4
• Topic 5

What would you like to know today?
```

---

## 📈 Analytics & Optimization

### Key Metrics to Monitor
| Metric | Good Target | Action if Low |
|--------|-------------|---------------|
| Sessions | Growing weekly | Promote more |
| Resolution rate | >70% | Improve topics |
| Escalation rate | <20% | Add content |
| CSAT score | >4.0/5 | Refine answers |
| Engaged sessions | >60% | Better greeting |

### Weekly Maintenance Tasks
- [ ] Review Analytics → Topics performance
- [ ] Check unrecognized phrases
- [ ] Add new trigger phrases
- [ ] Update outdated information
- [ ] Test new content changes
- [ ] Publish updates

---

## 🔐 Security Best Practices

### Do's
✅ Enable authentication for internal use
✅ Log conversations to Dataverse
✅ Use content moderation (Medium/High)
✅ Limit generative answers to data sources
✅ Regularly review conversation logs
✅ Update copilot with security patches

### Don'ts
❌ Include passwords or secrets in responses
❌ Share PII (personal identifiable information)
❌ Hard-code sensitive data in topics
❌ Allow unauthenticated access to sensitive info
❌ Ignore failed authentication attempts

---

## 🆘 Quick Troubleshooting

| Problem | Quick Fix |
|---------|-----------|
| Topic won't trigger | Add more trigger phrase variations |
| Generative answer irrelevant | Add specific data sources or refine instructions |
| Flow fails | Check Power Automate run history |
| Embed code doesn't work | Verify copilot is published |
| Slow responses | Reduce data source size, optimize flows |
| Teams install fails | Check admin approval status |
| Can't find copilot | Verify environment and permissions |

---

## 📋 Pre-Launch Checklist

### Content Review
- [ ] All company URLs are correct
- [ ] Contact information is current
- [ ] Training deadlines are accurate
- [ ] Portal links work
- [ ] No placeholder text remains
- [ ] Grammar and spelling checked

### Technical Review
- [ ] All topics published
- [ ] Generative answers configured
- [ ] Dataverse connection tested
- [ ] Authentication enabled (if needed)
- [ ] Channels configured
- [ ] Analytics enabled

### User Experience Review
- [ ] Greeting is welcoming
- [ ] Messages are concise
- [ ] Navigation is intuitive
- [ ] Escalation paths are clear
- [ ] Feedback mechanism works
- [ ] Mobile experience tested

---

## 🔗 Essential Links

| Resource | URL |
|----------|-----|
| Copilot Studio Portal | https://copilotstudio.microsoft.com |
| Documentation | https://learn.microsoft.com/microsoft-copilot-studio/ |
| Power Automate | https://make.powerautomate.com |
| Power Apps (Dataverse) | https://make.powerapps.com |
| Community Forums | https://powerusers.microsoft.com/ |
| Support | https://powerplatform.microsoft.com/support/ |

---

## 💬 Sample Response Templates

### Helpful Response
```
Here's how to [action]:

1. [Step 1]
2. [Step 2]
3. [Step 3]

**Need more help?**
• Link: [URL]
• Contact: [email/phone]

Is there anything else I can assist you with?
```

### Escalation Response
```
I understand you need help with [issue].

For this request, please contact:
• [Department]: [contact info]
• Portal: [URL]
• Hours: [availability]

They'll be able to assist you right away!
```

### Clarification Response
```
To help you better, could you provide more details about:
• [Question 1]
• [Question 2]

This will help me give you the most accurate information.
```

---

## 🎓 Power User Tips

### Tip 1: Use Variables for Personalization
```
Save: System.User.DisplayName
Use: "Hi " & Topic.UserName & ", here's what you need..."
```

### Tip 2: Create Topic Templates
Build a reusable topic structure and duplicate it for similar topics.

### Tip 3: Use Adaptive Cards for Rich Content
Create interactive cards with buttons, images, and input fields.

### Tip 4: Leverage Power Automate
Integrate with SharePoint, Outlook, Teams, and other systems.

### Tip 5: Monitor Unrecognized Phrases
Weekly review → Add to existing topics or create new ones.

### Tip 6: A/B Test Responses
Try different message styles and track CSAT scores.

### Tip 7: Use Entities for Better Recognition
Define custom entities for company-specific terms.

---

## 📞 Support Contacts

**For building the copilot:**
- Your Power Platform Admin
- IT Service Desk
- Center of Excellence team

**For content questions:**
- HR Department (policies, training)
- Learning & Development team
- IT Support (technical tools)

**For platform issues:**
- Microsoft Support Portal
- Power Platform Community

---

*Last Updated: December 2025*
*Version: 1.0*
