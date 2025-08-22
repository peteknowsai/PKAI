# PKAI Monorepo - Pete Knows AI

## Overview
This monorepo contains all client projects, documentation, and resources for Pete Knows AI (PKAI). We manage software development projects, communication logs, invoices, statements of work, and strategic documents for multiple clients.

## Repository Structure

```
PKAI/
├── clients/                  # Client-specific projects and resources
│   ├── atomic/              # Atomic client
│   │   ├── projects/        # Active software projects
│   │   ├── communications/  # Emails, meeting notes
│   │   ├── documents/       # SOWs, invoices, contracts
│   │   └── strategy/        # Strategic planning docs
│   │
│   ├── fidelity/           # Fidelity client
│   │   ├── projects/       # cells, fidelity-mvp, cc-container
│   │   ├── communications/
│   │   ├── documents/
│   │   └── strategy/
│   │
│   ├── p32/                # P32/Port32 client
│   │   ├── projects/       # boat32, excel-mcp, bank-draw
│   │   ├── communications/
│   │   ├── documents/
│   │   └── strategy/
│   │
│   └── peggyai/            # PeggyAI client
│       ├── projects/
│       ├── communications/
│       ├── documents/
│       └── strategy/
│
├── shared/                  # Shared resources across clients
│   ├── templates/          # Business document templates
│   ├── tools/              # Shared development tools
│   └── configs/            # Shared configurations
│
└── docs/                    # Overall PKAI documentation
```

## Client Projects

### Active Clients

#### 🔷 Atomic
- **Status:** Active
- **Focus:** Monthly insights and analytics projects
- **Key Deliverables:** Atomic Insights monthly proposals

#### 🔷 Fidelity
- **Status:** Active
- **Focus:** Cell-based architecture, resource management system
- **Key Projects:**
  - `cells` - Cell-based autonomous agent system
  - `fidelity-mvp` - Main application with Convex backend
  - `cc-container` - Containerized deployment solution

#### 🔷 P32 (Port32)
- **Status:** Active
- **Focus:** Various development projects including Boat32 app
- **Key Projects:**
  - `boat32` - Boat image transformation application
  - `excel-mcp-server` - Excel MCP integration
  - `p32-bank-draw` - Bank draw management system

#### 🔷 PeggyAI
- **Status:** Planning/Discovery Phase
- **Focus:** AI-powered educational calendar assistant
- **Approach:** Claude Code-based agentic workflow system

## Quick Start

### Prerequisites
- Node.js >= 18.0.0
- pnpm >= 8.0.0

### Installation
```bash
# Install pnpm if not already installed
npm install -g pnpm@8.15.0

# Install all dependencies
pnpm install

# Run all projects in development mode
pnpm dev
```

### Working with Specific Clients
```bash
# Work with a specific client's projects
pnpm client:atomic    # Atomic client
pnpm client:fidelity  # Fidelity client
pnpm client:p32       # P32 client
pnpm client:peggyai   # PeggyAI client
```

## Development Guidelines

### Project Organization
1. **Client Isolation:** Each client's work is completely isolated in their own directory
2. **Standardized Structure:** All clients follow the same directory structure for consistency
3. **Nested Repos:** Projects may contain their own git repositories within the monorepo
4. **Documentation:** Each project should have its own README and CLAUDE.md files

### File Management
- **Projects:** Active codebases and development work
- **Communications:** Email threads, meeting notes, call logs
- **Documents:** Contracts, SOWs, invoices, proposals
- **Strategy:** Roadmaps, planning documents, research

### Security & Privacy
- Client data is isolated and never shared between clients
- Sensitive information should be stored in environment variables
- Follow security best practices for each client's requirements

## Shared Resources

### Templates
Standard PKAI business templates are available in `/shared/templates/`:
- Discovery session outlines
- Engagement letters
- Monthly retainer agreements
- Statements of work
- Project completion summaries

### Tools & Configurations
Shared development tools and configurations in `/shared/`:
- Linting and formatting configs
- TypeScript configurations
- Docker templates
- CI/CD workflows

## Contributing

### Adding a New Client
1. Create directory: `clients/[client-name]/`
2. Add standard subdirectories: `projects/`, `communications/`, `documents/`, `strategy/`
3. Create a README.md with client overview
4. Update this main README with client information

### Adding a New Project
1. Place in appropriate client's `projects/` directory
2. Include README.md and CLAUDE.md documentation
3. Add package.json with proper naming: `@pkai/[client]-[project]`
4. Update pnpm-workspace.yaml if needed

## Contact
**Pete Knows AI**
- Organization: PKAI
- Purpose: Technical consulting and software development

---

*This monorepo structure allows us to efficiently manage multiple client relationships while maintaining clear boundaries and organization.*