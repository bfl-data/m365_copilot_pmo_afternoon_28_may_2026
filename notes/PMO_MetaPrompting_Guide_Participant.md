# Meta-Prompting Guide — Technology PMO
### Microsoft Copilot Training | Bajaj Finance Limited

---

## What Is Meta-Prompting?

Instead of writing a prompt yourself, you **ask Copilot to write the prompt for you** — by telling it your role, your task, and what you need.

You are essentially saying:  
> *"You are a prompt expert. You know how to talk to AI. Write me a prompt I can use for my actual work."*

The output becomes your **reference prompt** — something you refine and reuse across different projects and situations.

---

## The Core Meta-Prompt Formula

```
Act as a Microsoft Copilot prompt expert.

I am a [YOUR ROLE] at [COMPANY/CONTEXT].
I need to [WHAT YOU WANT TO DO].
My audience is [WHO WILL READ THE OUTPUT].

Write me a detailed, structured Copilot prompt I can use to complete this task.
The prompt should specify: role, task, context, output format, and tone.
```

---

## Meta-Prompts for Technology PMO — Bajaj Finance

Use these as your **starting point**. Copy, paste, and run in Copilot. Use the output as your working prompt for your exercises.

---

### 1. Project Status Reporting

> Act as a Microsoft Copilot prompt expert.
>
> I am a Technology PMO Analyst at Bajaj Finance Limited, an NBFC.
> I receive raw weekly update notes from squad leads across multiple technology projects.
> I need to convert these raw notes into a structured fortnightly project status report for senior leadership — including RAG (Red / Amber / Green) status, key risks, and decisions required.
> My audience is the CTO and Business Heads who want concise, factual updates — not technical detail.
>
> Write me a detailed, structured Copilot prompt I can use to produce this status report.
> The prompt should specify: my role, the task, what context I will provide, the exact output format I want, and the appropriate tone.

---

### 2. Stakeholder Communication — Tailoring by Audience

> Act as a Microsoft Copilot prompt expert.
>
> I am a Technology PMO Analyst at Bajaj Finance Limited.
> I have a full project status report already drafted.
> I need to extract a short, tailored update from it for a specific senior stakeholder — one who is not technical and cares only about timelines, budget, and business impact.
> The update should be 4–5 bullet points, not more than half a page.
>
> Write me a Copilot prompt I can use to produce this tailored communication from an existing status report.
> The prompt should tell Copilot exactly what to retain, what to drop, and what tone to use for a business (non-technical) audience.

---

### 3. Risk and Issue Log Summarisation

> Act as a Microsoft Copilot prompt expert.
>
> I am a Technology PMO Analyst at Bajaj Finance Limited.
> I maintain a project risk and issue log across multiple active programmes.
> I need to summarise this log for a Steering Committee — grouping risks by severity (Critical / High / Medium), highlighting any issues that are overdue or unresolved, and flagging items that require a governance decision.
>
> Write me a structured Copilot prompt that will produce a one-page risk summary from my raw risk-issue log data.
> The prompt should specify format (sections, table or bullets), tone (governance-ready), and any prioritisation logic I want applied.

---

### 4. Meeting Minutes — Governance Meetings

> Act as a Microsoft Copilot prompt expert.
>
> I am a Technology PMO Analyst at Bajaj Finance Limited.
> After every Steering Committee and Programme Governance meeting, I need to produce formal meeting minutes.
> I work from rough notes captured during the meeting — bullet points, shorthand, sometimes incomplete sentences.
> The minutes need to be formal, structured, and ready to circulate within 24 hours of the meeting.
>
> Write me a Copilot prompt I can use to convert rough meeting notes into formal minutes.
> The prompt should specify the required sections (Attendees, Agenda Items, Decisions Made, Actions with Owner and Due Date), the appropriate formal tone, and instructions for handling unclear or incomplete notes.

---

### 5. Capacity Planning and Resource Tracking

> Act as a Microsoft Copilot prompt expert.
>
> I am a Technology PMO Analyst at Bajaj Finance Limited.
> I track engineer capacity across multiple delivery squads each quarter.
> I have a raw capacity table — squad names, headcount, allocation percentages, and availability gaps.
> I need to produce a capacity summary that flags over-allocated squads, identifies availability for new project intake, and recommends where to prioritise resourcing decisions.
>
> Write me a Copilot prompt that will produce a PMO capacity planning summary from this raw data.
> The prompt should specify format (summary paragraph + table), tone (analytical, recommendation-ready), and what signals to surface (critical gaps, reallocation opportunities).

---

## Still Confused? Run This.

If the prompt Copilot wrote doesn't feel right — too generic, wrong format, wrong tone — don't rewrite it yourself. Use this follow-up prompt instead:

```
The prompt you wrote is a good start, but I need you to adjust it.

Here is what I want to change:
- [Describe what felt off — e.g., "the format doesn't match what my SteerCo expects"]
- [Describe what's missing — e.g., "it doesn't tell Copilot to flag overdue items"]
- [Describe the tone issue — e.g., "it sounds too casual for a governance document"]

Please rewrite the prompt with these corrections.
Keep the same structure (Role / Task / Context / Format / Tone) but fix the parts I've described.
```

---

## What to Do With the Output

Once Copilot gives you a well-structured prompt:

1. **Read it** — does it reflect your actual role and task?
2. **Replace the placeholders** — swap generic context with your real project data
3. **Run it** — use it on the exercise dataset provided
4. **Save it** — this is your reusable reference prompt for that task type

---

*Bajaj Finance Limited | AI Academy — Technology PMO*
*Microsoft Copilot Training Programme*
