# Meme Analytics Tracker

Track meme performance to learn what resonates with your audience.

## Usage
When user asks to track meme performance or wants analytics on what's working.

## Data Structure

Create/update `meme_performance.json`:

```json
{
  "memes": [
    {
      "id": "2026-02-01-001",
      "template": "Drake-Hotline-Bling",
      "pattern": 1,
      "voice": "weary_realism",
      "topic": "visiting hours",
      "platforms": {
        "x": {
          "posted": "2026-02-01",
          "impressions": 1234,
          "likes": 45,
          "reposts": 12,
          "replies": 5,
          "engagement_rate": 0.05
        },
        "linkedin": {
          "posted": "2026-02-01",
          "impressions": 5678,
          "reactions": 89,
          "comments": 23,
          "shares": 7
        }
      },
      "notes": "Resonated with nurses"
    }
  ],
  "insights": {
    "top_patterns": [1, 8, 4],
    "top_templates": ["Drake", "Woman-Yelling-At-Cat"],
    "best_voice_by_platform": {
      "x": "weary_realism",
      "linkedin": "gentle_education"
    },
    "optimal_posting_times": {
      "x": "08:00 GMT",
      "linkedin": "09:00 GMT"
    }
  }
}
```

## Commands

### Log a meme post
```
/meme-log [meme-id] [platform] [metrics]
```

### Get performance summary
```
/meme-stats [timeframe]
```

### Get recommendations
```
/meme-recommend
```
Returns: Top performing patterns, templates, and voices based on data.

## Analysis Dimensions

Track performance by:
- **Pattern**: Which of the 30 patterns performs best?
- **Template**: Which visual formats get engagement?
- **Voice**: Which tone resonates with audience?
- **Topic**: Which delirium topics spark discussion?
- **Platform**: What works on X vs LinkedIn?
- **Time**: When does posting work best?

## Reporting

Generate weekly/monthly reports:
- Top 5 memes by engagement
- Patterns trending up/down
- Templates to use more/less
- Voice adjustments needed
- Content gaps to fill
