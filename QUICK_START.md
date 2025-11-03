# Quick Start Guide

## Platform Requirements

**✅ Works in:**
- Claude Desktop
- Claude Web (claude.ai)

**❌ Does NOT work in:**
- Claude Code (CLI)

## Prerequisites (One-Time Setup)

Install tree command:

```bash
# macOS
brew install tree

# Linux
sudo apt-get install tree
```

## Installation (30 seconds)

1. Download `ignore-optimizer.skill`
2. Open Claude Desktop or Claude Web
3. Go to Settings/Profile → Skills
4. Drag and drop the .skill file
5. Done!

## First Use (2 minutes)

### Step 1: Generate Project Structure (10 seconds)

```bash
cd ~/projects/your-project

tree -L 3 -I 'node_modules|dist|build|coverage' --filesfirst -a > project_structure.txt
```

### Step 2: Use the Skill (60 seconds)

**In Claude Desktop or Claude Web:**

```
You: "Use the ignore-optimizer skill on this project"

[Upload project_structure.txt]

Claude: 🔍 Analyzing...
        
        Detected: Next.js + TypeScript
        Files: 1,549 total
        
        Questions:
        1. Keep ai_docs/? [Y/n] → y
        2. Primary tool? → .claude
        3. Ignore duplicates? [Y/n] → y
        
        ✅ Created .claudeignore
        📥 [Download link]
        
        Token reduction: 75%
```

### Step 3: Download & Install (30 seconds)

1. Click the download link
2. Copy file to your project:
   ```bash
   cp ~/Downloads/[filename] ~/projects/your-project/.claudeignore
   ```

3. Commit it:
   ```bash
   git add .claudeignore
   git commit -m "Add .claudeignore"
   ```

## Verify It Works

```bash
# Before
find . -type f | grep -v node_modules | wc -l
# Example: 1549 files

# After  
git ls-files --cached --others --exclude-from=.claudeignore | wc -l
# Example: 387 files

# That's 75% reduction!
```

## Next Steps

Use Claude Code normally. You'll notice:
- ⚡ Faster context loading
- 🎯 More focused responses
- 💰 Fewer tokens used
- 🚀 Better performance

## When to Re-Run

- ✅ Every 4 weeks during active development
- ✅ After major structural changes
- ✅ When token usage spikes
- ✅ When Claude Code feels slow

## Common Questions

**Q: Can I use this in Claude Code CLI?**  
A: No - skills only work in Claude Desktop and Claude Web. However, once you generate the .claudeignore file, it will work with Claude Code.

**Q: Do I need to run tree every time?**  
A: Only when your project structure changes significantly or you want to re-optimize.

**Q: What if I don't have tree?**  
A: Install it: `brew install tree` (Mac) or `apt-get install tree` (Linux)

**Q: Can I edit the .claudeignore afterwards?**  
A: Yes! It's just a text file. Edit it anytime.

## Pro Tips

1. **Keep .claude/ visible** - Your primary AI tool configs
2. **Archive completed work** - Move to `ai_docs/completed/` then ignore it
3. **Re-run periodically** - Projects evolve, so should your .claudeignore
4. **Commit it** - Share optimizations with your team

---

**That's it!** From installation to optimized project in under 2 minutes. 🚀
