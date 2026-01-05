# Web Development Agent Skills

A curated collection of Agent Skills for web development projects, focusing on web standards, semantic HTML, accessibility, security, and modern CSS practices.

## What Are Agent Skills?

Agent Skills are specialized knowledge packages that extend AI coding agents' capabilities with domain-specific expertise, best practices, and project patterns. Each skill contains:

- **SKILL.md**: Core instructions and guidance for the agent
- **reference/**: Supporting documentation, examples, and patterns

## Available Skills

### component-scaffolding

Generates component skeletons for Drupal/Twig projects with web components and Miyagi validation. Includes JSON schema and mock data patterns.

### component-usage-analysis

Analyzes component dependencies and usage patterns. Provides search patterns for finding usage, checking removal safety, and auditing dependencies.

### css-tokens

Provides a foundational set of CSS custom property tokens for design systems. Includes spacing, typography, color, and layout tokens that serve as a starting point for new projects and can be customized per project.

### css-coder

CSS authoring guidance emphasizing web standards, accessibility, and performance. Includes patterns for modern CSS syntax, logical properties, and responsive design.

### frontend-security

Comprehensive security audit capability for frontend codebases. Identifies XSS, CSRF, DOM vulnerabilities, CSP misconfigurations, and dependency issues. Supports React, Astro, Twig, Node.js, and vanilla web platform. Based on OWASP security guidelines with detailed reference documentation for common vulnerability patterns.

### frontend-testing

Write tests that start with acceptance criteria, then add implementation tests for robustness. Use when writing unit tests (Vitest), end-to-end tests (Playwright), visual regression tests, or accessibility tests. Emphasizes user-centric testing, semantic locators, accessibility validation, and the balance between acceptance and implementation testing.

### semantic-html

Guidance for well-considered semantic HTML. Emphasizes native HTML elements over ARIA, proper document structure, and accessibility foundations.

## Installation

### Step 1: Add the install script to your project

Copy this prompt to add the installation script:

```
Please copy the install script from https://github.com/schalkneethling/webdev-agent-skills/blob/main/scripts/install-skills.sh

Save it to: scripts/install-skills.sh in the current project root

Then make it executable: chmod +x scripts/install-skills.sh
```

### Step 2: Install skills using the script

Copy this prompt to install specific skills:

```
Please install these Agent Skills using the install script:

Skills to install: css-coder, semantic-html, frontend-security, frontend-testing

Run: bash scripts/install-skills.sh "css-coder,semantic-html,frontend-security,frontend-testing"

Install to: .claude/skills/ (default) or specify a different directory as the second argument
```

**Notes**:

- The parent directory is `.claude` by convention, but you can use a different name (e.g., `.ai`, `.agent`, etc.)
- Skills are installed to `[target-dir]/[skill-name]/`
- Run the script again anytime to update skills or add new ones
- The script is idempotent—safe to run multiple times

### Version Control

**To commit customized skills with your project:**

- Keep `.claude/skills/` in version control
- Your team will get the skills when they clone the repo

**To keep skills out of version control:**

- Add `.claude/skills/` to your `.gitignore`
- Team members install skills individually

## Cursor IDE Integration (Optional)

If you use [Cursor IDE](https://cursor.sh/), this repository includes a sync script that converts skills to Cursor's rule format (`.mdc` files).

### Installing the Sync Script

Copy this prompt to add the sync script to your project:

```
Please copy the sync script from https://github.com/schalkneethling/webdev-agent-skills/blob/main/scripts/sync-skills-for-cursor.sh

Save it to: scripts/sync-skills-for-cursor.sh in the current project root

Make the script executable: chmod +x scripts/sync-skills-for-cursor.sh
```

### Using the Sync Script

The script reads skills from `.claude/skills/` and converts them to `.cursor/rules/`:

```bash
./scripts/sync-skills-for-cursor.sh
```

This will:

- Read all `SKILL.md` files and reference docs from `.claude/skills/*/`
- Convert them to Cursor's `.mdc` format
- Write them to `.cursor/rules/*.mdc`
- Preserve skill metadata and file-based rule application triggers

Run this script whenever you update your skills to keep Cursor in sync.

## Skill Directory Structure

When installed, each skill follows this structure:

```
.claude/skills/
├── skill-name/
│   ├── SKILL.md           # Core instructions and guidance
│   ├── README.md          # (optional) Additional context
│   └── references/        # (optional) Supporting documentation
│       ├── patterns.md
│       ├── examples.md
│       └── ...
```

**Available skills** and their focus:

| Skill | Purpose | Files |
|-------|---------|-------|
| `css-coder` | CSS authoring with web standards, accessibility, and performance | SKILL.md, references/ |
| `css-tokens` | Design system token foundation (spacing, typography, color) | SKILL.md, references/tokens.css |
| `semantic-html` | Well-considered semantic HTML and accessibility foundations | SKILL.md, references/ |
| `frontend-security` | Security audit for XSS, CSRF, DOM vulnerabilities, and more | SKILL.md, references/ (9 docs) |
| `frontend-testing` | Acceptance and implementation testing strategies | SKILL.md, references/ |
| `component-scaffolding` | Drupal/Twig component skeletons with web components | SKILL.md, references/ |
| `component-usage-analysis` | Component dependency and usage pattern analysis | SKILL.md, references/ |

## Usage

Once installed, skills are automatically available to AI agents when working in your project. The agent will reference the skills when relevant to the task at hand.

You can customize installed skills for your specific project needs - they serve as starting points, not rigid templates.

## Contributing

Contributions are welcome! To add a new skill:

1. **Fork this repository**

2. **Create a skill directory** with this structure:

   ```
   your-skill-name/
   ├── SKILL.md          # Main skill instructions
   └── reference/        # Supporting materials (optional)
       ├── examples/
       └── patterns/
   ```

3. **Write clear SKILL.md content** that includes:
   - Purpose and when to use the skill
   - Key principles and best practices
   - Concrete examples
   - Common patterns or anti-patterns

4. **Submit a pull request** with:
   - Brief description of the skill's purpose
   - Example use cases
   - Any dependencies or prerequisites

### Skill Guidelines

- **Focus on reusability**: Skills should be useful across multiple projects
- **Provide context**: Explain _why_ not just _what_
- **Include examples**: Show practical applications
- **Keep it focused**: One clear domain per skill
- **Web standards first**: Emphasize platform features over framework-specific solutions

## License

MIT - see [LICENSE](LICENSE) file.
