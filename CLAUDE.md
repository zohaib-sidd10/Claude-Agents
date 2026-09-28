\# claude.md — KPI Analyst Agent Master Configuration



\*\*Project:\*\* AI Agents for Product Operations  

\*\*Agent:\*\* #6 KPI Analyst  

\*\*Purpose:\*\* Automated metric analysis, anomaly detection, and insight generation  

\*\*Creator:\*\* Zohaib Siddiqui  

\*\*Status:\*\* Phase 1 — Production Ready  



\---



\## 🎯 Quick Start for Claude Code



When you invoke Claude Code with this project:



```

Claude Code, analyze the metrics in \[filename].xlsx

```



Claude Code will:

1\. Load this claude.md file

2\. Extract the system prompt instructions

3\. Read the metrics file

4\. Generate analysis automatically

5\. Return formatted report



\*\*No manual prompt setup required.\*\*



\---



\## 📋 Project Structure



```

kpi-analyst-agent/

├── claude.md                           # THIS FILE — Master configuration

├── README.md                           # Project overview (for GitHub)

├── PORTFOLIO.md                        # Portfolio value \& talking points

│

├── agents/

│   └── 01-kpi-analyst/

│       ├── system-prompt.md           # Agent instructions (loaded automatically)

│       ├── example-output.md          # Real example output

│       ├── README.md                  # How to use this agent

│       └── INSTRUCTIONS.md            # Step-by-step usage guide

│

├── data/

│   ├── sample-metrics.csv             # Demo data (9 weeks)

│   ├── sample-metrics-extended.csv    # Extended demo (20 weeks)

│   └── schema/

│       └── metrics-schema.json        # Expected data format

│

├── examples/

│   ├── example-output-week9.md        # Real Slack report

│   ├── example-output-email.html      # Real email output

│   └── metrics-walkthrough.md         # Analysis walkthrough

│

└── docs/

&#x20;   ├── HOW-IT-WORKS.md               # Technical overview

&#x20;   └── TROUBLESHOOTING.md            # Common issues \& fixes

```



\---



\## ⚙️ Agent Configuration



\### Agent Name

\*\*KPI Analyst\*\*



\### Agent Type

\*\*Product Operations Analysis Engine\*\*



\### Primary Function

Analyze weekly product metrics, detect anomalies, provide context, and generate follow-up questions.



\### Input Format

\- \*\*File Type:\*\* CSV, XLSX, or Google Sheets data

\- \*\*Required Columns:\*\* Week identifier, at least 2-3 metrics

\- \*\*Data Volume:\*\* Minimum 4 weeks (8+ weeks recommended for baseline)

\- \*\*Supported Metrics:\*\*

&#x20; - Active Users / Monthly Active Users

&#x20; - Conversion Rate (%)

&#x20; - Retention (%)

&#x20; - NPS Score

&#x20; - Revenue / MRR

&#x20; - Churn Rate

&#x20; - Engagement metrics

&#x20; - Any custom business metrics



\### Output Formats

\- \*\*Slack:\*\* Formatted message with emoji, anomalies, questions

\- \*\*Email:\*\* HTML-formatted report

\- \*\*Markdown:\*\* Full analysis for documentation

\- \*\*JSON:\*\* Structured data for programmatic use



\### Execution Method

1\. \*\*User provides:\*\* Metrics file (CSV/XLSX)

2\. \*\*Claude Code loads:\*\* This claude.md + system-prompt.md

3\. \*\*Claude processes:\*\* Analyzes metrics using prompt instructions

4\. \*\*Output generated:\*\* Formatted report



\---



\## 🔧 System Instructions (Auto-Loaded)



\### Location

`agents/01-kpi-analyst/system-prompt.md`



\### What Claude Code Does When This File Is Loaded



Claude Code automatically:

1\. \*\*Reads\*\* the system prompt from `agents/01-kpi-analyst/system-prompt.md`

2\. \*\*Parses\*\* the metrics input (CSV/XLSX)

3\. \*\*Applies\*\* the 7-phase workflow:

&#x20;  - Phase 1: Validate data

&#x20;  - Phase 2: Calculate baselines

&#x20;  - Phase 3: Detect anomalies

&#x20;  - Phase 4: Contextualize findings

&#x20;  - Phase 5: Generate questions

&#x20;  - Phase 6: Synthesize story

&#x20;  - Phase 7: Format output

4\. \*\*Returns:\*\* Formatted report



\### Key Behavioral Rules (Built Into System Prompt)



\*\*DO:\*\*

✅ Distinguish observations from hypotheses  

✅ Explain anomalies with context  

✅ Flag uncertainty explicitly  

✅ Ask specific, investigative questions  

✅ Reference historical data and trends  

✅ Celebrate wins alongside concerns  



\*\*DON'T:\*\*

❌ Invent causation  

❌ Present assumptions as facts  

❌ Create vague alerts  

❌ Ignore context  

❌ Ask unanswerable questions  



\---



\## 📊 Data Input Requirements



\### Required Format



\*\*CSV Example:\*\*

```

Week,Active Users,Conversion %,Retention %,NPS

Week 1,50000,3.2,68,42

Week 2,52000,3.5,70,45

Week 3,48000,3.4,69,43

```



\*\*XLSX Example:\*\*

\- Column A: Week identifier (e.g., "Week 1", "2024-09-28")

\- Column B+: Metrics (one per column)

\- Row 1: Headers

\- Rows 2+: Data



\### Minimum Data Requirements

\- At least 4 weeks of data (8+ weeks recommended)

\- 2-3 key metrics minimum

\- Headers in first row

\- Numeric values (no text in metric columns)



\### Optional but Helpful

\- "Notes" column (feature launches, campaigns, known events)

\- Segment breakdowns (free vs. paid, geo, cohort)

\- Target values (what PM expected)



\### Data Quality Checks (Auto-Performed)

Claude will verify:

\- No negative values in user/engagement metrics

\- Percentages are 0-100 range

\- No duplicate rows

\- Dates/weeks are in order

\- Consistent metric definitions



\---



\## 🎬 Usage Workflows



\### Workflow A: Quick Analysis (Recommended)



```

User: "Analyze these metrics" + \[pastes or uploads CSV/XLSX]

↓

Claude Code loads: claude.md + system-prompt.md

↓

Claude analyzes automatically (no prompt needed)

↓

Output: Formatted Slack/email report

```



\### Workflow B: Custom Output Format



```

User: "Analyze these metrics and format as \[Email/Slack/JSON]"

↓

Claude Code: Loads system prompt + output format section

↓

Output: Custom formatted report

```



\### Workflow C: Comparative Analysis



```

User: "Compare Week 9 to Week 3 (both had user dips)"

↓

Claude Code: Analyzes both weeks

↓

Output: Side-by-side comparison with insights

```



\### Workflow D: Trend Investigation



```

User: "Why has conversion declined for 3 weeks straight?"

↓

Claude Code: Focuses analysis on conversion trend

↓

Output: Detailed breakdown with hypotheses

```



\---



\## 📈 Output Specifications



\### Slack Output Format



```

📊 Weekly KPI Analysis — \[Week]



✅ HIGHLIGHTS

• \[Positive metric] \[Change] \[Context]

• \[Positive metric] \[Change] \[Context]



⚠️ ANOMALIES \& CONCERNS

• \[Anomaly] \[Explanation] \[Uncertainty flag]

• \[Anomaly] \[Explanation] \[Uncertainty flag]



📈 TRENDS (8-Week View)

\[Narrative on trajectory]



🤔 FOLLOW-UP QUESTIONS

1\. \[Specific question]

2\. \[Specific question]

3\. \[Specific question]



📋 DATA SNAPSHOT

| Metric | Week X | Week X-1 | 8-Wk Avg | Change |

|--------|--------|----------|----------|--------|

| \[M] | \[V] | \[V] | \[V] | \[%] |



Last updated: \[ISO timestamp]

```



\### Email Output Format



```

Subject: Weekly KPI Analysis — Week \[X]



\## Executive Summary

\[1-2 sentence story]



\## Key Findings

✅ Highlights

⚠️ Concerns



\## Metric Analysis

\[Detailed breakdown]



\## Recommendations

\[Follow-up questions]



\## Trend Analysis

\[8-week view]

```



\### JSON Output Format



```json

{

&#x20; "week": "Week 9",

&#x20; "timestamp": "2026-09-28T09:00:00Z",

&#x20; "highlights": \[...],

&#x20; "anomalies": \[...],

&#x20; "questions": \[...],

&#x20; "trends": {...},

&#x20; "metrics": {...}

}

```



\---



\## 🧪 Quality Standards



Every report must pass this \*\*Quality Gate\*\*:



\### Data Validation

\- \[ ] All provided metrics are analyzed

\- \[ ] Data quality issues flagged if present

\- \[ ] Missing data handled gracefully



\### Anomaly Detection

\- \[ ] Anomalies correctly identified (statistical or contextual)

\- \[ ] Magnitude of change noted (%/points)

\- \[ ] Rarity context provided (is this unusual?)



\### Analysis Quality

\- \[ ] Observations separated from hypotheses

\- \[ ] No causation claimed without evidence

\- \[ ] Assumptions explicitly labeled

\- \[ ] Uncertainty flagged when appropriate



\### Questions Quality

\- \[ ] 3-5 specific, actionable questions

\- \[ ] Questions are investigative (not rhetorical)

\- \[ ] Prioritized by business relevance

\- \[ ] Answerable by PM



\### Output Quality

\- \[ ] Correct format for delivery channel

\- \[ ] Scannable (good emoji/headers/tables)

\- \[ ] Mobile-friendly

\- \[ ] Timestamp included

\- \[ ] Data source linked



\---



\## 🔄 Anomaly Detection Logic



Claude automatically detects anomalies using:



\### Statistical Detection

\- Calculate 8-week rolling mean and std dev

\- Flag if current week > 1.5σ from mean (notable)

\- Flag if current week > 2σ from mean (anomaly)



\### Contextual Detection

\- Compare to recent trend (trending up/down for weeks?)

\- Compare to seasonal patterns (provided in Notes)

\- Compare to PM targets (if provided)

\- Check metric correlations (if users down, what else moved?)



\### Severity Levels

\- \*\*🔴 Critical:\*\* Multiple metrics moving simultaneously (platform issue)

\- \*\*🟠 Concerning:\*\* Single metric down 3+ weeks, or large 1-week spike

\- \*\*🟡 Notable:\*\* Unusual change but could be normal variation

\- \*\*🟢 Positive:\*\* Good changes worth celebrating



\---



\## 🎯 Common Use Cases



\### Use Case 1: Weekly Metric Review

\*\*Input:\*\* Weekly metrics  

\*\*Output:\*\* Slack report with highlights/concerns  

\*\*Time:\*\* 1-2 minutes  



\### Use Case 2: Anomaly Investigation

\*\*Input:\*\* Metrics + notes about what changed  

\*\*Output:\*\* Deep-dive on unusual metric  

\*\*Time:\*\* 2-3 minutes  



\### Use Case 3: Trend Analysis

\*\*Input:\*\* 12+ weeks of data  

\*\*Output:\*\* Trend direction, momentum, inflection points  

\*\*Time:\*\* 2-3 minutes  



\### Use Case 4: Portfolio Audit

\*\*Input:\*\* Multiple agents' metrics  

\*\*Output:\*\* Comparative analysis across agents  

\*\*Time:\*\* 5-10 minutes  



\### Use Case 5: Presentation-Ready Report

\*\*Input:\*\* Metrics + "format as email"  

\*\*Output:\*\* HTML email ready to send to stakeholders  

\*\*Time:\*\* 2-3 minutes  



\---



\## 🚀 How to Use This Project



\### For Portfolio Development

1\. \*\*Test the agent\*\* with sample data

2\. \*\*Save outputs\*\* as examples

3\. \*\*Document results\*\* in `examples/`

4\. \*\*Take screenshots\*\* for LinkedIn

5\. \*\*Write walkthrough\*\* in PORTFOLIO.md



\### For Real Usage

1\. \*\*Prepare metrics\*\* in CSV/XLSX format

2\. \*\*Upload to Claude Code\*\*

3\. \*\*Specify output format\*\* (Slack/Email/JSON)

4\. \*\*Get analysis\*\* automatically

5\. \*\*Copy to Slack/email\*\* or integrate via API



\### For Integration

1\. \*\*Extract the system prompt\*\* from `agents/01-kpi-analyst/system-prompt.md`

2\. \*\*Call Claude API\*\* with metrics + prompt

3\. \*\*Parse output\*\* into delivery format

4\. \*\*Automate via Zapier/Make\*\* or custom script



\---



\## 📁 File References



\### System Prompt (Auto-Loaded)

\*\*File:\*\* `agents/01-kpi-analyst/system-prompt.md`  

\*\*Purpose:\*\* Agent instructions and behavioral rules  

\*\*Size:\*\* \~4KB  

\*\*When Used:\*\* Every time metrics are analyzed  



\### Sample Data

\*\*File:\*\* `data/sample-metrics.csv`  

\*\*Purpose:\*\* Test data for development  

\*\*Contents:\*\* 9 weeks of realistic SaaS metrics  



\*\*File:\*\* `data/sample-metrics-extended.csv`  

\*\*Purpose:\*\* Extended baseline testing  

\*\*Contents:\*\* 20 weeks for trend analysis  



\### Example Outputs

\*\*File:\*\* `examples/example-output-week9.md`  

\*\*Purpose:\*\* Real Slack report example  

\*\*Shows:\*\* How anomalies are formatted  



\*\*File:\*\* `examples/example-output-email.html`  

\*\*Purpose:\*\* Real email report example  

\*\*Shows:\*\* HTML formatting for email delivery  



\---



\## 🔑 Key Instructions for Claude Code



When this file is loaded, Claude Code should:



\### 1. Auto-Load System Prompt

```

Read: agents/01-kpi-analyst/system-prompt.md

Apply: All instructions to metric analysis

```



\### 2. Parse Metrics Input

```

Format: CSV, XLSX, or pasted data

Extract: Week identifier + metric columns

Validate: Data quality and format

```



\### 3. Apply 7-Phase Workflow

```

Phase 1: Validate data

Phase 2: Calculate baselines (8-week avg, trend)

Phase 3: Detect anomalies (statistical + contextual)

Phase 4: Contextualize (why did this happen?)

Phase 5: Generate questions (what to investigate?)

Phase 6: Synthesize (tell the story)

Phase 7: Format (Slack/Email/JSON)

```



\### 4. Enforce Quality Gate

```

Before outputting: Verify quality standards above

If any standard fails: Note in output or request clarification

```



\### 5. Handle Edge Cases

```

Missing data → Proceed, flag clearly

Low volume → Note limitation

Data errors → Flag, don't stop

All stable → Say so (good week!)

Multiple anomalies → Flag platform issue

```



\---



\## 💡 Pro Tips for Best Results



\### Tip 1: Include Notes Column

Add context about what changed:

```

Week 8: "Notification feature launched"

Week 9: "Holiday break (less acquisition)"

```

This helps Claude provide better explanations.



\### Tip 2: Include 8+ Weeks of Data

Statistical anomaly detection works better with baseline.

4-week minimum, 8+ weeks recommended, 20+ weeks excellent.



\### Tip 3: Be Consistent with Metrics

Same metrics each week (don't add/remove columns mid-stream).

Same calculation method (retention % calculated the same way).



\### Tip 4: Segment When Possible

If you have free vs. paid, add both:

```

Active Users (Total), Active Users (Paid), Conversion % (Paid)

```

Helps Claude identify cohort-specific issues.



\### Tip 5: Specify Output Format

If you want email instead of Slack:

```

"Analyze these metrics and format as email"

```



\---



\## ❓ Troubleshooting



\### Issue: Report is Too Verbose

\*\*Solution:\*\* Ask Claude Code: "Make this more concise"



\### Issue: Anomalies Not Detected

\*\*Solution:\*\* 

\- Ensure 8+ weeks of data

\- Check data format (numbers, not text)

\- Verify metric calculations are consistent



\### Issue: Questions Are Vague

\*\*Solution:\*\* Add Notes column with context about changes



\### Issue: Output Formatting Wrong

\*\*Solution:\*\* Specify format explicitly: "Format as Slack blocks"



\### Issue: Data Errors

\*\*Solution:\*\* Claude will flag them. Check for:

\- Negative numbers

\- % outside 0-100

\- Typos in week identifiers



\---



\## 🎬 Example Conversation with Claude Code



```

User: "Analyze these metrics"

\[Uploads: metrics.csv]



Claude Code:

1\. ✓ Loads claude.md (this file)

2\. ✓ Loads agents/01-kpi-analyst/system-prompt.md

3\. ✓ Parses metrics.csv (9 weeks, 4 metrics)

4\. ✓ Applies 7-phase workflow

5\. ✓ Generates Slack-formatted report

6\. ✓ Passes quality gate



Output:

📊 Weekly KPI Analysis — Week 9

✅ HIGHLIGHTS...

⚠️ ANOMALIES...

📈 TRENDS...

🤔 FOLLOW-UP QUESTIONS...

```



\---



\## 📝 System Prompt Loading



\### How Claude Code Knows to Use the System Prompt



This claude.md file tells Claude Code:



> "When analyzing metrics, load and apply the instructions from `agents/01-kpi-analyst/system-prompt.md`"



Claude Code then:

1\. Reads the system prompt

2\. Understands the 7-phase workflow

3\. Learns behavioral rules (fact vs. hypothesis, etc.)

4\. Applies those rules to metric analysis

5\. Returns formatted output



\### No Manual Setup Required



User doesn't need to paste the system prompt.  

User doesn't need to specify the workflow.  

User just provides metrics, and Claude Code handles the rest.



\---



\## 🎯 Success Criteria



This project is successful when:



1\. ✅ User provides metrics file

2\. ✅ Claude Code analyzes automatically (no prompt needed)

3\. ✅ Output passes quality gate

4\. ✅ Anomalies correctly identified

5\. ✅ Questions are specific and actionable

6\. ✅ Format is correct for delivery channel

7\. ✅ Report is professional and portfolio-ready



\---



\## 📊 Portfolio Value



This project demonstrates:



\- \*\*AI Prompt Engineering:\*\* Sophisticated system prompt that teaches Claude to think like an analyst

\- \*\*Data Analysis:\*\* Anomaly detection, trend identification, contextual reasoning

\- \*\*Product Operations:\*\* Understanding what metrics matter and why

\- \*\*Automation:\*\* No-code/low-code analysis engine

\- \*\*Documentation:\*\* Clear, comprehensive specifications

\- \*\*Professional Quality:\*\* Portfolio-ready outputs



\*\*Employer Takeaway:\*\*  

"This person understands how to design AI systems that do real work—not chatbots, but operational automation with business value."



\---



\## 🚀 Next Steps



1\. \*\*Test with sample data\*\*

&#x20;  ```

&#x20;  Use: data/sample-metrics.csv

&#x20;  Expect: Well-formatted report with anomalies

&#x20;  ```



2\. \*\*Create GitHub repo\*\*

&#x20;  ```

&#x20;  Add: All files in this project structure

&#x20;  Add: README.md, PORTFOLIO.md

&#x20;  Push: To your GitHub

&#x20;  ```



3\. \*\*Record demo video\*\*

&#x20;  ```

&#x20;  Show: Upload metrics → Get analysis

&#x20;  Post: On LinkedIn

&#x20;  ```



4\. \*\*Iterate on Phase 2\*\*

&#x20;  ```

&#x20;  Build: VOC Agent (#5)

&#x20;  Build: Product Discovery (#1)

&#x20;  Connect: Outputs feed into each other

&#x20;  ```



\---



\## 📞 Questions?



If Claude Code encounters issues:



1\. Check `TROUBLESHOOTING.md`

2\. Verify data format matches spec

3\. Ensure system prompt is loaded

4\. Review quality gate criteria

5\. Check example outputs for comparison



\---



\*\*Last Updated:\*\* 2026-09-28  

\*\*Author:\*\* Zohaib Siddiqui  

\*\*Status:\*\* Ready for Production  

\*\*Next Phase:\*\* VOC Agent (Phase 2)

