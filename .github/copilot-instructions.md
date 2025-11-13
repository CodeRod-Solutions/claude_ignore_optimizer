# Copilot Instructions for claude_ignore_optimizer

## Project Overview

This repository contains a Claude skill that helps developers optimize their Claude Code token usage by generating smart `.claudeignore` files. The tool analyzes project structures and creates ignore patterns that can reduce token usage by 50-90%.

## Key Technologies

- **Claude Skills**: Custom skills packaged as `.skill` files that work in Claude Desktop and Claude Web
- **Format**: The main skill file is `ignore-optimizer.skill`, which is a ZIP archive containing markdown files
- **Documentation**: Markdown files for README, QUICK_START, and CHANGELOG

## Repository Structure

```
.
├── ignore-optimizer.skill       # Main skill file (ZIP archive)
├── README.md                    # Main documentation
├── QUICK_START.md              # Quick start guide
├── CHANGELOG.md                # Version history and updates
├── LICENSE                     # MIT License
└── examples/
    └── demo.claudeignore       # Example output file
```

## Important Concepts

### Claude Skills
- Skills are packaged as `.skill` files (ZIP archives)
- Skills only work in Claude Desktop and Claude Web, NOT in Claude Code CLI
- Skills contain a `SKILL.md` file with instructions and reference files

### Token Optimization
- The tool helps reduce context size by ignoring build artifacts, dependencies, and other unnecessary files
- Typical reductions: 50-90% fewer files loaded into context
- Works by analyzing `tree` command output and generating ignore patterns

### File Patterns
- The skill detects various project types: Next.js, React, Python, Go, Rust, etc.
- Recognizes frameworks, ORMs (Drizzle, Prisma), test frameworks, and cloud platforms
- Handles multiple AI tool configs (.claude/, .cursor/, .windsurf/, etc.)

## Code Modification Guidelines

### When modifying the skill:
1. The skill file is a ZIP archive - extract it first before making changes
2. Main logic is in `ignore-optimizer/SKILL.md`
3. Pattern definitions are in `ignore-optimizer/references/patterns.md`
4. Examples are in `ignore-optimizer/references/examples.md`

### When updating documentation:
1. Update all three docs: README.md, QUICK_START.md, and CHANGELOG.md
2. Keep version numbers consistent across files
3. Maintain the conversational, practical tone
4. Include real-world examples and results

### Testing changes:
1. Package the skill as a `.skill` file (ZIP with specific structure)
2. Test in Claude Desktop or Claude Web (not Claude Code CLI)
3. Verify the skill creates downloadable `.claudeignore` files
4. Check that pattern detection works for various project types

## Style Guidelines

- Use emojis for visual clarity (✅, 🎯, 📚, etc.)
- Write in a friendly, practical tone
- Include concrete examples with real numbers
- Emphasize time savings and token reduction metrics
- Keep instructions simple and step-by-step

## Common Tasks

### Adding support for a new framework:
1. Add detection patterns to `patterns.md`
2. Add ignore rules for that framework
3. Update README.md with the new framework in the supported list
4. Test with a project using that framework

### Updating the skill logic:
1. Modify `SKILL.md` in the extracted skill archive
2. Update version number in all files
3. Add entry to CHANGELOG.md
4. Re-package as `.skill` file
5. Test in Claude Desktop/Web

### Documentation updates:
1. Keep the "2-minute setup" promise accurate
2. Update examples with real-world data
3. Ensure platform requirements are clear
4. Verify all links and commands work

## Important Notes

- **Platform limitation**: Skills do NOT work in Claude Code CLI - this is a hard limitation
- **Prerequisites**: Users must have the `tree` command installed
- **Output format**: The skill must create clean, downloadable artifact files (not mixed with analysis)
- **File location**: Generated files should be saved to `/mnt/user-data/outputs/` in Claude environments

## Version History

Current version: v1.1.1
- v1.1.1: Critical fix for downloadable file creation
- v1.1.0: Added smart documentation and multi-tool handling
- v1.0.0: Initial release
