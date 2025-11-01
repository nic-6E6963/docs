# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

# Mintlify documentation

## Development commands

### Local development
```bash
# Install Mintlify CLI globally
npm i -g mint

# Start local dev server (runs on port 3000 by default)
mint dev

# Start on custom port
mint dev --port 3333

# Update CLI to latest version
mint update

# Validate all links in documentation
mint broken-links
```

### Prerequisites
- Node.js version 19 or higher
- Global Mintlify CLI installed (`npm i -g mint`)

## Project structure

This is a Mintlify documentation site with the following architecture:

- **docs.json**: Central configuration file controlling navigation structure, theme, colors, and site settings. All navigation changes must be reflected here.
- **MDX pages**: Documentation content lives in `.mdx` files with YAML frontmatter
- **Navigation hierarchy**: Organized into tabs (Guides, API reference) with nested groups and pages
- **API documentation**: Can use OpenAPI specs (`api-reference/openapi.json`) or MDX components
- **Snippets**: Reusable content stored in `snippets/` directory for content that appears in multiple places

### Key directories
- `ai-tools/`: Documentation for AI coding assistants
- `api-reference/`: API endpoint documentation and OpenAPI specs
- `essentials/`: Core documentation about using Mintlify features
- `snippets/`: Reusable content fragments

## Working relationship
- You can push back on ideas—this can lead to better documentation. Cite sources and explain your reasoning when you do so
- ALWAYS ask for clarification rather than making assumptions
- NEVER lie, guess, or make up information

## Content strategy
- Document just enough for user success—not too much, not too little
- Prioritize accuracy and usability of information
- Make content evergreen when possible
- Search for existing information before adding new content. Avoid duplication unless it is done for a strategic reason
- Check existing patterns for consistency
- Start by making the smallest reasonable changes

## Frontmatter requirements for pages
All `.mdx` files MUST include:
- `title`: Clear, descriptive page title
- `description`: Concise summary for SEO/navigation
- Optional: `icon` for visual identification in navigation

## Writing standards
- Second-person voice ("you")
- Prerequisites at start of procedural content
- Test all code examples before publishing
- Match style and formatting of existing pages
- Include both basic and advanced use cases
- Language tags on all code blocks
- Alt text on all images
- **Relative paths for internal links** (root-relative preferred: `/writing-content/text`, not `../text`)

## Adding new pages
1. Create the `.mdx` file with required frontmatter
2. Add the page path to `docs.json` navigation structure
3. Test locally with `mint dev` before committing

## Git workflow
- NEVER use --no-verify when committing
- Ask how to handle uncommitted changes before starting
- Create a new branch when no clear branch exists for changes
- Commit frequently throughout development
- NEVER skip or disable pre-commit hooks

## Do not
- Skip frontmatter on any MDX file
- Use absolute URLs for internal links
- Include untested code examples
- Make assumptions—always ask for clarification