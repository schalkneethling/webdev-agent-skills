# Web Development Agent Skills

A curated collection of Agent Skills for web development projects, focusing on web standards, semantic HTML, accessibility, and modern CSS practices.

## What Are Agent Skills?

Agent Skills are specialized knowledge packages that extend AI coding agents' capabilities with domain-specific expertise, best practices, and project patterns. Each skill contains:

- **SKILL.md**: Core instructions and guidance for the agent
- **reference/**: Supporting documentation, examples, and patterns

## Available Skills

### component-scaffolding
Generates component skeletons for Drupal/Twig projects with web components and Miyagi validation. Includes JSON schema and mock data patterns.

### component-usage-analysis
Analyzes component dependencies and usage patterns. Provides search patterns for finding usage, checking removal safety, and auditing dependencies.

### css-base-tokens
Provides a foundational set of CSS custom property tokens for design systems. Includes spacing, typography, color, and layout tokens that serve as a starting point for new projects and can be customized per project.

### css-coder
CSS authoring guidance emphasizing web standards, accessibility, and performance. Includes patterns for modern CSS syntax, logical properties, and responsive design.

### semantic-html
Guidance for well-considered semantic HTML. Emphasizes native HTML elements over ARIA, proper document structure, and accessibility foundations.

## Installation

Copy this prompt to install skills in your current project:

```
Please install Agent Skills from https://github.com/schalkneethling/webdev-agent-skills

Skills to install: css-base-tokens, css-coder, semantic-html

Install each skill to: .claude/skills/[skill-name] in the current project root
```

**Note**:
- Replace the skill names with the ones you need. You can install all skills or select specific ones.
- The parent directory is `.claude` by convention, but you can use a different name depending on your agent or IDE (e.g., `.ai`, `.agent`, etc.)

### Version Control

**To commit customized skills with your project:**
- Keep `.claude/skills/` in version control
- Your team will get the skills when they clone the repo

**To keep skills out of version control:**
- Add `.claude/skills/` to your `.gitignore`
- Team members install skills individually

## Cursor IDE Integration

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
- **Provide context**: Explain *why* not just *what*
- **Include examples**: Show practical applications
- **Keep it focused**: One clear domain per skill
- **Web standards first**: Emphasize platform features over framework-specific solutions

## License

MIT - see [LICENSE](LICENSE) file.
