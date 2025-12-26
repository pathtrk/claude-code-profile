# Claude Code Profile

Personal configuration repository for [Claude Code](https://claude.com/claude-code) - AI-powered development assistant.

## Overview

This repository contains user-wide settings, custom commands, agents, and preferences for Claude Code. All configurations here apply globally across all projects unless overridden by project-specific settings.

## Repository Structure

```
.claude/
├── CLAUDE.md                # Global instructions for all projects
├── settings.json            # Claude Code settings
├── agents/                  # Custom agent definitions
├── commands/                # Custom slash commands
├── .github/workflows/       # CI/CD workflows (code review, security)
└── history.jsonl            # Conversation history
```

## Key Files

### CLAUDE.md
Contains global instructions that Claude follows in every project:
- Code quality preferences
- Communication language preferences
- Testing requirements
- Documentation standards

### settings.json
Claude Code configuration including:
- Model preferences
- Plugin settings
- UI preferences
- Feature flags

## Custom Commands

Custom slash commands are defined in the `commands/` directory:
- `/design` - Review and update design documentation
- `/test` - Generate unit tests for selected code
- `/docs` - Generate documentation from implementation

## Custom Agents

Specialized agents for specific tasks in the `agents/` directory:
- `runtime-debugger` - Verifies code changes in real environments
- `test-strategist` - Creates test strategies and identifies test cases
- `doc-researcher` - Researches documentation and creates summaries
- `architecture-analyst` - Analyzes codebase architecture

## Project-Specific Configuration

For project-specific instructions that override or supplement global settings, create a `CLAUDE.md` file in your project root:

```
your-project/
├── .git/
├── CLAUDE.md              # Project-specific instructions
├── src/
└── ...
```

See the "Project-Specific Documentation" section below for best practices.

## Plugins

Installed plugins from the marketplace:
- `code-review` - Code review tools
- `commit-commands` - Git commit helpers
- `frontend-design` - UI/UX design assistance
- `feature-dev` - Feature development workflow
- `pr-review-toolkit` - Pull request review tools
- `security-guidance` - Security best practices and vulnerability detection
- `learning-output-style` - Interactive learning mode

## CI/CD Workflows

GitHub Actions workflows in `.github/workflows/`:
- `claude-review.yml` - Automated code review on pull requests
- `security-review.yml` - Security vulnerability scanning

## Usage

Claude Code automatically loads configurations from this directory. When working in any project:

1. Global `CLAUDE.md` instructions always apply
2. Project-specific `CLAUDE.md` (if exists) supplements/overrides global settings
3. Custom commands and agents are available in all sessions

## Project-Specific Documentation

### Creating Project CLAUDE.md

Place a `CLAUDE.md` file in your project root to define project-specific behavior:

**Example: `~/projects/my-app/CLAUDE.md`**

```markdown
# Project: My Web Application

## Architecture
- Next.js 14 with App Router
- TypeScript (strict mode)
- Tailwind CSS for styling
- PostgreSQL database with Prisma ORM

## Code Style
- Use functional components with hooks
- Prefer server components over client components
- All API routes must include error handling and logging
- Database queries must use transactions for multi-step operations

## Testing Requirements
- All business logic must have unit tests (Jest)
- API endpoints require integration tests
- Minimum 80% code coverage

## Specific Rules
- Never commit directly to main branch
- All database migrations must be reversible
- API responses must follow the standard error format defined in /lib/errors.ts
- Use the logging utility in /lib/logger.ts, not console.log

## Domain Context
This is a SaaS platform for project management. Key concepts:
- Workspace: Top-level organization container
- Project: Collection of tasks within a workspace
- Task: Individual work item with status, assignee, and due date
```

### Best Practices for Project CLAUDE.md

1. **Architecture Overview**: Describe tech stack, folder structure, key patterns
2. **Code Standards**: Project-specific coding conventions and patterns
3. **Testing Strategy**: Coverage requirements, testing frameworks, test locations
4. **Domain Knowledge**: Business logic, terminology, important context
5. **Constraints**: What to avoid, deprecated patterns, migration notes
6. **Common Tasks**: Frequent workflows specific to this project

### Global vs Project Settings

| Aspect | Global (this repo) | Project-specific |
|--------|-------------------|------------------|
| Language preference | ✓ | Override if needed |
| Testing philosophy | ✓ | Specific requirements |
| Tech stack | | ✓ |
| Code style | General | ✓ Specific patterns |
| Domain knowledge | | ✓ |
| Architecture | | ✓ |

## Version Control

This repository is git-tracked to:
- Sync settings across machines
- Track configuration changes
- Share custom commands and agents
- Backup conversation history

**Note**: Sensitive credentials (`.credentials.json`) are git-ignored for security.

## Contributing

To add custom commands or agents:
1. Create markdown files in `commands/` or `agents/`
2. Follow the format of existing examples
3. Commit and push to sync across machines

## Resources

- [Claude Code Documentation](https://docs.anthropic.com/claude-code)
- [Plugin Development Guide](https://docs.anthropic.com/claude-code/plugins)
- [Agent SDK](https://docs.anthropic.com/claude-code/agent-sdk)
