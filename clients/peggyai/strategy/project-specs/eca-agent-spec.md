# ECA Agent System - Technical Specification

## Overview
Building an agent-based system to automatically extract, parse, and manage extracurricular activity information for the Peggy AI parenting assistant app.

## System Architecture

### Core Components

#### 1. Email Scanner Agent
- **Purpose:** Identify relevant extracurricular emails
- **Input:** Gmail inbox access, activity type, child name
- **Output:** List of potential source emails
- **Implementation:** 
  - Header-only scanning initially (privacy-first)
  - Pattern matching for activity keywords
  - Domain identification

#### 2. Program Extraction Agent
- **Purpose:** Extract program details from approved sources
- **Input:** Email content, website URLs, attachments
- **Output:** Structured program information
- **Fields to Extract:**
  - Program name
  - Organization/provider
  - Start/end dates
  - Schedule (days, times)
  - Location
  - Cost
  - Required equipment
  - Contact information

#### 3. Website Parser Agent
- **Purpose:** Visit and extract information from program websites
- **Challenges:**
  - Login walls
  - Dynamic content
  - Varying structures
- **Approach:**
  - Initial: Public pages only
  - Future: Browser automation for login-protected content

#### 4. Attachment Processor Agent
- **Purpose:** Parse PDFs and documents for actionable information
- **Implementation:**
  - Large context window models (Gemini)
  - Identify actionable vs. informational content
  - Extract tasks and calendar items

#### 5. Item Card Generator
- **Purpose:** Create structured, actionable cards for parents
- **Components:**
  - Summary information
  - Calendar entries
  - Task list
  - Quick actions (assign, remind, archive)

## Data Flow

```
1. Parent Input
   └── Activity Type + Child Name
       
2. Email Discovery
   └── Scan headers → Present sources → Get approval
       
3. Information Extraction
   ├── Read approved emails
   ├── Visit linked websites
   └── Process attachments
       
4. Program Confirmation
   └── Present extracted data → Parent confirms/edits
       
5. Ongoing Monitoring
   ├── Watch for new emails
   ├── Check website updates
   └── Generate item cards
```

## Technical Stack

### Development Environment
- **Framework:** Cloud Code with subagents
- **Container:** Docker
- **API:** RESTful/gRPC to match Peggy's infrastructure
- **Database:** PostgreSQL (local mirror of production schema)

### AI/ML Components
- **Email Parsing:** GPT-4o-mini with structured outputs
- **Web Scraping:** Browser automation (Playwright/Puppeteer)
- **Document Processing:** Large context models
- **Evaluation:** Braintrust for testing prompts

### Integration Points
- Gmail API for email access
- Google Calendar API for calendar management
- Peggy AI backend API for data persistence

## Implementation Phases

### Phase 1: Proof of Concept (Terminal-based)
- No UI, terminal interface only
- Focus on capability validation
- 10-25 test cases
- Success metric: 90% accuracy in program identification

### Phase 2: Production Prototype
- Docker containerization
- API implementation
- Error handling and retries
- Monitoring and logging

### Phase 3: Integration
- Connect to Peggy's production systems
- UI integration (iOS app)
- User feedback loops
- Performance optimization

## Key Challenges & Solutions

### Challenge 1: Fragmented Data Sources
- **Solution:** Multiple specialized agents for different source types

### Challenge 2: Login-Protected Content
- **Initial:** Skip or request manual input
- **Future:** Browser automation with stored credentials

### Challenge 3: Information Variety
- **Solution:** Flexible NoSQL-like structure for program data

### Challenge 4: Parent Trust
- **Solution:** Explicit confirmation steps, transparency in AI actions

### Challenge 5: Cost Management
- **Solution:** Start with best models, optimize later with smaller models

## Privacy & Security

### Principles
- Explicit permission for each email source
- No automatic reading without approval
- Secure credential storage for future login features
- Clear data retention policies

### Implementation
- Header-only scanning for discovery
- Source-level permissions
- Audit trail of AI actions
- Parent review before automation

## Success Metrics

### Technical
- 90%+ accuracy in program identification
- <5 second response time for email parsing
- 95%+ success rate in calendar extraction

### User Experience
- <2 minutes to add new extracurricular
- Single confirmation step for program details
- Zero missed important dates/tasks

### Business
- Reduce parent time spent on logistics by 50%
- Increase app engagement to 3x weekly
- Enable premium tier pricing with ECA features

## Future Enhancements

### Near-term (3-6 months)
- Registration automation
- Equipment purchase links
- Carpool coordination
- Performance analytics from instructors

### Long-term (6-12 months)
- Discovery of new programs
- Parent-led activity creation
- Multi-family coordination
- College application portfolio building