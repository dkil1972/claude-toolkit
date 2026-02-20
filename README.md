# Claude Toolkit

A Claude Code plugin providing shared skills for software development workflows.

## Skills

| Skill | Invocation | Description |
|-------|-----------|-------------|
| `discover` | `/discover` | Feature discovery conversation that produces structured spec files matching your project's conventions |

## Installation

### Option 1: Plugin marketplace (recommended for teams)

If this repo is registered as a marketplace source:

```
/plugin marketplace add <owner>/claude-toolkit
/plugin install claude-toolkit
```

### Option 2: Local plugin (development / testing)

Clone the repo and point Claude Code at it:

```bash
git clone git@github.com:<owner>/claude-toolkit.git
claude --plugin-dir ./claude-toolkit
```

### Option 3: Direct skill copy

Copy individual skills into your personal skills directory:

```bash
cp -r skills/discover ~/.claude/skills/discover
```

## Usage

### `/discover`

Start a conversation about a proposed feature:

```
/discover user authentication
```

Or just invoke it and start talking:

```
/discover
```

The skill guides you through:
1. **Conversation** — free-form discussion about the feature, grounded in your codebase
2. **Summary** — structured feature brief for alignment before writing anything
3. **Convention detection** — reads your project's existing specs to match their format
4. **Spec generation** — writes OVERVIEW.md and individual spec files

## Structure

```
.claude-plugin/
  plugin.json          # Plugin manifest
skills/
  discover/
    SKILL.md           # Skill definition
    default-template.md  # Fallback spec conventions
```

## Contributing

To add a new skill:

1. Create a directory under `skills/` with your skill name
2. Add a `SKILL.md` with YAML frontmatter and instructions
3. Add supporting files (templates, reference docs) as needed
4. Update this README's skills table
