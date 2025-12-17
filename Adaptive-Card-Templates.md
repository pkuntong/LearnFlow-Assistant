# Adaptive Card Templates - LearnFlow Assistant

Adaptive Cards provide rich, interactive content within your copilot conversations. This document includes ready-to-use templates for LearnFlow Assistant.

---

## 📋 Table of Contents
1. [Card 1: Training Requirements Overview](#card-1-training-requirements-overview)
2. [Card 2: Learning Portal Quick Links](#card-2-learning-portal-quick-links)
3. [Card 3: Career Path Roadmap](#card-3-career-path-roadmap)
4. [Card 4: Performance Review Checklist](#card-4-performance-review-checklist)
5. [Card 5: Tech Support Contact Card](#card-5-tech-support-contact-card)
6. [Card 6: Course Recommendation](#card-6-course-recommendation)
7. [Card 7: Feedback Collection](#card-7-feedback-collection)
8. [Card 8: Escalation Confirmation](#card-8-escalation-confirmation)

---

## Card 1: Training Requirements Overview

**Use Case**: Display user's compliance training requirements with due dates and completion status.

### Preview
```
┌────────────────────────────────────────────┐
│ 📚 Your Training Requirements              │
├────────────────────────────────────────────┤
│ Annual Ethics Training                     │
│ Status: Not Started  |  Due: Jan 31, 2025  │
│ [Start Course →]                           │
├────────────────────────────────────────────┤
│ Data Privacy & Security                    │
│ Status: Not Started  |  Due: Jan 31, 2025  │
│ [Start Course →]                           │
├────────────────────────────────────────────┤
│ Anti-Harassment Training                   │
│ Status: ✓ Completed  |  Completed: Dec 15  │
├────────────────────────────────────────────┤
│           [View All Courses]               │
│        [Download My Transcript]            │
└────────────────────────────────────────────┘
```

### JSON Code
```json
{
  "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
  "type": "AdaptiveCard",
  "version": "1.4",
  "body": [
    {
      "type": "Container",
      "items": [
        {
          "type": "TextBlock",
          "text": "📚 Your Training Requirements",
          "weight": "Bolder",
          "size": "Large",
          "color": "Accent"
        },
        {
          "type": "TextBlock",
          "text": "Complete these courses by the due dates to stay compliant.",
          "wrap": true,
          "spacing": "Small",
          "isSubtle": true
        }
      ]
    },
    {
      "type": "Container",
      "style": "emphasis",
      "spacing": "Medium",
      "items": [
        {
          "type": "ColumnSet",
          "columns": [
            {
              "type": "Column",
              "width": "stretch",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "Annual Ethics Training",
                  "weight": "Bolder",
                  "wrap": true
                },
                {
                  "type": "TextBlock",
                  "text": "45 minutes • Interactive scenarios",
                  "size": "Small",
                  "isSubtle": true,
                  "wrap": true
                }
              ]
            },
            {
              "type": "Column",
              "width": "auto",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "Due: Jan 31",
                  "color": "Attention",
                  "weight": "Bolder",
                  "horizontalAlignment": "Right"
                },
                {
                  "type": "TextBlock",
                  "text": "Not Started",
                  "size": "Small",
                  "horizontalAlignment": "Right",
                  "color": "Warning"
                }
              ]
            }
          ]
        }
      ]
    },
    {
      "type": "Container",
      "style": "emphasis",
      "spacing": "Small",
      "items": [
        {
          "type": "ColumnSet",
          "columns": [
            {
              "type": "Column",
              "width": "stretch",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "Data Privacy & Security",
                  "weight": "Bolder",
                  "wrap": true
                },
                {
                  "type": "TextBlock",
                  "text": "60 minutes • Quiz included",
                  "size": "Small",
                  "isSubtle": true,
                  "wrap": true
                }
              ]
            },
            {
              "type": "Column",
              "width": "auto",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "Due: Jan 31",
                  "color": "Attention",
                  "weight": "Bolder",
                  "horizontalAlignment": "Right"
                },
                {
                  "type": "TextBlock",
                  "text": "Not Started",
                  "size": "Small",
                  "horizontalAlignment": "Right",
                  "color": "Warning"
                }
              ]
            }
          ]
        }
      ]
    },
    {
      "type": "Container",
      "style": "good",
      "spacing": "Small",
      "items": [
        {
          "type": "ColumnSet",
          "columns": [
            {
              "type": "Column",
              "width": "stretch",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "✓ Anti-Harassment Training",
                  "weight": "Bolder",
                  "wrap": true,
                  "color": "Good"
                },
                {
                  "type": "TextBlock",
                  "text": "Completed on Dec 15, 2024",
                  "size": "Small",
                  "isSubtle": true,
                  "wrap": true
                }
              ]
            }
          ]
        }
      ]
    }
  ],
  "actions": [
    {
      "type": "Action.OpenUrl",
      "title": "View All Courses",
      "url": "https://learning.company.com/courses",
      "style": "positive"
    },
    {
      "type": "Action.OpenUrl",
      "title": "Download Transcript",
      "url": "https://learning.company.com/transcript"
    }
  ]
}
```

### How to Use in Copilot Studio
1. In your topic, add **"Send a message"** node
2. Click **"+ Add"** → **"Adaptive Card"**
3. Paste the JSON above
4. Replace URLs with your actual portal links
5. Optionally, use variables to populate dynamic data

---

## Card 2: Learning Portal Quick Links

**Use Case**: Provide easy access to various learning portals and resources.

### Preview
```
┌────────────────────────────────────────────┐
│ 🌐 Learning Portals & Resources            │
├────────────────────────────────────────────┤
│ [🎓 Main Learning Portal]                  │
│ Access all required and elective courses   │
├────────────────────────────────────────────┤
│ [💼 LinkedIn Learning]                     │
│ 16,000+ courses on business & tech skills  │
├────────────────────────────────────────────┤
│ [📊 Skills Academy]                        │
│ Technical certifications and deep dives    │
├────────────────────────────────────────────┤
│ [✓ Compliance Hub]                         │
│ Annual training and policy acknowledgments │
└────────────────────────────────────────────┘
```

### JSON Code
```json
{
  "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
  "type": "AdaptiveCard",
  "version": "1.4",
  "body": [
    {
      "type": "TextBlock",
      "text": "🌐 Learning Portals & Resources",
      "weight": "Bolder",
      "size": "Large",
      "color": "Accent"
    },
    {
      "type": "TextBlock",
      "text": "Click any portal below to access learning resources.",
      "wrap": true,
      "spacing": "Small",
      "isSubtle": true
    },
    {
      "type": "Container",
      "style": "emphasis",
      "spacing": "Medium",
      "items": [
        {
          "type": "ColumnSet",
          "columns": [
            {
              "type": "Column",
              "width": "auto",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "🎓",
                  "size": "ExtraLarge"
                }
              ],
              "spacing": "Small"
            },
            {
              "type": "Column",
              "width": "stretch",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "Main Learning Portal",
                  "weight": "Bolder"
                },
                {
                  "type": "TextBlock",
                  "text": "Access all required and elective courses",
                  "size": "Small",
                  "wrap": true,
                  "isSubtle": true
                }
              ]
            }
          ],
          "selectAction": {
            "type": "Action.OpenUrl",
            "url": "https://learning.company.com"
          }
        }
      ]
    },
    {
      "type": "Container",
      "style": "emphasis",
      "spacing": "Small",
      "items": [
        {
          "type": "ColumnSet",
          "columns": [
            {
              "type": "Column",
              "width": "auto",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "💼",
                  "size": "ExtraLarge"
                }
              ]
            },
            {
              "type": "Column",
              "width": "stretch",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "LinkedIn Learning",
                  "weight": "Bolder"
                },
                {
                  "type": "TextBlock",
                  "text": "16,000+ courses on business & tech skills",
                  "size": "Small",
                  "wrap": true,
                  "isSubtle": true
                }
              ]
            }
          ],
          "selectAction": {
            "type": "Action.OpenUrl",
            "url": "https://learning.linkedin.com"
          }
        }
      ]
    },
    {
      "type": "Container",
      "style": "emphasis",
      "spacing": "Small",
      "items": [
        {
          "type": "ColumnSet",
          "columns": [
            {
              "type": "Column",
              "width": "auto",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "📊",
                  "size": "ExtraLarge"
                }
              ]
            },
            {
              "type": "Column",
              "width": "stretch",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "Skills Academy",
                  "weight": "Bolder"
                },
                {
                  "type": "TextBlock",
                  "text": "Technical certifications and deep dives",
                  "size": "Small",
                  "wrap": true,
                  "isSubtle": true
                }
              ]
            }
          ],
          "selectAction": {
            "type": "Action.OpenUrl",
            "url": "https://skills.company.com"
          }
        }
      ]
    },
    {
      "type": "Container",
      "style": "emphasis",
      "spacing": "Small",
      "items": [
        {
          "type": "ColumnSet",
          "columns": [
            {
              "type": "Column",
              "width": "auto",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "✓",
                  "size": "ExtraLarge",
                  "color": "Good"
                }
              ]
            },
            {
              "type": "Column",
              "width": "stretch",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "Compliance Hub",
                  "weight": "Bolder"
                },
                {
                  "type": "TextBlock",
                  "text": "Annual training and policy acknowledgments",
                  "size": "Small",
                  "wrap": true,
                  "isSubtle": true
                }
              ]
            }
          ],
          "selectAction": {
            "type": "Action.OpenUrl",
            "url": "https://compliance.company.com"
          }
        }
      ]
    }
  ],
  "actions": [
    {
      "type": "Action.OpenUrl",
      "title": "Need Help Logging In?",
      "url": "https://support.company.com/learning-portal-help"
    }
  ]
}
```

---

## Card 3: Career Path Roadmap

**Use Case**: Show career progression from current role to target role.

### Preview
```
┌────────────────────────────────────────────┐
│ 📈 Your Career Path                        │
│ Software Engineer → Senior Software Engineer│
├────────────────────────────────────────────┤
│ Your Current Level: Software Engineer II   │
│                                            │
│ ● Technical Skills (80% complete)          │
│ ████████░░ 8/10 skills mastered            │
│                                            │
│ ● Leadership (40% complete)                │
│ ████░░░░░░ Led 2 projects, need 3 more     │
│                                            │
│ ● Impact (60% complete)                    │
│ ██████░░░░ 3 major contributions           │
│                                            │
│ Estimated Timeline: 6-12 months            │
│                                            │
│ [View Detailed Roadmap]  [Talk to Manager] │
└────────────────────────────────────────────┘
```

### JSON Code
```json
{
  "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
  "type": "AdaptiveCard",
  "version": "1.4",
  "body": [
    {
      "type": "TextBlock",
      "text": "📈 Your Career Path",
      "weight": "Bolder",
      "size": "Large",
      "color": "Accent"
    },
    {
      "type": "TextBlock",
      "text": "Software Engineer II → Senior Software Engineer",
      "weight": "Bolder",
      "size": "Medium",
      "spacing": "None"
    },
    {
      "type": "TextBlock",
      "text": "Your Current Level: Software Engineer II",
      "isSubtle": true,
      "spacing": "Small"
    },
    {
      "type": "Container",
      "style": "emphasis",
      "spacing": "Medium",
      "items": [
        {
          "type": "TextBlock",
          "text": "Technical Skills",
          "weight": "Bolder"
        },
        {
          "type": "ProgressBar",
          "title": "80% complete",
          "value": 80
        },
        {
          "type": "TextBlock",
          "text": "8/10 core skills mastered",
          "size": "Small",
          "isSubtle": true,
          "spacing": "Small"
        }
      ]
    },
    {
      "type": "Container",
      "style": "emphasis",
      "spacing": "Small",
      "items": [
        {
          "type": "TextBlock",
          "text": "Leadership & Mentorship",
          "weight": "Bolder"
        },
        {
          "type": "ProgressBar",
          "title": "40% complete",
          "value": 40
        },
        {
          "type": "TextBlock",
          "text": "Led 2 projects, mentor 1 junior engineer. Need: Lead 3 more projects",
          "size": "Small",
          "isSubtle": true,
          "spacing": "Small",
          "wrap": true
        }
      ]
    },
    {
      "type": "Container",
      "style": "emphasis",
      "spacing": "Small",
      "items": [
        {
          "type": "TextBlock",
          "text": "Business Impact",
          "weight": "Bolder"
        },
        {
          "type": "ProgressBar",
          "title": "60% complete",
          "value": 60
        },
        {
          "type": "TextBlock",
          "text": "3 major contributions to product roadmap",
          "size": "Small",
          "isSubtle": true,
          "spacing": "Small"
        }
      ]
    },
    {
      "type": "FactSet",
      "spacing": "Medium",
      "facts": [
        {
          "title": "Estimated Timeline:",
          "value": "6-12 months"
        },
        {
          "title": "Next Milestone:",
          "value": "Complete System Design course"
        }
      ]
    }
  ],
  "actions": [
    {
      "type": "Action.OpenUrl",
      "title": "View Detailed Roadmap",
      "url": "https://career.company.com/roadmap",
      "style": "positive"
    },
    {
      "type": "Action.OpenUrl",
      "title": "Talk to Manager",
      "url": "https://outlook.office.com/calendar"
    }
  ]
}
```

**Note**: The ProgressBar element requires Adaptive Cards version 1.5. For older versions, use a visual representation with TextBlocks.

---

## Card 4: Performance Review Checklist

**Use Case**: Help employees prepare for their performance review.

### Preview
```
┌────────────────────────────────────────────┐
│ 📝 Performance Review Preparation          │
│ Due: January 31, 2025                      │
├────────────────────────────────────────────┤
│ ✓ Review job description                   │
│ ✓ Gather accomplishment examples           │
│ ○ Complete self-assessment form            │
│ ○ List development goals for next year     │
│ ○ Prepare questions for your manager       │
│ ○ Submit self-assessment                   │
│                                            │
│ Progress: 2 of 6 steps complete            │
│ ███░░░░░░░                                 │
│                                            │
│ [Open Self-Assessment]  [View Guide]       │
└────────────────────────────────────────────┘
```

### JSON Code
```json
{
  "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
  "type": "AdaptiveCard",
  "version": "1.4",
  "body": [
    {
      "type": "ColumnSet",
      "columns": [
        {
          "type": "Column",
          "width": "stretch",
          "items": [
            {
              "type": "TextBlock",
              "text": "📝 Performance Review Preparation",
              "weight": "Bolder",
              "size": "Large"
            }
          ]
        },
        {
          "type": "Column",
          "width": "auto",
          "items": [
            {
              "type": "TextBlock",
              "text": "Due: Jan 31",
              "color": "Attention",
              "horizontalAlignment": "Right",
              "weight": "Bolder"
            }
          ]
        }
      ]
    },
    {
      "type": "Container",
      "spacing": "Medium",
      "items": [
        {
          "type": "TextBlock",
          "text": "✓ Review job description and expectations",
          "wrap": true,
          "color": "Good"
        },
        {
          "type": "TextBlock",
          "text": "✓ Gather 5-7 accomplishment examples",
          "wrap": true,
          "spacing": "Small",
          "color": "Good"
        },
        {
          "type": "TextBlock",
          "text": "○ Complete self-assessment form",
          "wrap": true,
          "spacing": "Small"
        },
        {
          "type": "TextBlock",
          "text": "○ List 3-5 development goals for next year",
          "wrap": true,
          "spacing": "Small"
        },
        {
          "type": "TextBlock",
          "text": "○ Prepare questions for your manager",
          "wrap": true,
          "spacing": "Small"
        },
        {
          "type": "TextBlock",
          "text": "○ Submit self-assessment by deadline",
          "wrap": true,
          "spacing": "Small"
        }
      ]
    },
    {
      "type": "Container",
      "style": "emphasis",
      "spacing": "Medium",
      "items": [
        {
          "type": "TextBlock",
          "text": "Progress: 2 of 6 steps complete",
          "weight": "Bolder"
        },
        {
          "type": "ProgressBar",
          "value": 33
        }
      ]
    },
    {
      "type": "Container",
      "spacing": "Medium",
      "items": [
        {
          "type": "TextBlock",
          "text": "💡 Pro tip: Use the STAR method (Situation, Task, Action, Result) when describing accomplishments.",
          "wrap": true,
          "size": "Small",
          "isSubtle": true
        }
      ]
    }
  ],
  "actions": [
    {
      "type": "Action.OpenUrl",
      "title": "Open Self-Assessment",
      "url": "https://reviews.company.com/self-assessment",
      "style": "positive"
    },
    {
      "type": "Action.OpenUrl",
      "title": "View Preparation Guide",
      "url": "https://reviews.company.com/guide"
    }
  ]
}
```

---

## Card 5: Tech Support Contact Card

**Use Case**: Provide all IT support contact options in one card.

### Preview
```
┌────────────────────────────────────────────┐
│ 🛠️ IT Support Contact Options              │
├────────────────────────────────────────────┤
│ Choose the best way to reach IT support:   │
│                                            │
│ [💬 Live Chat] (Fastest - 2 min wait)      │
│ Available: Mon-Fri, 8am-6pm ET            │
│                                            │
│ [📞 Call Help Desk] (5 min wait)           │
│ Phone: 1-800-555-0100                     │
│                                            │
│ [✉️ Submit Ticket] (4-6 hour response)     │
│ For non-urgent issues                     │
│                                            │
│ [📱 Teams Chat] (Internal only)            │
│ Message @ITSupport                        │
└────────────────────────────────────────────┘
```

### JSON Code
```json
{
  "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
  "type": "AdaptiveCard",
  "version": "1.4",
  "body": [
    {
      "type": "TextBlock",
      "text": "🛠️ IT Support Contact Options",
      "weight": "Bolder",
      "size": "Large",
      "color": "Accent"
    },
    {
      "type": "TextBlock",
      "text": "Choose the best way to reach IT support:",
      "wrap": true,
      "spacing": "Small"
    },
    {
      "type": "Container",
      "style": "good",
      "spacing": "Medium",
      "items": [
        {
          "type": "ColumnSet",
          "columns": [
            {
              "type": "Column",
              "width": "auto",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "💬",
                  "size": "Large"
                }
              ]
            },
            {
              "type": "Column",
              "width": "stretch",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "Live Chat (Fastest)",
                  "weight": "Bolder"
                },
                {
                  "type": "TextBlock",
                  "text": "Average wait: 2 minutes",
                  "size": "Small",
                  "color": "Good"
                },
                {
                  "type": "TextBlock",
                  "text": "Available: Mon-Fri, 8am-6pm ET",
                  "size": "Small",
                  "isSubtle": true
                }
              ]
            }
          ]
        }
      ],
      "selectAction": {
        "type": "Action.OpenUrl",
        "url": "https://support.company.com/chat"
      }
    },
    {
      "type": "Container",
      "style": "emphasis",
      "spacing": "Small",
      "items": [
        {
          "type": "ColumnSet",
          "columns": [
            {
              "type": "Column",
              "width": "auto",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "📞",
                  "size": "Large"
                }
              ]
            },
            {
              "type": "Column",
              "width": "stretch",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "Call Help Desk",
                  "weight": "Bolder"
                },
                {
                  "type": "TextBlock",
                  "text": "Phone: 1-800-555-0100",
                  "size": "Small"
                },
                {
                  "type": "TextBlock",
                  "text": "Average wait: 5 minutes",
                  "size": "Small",
                  "isSubtle": true
                }
              ]
            }
          ]
        }
      ],
      "selectAction": {
        "type": "Action.OpenUrl",
        "url": "tel:18005550100"
      }
    },
    {
      "type": "Container",
      "style": "emphasis",
      "spacing": "Small",
      "items": [
        {
          "type": "ColumnSet",
          "columns": [
            {
              "type": "Column",
              "width": "auto",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "✉️",
                  "size": "Large"
                }
              ]
            },
            {
              "type": "Column",
              "width": "stretch",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "Submit Ticket",
                  "weight": "Bolder"
                },
                {
                  "type": "TextBlock",
                  "text": "For non-urgent issues",
                  "size": "Small"
                },
                {
                  "type": "TextBlock",
                  "text": "Response time: 4-6 hours",
                  "size": "Small",
                  "isSubtle": true
                }
              ]
            }
          ]
        }
      ],
      "selectAction": {
        "type": "Action.OpenUrl",
        "url": "https://support.company.com/ticket"
      }
    },
    {
      "type": "Container",
      "style": "emphasis",
      "spacing": "Small",
      "items": [
        {
          "type": "ColumnSet",
          "columns": [
            {
              "type": "Column",
              "width": "auto",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "📱",
                  "size": "Large"
                }
              ]
            },
            {
              "type": "Column",
              "width": "stretch",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "Teams Chat",
                  "weight": "Bolder"
                },
                {
                  "type": "TextBlock",
                  "text": "Message @ITSupport channel",
                  "size": "Small"
                },
                {
                  "type": "TextBlock",
                  "text": "Internal employees only",
                  "size": "Small",
                  "isSubtle": true
                }
              ]
            }
          ]
        }
      ],
      "selectAction": {
        "type": "Action.OpenUrl",
        "url": "https://teams.microsoft.com/l/channel/..."
      }
    }
  ]
}
```

---

## Card 6: Course Recommendation

**Use Case**: Recommend learning courses based on user's role or goals.

### JSON Code
```json
{
  "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
  "type": "AdaptiveCard",
  "version": "1.4",
  "body": [
    {
      "type": "TextBlock",
      "text": "📚 Recommended for You",
      "weight": "Bolder",
      "size": "Large",
      "color": "Accent"
    },
    {
      "type": "TextBlock",
      "text": "Based on your role as Software Engineer II",
      "isSubtle": true,
      "spacing": "None"
    },
    {
      "type": "Container",
      "style": "emphasis",
      "spacing": "Medium",
      "items": [
        {
          "type": "Image",
          "url": "https://via.placeholder.com/400x200/0078D4/FFFFFF?text=System+Design+Fundamentals",
          "size": "Large"
        },
        {
          "type": "TextBlock",
          "text": "System Design Fundamentals",
          "weight": "Bolder",
          "size": "Medium",
          "spacing": "Medium"
        },
        {
          "type": "FactSet",
          "facts": [
            {
              "title": "Duration:",
              "value": "6 hours"
            },
            {
              "title": "Level:",
              "value": "Intermediate"
            },
            {
              "title": "Rating:",
              "value": "⭐ 4.8/5 (234 reviews)"
            }
          ]
        },
        {
          "type": "TextBlock",
          "text": "Learn to design scalable systems, understand trade-offs, and prepare for technical leadership roles.",
          "wrap": true,
          "spacing": "Medium"
        }
      ]
    }
  ],
  "actions": [
    {
      "type": "Action.OpenUrl",
      "title": "Enroll Now",
      "url": "https://learning.company.com/courses/system-design",
      "style": "positive"
    },
    {
      "type": "Action.OpenUrl",
      "title": "Add to Wishlist",
      "url": "https://learning.company.com/wishlist"
    },
    {
      "type": "Action.OpenUrl",
      "title": "View More Recommendations",
      "url": "https://learning.company.com/recommended"
    }
  ]
}
```

---

## Card 7: Feedback Collection

**Use Case**: Collect user feedback after interaction.

### JSON Code
```json
{
  "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
  "type": "AdaptiveCard",
  "version": "1.4",
  "body": [
    {
      "type": "TextBlock",
      "text": "How was your experience?",
      "weight": "Bolder",
      "size": "Large"
    },
    {
      "type": "TextBlock",
      "text": "Your feedback helps us improve LearnFlow Assistant",
      "wrap": true,
      "isSubtle": true,
      "spacing": "Small"
    },
    {
      "type": "Input.ChoiceSet",
      "id": "satisfaction",
      "label": "How satisfied are you with the help you received?",
      "style": "expanded",
      "choices": [
        {
          "title": "😀 Very Satisfied",
          "value": "5"
        },
        {
          "title": "🙂 Satisfied",
          "value": "4"
        },
        {
          "title": "😐 Neutral",
          "value": "3"
        },
        {
          "title": "🙁 Dissatisfied",
          "value": "2"
        },
        {
          "title": "😞 Very Dissatisfied",
          "value": "1"
        }
      ]
    },
    {
      "type": "Input.Text",
      "id": "comments",
      "label": "Any additional comments? (Optional)",
      "isMultiline": true,
      "placeholder": "Tell us more about your experience..."
    }
  ],
  "actions": [
    {
      "type": "Action.Submit",
      "title": "Submit Feedback",
      "data": {
        "action": "submitFeedback"
      }
    },
    {
      "type": "Action.Submit",
      "title": "Skip",
      "data": {
        "action": "skip"
      }
    }
  ]
}
```

**Note**: To handle Action.Submit in Copilot Studio, you'll need to configure a Power Automate flow to receive and process the feedback.

---

## Card 8: Escalation Confirmation

**Use Case**: Confirm that a support ticket or escalation has been created.

### JSON Code
```json
{
  "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
  "type": "AdaptiveCard",
  "version": "1.4",
  "body": [
    {
      "type": "Container",
      "style": "good",
      "items": [
        {
          "type": "ColumnSet",
          "columns": [
            {
              "type": "Column",
              "width": "auto",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "✓",
                  "size": "ExtraLarge",
                  "color": "Good",
                  "weight": "Bolder"
                }
              ]
            },
            {
              "type": "Column",
              "width": "stretch",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "Support Ticket Created",
                  "weight": "Bolder",
                  "size": "Large",
                  "color": "Good"
                },
                {
                  "type": "TextBlock",
                  "text": "Your request has been submitted to our IT support team",
                  "wrap": true,
                  "spacing": "None"
                }
              ]
            }
          ]
        }
      ]
    },
    {
      "type": "FactSet",
      "spacing": "Medium",
      "facts": [
        {
          "title": "Ticket Number:",
          "value": "INC0012345"
        },
        {
          "title": "Priority:",
          "value": "Medium"
        },
        {
          "title": "Estimated Response:",
          "value": "4-6 hours"
        },
        {
          "title": "Assigned To:",
          "value": "IT Support Team"
        }
      ]
    },
    {
      "type": "TextBlock",
      "text": "What happens next:",
      "weight": "Bolder",
      "spacing": "Medium"
    },
    {
      "type": "TextBlock",
      "text": "1. Our IT team will review your request\n2. You'll receive an email confirmation shortly\n3. A support agent will contact you within 4-6 hours\n4. Track your ticket status using the link below",
      "wrap": true,
      "spacing": "Small"
    },
    {
      "type": "Container",
      "style": "emphasis",
      "spacing": "Medium",
      "items": [
        {
          "type": "TextBlock",
          "text": "💡 Meanwhile, you can check our Knowledge Base for quick solutions.",
          "wrap": true,
          "size": "Small"
        }
      ]
    }
  ],
  "actions": [
    {
      "type": "Action.OpenUrl",
      "title": "Track Ticket Status",
      "url": "https://support.company.com/ticket/INC0012345",
      "style": "positive"
    },
    {
      "type": "Action.OpenUrl",
      "title": "Browse Knowledge Base",
      "url": "https://support.company.com/kb"
    }
  ]
}
```

---

## 🎨 Design Best Practices

### Visual Hierarchy
- Use **size** and **weight** to emphasize important information
- Group related content in containers
- Use spacing strategically (Medium for sections, Small within sections)

### Color Usage
- **Accent**: Headers and important titles
- **Good** (Green): Success states, completed items
- **Attention** (Orange/Yellow): Warnings, urgent deadlines
- **Warning** (Red): Errors, critical issues
- **Default**: Regular content

### Accessibility
- Always include descriptive alt text for images
- Use sufficient color contrast
- Don't rely on color alone to convey meaning
- Keep text concise and readable

### Interactive Elements
- Use Action.OpenUrl for external links
- Use Action.Submit for form submissions (requires Power Automate)
- Use selectAction on containers for clickable cards
- Provide clear button labels

### Mobile Optimization
- Test cards on mobile devices
- Use ColumnSets with appropriate widths
- Avoid horizontal scrolling
- Keep images responsive

---

## 🔧 Testing Adaptive Cards

### Online Designer
Use the [Adaptive Cards Designer](https://adaptivecards.io/designer/) to:
- Preview cards in real-time
- Test on different platforms (Teams, Outlook, etc.)
- Validate JSON schema
- Export code

### Testing in Copilot Studio
1. Create a test topic
2. Add "Send a message" → "Adaptive Card"
3. Paste JSON code
4. Use **Test copilot** panel to preview
5. Check mobile view using browser dev tools

---

## 📚 Additional Resources

- [Adaptive Cards Documentation](https://adaptivecards.io/)
- [Adaptive Cards Schema Explorer](https://adaptivecards.io/explorer/)
- [Adaptive Cards Samples](https://adaptivecards.io/samples/)
- [Teams Adaptive Card Templates](https://learn.microsoft.com/microsoftteams/platform/task-modules-and-cards/cards/design-effective-cards)

---

*Last Updated: December 2025*
*Version: 1.0*
