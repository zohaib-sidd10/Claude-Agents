# How to Use the KPI Analyst Agent — agents/01-kpi-analyst/INSTRUCTIONS.md

## Quick Start (2 Minutes)

### Step 1: Prepare Your Metrics

Create a CSV file with your metrics:

```csv
Week,Active Users,Conversion %,Retention %,NPS
Week 1,50000,3.2,68,42
Week 2,52000,3.5,70,45
...
Week 9,49000,3.1,68,42
```

**Minimum:** 4 weeks of data  
**Recommended:** 8+ weeks (for baseline analysis)

### Step 2: Open Claude Code

Open Claude Code or visit claude.ai

### Step 3: Load the System Prompt

**Option A (Manual):**
1. Open `system-prompt.md` from this folder
2. Copy the entire content
3. Paste into Claude as the first message

**Option B (Automatic):**
1. Load `../claude.md` (master configuration)
2. Claude automatically loads this agent's system prompt
3. No manual copy-paste needed

### Step 4: Provide Your Metrics

After the system prompt, provide your metrics:

```
[PASTE YOUR METRICS CSV HERE]
```

Or:

```
Analyze these metrics:
Week 1: Active Users 50K, Conversion 3.2%, Retention 68%, NPS 42
Week 2: Active Users 52K, Conversion 3.5%, Retention 70%, NPS 45
...
Week 9: Active Users 49K, Conversion 3.1%, Retention 68%, NPS 42
```

### Step 5: Get Analysis

Claude will automatically:
1. Analyze your metrics
2. Detect anomalies
3. Explain findings
4. Generate follow-up questions
5. Format for Slack (default)

**Done in 1-2 minutes!**

---

## Detailed Usage Guide

### Understanding the Output

#### Highlights Section
**What it shows:** Metrics that went well

✅ Good interpretation:
```
• Retention increased to 72% (8-week high)
• NPS stable at 48 (on target)
```

❌ Bad interpretation:
```
• Active users increased (no context)
• Metrics moved
```

#### Anomalies Section
**What it shows:** Unusual metric movements and explanations

✅ Good format:
```
• Active Users: 49K (-8% from last week, -6.5% from average)
  Similar to Week 3 dip. Possible causes: seasonal pattern or reduced acquisition.
  Uncertainty: Could be temporary or signal new problem.
```

❌ Bad format:
```
• Active users are down
• Something unusual happened
```

#### Follow-up Questions Section
**What it shows:** Specific investigations to prioritize

✅ Specific questions:
```
1. Did acquisition spend decrease this week?
2. Is the conversion drop related to a specific traffic source?
3. Compare Week 9 churn to Week 3 (similar user dip week)
```

❌ Vague questions:
```
1. What happened?
2. Why are metrics down?
3. Is this good or bad?
```

#### Trends Section
**What it shows:** 4-8 week trajectory and momentum

✅ Good analysis:
```
Active Users: Growing for 6 weeks, declined this week. Need to determine if temporary.
Conversion: Declining for 3 weeks straight (concerning). Investigate cause immediately.
Retention: Stable, no trend change.
```

❌ Bad analysis:
```
Metrics are going up and down
Things have changed
```

---

## Advanced Usage

### Specifying Output Format

**Slack (default):**
```
[No action needed - Slack format is default]
```

**Email:**
```
Analyze these metrics and format as email:
[PASTE METRICS]
```

**JSON:**
```
Analyze these metrics and return as JSON:
[PASTE METRICS]
```

**Markdown:**
```
Analyze these metrics and format as markdown:
[PASTE METRICS]
```

### Providing Context (Optional but Recommended)

Add a Notes column to help the agent:

```csv
Week,Active Users,Conversion %,Retention %,NPS,Notes
Week 1,50000,3.2,68,42,Launch week
Week 2,52000,3.5,70,45,Viral growth + PR
Week 3,48000,3.4,69,43,Seasonal dip (expected)
Week 4,51000,3.6,71,46,Recovery
...
Week 8,53000,3.3,70,45,Notification feature launched
Week 9,49000,3.1,68,42,—
```

The agent uses Notes to:
- Explain anomalies contextually
- Avoid blaming external factors
- Provide specific hypotheses
- Ask more targeted questions

### Comparing Weeks

```
Compare Week 9 to Week 3. Both show similar user dips.
What's the same? What's different?

Metrics for both weeks:
[PASTE BOTH WEEKS' DATA]
```

### Investigating a Specific Metric

```
Focus on conversion rate. It's declined 3 weeks in a row.
What could explain this?

Full metrics for analysis:
[PASTE YOUR METRICS]
```

### Getting Detailed Trend Analysis

```
Provide a deep-dive on trends over the past 12 weeks.
Which metrics are concerning? Which are positive?

[PASTE 12 WEEKS OF DATA]
```

---

## Quality Standards

The agent will automatically:

✅ **Validate your data** — Flag quality issues  
✅ **Calculate changes** — Week-over-week and month-over-month  
✅ **Identify trends** — Is this metric going up or down?  
✅ **Detect anomalies** — What's unusual about this week?  
✅ **Explain findings** — Why did metrics move?  
✅ **Distinguish fact from hypothesis** — Clear about what we know vs. don't  
✅ **Generate questions** — Specific investigations for the PM  
✅ **Format output** — Professional, scannable, ready for Slack  

---

## Tips for Best Results

### Tip 1: Use Consistent Metrics
Don't add/remove metrics mid-stream. Same metrics each week helps trend detection.

❌ Bad:
```
Week 1-3: Active Users, Conversion, Retention
Week 4-6: Active Users, Conversion, Retention, NPS (added NPS)
Week 7-9: Active Users, Conversion (removed Retention)
```

✅ Good:
```
All weeks: Active Users, Conversion, Retention, NPS (consistent)
```

### Tip 2: Use Consistent Calculation Methods
If Retention % is calculated differently in Week 1 vs. Week 9, agent can't detect trends.

❌ Bad:
```
Week 1 Retention: 30-day cohort retention
Week 2 Retention: 7-day cohort retention
```

✅ Good:
```
All weeks: 30-day cohort retention (same definition)
```

### Tip 3: Include at Least 8 Weeks
4 weeks is minimum, but 8+ weeks allows baseline calculation.

❌ Poor:
```
Only 3 weeks of data (no baseline)
```

✅ Good:
```
8-12 weeks of data (clear baseline)
```

### Tip 4: Add Notes Column
Context helps the agent explain anomalies accurately.

❌ No context:
```
Week 5: Active Users 55K (up 10%)
[Agent has to guess why]
```

✅ With context:
```
Week 5: Active Users 55K, Notes: PR coverage + product hunt
[Agent explains the spike with evidence]
```

### Tip 5: Use Realistic Numbers
Don't use obviously fake data if you want realistic insights.

❌ Unrealistic:
```
Week 1: Active Users 1,000,000
Week 2: Active Users 999,999,999
```

✅ Realistic:
```
Week 1: Active Users 50,000
Week 2: Active Users 52,000
```

---

## Example Workflows

### Workflow A: Weekly Review (5 min)

1. Prepare this week's metrics in CSV
2. Paste system prompt
3. Provide metrics
4. Get Slack-formatted report
5. Copy-paste to Slack channel
6. Team discusses anomalies

### Workflow B: Deep Investigation (10 min)

1. Provide 12+ weeks of data
2. Ask: "Why has conversion declined for 3 weeks?"
3. Get detailed analysis
4. Review hypotheses
5. Ask follow-up: "What does your data say about [specific cause]?"
6. Get targeted insights

### Workflow C: Portfolio Demo (5 min)

1. Use sample data: `../data/sample-metrics.csv`
2. Paste system prompt
3. Provide metrics
4. Screenshot output
5. Use for LinkedIn post or interview demo

### Workflow D: Automated Analysis (No manual prompts)

1. Load master `../claude.md`
2. Say: "Analyze this week's metrics"
3. Provide CSV/data
4. Claude automatically loads system prompt
5. Get formatted report
6. No manual prompt needed!

---

## Troubleshooting

### "Data Quality Issue Detected"

**Possible causes:**
- Negative values (Active Users can't be negative)
- % values outside 0-100 (Conversion should be 0-100%)
- Missing values
- Duplicate rows

**Solution:**
- Check your source data
- Fix the issue
- Re-analyze

### "Not Enough Historical Data"

**Possible causes:**
- Only 1-3 weeks of data
- Agent wants more baseline for anomaly detection

**Solution:**
- Provide at least 8 weeks of data
- If you only have 4 weeks, that's OK but analysis is preliminary

### "Report Seems Generic"

**Possible causes:**
- Missing Notes column
- All metrics stable (no anomalies to discuss)
- Metrics too similar to average

**Solution:**
- Add Notes column with context
- Check if this is actually a "stable week" (could be good news!)
- Check if metrics are actually unusual

### "Questions Aren't Specific"

**Possible causes:**
- Agent can't determine cause without context
- Multiple possible explanations

**Solution:**
- Add more context in Notes
- Provide segment data if available
- Agent will ask more specific questions

### "Output format wrong"

**Solution:**
- Specify format: "Format as email" or "Format as JSON"
- Agent will reformat

---

## When to Use This Agent

✅ **Use when:**
- You need to review weekly/daily metrics
- You want anomaly detection
- You need context for metric movements
- You want specific follow-up questions
- You need a professional report for stakeholders

❌ **Don't use when:**
- You need real-time dashboards (use Looker/Tableau)
- You need deep statistical analysis (use data science tools)
- You're not sure what your metrics should be
- You don't have data yet

---

## Common Questions

**Q: How long does analysis take?**  
A: 1-2 minutes per week of metrics. Longer data takes proportionally more time.

**Q: Can I use my own metrics?**  
A: Yes! Any product metrics work: Active Users, Conversion, Revenue, MRR, Churn, etc.

**Q: What if I have more than 4 metrics?**  
A: Agent will analyze all of them. More metrics = richer analysis.

**Q: Can I schedule this weekly?**  
A: Yes! Use Zapier/Make.com to automate: Sheet → Claude API → Slack

**Q: Is this a replacement for BI tools?**  
A: No. Use with Looker/Tableau/dashboards. This agent adds analytical layer on top.

**Q: Can I modify the system prompt?**  
A: Yes, but carefully. Prompt teaches the agent how to think.

**Q: What if anomalies aren't detected?**  
A: Check: Are you providing 8+ weeks? Are metrics actually anomalous? Is this a "stable week"?

**Q: How do I save reports?**  
A: Screenshot or copy-paste to Slack/email. Or export as JSON for programmatic use.

---

## Support & Issues

**For questions about:**
- **Using this agent** → See this file (INSTRUCTIONS.md)
- **Understanding output** → See README.md
- **How the agent thinks** → See system-prompt.md
- **Project overview** → See ../README.md
- **Why this exists** → See ../PORTFOLIO.md

---

**Happy analyzing! 🚀**
