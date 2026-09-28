# Why I Built This — Portfolio Context

## The Vision

Most AI projects are chatbots. I wanted to build something different: **an operational automation system** that does real work in product operations.

This KPI Analyst agent is Phase 1 of a 12-agent suite designed to automate the entire product operations workflow.

## Why It Matters (Employer Perspective)

### What This Shows

✅ **AI System Design:** I understand how to architect AI systems that work autonomously—not just chat interfaces, but operational engines.

✅ **Product Thinking:** I know which metrics matter, why anomalies happen, and what questions PMs need answered.

✅ **Documentation as Code:** The `claude.md` file is a specification that tells Claude how to behave. Professional, maintainable, scalable.

✅ **No-Code Approach:** I can build production automation without traditional engineering overhead.

✅ **Quality Standards:** Every output passes a quality gate. Anomalies are validated. Context is required. No hallucinations.

### The Problem I'm Solving

Product managers spend **2-3 hours per week** manually reviewing metrics:
- Opening dashboards
- Calculating changes
- Spotting anomalies
- Typing summaries
- Asking the same questions

This agent does that in **2 minutes**—automatically, consistently, professionally.

## How to Evaluate This

### Look For

1. **System Prompt Quality:** See `agents/01-kpi-analyst/system-prompt.md`
   - Is it detailed?
   - Does it teach reasoning?
   - Does it prevent hallucinations?

2. **Example Output:** See `examples/week9-slack-report.md`
   - Are anomalies correctly detected?
   - Are explanations thoughtful?
   - Are questions specific and answerable?

3. **Documentation:** See `README.md` and `docs/`
   - Can someone replicate this?
   - Is it clear and professional?
   - Does it scale?

4. **claude.md Design:** See `claude.md`
   - How does it guide Claude?
   - Can you just provide data and get analysis?
   - No manual prompts needed?

### Interview Talking Points

**"Tell me about a project where you automated something"**

> "I built an AI system that automates weekly product metric analysis. Here's what makes it different: Most people treat AI as a chatbot. I treated it as a workflow system. I designed a system prompt that teaches Claude how to think like a Product Operations analyst—it detects anomalies, asks investigative questions, and distinguishes hypotheses from facts. The claude.md file is the specification that guides Claude automatically. Users just provide metrics, and they get a professional report in minutes. It's designed to scale—I'm building 11 more agents to cover the full product ops workflow."

**"What technical decisions did you make and why?"**

> "I chose Claude API because of its reasoning capabilities. Anomaly detection requires context—it's not just math, it's understanding what's normal for a business. I made the system prompt detailed (2000+ words) because that's how you get consistent quality. I stored configuration in claude.md so Claude Code can load it automatically—no copy-pasting prompts each time. I built a quality gate so every report is validated before output. All of these decisions prioritize reliability and maintainability over quick hacks."

**"How would you extend this?"**

> "Phase 2 is adding a VOC (Voice of Customer) agent that processes customer feedback. Phase 3 is a Product Discovery agent. The key is connecting them—VOC findings feed into discovery, discovery feeds into prioritization. I'm designing each agent independently but with a focus on data flow between them. The master claude.md orchestrates all 12 agents to cover the full product operations workflow."

## The Full Vision

### 12 AI Agents for Product Operations

**Product Management (3 agents)**
1. Product Discovery Agent — Find opportunities from interviews
2. PRD & Requirements Agent — Generate PRDs from ideas
3. Feature Prioritization Agent — RICE scoring, trade-off analysis

**Product Operations (3 agents)**
4. **KPI Analyst** — *You are here*
5. Product Feedback & VOC Agent — Process customer feedback
6. Release Readiness Agent — Cross-team go/no-go assessment

**Program Management (3 agents)**
7. Project Health Agent — Timeline & milestone tracking
8. RAID & Risk Agent — Risk/issue/assumption/dependency registry
9. Meeting-to-Action Agent — Turn meetings into tasks

**Cross-Functional (3 agents)**
10. Product Operations Digest — Weekly exec summary
11. Portfolio Command Center — Cross-project view
12. Roadmap Planning Agent — Roadmap generation & management

Each agent builds on the previous one. By the end, you have an **AI-powered product operations suite** that automates the entire workflow.

## Portfolio Strategy

**Phase 1 (Now):** Build KPI Analyst, showcase on GitHub + LinkedIn
- Demonstrate understanding of one workflow deeply
- Show quality and attention to detail
- Get feedback and iterate

**Phase 2 (Weeks 2-3):** Add VOC Agent + Product Discovery
- Show how agents feed into each other
- Demonstrate scalability
- Build momentum

**Phase 3 (Week 4):** Showcase everything
- Write blog post: "I Built a 12-Agent AI Suite for Product Operations"
- Create video walkthrough
- Share real examples and outputs
- Highlight learnings and architectural decisions

**Phase 4 (Ongoing):** Maintain and extend
- Keep agents production-ready
- Document learnings
- Use for real product work (if building products)
- Iterate based on usage

## Why This Is Impressive

Most people building portfolio projects:
- Make toy projects (to-do list, weather app)
- Build what tutorials tell them to build
- Don't think about real problems

You're:
- Solving a real problem (metric analysis takes time)
- Building a system that scales (12 agents, not 1)
- Thinking about production concerns (quality gates, error handling)
- Demonstrating product thinking (which metrics matter, why questions drive investigation)
- Creating professional documentation (employer-ready, not hobby-grade)

That's the kind of thinking hiring managers look for.

## LinkedIn Post (When You Push)

Here's a draft post for when you're ready to share:

---

Just shipped the KPI Analyst Agent 🚀

Most AI projects are chatbots. I built something different: an operational automation system for product metrics.

Upload your weekly metrics → Agent detects anomalies → Generates follow-up questions → Returns professional report (in Slack format).

What makes it different:
• It distinguishes observations from hypotheses (no wild guesses)
• It asks specific questions (not "why are users down?")
• It handles edge cases (missing data, seasonal patterns)
• It scales (documentation + architecture designed for 11 more agents)

This is Phase 1 of a 12-agent suite for product operations. The goal: automate the entire product ops workflow.

Check it out: [Link to GitHub]

Swipe for the analysis process.

---

## Evaluation Criteria

When reviewing this project, look at:

| Criterion | What to Check |
|-----------|---------------|
| **System Prompt Quality** | Is it detailed? Does it teach reasoning? Does it prevent hallucinations? |
| **Example Output** | Are anomalies detected correctly? Are explanations thoughtful? Are questions specific? |
| **Documentation** | Is it clear? Professional? Reproducible? |
| **Architecture** | Can it scale? Is it designed for extension? |
| **Product Thinking** | Does it understand what metrics matter? Why context matters? |
| **Quality Standards** | Are there quality gates? Is error handling explicit? |

---

## Questions?

This project is designed to be:
- **Impressive:** Shows serious thinking about AI systems
- **Transparent:** Full documentation and reasoning
- **Reproducible:** Anyone can clone and use it
- **Extensible:** Easy to add more agents
- **Production-Ready:** Quality gates, error handling, clear specs

If you're evaluating this for hiring or learning, I'm happy to discuss:
- Design decisions
- Why I chose specific approaches
- How I'd extend it
- What I learned building it

---

**Status:** Phase 1 Complete  
**Next:** Phase 2 (VOC Agent, Product Discovery Agent)  
**Vision:** 12-agent suite for product operations automation
