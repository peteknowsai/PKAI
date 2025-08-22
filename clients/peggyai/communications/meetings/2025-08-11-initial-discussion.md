# Meeting Notes: Initial Discussion with Nick Gidwani
**Date:** August 11, 2025  
**Duration:** ~1 hour  
**Participants:** Pete, Nick Gidwani (CEO, Peggy AI)

## Meeting Summary
Nick presented Peggy AI's current state and vision, focusing on two immediate priorities:
1. **Delegate feature** - Automating routine actions based on learned user behavior
2. **Extracurricular Activities (ECA) management** - Extracting and managing sports/activity information

## Peggy AI Overview

### Product Vision
- "Chief of Staff for families" / "Operating system for your family"
- AI-powered parenting assistant app
- Initial wedge: School and activity logistics
- Target: Get parents checking app 2-3 times weekly

### Core App Mechanics
1. **Today Screen** - Daily calendar and reminders
2. **Catch Up** - Swipe interface for triaging new items (left=archive, right=keep)
3. **For You** - Prioritized list of kept items requiring action
4. **Item Cards** - Structured, AI-parsed information with actionable buttons

### Current Technical Implementation
- **LLM Usage:** GPT-4o-mini for email parsing with 8-page, 14-step prompt
- **Evaluation:** Using Braintrust for testing
- **Backend:** Django with gRPC (transitioning from OpenAPI)
- **Integration:** Direct Gmail and Google Calendar integration
- **Mobile:** iOS native app

## Extracurricular Activities (ECA) Project

### Problem Space
- 50% of extracurriculars are sports-related
- Highly fragmented market with no standardization
- Information scattered across emails, websites, attachments, and login-protected portals
- Different complexity levels by age group (5-8: exploration, 8-12: narrowing, 12-16: competitive)

### Proposed Solution Approach

#### Phase 1: Program Identification
1. Parent selects activity type (e.g., "tennis") and child
2. System scans email for relevant sources
3. Parent approves email sources for reading
4. AI reads emails, visits websites, extracts program details
5. Parent confirms program information

#### Phase 2: Item Card Creation
- Extract calendar events (dates, times, locations)
- Identify tasks (equipment purchases, form submissions)
- Parse attachments for additional information
- Monitor websites for updates

### Key Challenges
- Information behind login walls
- Varying information formats across providers
- Need for parent confirmation/QA steps
- Cost-efficiency of LLM usage at scale

## Technical Architecture Discussion

### Data Flow
1. **Email Ingestion** → Parse headers first for privacy
2. **Source Approval** → Parent confirms which emails to read
3. **Content Extraction** → Emails, websites, attachments
4. **Program Confirmation** → Parent verifies extracted data
5. **Ongoing Monitoring** → Watch for new emails/updates

### Agent Architecture
Nick's team has started building with multiple agents:
- Email classification agent
- Extraction agent
- Website parsing agent
- Schedule detection agent

## Action Items for Pete

### Immediate Deliverables
1. **Requirements List** - Define what raw materials needed to start
2. **Proposal** - Document approach and timeline
3. **Architecture Plan** - Docker container with API, terminal-based prototype

### Prototype Specifications
- **Deliverable:** Cloud Code in Docker container with robust API
- **Interface:** Split-screen terminal (Cloud Code + terminal app)
- **Stack:** Match Peggy's PostgreSQL database structure
- **Goal:** Production-ready code, not just proof of concept

### Raw Materials Needed
- Gmail account with 10-25 real extracurricular registration emails
- Mix of simple and complex programs
- Some with/without login requirements
- Variety of sports and non-sports activities
- Access to corresponding websites

## Learning Component
- Nick wants to learn the agent development process
- Pair programming/vibe coding sessions
- Loom videos and async collaboration via GitHub
- Focus on making Nick self-sufficient with the framework

## Next Steps
1. Pete to provide list of required materials (1 week for Nick to gather)
2. Pete to review Nick's existing agent work (Miro board documentation)
3. Begin with terminal-based prototype, no UI initially
4. Focus on capability validation before UI implementation

## Key Insights
- Parents need high trust in AI for delegation features
- QA/confirmation steps critical for parent confidence
- Cost not primary concern - solving the problem is priority
- System should act like a human assistant would (ask when uncertain)
- Focus on habit formation through regular engagement

## Future Vision
- Store all child history (schools, activities, camps)
- Become source of truth for child's life
- Enable college planning with full context
- Parent-led activity creation and coordination
- Analytics on child performance/progress

## Technical Notes
- Using structured outputs from LLMs
- Caching/deduping for shared school emails
- NoSQL consideration for varied ECA data structures
- Privacy-first approach with explicit permissions