# PKAI Monorepo - Claude Code Instructions

## Overview
This is the main monorepo for Pete Knows AI (PKAI) containing all client projects, documentation, and business resources.

## Repository Structure

### Client Organization
Each client has a standardized directory structure:
- `/projects` - Active software development projects
- `/communications` - Email logs, meeting notes, correspondence
- `/documents` - SOWs, proposals, invoices, contracts
- `/strategy` - Strategic documents, roadmaps, planning

### Active Clients
1. **Atomic** - Monthly insights and analytics projects
2. **Fidelity** - Cell-based architecture, resource management
3. **P32/Port32** - Boat32 app, Excel MCP, bank draw system
4. **PeggyAI** - AI-powered educational assistant (planning phase)

## Important Guidelines

### Working with Client Projects
- Each client's work is isolated - never mix client data
- Projects may contain nested git repositories
- Always check for existing CLAUDE.md files in project subdirectories

### File Organization Rules
- Code goes in `/projects`
- Business documents go in `/documents`
- Meeting notes go in `/communications`
- Planning docs go in `/strategy`

### When Creating New Files
- Always prefer editing existing files over creating new ones
- Never create documentation unless explicitly requested
- Follow the existing patterns in each project

### Security Considerations
- Never expose client-specific secrets or API keys
- Keep sensitive financial information in appropriate folders
- Client data must remain isolated

## Common Tasks

### Adding a New Project
1. Place in `clients/[client-name]/projects/`
2. Include README.md with project overview
3. Add CLAUDE.md with specific instructions

### Working with the Monorepo
```bash
# Install dependencies
pnpm install

# Work with specific client
pnpm client:fidelity  # or atomic, p32, peggyai

# Run all projects
pnpm dev
```

### Nested Repositories
Some projects contain their own git repos. This is intentional for:
- Deploying individual projects
- Managing project-specific version control
- Isolating client codebases

## Client-Specific Notes

### Fidelity
- Complex multi-project setup with cells, MVP, and container
- Uses Convex for backend
- Has active cell-based agent system

### P32/Port32
- Boat32 uses Next.js and Convex
- Excel MCP is a Python-based MCP server
- Contains contract templates in documents folder

### PeggyAI
- Focus on Claude Code-based workflows
- Educational component for teaching agentic thinking
- Currently in planning/discovery phase

## Shared Resources
Templates and tools in `/shared` are available for all clients:
- Business document templates
- Development configurations
- Common utilities

Remember: This is a business repository containing both code and business documents. Treat all client information with appropriate confidentiality.