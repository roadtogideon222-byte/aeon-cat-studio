---
name: Morning Cat Report
description: Generate daily cat content report with stats and suggestions
var: ""
tags: [content, automation, report]
---

> **${var}** — Date override (YYYY-MM-DD). If empty, uses today.

Today is ${today}. Your task is to generate a morning cat content report.

## Steps

1. **Read memory** - Check `memory/MEMORY.md` for:
   - Yesterday's generated videos
   - Engagement metrics (if available)
   - What worked well
   - What's been trending

2. **Check outputs** - Review `cat-automation/outputs/`:
   ```bash
   ls -la /root/.nanobot-ceobot/workspace/cat-automation/outputs/
   ```
   Get counts and recent files.

3. **Check engagement** - If tracking file exists:
   ```bash
   cat /root/.nanobot-ceobot/workspace/cat-automation/data/engagement.json 2>/dev/null || echo "No engagement data"
   ```

4. **Check API status**:
   ```bash
   cd /root/.nanobot-ceobot/workspace/cat-automation
   python3 unified-video-studio/cli.py status 2>/dev/null | head -20
   ```

5. **Generate report** - Create `articles/morning-cat-report-${today}.md`:
   ```
   # 🐱 Morning Cat Report - ${today}
   
   ## Yesterday's Content
   - Videos generated: X
   - Average viral score: XX/100
   - Best performer: [topic]
   
   ## Today's Recommendations
   - Trending topics to try
   - Best posting times
   - Style suggestions
   
   ## Pipeline Status
   - API credits: XX
   - Last run: HH:MM
   - Queue status: [pending/active/idle]
   
   ## Action Items
   - [ ] Check engagement metrics
   - [ ] Review best performing videos
   - [ ] Schedule next batch
   ```

6. **Update memory** - Record this report in `memory/MEMORY.md`

7. **Notify** - Send via `./notify`:
   ```
   🐱 Morning Cat Report - ${today}
   
   Yesterday: X videos, avg score XX/100
   Today's focus: [recommended topics]
   
   Pipeline status: ✅ Ready
   ```

## Output

Report saved to: `articles/morning-cat-report-${today}.md`
