# From Call Centre Team Leader to BI Developer: A Transformational Journey

## Where I Started

I spent nine years at FirstSource Solutions, a BPO handling multi-channel work for some fairly prestigious clients. Started as an advisor, made deputy team leader within six months, then team leader five months after that. Quick progression, decent money, and I was good at it.

But here's the thing about being good at something you're starting to outgrow—it doesn't make you happy, it makes you restless.

At my peak, I was responsible for 50+ advisors in the Academy. When intake slowed, I'd manage teams of around 25. I genuinely loved coaching people, watching them develop, seeing that moment when something clicks. That part never got old.

What *did* get old? The politics. The endless battles with upper management. The feeling that I was fighting the same fights on repeat with no real progression in sight.

So I moved sideways into Quality Assurance—listening to calls, reading chats, scoring interactions. Different problems, same company. It bought me time to figure out what I actually wanted.

### The Problem That Wouldn't Go Away

Here's what drove me mad about managing teams at FirstSource: **the data was everywhere and nowhere at the same time.**

Sales performance lived across multiple reports. No aggregation. No trends. No heat mapping. Some data was in emails, some on SharePoint, some buried in the internal CMS. The systems didn't talk to each other, and pulling together meaningful insights for a monthly 1-2-1 took longer than the bloody meeting itself.

You'd spend 45 minutes cobbling together stats from five different sources to have a 30-minute coaching conversation. Absolute madness.

So I built something in Excel. Nothing fancy—pivot tables, conditional formatting, basic formulas. But it aggregated everything in one place, showed trends, highlighted patterns, and gave me solid data for coaching conversations.

My team loved it. Then other team leaders asked for it. Then I got pulled into a meeting with HOSOs (Head of Something or Others) and upper management to showcase it across the wider operation.

That's when I realised: I didn't want to manage people who worked *with* data. I wanted to *be* the person working with data.

But I had a problem. I was 40+, no degree, no technical background. Excel was the most advanced tool I'd ever used. I'd dabbled in HTML and Dreamweaver back in 2000-something, but that was ancient history and probably doesn't count.

I had no idea what VBA was. I'd never heard of Python or SQL. I didn't even know what a BI Developer did.

What I *did* have was a track record of solving problems, a desperate need for a new challenge, and an increasingly clear sense that data work was where I belonged.

---

## The Interview That Changed Everything

In late 2023, I got headhunted for a Quality Assurance role at FlintBishop. Different company, similar work, but it felt like a step forward.

What I didn't expect was the gauntlet.

**Five interviews. Five consecutive days.**

By day three, I was wondering if this was some kind of corporate endurance test. But here's what happened: every conversation kept circling back to the dashboards I'd built at FirstSource. Not the QA stuff. The *data* stuff.

I'd prepared a presentation for one of the interviews—heavily focused on QA compliance and quality improvements. But the real star of the show? The dashboards I'd created to fill gaps in leadership reporting. How I'd worn "many hats" to solve problems that weren't technically in my job description.

The senior leadership team kept asking questions. Not about call quality frameworks or compliance standards. About how I approached problems. How I thought about data. How I turned messy information into actionable insights.

On the fifth day, they made me an offer.

But it wasn't for the QA role.

**"We'd like you to join our Data & Analytics team as a Data Administrator."**

They wanted an answer quickly. Ideally there and then.

I had a choice: take the safe option (go for the QA role I'd applied for and actually understood), or leap into something I knew absolutely nothing about but desperately wanted.

### The Terrifying "Yes"

Let me be clear about what I knew when I accepted that Data Administrator role:

**VBA:** Nothing.  
**Python:** Never heard of it.  
**SQL:** Whispers only. I'd jumped on calls with the BI team at FirstSource, always with an agenda to understand what a data role actually involved, but I'd never written a line of SQL.  
**Excel:** I thought I was good. I was about to discover I was barely intermediate.

I said yes anyway.

Not because I was confident. Not because I had a plan. But because I'd spent nine years at FirstSource building towards this exact opportunity, even if I hadn't realised it at the time.

If you're reading this and thinking, "But surely they wouldn't hire someone with zero technical skills?"—you're both right and wrong.

They didn't hire me for what I *knew*. They hired me for how I *thought*.

Problem-solving ability. Curiosity. A track record of delivering value with basic tools. The potential to learn.

And here's the thing about potential: it's only valuable if you're absolutely committed to making it real.

I started at FlintBishop in October 2023. My brief was clear: streamline processes, bring in automation, leverage LEAN methodologies to improve client onboarding and file ingestion.

**Translation:** Figure it out, build things that work, and do it fast.

No pressure then.

---

## The First Three Months: Survival Mode

I walked into FlintBishop's Data & Analytics team in October 2023 feeling like I'd accidentally gatecrashed a Mensa meeting.

I was surrounded by university graduates with mathematical degrees and 15+ years in analyst roles. People who spoke fluent SQL over their morning coffee. People who could debug Python in their sleep.

And there was me: the ex-call centre manager who'd built some pivot tables and blagged his way into the room.

**Imposter syndrome doesn't quite cover it.**

The role was Data Administrator—responsible for client onboarding, file ingestion, process improvement. My mission was to streamline everything, automate the manual stuff, and make the team more efficient.

Simple enough, right?

Except I had to learn VBA, Python, and SQL *simultaneously* while delivering actual work that actually mattered. No grace period. No "learning phase." Just tickets coming in, stakeholders expecting results, and me frantically Googling syntax at 11pm.

### The Learning Curve (Or: How I Broke Everything)

Here's what nobody tells you about learning on the job: **you will make mistakes that matter.**

Not little "oops, typo" mistakes. Mistakes with financial impacts. Mistakes that affect clients. Mistakes that make you question whether you should've stayed in your lane.

I made three that still make me wince.

---

**Mistake #1: The Excel Filter Disaster**

**What happened:** I filtered a dataset in Excel, but not all columns had headers. Excel only filtered the columns with headers, leaving the rest of the rows untouched. The data misaligned—values that should've matched up were now completely out of sync.

**Why it mattered:** This wasn't a one-off. It happened *twice*. 

The first time, I sent misaligned data to stakeholders for decision-making. The numbers were wrong. The decisions based on those numbers were wrong.

The second time was worse: I loaded the corrupted file onto the CMS. This cascaded downstream to file handlers, clients, and debtors. People were working with incorrect information, making decisions based on data that didn't match reality. The ripple effect was significant.

**The lesson:** Always, *always* check your data structure before filtering. Headers matter. Data validation matters. Assuming Excel will "just work" is a rookie mistake. And if you make a mistake once, implement checks to ensure it never happens again—I clearly didn't learn fast enough the first time.

> **Technical Detail:**  
> When you apply a filter in Excel, it operates on a range. If some columns lack headers, Excel treats them as separate ranges and doesn't include them in the filter operation. This creates a scenario where:
> 
> - Columns A-D (with headers) filter correctly
> - Columns E-F (without headers) remain static
> - Row 5 in Column A no longer corresponds to Row 5 in Column E
> 
> The fix: Ensure consistent headers across all columns, or use structured tables (Ctrl+T) which force proper range behaviour.

---

**Mistake #2: The SQL Payment Misallocation**

**What happened:** I wrote SQL code to apply payments and invoice adjustments to client accounts. Multiple matters existed per client—some open, some closed. I didn't account for case priority when matching payments to matters.

**Why it mattered:** Payments and invoices landed on the wrong accounts. Open matters that should've been prioritised were skipped. Recently closed matters got payments they shouldn't have received. This caused reconciliation chaos and impacted financial reporting.

**The lesson:** SQL doesn't assume business logic. You have to explicitly code it.

> **Technical Detail:**  
> The issue was a missing `ROW_NUMBER()` window function with a `CASE WHEN` statement to prioritise open cases.
> 
> **What I should've written:**
> ```sql
> WITH RankedMatters AS (
>     SELECT 
>         MatterID,
>         ClientID,
>         Status,
>         ClosedDate,
>         ROW_NUMBER() OVER (
>             PARTITION BY ClientID 
>             ORDER BY 
>                 CASE WHEN Status = 'Open' THEN 0 ELSE 1 END,
>                 ClosedDate DESC
>         ) AS Priority
>     FROM Matters
> )
> SELECT * FROM RankedMatters WHERE Priority = 1
> ```
> 
> This ensures open matters are selected first. If all matters are closed, it selects the most recently closed one. Without this logic, SQL just picks... whatever it feels like that day.

---

**Mistake #3: The Python Default Else**

**What happened:** I built a script to process new referral debt recovery matters and assign them to client codes and ledgers. I used an `if` statement to route certain cases, but added a default `else` clause without fully thinking through edge cases.

**Why it mattered:** Edge cases I hadn't anticipated hit the `else` clause and got routed to the wrong client code and wrong ledger. New referrals ended up on incorrect accounts, creating data integrity issues downstream.

**The lesson:** `else` is dangerous if you don't know *exactly* what conditions it's catching. Explicit is better than implicit.

> **Technical Detail:**  
> The code structure looked something like this:
> 
> ```python
> if condition_A:
>     client_code = "ClientA"
>     ledger = "LedgerX"
> elif condition_B:
>     client_code = "ClientB"
>     ledger = "LedgerY"
> else:
>     client_code = "DefaultClient"  # ← The problem
>     ledger = "DefaultLedger"
> ```
> 
> I assumed `condition_A` and `condition_B` covered all cases. They didn't. When an unexpected scenario hit the `else`, it defaulted to values that made no sense for that referral type.
> 
> **Better approach:** Explicitly define all expected conditions, and raise an exception or log a warning for anything that doesn't match:
> 
> ```python
> if condition_A:
>     client_code = "ClientA"
>     ledger = "LedgerX"
> elif condition_B:
>     client_code = "ClientB"
>     ledger = "LedgerY"
> elif condition_C:
>     client_code = "ClientC"
>     ledger = "LedgerZ"
> else:
>     raise ValueError(f"Unexpected referral type: {referral_type}")
> ```
> 
> Now if something unexpected happens, the script fails loudly instead of silently corrupting data.

---

### The Moment I Nearly Quit

About three months in, the imposter syndrome peaked.

I'd made these mistakes—some of them twice. I was working evenings and weekends just to keep up. I was surrounded by people who *knew* what they were doing, whilst I was fumbling through documentation and begging ChatGPT (and later Claude) to explain things like I was five.

I called FirstSource.

Had conversations. Tried to negotiate a higher salary and hybrid working. Seriously considered going back to what I knew.

It felt safer. Familiar. Less terrifying than being the least experienced person in a room full of experts.

Then I had a conversation with my manager at FlintBishop.

They put it in perspective: compared to the data breaches and multi-million-pound impacts you see in the news—the kind that sink companies—my mistakes were fixable. They were learning experiences, not career-ending disasters. The scale of risk was manageable.

But the conversation that mattered most was the one I had with myself.

Serious self-reflection. Confidence building. A decision point.

I could run back to comfort, or I could refuse to quit.

I chose stubbornness.

---

## The Turning Point

Here's what I realised during those self-reflection conversations: **nobody expected me to be an expert.**

They'd hired me knowing I had zero technical background. They'd seen my Excel dashboards and thought, "This person solves problems. We can teach them the tools."

The pressure to be perfect? That was entirely self-imposed.

The comparison to colleagues with 15 years' experience and maths degrees? Pointless. They weren't my competition—they were proof that different paths lead to the same destination.

So I made a decision.

I was going to stop trying to look like I knew what I was doing, and start *actually learning* what I was doing. Properly. Systematically. Without the constant fear that someone would expose me as a fraud.

It took about three months from the crisis point for the mindset to properly shift. I became more confident. More positive. Less apologetic about asking questions.

And I stopped treating mistakes as evidence I didn't belong—I started treating them as proof I was learning.

### The Strategy: Block, Build, Deliver

I knew I couldn't keep winging it. I needed structure.

**Step 1: Block out learning time**

I put five hours a week into my calendar—dedicated, protected learning time. Non-negotiable. Some of it was during work hours (when I could justify it), most of it was evenings and weekends.

But here's the thing: I didn't just passively watch tutorials. I *built* things during that time.

**Step 2: Rush through admin work to grab more tickets**

The work at FlintBishop came through a ticketing system. The more tickets I completed, the more exposure I got to different problems. Different data structures. Different stakeholder needs.

I started racing through my Data Administrator tasks so I could pick up additional tickets. Not because I was a martyr—because every ticket was a learning opportunity disguised as work.

**Step 3: Make everything self-serve**

I spotted a pattern early: people kept requesting the same data, over and over.

So I stopped giving them one-off extracts.

Every time someone put in a request for data, I built them a **refreshable version** with a "Save As" button. They could self-serve. They could update it themselves. They didn't need to come back to me.

This wasn't altruism—it was survival. If I could automate myself out of repetitive tasks, I'd have more time to learn *and* build things that actually mattered.

### The Tools I Used to Learn

**AI as my tutor**

I dabbled with ChatGPT in late 2023 to troubleshoot basic issues. But I quickly moved to Claude after realising its power for complex tasks and coding.

I treated it like a patient tutor who never got annoyed when I asked the same question three different ways. I'd paste error messages, explain what I was trying to achieve, and ask it to walk me through the logic.

But—and this is critical—I didn't just copy-paste code and hope for the best. I investigated the output. I broke it. I rebuilt it. I needed to understand *why* it worked, not just *that* it worked.

I also explored ChatGPT, Claude, and Grok depending on the task. Different tools for different problems.

**YouTube and trial-by-fire**

For SQL, I learned the basics—`SELECT`, `WHERE`, `JOIN`—from YouTube tutorials and just... doing it. I was missing a lot of foundational knowledge, but I was learning on the job while dedicating time outside work to fill the gaps.

Support in the office was minimal due to workload and staffing constraints, so I became comfortable with discomfort. If I didn't know something, I figured it out. Usually by breaking it first.

**The self-serve obsession became my signature**

Within a few months, stakeholders started noticing a pattern: when they asked me for something, they didn't just get an answer—they got a *tool*.

This became my brand. And it forced me to think beyond one-off solutions. Every request became: "How do I make this scalable? How do I never have to do this manually again?"

### The Soft Skills Nobody Warned Me About

Here's what surprised me most about being an analyst: **the technical stuff is only half the battle.**

Understanding the actual request—not just what someone *says* they want, but what they *actually need*—that's the skill.

Holding multiple stakeholder conversations. Not being afraid to persistently ask "Why?" five times until you get to the real problem.

Presenting alternatives and solutions to problems they didn't even know they had.

I leaned heavily on my leadership background here. Years of coaching, managing expectations, translating complex issues into plain English—it all transferred. My Team Leader experience at FirstSource wasn't wasted; it just got repurposed.

---

## What I Actually Built

Right, let's talk about the actual work. Because this is where potential became proof.

### The Early Win: Python File Monitoring Tool

A few months into the role, I identified a massive pain point: we were managing file ingestion for 60+ clients. Tracking which files had been processed, which were missing, which were delayed—it was chaos.

Missing or delayed files meant referrals and payments weren't being processed. That's direct revenue impact.

The old system? Pen and paper. Then someone tried Excel tracking. Neither scaled.

So I built a Python-based file monitoring system that:
- Tracked all inbound files across clients
- Identified missing or delayed files automatically
- Logged everything to an audit table
- Sent automated daily emails to key stakeholders and data administrators

I leveraged Python, AI for troubleshooting the logic, and Excel as the output layer (because stakeholders understood Excel).

**The impact:** Visibility. Accountability. Revenue protection. Stakeholders could see at a glance what was processed, what wasn't, and where bottlenecks were forming.

This was my first "proper" Python project. It worked. People noticed.

### The Self-Serve Philosophy in Action

Once I'd proven I could deliver, I started building tools that removed me from the equation.

**Fee Earner Maintenance Tool**

Staff alignments, hierarchy changes, adding or removing fee earners—these were constant requests. I built a tool that allowed stakeholders to update a SQL table directly, which controlled all reporting and hierarchy.

**The clever bit:** Built-in audit table. Every change logged who changed what, when, and where. Full traceability, zero risk of silent corruption.

**Capacity Planning Tool**

Helped leadership understand resource allocation and workload distribution across teams.

**QA Analyst Tool**

Streamlined quality assurance workflows—ironic given I'd started this journey in QA and had now built tools for the function I'd left behind.

**Job Reallocation Tool & Reassigned Fee Earner Tool**

Both solved workflow bottlenecks. When matters needed reassigning or fee earners changed, these tools automated what used to be manual, error-prone processes.

All of these followed the same principle: **if someone asks for it twice, build something they can use forever.**

### The Big One: KPI Dashboard

This was my largest project to date when I built it.

A comprehensive KPI dashboard that aggregated performance metrics across the business. Multiple data sources, complex calculations, automated refresh, executive-ready reporting.

This wasn't a quick win—it was a multi-week build that required stakeholder management, requirement gathering, iterative development, and proper testing.

It also taught me something important: **building dashboards is easy. Building dashboards that people actually use is hard.**

More on that in a moment.

### The PowerBI Transition

I taught myself PowerBI and started migrating tools out of Excel.

**Quality Dashboard:** Moved from Excel to PowerBI. Better performance, better visuals, easier refresh.

**Workload Management Tool:** Same story. Excel was groaning under the weight of the data. PowerBI handled it without breaking a sweat.

But here's where I made a classic mistake: **I spent too much time making things look good.**

Flashy charts. Strong aesthetics. Gradients and custom colour palettes and beautifully aligned visuals.

Meanwhile, users just wanted clear numbers and the ability to filter by date.

**The lesson:** Function over form. Aesthetics matter, but only after the tool *works* and delivers actual value. A beautiful dashboard that doesn't answer the question is worse than an ugly one that does.

I've since dialled back the design obsession and focused on clarity, speed, and usability. Turns out stakeholders care more about "Can I get my answer in three clicks?" than "Does this use the company brand hex codes?"

### The One I'm Most Proud Of: CCJ SOA Script

This is the project that made me realise I'd actually become competent.

**What it does:**

It's a County Court Judgment (CCJ) Statement of Account (SOA) generator. Built as a SQL stored procedure with elaborate Python orchestration.

It:
- Follows a template and loads all judgment data into an SOA
- Adds everything to an audit table for traceability
- Ensures there are no duplicates (critical for legal documents)
- Hits multiple validation criteria before sending
- Self-validates the output before emailing externally to clients and courts

**Why it matters:**

This is production-level automation with legal and financial consequences. If it breaks, people notice. If it sends incorrect data, there are compliance issues.

It works. It's robust. It's been running reliably since deployment.

When I built this, I knew I wasn't a "junior" anymore—I was just waiting for the job title to catch up.

### Current Project: Call Proforma Tool

Right now, I'm working on a call proforma/toolbox for frontline staff. The goal is to move more business logic out of Excel and into strong, scalable solutions that can handle growth without collapsing.

This is ongoing, but it's indicative of where the role has evolved: I'm no longer just fixing problems—I'm designing systems.

### The Learning Documentation Project

As I learned SQL, Python, PowerBI, and various development practices, I started documenting everything in comprehensive guides—not just for myself, but for others making the same journey.

I created four mastery guides:
- **Python & Excel Complete Mastery Guide** (15 chapters, 250+ examples)
- **PowerBI Complete Mastery Guide** 
- **Azure DevOps & GitHub Complete Mastery Guide**
- **QA Design Principles Complete Mastery Guide**

Why bother documenting? The Feynman Technique: **if you can't explain it simply, you don't understand it well enough.**

Writing these guides forced me to:
- Consolidate fragmented knowledge into structured frameworks
- Test my understanding by teaching concepts
- Create the resources I wish I'd had when starting out
- Build a portfolio of work beyond code

These guides became proof—not just to employers, but to myself—that I'd moved from "learning" to "mastery."

These projects fundamentally changed how I spent my time. I was no longer just responding to data requests—I was designing systems that prevented those requests from existing in the first place. From reactive to proactive. From data administrator to systems designer.

---

## The Promotion

Eight months after starting as a Data Administrator, I got pulled into the office.

"We're promoting you to Junior Data Analyst."

That was it. No formal interview. No competency assessment. No lengthy deliberation.

They'd been watching what I was building. The tools. The solutions. The self-serve philosophy that was reducing repetitive requests and freeing up the team's capacity.

And here's the truth: **I was already doing the work of a data analyst.**

I wasn't just administering data anymore—I was designing systems, building automation, managing stakeholder relationships, and delivering solutions that had measurable business impact.

The promotion wasn't a reward for potential. It was recognition of what I'd already proven.

### What Changed (And What Didn't)

**What changed:**
- Job title
- Salary (finally)
- Increased autonomy on projects
- More complex stakeholder conversations

**What didn't change:**
- The work (I was already doing it)
- The learning (still constant, still necessary)
- The imposter syndrome (it was quieter, but it never fully left)

With the promotion came a new responsibility: they hired another Data Administrator for me to train.

This was surreal. Eight months earlier, I'd known nothing. Now I was responsible for onboarding someone else into the same role I'd barely survived.

But it forced me to consolidate what I'd learned. Teaching someone else is the fastest way to realise what you actually understand vs. what you've just been blagging through.

### The Work Ethic That Got Me There

I'm not going to pretend the promotion was inevitable. It wasn't.

What got me from "panicking Data Administrator" to "promoted Junior Analyst" in eight months was:

**1. Head down, relentless delivery**

I didn't wait for perfect. I shipped things that worked, then improved them. I took on every ticket I could handle (and some I couldn't). I made myself useful.

**2. Scalable solutions, not quick fixes**

Every tool I built solved the problem *and* prevented it from recurring. Stakeholders didn't need to come back to me—they had systems they could use themselves.

**3. Process improvements that actually improved processes**

I didn't just automate for the sake of it. I looked at workflows, identified bottlenecks, and built tools that removed friction. Real impact, measurable results.

**4. Stakeholder trust**

I delivered what I said I'd deliver. I communicated clearly. I asked the right questions. I didn't overpromise.

This wasn't about being the smartest person in the room. It was about being the most reliable.

### The Colleague Dynamic

Remember that Junior Analyst with a Python Master's degree who was training to be a data scientist?

We ended up supporting each other.

He had strengths. I had strengths. His Python knowledge was deeper and more theoretical; I'd built practical experience with SQL through sheer volume of tickets. He understood statistical modelling; I understood stakeholder management and business context.

We didn't compete. We collaborated.

But I'd be lying if I said the qualification gap didn't bother me. It still does, to this day. That's why certifications are part of my roadmap—not because I need them to do the work, but because imposter syndrome whispers that I'm not "legitimate" without them.

Logically, I know that's nonsense. My work speaks for itself.

Emotionally? I still feel like I'm proving something.

---

## Where I Am Now

It's October 2025. I started at FlintBishop in October 2023.

Two years. That's how long it's taken to go from "I don't know what SQL is" to "I'm confidently building production systems."

**Current role:** Junior Data Analyst (though let's be honest, the "Junior" feels increasingly inaccurate based on what I'm delivering).

**Current skills:**
- **SQL:** Confident. Solo. I can write complex queries, stored procedures, optimise performance, and troubleshoot issues without hand-holding.
- **Excel:** Still relevant, still useful, but no longer my primary tool. I know it inside-out now—properly, not just "I can make a pivot table" level.
- **Python:** Competent. I can build automation, process files, handle APIs, and structure code that doesn't fall apart when someone else looks at it. Still learning, but functional.
- **PowerBI:** Self-taught. Building dashboards, writing DAX, understanding data modelling. Room for growth, but delivering production-ready reports.
- **VBA:** Less frequent now, but still in the toolkit when needed.

**What's changed from October 2023:**

Everything.

I'm no longer frantically Googling basic syntax at midnight. I'm no longer terrified of stakeholder meetings. I'm no longer wondering if I've made a catastrophic mistake every time I deploy something.

I'm... comfortable. Competent. Confident (most days).

The imposter syndrome hasn't vanished—it's just quieter. It still flares up when I'm surrounded by colleagues with formal qualifications or when I'm working on something outside my comfort zone. But I've learned to recognise it for what it is: noise, not truth.

### The Daily Reality

A typical week now looks like this:

**45% SQL** – Writing queries, building stored procedures, data transformation and validation. This is where I'm strongest.

**40% Python** – Automation scripts, file processing, orchestration. Still learning, still improving, but capable of delivering reliable solutions.

**10% Excel** – Still pops up for quick analysis, stakeholder-friendly outputs, or when someone just needs a bloody spreadsheet.

**5% Meetings and stakeholder management** – Understanding requirements, presenting solutions, managing expectations. The soft skills that nobody tells you matter as much as the code.

I'm still using AI daily—Claude mostly, with occasional ChatGPT and Grok depending on the task. Not because I *need* it for basic work, but because it's efficient.

Why spend 20 minutes debugging a complex piece of logic when I can paste it into Claude, explain what I'm trying to achieve, and get a clear explanation in 30 seconds?

Workload vs. staffing constraints is still very much a thing. AI helps me move faster without sacrificing quality.

### The Learning Curve Now

I'm still learning, but the intensity has plateaued slightly.

In the first year, every single day felt like drinking from a fire hose. New concepts. New tools. New mistakes. Constant overwhelm.

Now, the learning is more targeted. I'm not scrambling to understand fundamentals—I'm deepening expertise in specific areas and expanding into adjacent skills.

I can troubleshoot solo where needed. I can read documentation and actually understand it. I can look at someone else's code and follow the logic (most of the time).

But I'm not complacent. The moment you stop learning in this field, you're already behind.

### What's Next

**Short-term goal:** PowerBI and DAX mastery.

I've built dashboards. I've delivered reports. But I know there's a gap between "functional PowerBI user" and "proper BI Developer." I'm working to close that gap.

**Certification goal:** Microsoft PL-300 (Power BI Data Analyst).

Not because I think a certificate will magically make me better at my job, but because imposter syndrome won't shut up about qualifications. If getting certified quiets that voice, it's worth the effort.

**Career goal:** Progress from Junior Data Analyst to Data Analyst, then to BI Developer.

That's the target. That's where the journey is heading.

### The Honest Reflection

If you'd told me in October 2023 that I'd be here—building production systems, automating workflows, managing stakeholder relationships, training other people—I wouldn't have believed you.

I felt like a fraud then. I feel less like a fraud now.

My skills have improved massively. I'm solo on SQL and Excel. I'm competent in Python. I'm functional in PowerBI. I'm delivering work that has measurable business impact.

But the biggest change isn't technical.

It's confidence.

I know I can figure things out. I know I can learn. I know I can deliver.

I'm no longer the person who freezes when someone asks a question I don't immediately know the answer to. I'm the person who says, "I don't know, but I'll find out."

That mindset shift—from "I'm not good enough" to "I'm capable of becoming good enough"—is worth more than any qualification.

---

## The Honest Lessons

Right. Let's talk about what actually worked, what didn't, and what nobody tells you about making this kind of career transition.

### What Worked

**1. Learning by solving real problems**

I didn't learn Python by completing a Udemy course. I learned it because I had 60+ clients with missing files and no scalable way to track them.

I didn't master SQL by reading a textbook. I learned it by writing queries that pulled data stakeholders needed *today*.

Every tool I built served a real purpose. Every line of code solved an actual problem. That context—the *why* behind the learning—made everything stick.

**Lesson:** Don't learn tools in isolation. Find a problem worth solving, then learn whatever you need to solve it.

**2. Building in public (sort of)**

Every tool I built, I shared. With my team. With stakeholders. With leadership.

I wasn't precious about showing work-in-progress or admitting when something could be better. I delivered functional solutions, got feedback, iterated.

This did two things:
- It proved I could deliver value (which led to promotion)
- It forced me to build things people would actually use (not just things that looked impressive)

**Lesson:** Make your learning visible. Build things other people can benefit from. You'll learn faster and get noticed faster.

**3. AI as a tutor, not a crutch**

I used ChatGPT, Claude, and Grok extensively—but I didn't just copy-paste code and hope for the best.

I'd paste error messages and ask for explanations. I'd request breakdowns of complex logic. I'd ask "why does this work?" instead of just "make this work."

Then I'd break the code. Change variables. Test edge cases. Make sure I understood *why* it worked, not just *that* it worked.

**Lesson:** AI is a phenomenal learning accelerator if you use it to *understand*, not to *avoid understanding*.

**4. The self-serve obsession**

Building tools that removed me from repetitive tasks wasn't just efficient—it was strategic.

Every time I automated something, I freed up capacity to learn something new or tackle a bigger problem. And stakeholders loved it because they didn't need to wait for me.

**Lesson:** Automate yourself out of boring work. Use the time you save to build things that matter.

**5. Blocking time like it's a meeting**

Five hours a week, protected in my calendar. Non-negotiable learning time.

Some weeks I stuck to it religiously. Other weeks, work got in the way. But having it scheduled meant I defaulted to learning rather than scrolling LinkedIn or convincing myself I was "too tired."

**Lesson:** If it's not in the calendar, it won't happen. Treat learning like a meeting you can't skip.

**6. Teaching what you learn**

I documented my learning journey by creating comprehensive mastery guides for Python, Excel, PowerBI, Azure DevOps, and QA principles.

This wasn't altruistic—it was selfish learning.

When you teach something, you're forced to understand it at a deeper level. Creating guides with 250+ examples meant I had to test concepts, handle edge cases, and structure information logically.

**Lesson:** Document what you're learning. Publish it. Even if no one reads it, the act of teaching forces mastery.

### What Didn't Work (Or What I'd Do Differently)

**1. Trying to learn everything at once**

In the first few months, I tried to learn VBA, SQL, Python, and PowerBI simultaneously.

Result? Surface-level knowledge of everything, mastery of nothing.

I should've gone deeper on SQL first (since that's where most of the business value was), then layered Python on top once I had a solid foundation.

**Lesson:** Depth beats breadth. Master one tool properly before moving to the next.

**2. Obsessing over dashboard aesthetics in PowerBI**

I spent *hours* perfecting gradients, colour schemes, and visual alignment.

Stakeholders didn't care. They wanted clear numbers and fast answers.

Function > form. Always.

**Lesson:** Build ugly things that work, then make them pretty if there's time. Never the other way around.

**3. Not asking for help sooner**

I was terrified of looking incompetent, so I spent too long trying to figure things out solo.

In reality, asking a colleague for five minutes of their time would've saved me hours of frustration. Most people are happy to help if you ask specific questions.

**Lesson:** "I don't know" is fine. "I don't know and I'm too scared to ask" wastes everyone's time.

### What Surprised Me

**1. Soft skills matter MORE than technical skills**

I thought being an analyst was all about code and queries.

It's not.

It's about understanding what stakeholders *actually* need (which is rarely what they ask for). It's about managing expectations. It's about explaining technical concepts to non-technical people without being condescending.

My years as a Team Leader—coaching, communicating, translating complex problems into plain English—transferred directly. Those skills are worth more than any certification.

**Lesson:** If you've managed people, you've already got half the skills you need. Don't underestimate the value of soft skills in a technical role.

**2. Nobody expects you to know everything**

I thought I needed to be an expert before I could be useful.

Wrong.

People valued problem-solving ability and reliability more than encyclopaedic knowledge. Delivering a functional solution on time beats delivering a perfect solution late.

**Lesson:** You don't need to be the smartest person in the room. You need to be the person who gets things done.

**3. Imposter syndrome doesn't disappear**

I thought once I "proved myself," the self-doubt would vanish.

It hasn't.

It's quieter now. It flares up less often. But it's still there, whispering that I'm not legitimate because I don't have a degree, because I learned on the job, because I still use AI to troubleshoot.

I've learned to recognise it as noise. It doesn't stop me anymore, but it hasn't disappeared either.

**Lesson:** Imposter syndrome is part of the package. Accept it, ignore it, keep building anyway.

**4. Mistakes are expensive, but survivable**

I made errors with financial impacts. Data misalignments. Payment misallocations.

They were fixable. They were learning experiences. They didn't end my career.

The fear of making mistakes is worse than the actual mistakes.

**Lesson:** You will break things. You will get things wrong. Build systems that catch errors, learn from them, and move on.

**5. The journey never stops**

I thought there'd be a point where I'd "arrive"—where I'd know enough to feel comfortable.

That point doesn't exist.

New tools emerge. Business requirements change. Technology evolves. Learning is constant.

But that's also what makes it interesting. If you're not curious, you'll hate this field. If you love learning, you'll thrive.

**Lesson:** Comfort with discomfort is the most valuable skill you can develop.

---

## Advice for Others Making the Transition

If you're reading this from a call centre, a QA role, or any non-technical position thinking "could I actually do this?"—the answer is yes.

But let me be clear about what "yes" actually means.

It doesn't mean it's easy. It doesn't mean you'll do it in three months. It doesn't mean you won't want to quit halfway through.

It means it's *possible*—if you're willing to be uncomfortable for a sustained period of time.

Here's what I'd tell someone starting where I was in 2023:

### Do This

**1. Start solving problems in your current role**

Don't wait for permission. Don't wait for a data role to exist.

Look around your current job and ask: "What manual, repetitive task could I automate? What data do people struggle to access?"

Build something. Even if it's just a better Excel dashboard. Even if it's a VBA macro that saves your team 20 minutes a day.

This does three things:
- Proves you can deliver value with data
- Gives you a portfolio of real work (not tutorial projects)
- Makes you visible to leadership as someone who solves problems

I got hired at FlintBishop because I'd built dashboards at FirstSource. I didn't have skills—I had *proof* I could apply skills to real problems.

**2. Learn with a specific problem in mind**

Don't start with "I'm going to learn Python."

Start with "I need to automate this weekly report. Python can do that. Let me learn enough Python to solve this specific problem."

Context makes learning stick. Tutorials are fine for syntax, but you'll only truly understand a tool when you're using it to solve something that matters.

**3. Use AI as a tutor, not a shortcut**

ChatGPT, Claude, Grok—they're phenomenal learning tools if you use them properly.

**Good use:**
- "Here's my code. It's throwing this error. Can you explain what's going wrong and why?"
- "I'm trying to achieve X. Here's my approach. Is there a better way?"
- "Can you break down how this SQL query works, step by step?"

**Bad use:**
- "Write me a script that does X" → copy-paste → move on

You need to understand *why* the code works. Break it. Change it. Test edge cases. Make it yours.

**4. Block out dedicated learning time**

Five hours a week. Minimum.

Put it in your calendar. Treat it like a meeting you can't skip.

Some of it during work hours (if you can justify it as professional development). Most of it evenings or weekends.

This isn't optional. You can't learn a technical skill by "finding time when you're free." You have to *make* time.

**5. Build a portfolio of real projects**

Not Kaggle competitions. Not "follow-along" tutorials.

Actual tools that solve actual problems.

Publish them on GitHub. Write about them on LinkedIn. Show your work.

When I interviewed at FlintBishop, I didn't have a CS degree or certifications. I had a presentation full of dashboards I'd built that solved real business problems.

That's what got me hired.

**6. Make your learning visible**

Post about what you're building. Share your progress. Write about what you're learning.

Not to show off—to prove you can communicate technical concepts and to make yourself discoverable.

I didn't do this enough early on. In hindsight, it would've opened doors faster.

**7. Ask for stretch assignments**

Volunteer for anything involving data in your current role.

"Can I help build that report?"  
"I'd like to automate that process—can I have a go?"  
"I've been learning SQL—can I shadow the BI team?"

Most managers will say yes if you're offering to take work *off* their plate.

**8. Network locally (and online)**

Find data meetups in your area. Join online communities (r/PowerBI, Power BI Community forums, LinkedIn groups).

Ask questions. Share what you're learning. Connect with people doing the work you want to do.

This isn't about "networking" in the cringey sense—it's about learning from people who've already walked the path.

**9. Document and share what you're learning**

As you learn, create guides, write blog posts, make tutorial videos—anything that forces you to teach what you're learning.

I created four comprehensive mastery guides covering Python, Excel, PowerBI, Azure DevOps, and QA principles. These became:
- **Portfolio pieces** (proof of knowledge)
- **Learning tools** (teaching forced deeper understanding)
- **Community contributions** (helping others on the same path)
- **Confidence builders** (you can't write a mastery guide without believing you know the material)

You don't need to be an expert to teach. You just need to be one step ahead of someone else and willing to share what you've learned.

### Don't Do This

**1. Don't wait until you feel "ready"**

You will never feel ready.

I felt like a fraud when I accepted the Data Administrator role. I still feel underqualified sometimes, two years later.

Apply for roles even if you only meet 60% of the requirements. The worst they can say is no.

**2. Don't quit your job to study full-time**

Learn while earning.

I know it's tempting to think "I'll just take six months off and focus on learning." But unless you have significant savings and zero financial pressure, this is a bad idea.

You'll learn faster solving real problems in a real job than you will grinding through online courses in isolation.

**3. Don't try to learn everything at once**

Depth beats breadth.

Pick one tool. Master it. Build things with it. *Then* move to the next tool.

For most people transitioning into BI/Data Analyst roles, I'd recommend this order:
- **Excel** (if you're not already solid—most people think they're better than they are)
- **SQL** (this is where the business value lives)
- **PowerBI or Tableau** (visualisation and reporting)
- **Python** (automation and advanced work)

But adapt based on what your target role actually needs. Read job descriptions and prioritise accordingly.

**4. Don't ignore the business side**

Technical skills get you in the door. Business understanding keeps you there.

Learn the domain you're working in. Understand how the business makes money. Know what metrics actually matter.

An analyst who understands the business and writes average SQL is more valuable than an analyst who writes perfect SQL but doesn't understand the context.

**5. Don't compare your Chapter 1 to someone else's Chapter 20**

You're competing with CS grads who've been coding since they were 12? So what.

They have different strengths. You have different strengths.

Your non-technical background—leadership, communication, stakeholder management—those are skills they often lack. Leverage them.

Different paths. Same destination.

**6. Don't let imposter syndrome stop you**

It will be there. Accept it. Acknowledge it. Ignore it.

Everyone feels like a fraud sometimes. The difference between people who succeed and people who quit is that the former keep building anyway.

You don't need to feel confident. You just need to keep moving forward.

### One More Thing: You're Not Starting From Zero

When I accepted that Data Administrator role with zero technical skills, I felt like I was throwing away nine years of experience and starting from scratch.

I wasn't.

**You never start from scratch. You start from experience.**

Every skill you've developed—every job you've done—transfers in ways you won't see until you're already doing the new work.

My years as a Team Leader? That became:
- Stakeholder management
- Requirement gathering (listening to what people *actually* need, not just what they say)
- Clear communication of complex ideas
- Project management
- User-focused design thinking

My time in QA? That became:
- Attention to detail
- Process improvement mindset
- Understanding operational workflows
- Building tools that prevent errors

None of that was wasted. None of it was irrelevant.

When you transition careers, you're not abandoning your past—you're repurposing it.

The technical skills? You can learn those. The judgment, the communication, the business understanding—those take years to develop, and you've already got them.

**Don't be afraid to start over. You're not starting from scratch—you're starting from experience.**

And that's a far stronger foundation than you think.

### The Reality Check

Let me be honest about what this actually takes:

**Time investment:** 5-10 hours per week, minimum, for 12-18 months.

That's evenings. Weekends. Time you'd rather spend doing literally anything else.

**Financial reality:** You might take a step back in salary initially (I did). Budget for this possibility.

**Emotional cost:** Imposter syndrome. Frustration. Mistakes with consequences. Moments where you genuinely consider quitting.

**No shortcuts:** Certifications are nice-to-have, not must-haves. Bootcamps can help, but they're not magic. There is no "get skilled quick" scheme that actually works.

But here's the trade-off:

**What you get:** A career with growth potential, intellectual challenge, better pay ceiling, remote work options, and work that genuinely matters.

For me? Absolutely worth it.

For you? Only you can decide.

---

## Resources That Made the Difference

Right, let's talk about the actual tools, courses, and resources that helped me go from "I don't know what SQL is" to "I'm building production systems."

This isn't a comprehensive list of every data learning resource on the internet. It's the specific things *I* used, that *actually* helped, with context on why they mattered.

### AI Tools (The Game-Changers)

**ChatGPT** (Free tier is fine to start)  
- **When I used it:** Late 2023, for basic troubleshooting and syntax questions
- **Why it helped:** Patient tutor that never judged me for asking the same question three different ways
- **Best for:** Quick explanations, debugging simple errors, learning basic concepts

**Claude** (by Anthropic)  
- **When I used it:** From early 2024 onwards—became my primary AI tool
- **Why it helped:** Better at complex coding tasks, clearer explanations, stronger reasoning for multi-step problems
- **Best for:** Building complex scripts, understanding intricate logic, architectural guidance
- **Honest take:** This became my "senior developer" when I didn't have one available in the office

**Grok** (via X/Twitter Premium)  
- **When I used it:** Occasionally, for alternative perspectives
- **Why it helped:** Different training approach sometimes gave fresh angles on stubborn problems
- **Best for:** When ChatGPT and Claude weren't quite hitting the mark

**Critical point:** I never just copy-pasted code. I'd ask these tools to *explain* why something worked, then I'd break it, modify it, and rebuild it until I understood the logic. AI as tutor, not crutch.

### SQL Resources

**SQL Server Management Studio (SSMS)**  
- **Why it mattered:** You learn SQL by writing SQL. SSMS was my playground.
- **What I did:** Asked for read access to company databases, then queried operational data until the syntax became second nature
- **Cost:** Free (if you have access to SQL Server)

**W3Schools SQL Tutorial**  
- **Why it helped:** Clear, simple explanations of basic syntax
- **Best for:** Complete beginners who need to understand `SELECT`, `WHERE`, `JOIN`, `GROUP BY`
- **Cost:** Free
- **Honest take:** Not comprehensive, but excellent for building foundational understanding quickly

**YouTube (various channels)**  
- **Why it helped:** Visual learning for complex concepts like window functions and CTEs
- **Best for:** When written documentation isn't clicking
- **Cost:** Free
- **Approach:** I'd search for specific problems ("SQL calculate running total") rather than following full courses

### Python Resources

**Python Crash Course by Eric Matthes** (Book)  
- **Why it mattered:** Structured learning path with practical projects
- **Best for:** Complete beginners who need hand-holding through fundamentals
- **Cost:** ~£30
- **Honest take:** I didn't finish it. I read the first half, built some basics, then jumped to solving real problems. That's fine.

**Automate the Boring Stuff with Python** (Book + free online version)  
- **Why it helped:** Practical automation examples that directly applied to my work
- **Best for:** People who need to see *why* Python is useful, not just *how* it works
- **Cost:** Free online, or buy the book
- **What I built from it:** File monitoring concepts, automated email logic

**Pandas Documentation**  
- **Why it mattered:** When you're working with data in Python, you're working with Pandas
- **Best for:** Learning data manipulation and transformation
- **Cost:** Free
- **Honest take:** Dense and technical. I used it alongside AI tools to translate the documentation into plain English.

### PowerBI Resources

**Guy in a Cube** (YouTube Channel)  
- **Why it mattered:** Clear, practical tutorials on PowerBI and DAX
- **Best for:** Learning PowerBI features, understanding DAX logic, keeping up with new releases
- **Cost:** Free
- **Honest take:** This channel taught me more than any formal course

**Microsoft Learn** (Official PowerBI Learning Path)  
- **Why it helped:** Structured, comprehensive, directly from the source
- **Best for:** Understanding PowerBI properly, not just cobbling together dashboards
- **Cost:** Free
- **Approach:** I didn't complete entire modules—I cherry-picked topics I needed

**Power BI Community Forum**  
- **Why it mattered:** Real problems, real solutions, real people
- **Best for:** Troubleshooting specific issues, learning from others' mistakes
- **Cost:** Free
- **Honest take:** Search first, ask second. Most problems have already been solved.

**Curbal** (YouTube Channel)  
- **Why it helped:** Excellent for both PowerBI and advanced Excel techniques
- **Best for:** DAX explanations, data modelling concepts
- **Cost:** Free

### Excel & VBA Resources

**Excel VBA Programming for Dummies** (Book)  
- **Why it mattered:** Taught me the fundamentals when I knew absolutely nothing about VBA
- **Best for:** Complete beginners starting with Excel automation
- **Cost:** ~£20
- **Honest take:** Basic, but that's exactly what I needed at the time

**YouTube Tutorials (various)**  
- **Why it helped:** Solving specific problems ("VBA loop through rows," "VBA automate email")
- **Best for:** Learning by doing, not by reading
- **Cost:** Free

**Trial and Error**  
- **Why it mattered:** Honestly? This was the best teacher
- **Best for:** Actually understanding how things work
- **Cost:** Time and frustration
- **Honest take:** You can watch 100 tutorials, but you won't truly understand VBA until you've accidentally deleted an entire worksheet and had to rebuild it

### Communities & Networking

**r/PowerBI** (Reddit)  
- **Why it helped:** Active community, helpful responses, portfolio inspiration
- **Best for:** Seeing what's possible, troubleshooting, learning from others' work
- **Cost:** Free

**LinkedIn**  
- **Why it mattered:** Following data professionals, seeing what skills were in demand, making myself visible
- **Best for:** Building a professional presence, networking, job hunting
- **Cost:** Free (Premium not necessary)

**Local Data Meetups**  
- **Why it helped:** Real conversations with real professionals doing the work
- **Best for:** Understanding what day-to-day work actually looks like, making connections
- **Cost:** Usually free
- **Honest take:** I didn't do enough of this. Wish I'd started earlier.

### My Own Learning Resources

As part of my journey, I created comprehensive mastery guides that I wish had existed when I started:

**Python & Excel Complete Mastery Guide**
- 15 chapters covering integration of Python with Excel
- 250+ practical examples
- From absolute beginner to advanced automation
- Available on my portfolio: https://alanfullagar.github.io/

**PowerBI Complete Mastery Guide**
- Comprehensive DAX and data modelling
- Dashboard design principles
- Real-world business scenarios
- Available on my portfolio: https://alanfullagar.github.io/

**Azure DevOps & GitHub Complete Mastery Guide**
- Version control for data professionals
- CI/CD pipelines for analytics
- Collaboration workflows
- Available on my portfolio: https://alanfullagar.github.io/

**QA Design Principles Complete Mastery Guide**
- Quality assurance best practices
- Testing frameworks
- Process improvement methodologies
- Available on my portfolio: https://alanfullagar.github.io/

These guides represent my learning journey consolidated and structured for others to follow. The act of creating them forced me to truly master the material rather than just understand it superficially.

### What I Didn't Use (And Why That's Fine)

**Formal certifications early on:** I'm pursuing them now, but they weren't necessary to get hired or to deliver value. Skills first, certificates later.

**Expensive bootcamps:** Couldn't afford them. Didn't need them. Focused on free/cheap resources and real-world projects instead.

**University courses:** No degree, no problem. My work spoke louder than credentials.

### The Honest Take on Learning Resources

Here's the truth: **the resource matters less than how you use it.**

You can spend £5,000 on bootcamps and learn nothing if you're just passively consuming content.

You can spend £50 on books and build a portfolio that gets you hired if you're actively solving problems.

The pattern that worked for me:
1. Learn just enough theory to understand the basics
2. Find a real problem to solve
3. Build something that works (even if it's ugly)
4. Use AI/documentation/YouTube to troubleshoot when stuck
5. Iterate and improve
6. Repeat

That's it. That's the system.

Don't get paralysed trying to find the "perfect" learning path. Pick something, start building, and adjust as you go.

---

## Final Thoughts

Two years ago, I was a call centre Team Leader who thought Excel pivot tables were the height of technical sophistication.

Today, I'm building production systems that process data for 60+ clients, automate financial workflows, and deliver measurable business value.

I don't have a Computer Science degree. I didn't go to university. I didn't spend years "preparing" before making the leap.

What I did have was:
- A genuine curiosity about data
- A willingness to be uncomfortable for an extended period
- Real problems that needed solving
- Consistency over 12-18 months
- Stubbornness when imposter syndrome told me to quit

That was enough.

### What This Journey Actually Taught Me

**1. You don't need permission to start learning.**

I didn't wait for a data role to exist. I built dashboards in my call centre job and proved I could deliver value. That got me noticed.

Start where you are. Use what you have. Build what matters.

**2. Mistakes are expensive, but survivable.**

I misaligned data that went to clients. I misallocated payments. I put referrals on the wrong ledgers.

I'm still here. Still learning. Still building.

The fear of failure is worse than the actual failure.

**3. Soft skills are worth more than you think.**

Your leadership experience? Your communication skills? Your ability to understand what people actually need?

Those transfer directly. They're more valuable than you realise.

Technical skills can be taught. Judgment, empathy, and stakeholder management take years to develop—and you've already got them.

**4. There is no "arrival point."**

I thought I'd reach a point where I felt competent and confident and the learning would ease off.

That point doesn't exist.

New tools emerge. Requirements change. Technology evolves. The learning never stops.

But if you're curious—if you genuinely enjoy solving problems—that's a feature, not a bug.

**5. You're not starting from scratch.**

Every skill you've developed, every role you've held, every challenge you've overcome—it all transfers.

You're not abandoning your past. You're repurposing it.

When I walked into FlintBishop with zero technical skills, I felt like I was starting over. I wasn't. I was starting from nine years of leadership, coaching, problem-solving, and stakeholder management.

That foundation matters more than you think.

### If You're Thinking About Making This Transition

Here's what I'd tell you:

**You don't need to feel ready.** You just need to start.

**You don't need a degree.** You need curiosity, consistency, and the ability to solve real problems.

**You don't need to know everything.** You need to know how to learn, how to ask questions, and how to build things that work.

**You don't need years of preparation.** You need to start building now, in your current role, with the tools you already have.

The gap between where you are and where you want to be isn't as wide as it feels.

It's just uncomfortable. And uncomfortable is temporary.

### What's Next for Me

I'm not done.

**Short-term:** Master PowerBI and DAX. Get the PL-300 certification (not because I need it to do the work, but because imposter syndrome won't shut up about credentials).

**Medium-term:** Progress from Junior Data Analyst to Data Analyst, then to BI Developer.

**Long-term:** Keep building. Keep learning. Keep solving problems that matter.

The journey doesn't end. It just evolves.

### What's Next for You?

If you're reading this at 2am, wondering if you can actually make this transition—yes, you can.

But only if you start.

Not next month. Not when you feel "ready." Not after you've completed another online course.

**Now.**

Find a problem in your current role. Build something that solves it. Share it with your team. Do it again.

That's the path. There's no shortcut. But there's also no barrier except the one you create by waiting.

If I can go from call centre Team Leader to BI Developer at 40+ with no technical background, so can you.

The only question is: will you?

---

**Currently seeking:** BI Developer and Data Analyst opportunities where I can leverage my SQL, Python, and PowerBI skills to build scalable solutions that drive business value.

**Connect with me:**  
- **LinkedIn:** https://www.linkedin.com/in/alanfullagar19800509/
- **GitHub:** https://github.com/AlanFullagar
- **Portfolio:** https://alanfullagar.github.io/

I'm always happy to chat with others making similar transitions. Feel free to reach out.

---

*Thank you for reading. Now go build something.*
