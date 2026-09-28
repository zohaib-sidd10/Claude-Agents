# KPI Analyst Agent — agents/01-kpi-analyst/README.md

## Agent Overview

**Name:** KPI Analyst  
**Purpose:** Analyze weekly product metrics, detect anomalies, and generate actionable insights  
**Type:** Product Operations Analysis Engine  
**Status:** Production Ready  

## What This Agent Does

Takes product metrics and analyzes them like a seasoned Product Operations analyst:

1. **Validates data** — Checks for quality issues
2. **Calculates baselines** — Compares to 8-week average
3. **Detects anomalies** — Statistical and contextual analysis
4. **Contextualizes findings** — Explains why metrics moved
5. **Generates questions** — Specific follow-up investigations
6. **Synthesizes insights** — Tells the story of the week
7. **Formats output** — Slack, Email, or JSON

## Input Requirements

### Data Format

**Required Columns:**
- Week identifier (e.g., "Week 1", "2024-09-28")
- Metric 1 (e.g., Active Users)
- Metric 2 (e.g., Conversion %)
- Metric 3 (e.g., Retention %)
- Metric 4 (e.g., NPS)

**Required Volume:** Minimum 4 weeks, 8+ weeks recommended for baseline

**File Types Supported:**
- CSV (.csv)
- XLSX (.xlsx)
- Pasted data in Claude Code

### Example Input

```
Week,Active Users,Conversion %,Retention %,NPS
Week 1,50000,3.2,68,42
Week 2,52000,3.5,70,45
Week 3,48000,3.4,69,43
Week 4,51000,3.6,71,46
...
Week 9,49000,3.1,68,42
```

## Output Formats

### Slack Format (Default)

```
📊 Weekly KPI Analysis — Week 9

✅ HIGHLIGHTS
• [Metric]: [Change] [Context]

⚠️ ANOMALIES & CONCERNS
• [Metric]: [Observation] [Hypothesis]

📈 TRENDS (8-Week View)
[Narrative on trajectory]

🤔 FOLLOW-UP QUESTIONS
1. [Specific question]
2. [Specific question]
3. [Specific question]

📋 DATA SNAPSHOT
| Metric | Week 9 | Week 8 | 8-Wk Avg | Change |
|--------|--------|--------|----------|--------|
| [M] | [V] | [V] | [V] | [%] |

Last updated: [Timestamp]
```

### Email Format

```
Subject: Weekly KPI Analysis — Week 9

Hello,

Here's your weekly product metrics analysis.

## Executive Summary
[1-2 sentence headline]

## Key Findings
✅ Highlights
⚠️ Concerns

## Detailed Analysis
[Metric-by-metric breakdown]

## Follow-up Questions
[3-5 investigative questions]

## Trend Analysis
[8-week view]
```

### JSON Format

```json
{
  "week": "Week 9",
  "timestamp": "2026-09-28T09:00:00Z",
  "highlights": [...],
  "anomalies": [...],
  "questions": [...],
  "trends": {...},
  "metrics": {...}
}
```

## System Prompt

**Location:** `system-prompt.md`

The system prompt is the agent's "brain." It defines:
- Analysis methodology (7-phase workflow)
- Behavioral rules (fact vs. hypothesis, uncertainty handling)
- Output formatting
- Quality standards

**Key Principles:**
- Distinguish observations from hypotheses
- Flag uncertainty explicitly
- Ask specific, investigative questions
- Provide context before conclusions
- Prevent hallucinations and fabrication

## How to Use This Agent

### Method 1: Claude Code (Recommended)

```bash
# In Claude Code:
1. Copy this agent's system prompt from system-prompt.md
2. Provide your metrics (CSV/XLSX or pasted data)
3. Say: "Analyze these metrics"
4. Get formatted report
```

### Method 2: Using Master claude.md

```bash
# In Claude Code:
1. Load master claude.md from project root
2. Say: "Analyze these metrics" + [provide data]
3. Claude automatically loads system prompt
4. Get formatted report (no manual prompt needed)
```

### Method 3: Claude API (Direct)

```bash
# Programmatically:
1. Read system prompt from system-prompt.md
2. Call Claude API with: system_prompt + metrics_data
3. Parse response into desired format
4. Deliver to Slack/email/dashboard
```

## Example Usage

### Input
```
Week 1: Active Users 50K, Conversion 3.2%, Retention 68%, NPS 42, Notes: Launch
Week 2: Active Users 52K, Conversion 3.5%, Retention 70%, NPS 45, Notes: Viral growth
...
Week 9: Active Users 49K, Conversion 3.1%, Retention 68%, NPS 42, Notes: —
```

### Output (Slack Format)

```
📊 Weekly KPI Analysis — Week 9

✅ HIGHLIGHTS
• Retention holding steady at 68% (on target)

⚠️ ANOMALIES & CONCERNS
• Active Users: 49K (-8% from Week 8, -6.5% from 8-wk avg)
  This is notable but similar to Week 3 dip.
  Possible causes: Seasonal variation, reduced acquisition, or churn spike.

• Conversion Rate: 3.1% (-6% from Week 8, -11.4% from 8-wk avg)
  Concerning: 3rd consecutive week of decline (3.8% → 3.1%).

📈 TRENDS (8-Week View)
Active Users: Upward trend broken this week after 6 weeks of growth.
Conversion: Downward trend for 3 weeks (concerning).
Retention: Stable around 70%.
NPS: Following user decline (expected correlation).

🤔 FOLLOW-UP QUESTIONS
1. Active users down 8%—is this seasonal (like Week 3) or a new problem?
2. Conversion declining 3 weeks straight—what changed? (Pricing? Onboarding? Traffic quality?)
3. Both users and conversion down—is this platform-wide or cohort-specific?

📋 DATA SNAPSHOT
| Metric | Week 9 | Week 8 | 8-Wk Avg | Change |
|--------|--------|--------|----------|--------|
| Active Users | 49K | 53K | 52.4K | -6.5% |
| Conversion % | 3.1% | 3.3% | 3.5% | -11.4% |
| Retention % | 68% | 70% | 70.1% | -3.0% |
| NPS | 42 | 45 | 45.1% | -6.9% |

Last updated: 2026-09-28 09:00 AM PT
Data source: [Google Sheet: Weekly Metrics]
```

## Quality Gate

Every report must pass this quality gate before output:

- [ ] All provided metrics are analyzed
- [ ] Anomalies are correctly identified (statistical or contextual)
- [ ] Explanations distinguish observation from hypothesis
- [ ] No causation claimed without evidence
- [ ] Assumptions explicitly labeled
- [ ] Uncertainty flagged when appropriate
- [ ] Follow-up questions are specific and actionable
- [ ] Output format is correct for delivery channel
- [ ] Scannable with good emoji/headers/tables
- [ ] Mobile-friendly
- [ ] Timestamp included
- [ ] Data source linked
- [ ] No fabricated metrics or context

## Configuration

**Master Configuration:** See `../claude.md`

This agent's behavior is controlled by:
1. **System Prompt** (`system-prompt.md`) — Agent instructions
2. **Master claude.md** — How Claude Code invokes the agent

Users don't need to understand these—they just provide metrics and get analysis.

## Troubleshooting

### Issue: "Anomalies not detected"

**Possible Causes:**
- Insufficient data (need 8+ weeks)
- Inconsistent metric calculations
- All metrics stable (which is fine!)

**Solution:**
- Provide 8+ weeks of data
- Verify metrics are calculated consistently
- Check if this is actually a "stable week" (good news!)

### Issue: "Report too verbose"

**Solution:**
- Ask Claude: "Make this more concise"
- Agent will summarize key points only

### Issue: "Questions are vague"

**Solution:**
- Add Notes column with context
- Specify what changed (feature launch, campaign, etc.)
- Agent will ask more specific questions

### Issue: "Output formatting wrong"

**Solution:**
- Specify format: "Format as email" or "Format as JSON"
- Agent will reformat accordingly

### Issue: "Data quality flag raised"

**Solution:**
- Check for: negative numbers, % outside 0-100, duplicates
- Fix source data
- Re-analyze

## Performance Metrics

**Analysis Speed:** 1-2 minutes per week of metrics  
**Data Volume:** Tested with up to 52 weeks (1 year) of data  
**Accuracy:** Anomalies correctly detected in test cases  
**Reliability:** No failures on edge cases (missing data, errors)  

## Example Files

- **Input:** `../data/sample-metrics.csv` (9 weeks of data)
- **Output:** `example-output.md` (real generated report)
- **Extended Data:** `../data/sample-metrics-extended.csv` (20 weeks)

## Next Steps

- **Phase 1 Complete:** KPI Analyst ✅
- **Phase 2:** VOC Agent (process customer feedback)
- **Phase 3:** Product Discovery Agent
- **Phase 4+:** Connect agents into workflow

## Questions?

See main README.md for project overview  
See ../claude.md for system architecture  
See system-prompt.md for agent logic  

---

**Status:** Production Ready  
**Last Updated:** 2026-09-28  
**Owner:** [Your Name]
