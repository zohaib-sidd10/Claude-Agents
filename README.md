# KPI Analyst Agent

Automated product metrics analysis using Claude AI. Detect anomalies, identify trends, and generate actionable insights—no engineering required.

## 🎯 What It Does

Takes product metrics (Active Users, Conversion Rate, Retention, NPS) and analyzes them like a seasoned Product Operations analyst:

- ✅ Detects anomalies with statistical and contextual analysis
- ✅ Explains why metrics moved (hypotheses, not just alerts)
- ✅ Generates 3-5 specific follow-up questions for investigation
- ✅ Identifies trends over 4-8 weeks
- ✅ Formats output for Slack, Email, or JSON

## 🚀 Quick Start

### Option 1: Test with Sample Data (5 min)

1. Clone this repo
2. Open `data/sample-metrics.csv`
3. Copy metrics into Claude Code
4. Use system prompt from `agents/01-kpi-analyst/system-prompt.md`
5. Get analysis with anomalies and questions

### Option 2: Analyze Your Own Metrics (2 min)

1. Prepare your metrics in CSV/XLSX format
2. Upload to Claude Code
3. Say: "Analyze these metrics"
4. Get formatted report

## 📊 Example Output

Input: 9 weeks of SaaS metrics  
Output: See `examples/week9-slack-report.md`

```
📊 Weekly KPI Analysis — Week 9

✅ HIGHLIGHTS
• Retention holding steady at 68%

⚠️ ANOMALIES
• Active Users: -8% (down to 49K)
• Conversion: -6% (down to 3.1%, 3rd week declining)

🤔 FOLLOW-UP QUESTIONS
1. Is the user drop seasonal (like Week 3)?
2. Why has conversion declined 3 weeks straight?
3. Is this platform-wide or cohort-specific?
```

**[See full example in examples/week9-slack-report.md]**

## 📁 Project Structure

```
agents/
└── 01-kpi-analyst/          # The KPI Analyst Agent
    ├── system-prompt.md     # Agent instructions
    ├── README.md            # How to use this agent
    └── example-output.md    # Real output example

data/
├── sample-metrics.csv       # 9-week test data
└── sample-metrics-extended.csv  # 20-week data

examples/
├── week9-slack-report.md    # Real Slack report
└── walkthrough.md           # Analysis walkthrough

docs/
├── HOW-IT-WORKS.md
├── GETTING-STARTED.md
└── TROUBLESHOOTING.md
```

## 🔧 How It Works

1. **You provide:** Metrics file (CSV/XLSX) with 4+ weeks of data
2. **Claude loads:** System prompt from `agents/01-kpi-analyst/system-prompt.md`
3. **Claude analyzes:**
   - Phase 1: Validate data
   - Phase 2: Calculate baselines (8-week average)
   - Phase 3: Detect anomalies (statistical + contextual)
   - Phase 4: Contextualize findings
   - Phase 5: Generate questions
   - Phase 6: Synthesize story
   - Phase 7: Format output
4. **You get:** Professional analysis report

## 🎓 What This Demonstrates

- **AI Prompt Engineering:** Sophisticated system prompt that teaches Claude analytical thinking
- **Data Analysis:** Anomaly detection, trend identification, contextual reasoning
- **Product Operations:** Understanding which metrics matter and why
- **No-Code Automation:** Production automation without traditional engineering
- **Documentation:** Clear, comprehensive specifications

## 📚 Documentation

- **[HOW-IT-WORKS.md](docs/HOW-IT-WORKS.md)** — Technical deep-dive
- **[GETTING-STARTED.md](docs/GETTING-STARTED.md)** — Step-by-step setup
- **[PORTFOLIO.md](PORTFOLIO.md)** — Why this project matters
- **[System Prompt](agents/01-kpi-analyst/system-prompt.md)** — Agent instructions

## 💡 Usage Examples

### Weekly Analysis
```
Input: Your weekly metrics
Output: Slack report with anomalies + questions
Time: 1-2 minutes
```

### Trend Investigation
```
Input: 12+ weeks of data
Output: Trajectory analysis with inflection points
Time: 2-3 minutes
```

### Portfolio Demo
```
Input: Sample data from examples/
Output: Screenshot-ready report
Use: LinkedIn post, portfolio site, interview demo
```

## 🔄 Workflow

```
Metrics File (CSV/XLSX)
    ↓
Claude Code + System Prompt
    ↓
7-Phase Analysis Workflow
    ↓
Formatted Output (Slack/Email/JSON)
```

## 🛠️ Configuration

Main configuration file: `claude.md`

This tells Claude Code:
- Where to find the system prompt
- How to parse metrics
- What workflow to follow
- How to format output

No manual setup needed—just provide metrics.

## 📈 Success Criteria

✅ Correctly identifies anomalies  
✅ Provides contextual explanations  
✅ Generates specific follow-up questions  
✅ Formats output professionally  
✅ Handles edge cases (missing data, errors)  
✅ Passes quality gate before output  

## 🚀 Next Steps

- **Phase 1 (Done):** KPI Analyst agent
- **Phase 2:** VOC Agent (#5 — Process customer feedback)
- **Phase 3:** Product Discovery Agent (#1)
- **Phase 4:** Connect agents (outputs feed into each other)

See [PORTFOLIO.md](PORTFOLIO.md) for the full vision.

## 📝 License

MIT License - See LICENSE file

## 👤 Author

[Your Name]  
[Your LinkedIn]  
[Your GitHub]

---

## 🎬 Quick Demo

See real output: [examples/week9-slack-report.md](examples/week9-slack-report.md)

Try it: Copy `data/sample-metrics.csv` → Paste into Claude → Use system prompt

---

**Built with:** Claude API + Markdown + Product Operations thinking  
**For:** Portfolio development & production product metric analysis  
**Status:** Phase 1 Complete — Ready for Production
