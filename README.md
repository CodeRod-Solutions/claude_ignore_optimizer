# .claudeignore Optimizer

Universal tool for optimizing Claude Code token usage by 50-90% across any project type.

## Problem

Claude Code loads unnecessary files (build artifacts, caches, dependencies, .git/ objects) into context, wasting tokens and slowing performance. Manual .claudeignore creation is tedious and error-prone.

## Solution

This skill automatically:
- ✅ Analyzes your project structure
- ✅ Detects frameworks, languages, and patterns
- ✅ Identifies token-heavy directories
- ✅ Generates optimized .claudeignore file
- ✅ Saves 50-90% on token usage per session

## Supported Technologies

**Languages:**
JavaScript/TypeScript, Python, Go, Rust, Ruby, PHP, Java, and more

**Frameworks:**
Next.js, React, Django, FastAPI, Rails, Laravel, and more

**Tools:**
Docker, GCP, AWS, Vercel, Drizzle, Prisma, Vitest, Jest, Pytest

## Platform Support

**✅ Fully Supported:**
- Claude Desktop (recommended)
- Claude Web (claude.ai)

**❌ Not Supported:**
- Claude Code (CLI) - While Claude Code has skill capability, custom skill installation method is not currently documented

## Installation

### Prerequisites

Install the `tree` command:

```bash
# macOS
brew install tree

# Linux (Ubuntu/Debian)
sudo apt-get install tree

# Verify
tree --version
```

### Install the Skill

#### Claude Desktop (Recommended)
1. Download `ignore-optimizer.skill`
2. Open Claude Desktop
3. Settings → Skills
4. Drag and drop the .skill file
5. Done!

#### Claude Web
1. Download `ignore-optimizer.skill`  
2. Go to claude.ai
3. Profile → Skills
4. Upload the .skill file
5. Done!

## Usage

### Step 1: Generate Project Structure

```bash
cd ~/projects/your-project

tree -L 3 -I 'node_modules|dist|build|coverage' --filesfirst -a > project_structure.txt
```

**What this does:**
- `-L 3` - Shows 3 levels deep
- `-I` - Excludes noise directories
- `--filesfirst` - Files before directories
- `-a` - Includes hidden files

### Step 2: Use the Skill

**In Claude Desktop or Claude Web:**

1. Start a new conversation
2. Upload `project_structure.txt` OR paste its contents
3. Say: **"Use the ignore-optimizer skill on this project"**

### Step 3: Answer Questions

```
Q: Keep ai_docs/ visible? [Y/n]
Q: Primary AI tool? (.claude/.cursor/.windsurf)
Q: Ignore duplicate configs? [Y/n]
Q: Keep test files visible? [Y/n]
```

### Step 4: Download & Use

```
✅ Created .claudeignore

📥 [Download .claudeignore](link)

Token reduction: 70% (500 → 150 files)
```

1. Download the file
2. Copy to your project root as `.claudeignore`
3. Commit: `git add .claudeignore && git commit -m "Add .claudeignore"`
4. Use Claude Code - notice the improvement!

## Real-World Results

**Next.js + TypeScript + Drizzle:**
- Before: 1,549 files
- After: 387 files
- **Reduction: 75%**
- **Savings: ~581,000 tokens per session**

**Python + FastAPI + GCP:**
- Before: ~800 files
- After: ~100 files
- **Reduction: 85%**
- **Savings: ~350,000 tokens per session**

**Typical Weekly Impact:**
- 20 Claude Code sessions per project
- 3-5 active projects
- **Total savings: 30-50 million tokens per week**

## When to Use

**Initial Setup:**
- Starting a new project
- First time using Claude Code on existing project

**Regular Maintenance:**
- Every 4 weeks during active development
- When project structure changes
- After adding major features

**Performance Issues:**
- Claude Code feels slow
- Token usage is high
- Hitting usage limits
- Claude mentions irrelevant files

## Features

### Smart Documentation Detection
- Detects `ai_docs/`, `docs/`, `planning/`, `design/`
- Asks about archive subdirectories (`completed/`, `scratch/`)
- Supports project evolution (keep initially, ignore later)

### Multiple AI Tool Handling
- Detects `.claude/`, `.cursor/`, `.windsurf/`, `.aider/`, `.cline/`
- Asks which is primary
- Ignores duplicates to reduce redundancy

### Project Evolution Support
- **Week 1:** Keep everything (max context)
- **Week 4+:** Ignore completed work
- **Month 3+:** Minimal context (maintenance mode)

### Universal Patterns
Works across 15+ languages, 20+ frameworks, all major cloud platforms and ORMs.

## What Gets Ignored

**Always (token hogs):**
- Build artifacts (`.next/`, `dist/`, `build/`)
- Dependencies (`node_modules/`, `venv/`)
- Git internals (`.git/`)
- Lock files (`package-lock.json`, `yarn.lock`)
- IDE configs (`.vscode/`, `.idea/`)
- OS files (`.DS_Store`)

**Kept (valuable):**
- Source code
- Configuration files
- Documentation (unless archived)
- Your primary AI tool configs
- Test files (optional)

## Troubleshooting

**"tree command not found"**
- Install: `brew install tree` or `apt-get install tree`

**"Too many files ignored"**
- Re-run and answer questions differently
- Manually edit .claudeignore

**"Not enough improvement"**
- Check for large data/media directories
- Look for project-specific artifacts

## Updating the Skill

**To update:**
1. Remove old version (Settings → Skills → Remove)
2. Install new version (drag and drop new .skill file)

**Check version:**
- Look for download link in output
- v1.1.1+ provides clean downloadable .claudeignore file

## Contributing

Found a pattern we don't support? 

1. Use the skill
2. Tell Claude what wasn't detected
3. Claude can update the skill
4. Share the improvement!

## License

MIT License - Free to use, modify, and share.

## Credits

Built and validated through real-world use across production projects.

**Author:** Rod Morrison

---

**Start saving millions of tokens today.** Install the skill and optimize your first project in under 2 minutes.
