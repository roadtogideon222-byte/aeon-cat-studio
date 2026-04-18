---
name: Cat Video Generator
description: Generate viral cat videos using the Unified Video Studio
var: ""
tags: [content, automation, video]
---

> **${var}** — Video topic (e.g., "cat judging you" or "cat at 3am"). If empty, auto-selects from trending cat topics.

If `${var}` is set, generate a video about that topic instead of auto-selecting.

Today is ${today}. Your task is to generate a viral cat video.

## Prerequisites

Make sure you're in the cat-automation directory:
```bash
cd /root/.nanobot-ceobot/workspace/cat-automation
```

## Steps

1. **Read memory** - Check `memory/MEMORY.md` for recent videos and what's worked well.

2. **Select topic** - If `${var}` is empty, pick a trending cat video topic:
   - "cat judging you"
   - "cat at 3am"  
   - "cat making weird noises"
   - "POV your cat knows you lied"
   - "cat zoomies at midnight"
   - Random from: https://www.reddit.com/r/Catsubs/

3. **Generate video** - Use the unified video studio:
   ```bash
   cd /root/.nanobot-ceobot/workspace/cat-automation
   python3 unified-video-studio/cli.py generate "${topic}" --style vivid_saturation
   ```

4. **Score for virality** - Check the viral score:
   ```bash
   python3 unified-video-studio/cli.py score outputs/latest.mp4 --topic "${topic}" --detailed
   ```

5. **Update memory** - Record the generated video:
   - Topic
   - Viral score
   - Style used
   - Date generated

6. **Log to file** - Create `memory/logs/${today}.md` with:
   - Topic
   - Viral score
   - Output path
   - What made it good/bad

7. **Notify** - Send notification via `./notify`:
   ```
   🐱 Cat Video Generated!
   
   Topic: ${topic}
   Viral Score: ${score}/100
   Style: vivid_saturation
   
   Generated at: ${now}
   ```

## Quality Gates

- Viral score must be >= 60 for auto-posting
- Score < 60? Regenerate with different style
- Maximum 3 retries per topic

## Output

Videos are saved to: `outputs/`
Subtitles: `temp/subtitles.srt`
Logs: `memory/logs/`

## Tips

- POV hooks score highest for cat content
- 9-15 seconds is the TikTok sweet spot
- Warm tones perform better for pet content
- Questions drive engagement ("tag someone who...")

Generate complete, production-ready videos. No placeholders or TODOs.
