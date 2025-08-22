# Action Items - Peggy AI Engagement

## For Pete (Immediate)
- [ ] **Create requirements document** - List all raw materials needed to start development
- [ ] **Write project proposal** - Include approach, timeline, and deliverables
- [ ] **Review existing work** - Examine Nick's team's Miro board and current agent implementation
- [ ] **Set up development environment** - Mirror Peggy's stack (PostgreSQL, Django, gRPC)

## For Nick Gidwani
- [ ] **Gather test data** (1 week timeline)
  - Gmail account with 10-25 real extracurricular registration emails
  - Mix of complexity levels (simple programs to competitive sports)
  - Include examples with/without login requirements
  - Variety of sports and non-sports activities
- [ ] **Share existing work**
  - Miro board documentation
  - Current agent implementation details
  - API documentation
  - Database schema

## Development Milestones

### Phase 1: Program Identification (Week 1-2)
- [ ] Build email scanning capability
- [ ] Implement website parsing agent
- [ ] Create program extraction logic
- [ ] Develop confirmation UI (terminal-based)

### Phase 2: Item Card Creation (Week 3-4)
- [ ] Parse calendar information
- [ ] Extract task lists
- [ ] Process attachments
- [ ] Build monitoring system for updates

### Phase 3: Integration (Week 5-6)
- [ ] Connect to Peggy's API
- [ ] Implement data persistence
- [ ] Add error handling and retry logic
- [ ] Create production deployment setup

## Deliverables
- [ ] Terminal-based prototype application
- [ ] Docker container with Cloud Code
- [ ] API documentation
- [ ] Agent architecture documentation
- [ ] Loom videos explaining implementation
- [ ] GitHub repository with full source code

## Success Criteria
- Successfully identify programs from email with >90% accuracy
- Extract calendar and task information reliably
- Handle edge cases gracefully
- Production-ready code (not just prototype)
- Nick able to modify and extend agents independently

## Questions to Address
- How to handle login-protected content?
- Frequency of website monitoring?
- Cost optimization strategies for LLM usage?
- Privacy and permission management approach?