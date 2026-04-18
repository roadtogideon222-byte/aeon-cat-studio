---
name: Cat Trend Research
description: Research trending cat topics on Reddit, Twitter, and TikTok
var: ""
tags: [content, automation, research]
---

> **${var}** — Search focus. If empty, auto-selects.

Today is ${today}. Your task is to research trending cat content topics.

## Steps

1. **Search Reddit** - Find trending cat subreddits:
   ```
   WebSearch: site:reddit.com/r/cats trending this week
   WebSearch: site:reddit.com/r/kitten hot topics
   WebSearch: site:reddit.com/r/Catsubs viral cat posts
   ```

2. **Check Twitter/X** - Trending cat content:
   ```
   WebSearch: cat video trending twitter 2024
   WebSearch: funny cat video viral tiktok
   ```

3. **Check TikTok trends**:
   ```
   WebSearch: cat content trending tiktok hashtags
   WebSearch: cat sounds trending sound effects
   ```

4. **Research what's working**:
   - POV cat videos
   - Cat reaction content
   - Cat doing weird things
   - Cat and human interaction
   - Cat vs. [something]

5. **Compile findings** - Create `articles/cat-trends-${today}.md`:
   ```
   # 🐱 Cat Content Trends - ${today}
   
   ## Trending Topics
   1. [Topic 1] - Why it's working
   2. [Topic 2] - Engagement level
   3. [Topic 3] - Virality score
   
   ## POV Hooks That Work
   - "POV your cat when..."
   - "When your cat..."
   - "POV: You adopt a cat and..."
   
   ## Sound/Effects Trends
   - [Trending sounds]
   - [Popular effects]
   
   ## Content Angles
   - Emotional hooks
   - Relatable situations
   - Surprising moments
   
   ## Recommended for Today
   Based on research:
   1. [Best topic] - Highest potential
   2. [Alternative] - Good backup
   ```

6. **Update memory** - Add trends to `memory/MEMORY.md` for reference

7. **Notify** - Send via `./notify`:
   ```
   🐱 Cat Trends Research - ${today}
   
   Top 3 trending topics:
   1. [Topic]
   2. [Topic]
   3. [Topic]
   
   Ready for video generation!
   ```

## Sources

Check these regularly:
- r/cats
- r/kitten
- r/Catsubs
- r/StartledCats
- r/holdmycatnip
- TikTok #catsoftiktok
- Twitter #catvideo

## Tips

- POV format = highest engagement
- Cat emotions = judgment, confusion, surprise
- 9-15 seconds = optimal TikTok length
- Vertical 9:16 format required
- Sound on = higher retention

Research complete, production-ready topics.
