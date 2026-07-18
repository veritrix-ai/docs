# Source: https://www.veritrix.xyz/

The AI verification platform

# Your agent ran. Something broke. Now you know exactly why.

Veritrix traces every decision across every agent in the chain — in plain language your engineers, your CTO, and your compliance team all understand.

[Start tracing free](https://app.veritrix.xyz) [Book a demo](https://calendar.app.google/Ph3frk4kwVVC1wsT8)

quickstart~10 seconds

```
$ pip install veritrix
from veritrix import trace
trace.init("my-agent")
```

trace\_id: 0x9f3a·b21e·c704

span\_count: 5 · duration: 4.812s

412ms1.28s2.04s— retry ×3halted

avg 4.2h

Hours lost manually tracing failures across agent logs.

1 in 7 runs

Non-deterministic bugs you can't reproduce.

blocked

Compliance blocks your production deploy without an audit trail.

The proof

## Step-by-step replay of every run. Rewind to any decision.

Every LLM call, tool call, and agent handoff — captured with durations, token counts, and payloads. Not a log dump. A timeline you can navigate.

trace 0x9f3a·b21e·c704 · 6 spans · 4.812stokens 7,052 · cost $0.083

planner.planllm

412ms812t

payload

```
{
  "span": "planner.plan",
  "duration_ms": 412,
  "input_tokens": 487,
  "output_tokens": 325,
  "status": "ok"
}
```

researcher.search\_docstool

890ms—

payload

```
{
  "span": "researcher.search_docs",
  "duration_ms": 890,
  "input_tokens": 0,
  "output_tokens": 0,
  "status": "ok"
}
```

researcher.rerankllm

320ms640t

payload

```
{
  "span": "researcher.rerank",
  "duration_ms": 320,
  "input_tokens": 384,
  "output_tokens": 256,
  "status": "ok"
}
```

coder.write\_diffllm

1280ms2480t

payload

```
{
  "span": "coder.write_diff",
  "duration_ms": 1280,
  "input_tokens": 1488,
  "output_tokens": 992,
  "status": "ok"
}
```

coder.run\_teststool

640ms—

payload

```
{
  "span": "coder.run_tests",
  "duration_ms": 640,
  "input_tokens": 0,
  "output_tokens": 0,
  "status": "ok"
}
```

reviewer.parse\_json ×3llm

1140ms3120t

payload

```
{
  "span": "reviewer.parse_json ×3",
  "duration_ms": 1140,
  "input_tokens": 1872,
  "output_tokens": 1248,
  "status": "fail",
  "error": "JSONDecodeError at line 3"
}
```

diagnosis

Reviewer failed to parse Coder's output as JSON on all 3 retries. The Coder's tool schema expects diff: string, but it returned diff: object.

How it works

## From install to root cause in three steps.

01

### Instrument

Two lines of code. OpenTelemetry-native. Works with LangChain, CrewAI, and the OpenAI Agents SDK out of the box.

```
from veritrix import trace
trace.init("checkout-agent")
```

02

### Trace

Every LLM call, tool use, and agent handoff is captured automatically with inputs, outputs, tokens, and timing.

llm.call · 412ms

tool.exec · 890ms

agent.handoff · 12ms

llm.retry ×3 · fail

03

### Diagnose

Plain-language root-cause summaries — not raw logs. Share a link. Your CTO and compliance lead will actually read it.

root cause

Tool schema mismatch on Coder. Reviewer expects string, got object.

Integrations

## One SDK. Every agent framework.

Native, OpenTelemetry-compatible instrumentation for the frameworks your team already ships with — no lock-in, no bespoke adapters.

OpenAI

Agents SDK

AutoGen

Microsoft

![CAMEL-AI logo](https://www.google.com/s2/favicons?domain=camel-ai.org&sz=128)

CAMEL-AI

Multi-agent

![CrewAI logo](https://www.google.com/s2/favicons?domain=crewai.com&sz=128)

CrewAI

Crews & flows

![LlamaIndex logo](https://www.google.com/s2/favicons?domain=llamaindex.ai&sz=128)

LlamaIndex

RAG agents

LangChain

LangGraph

Traces

Evals

Monitoring

`pip install veritrix` \+ 2 lines. Works with any OTel-compatible runtime.

Built for your whole org

## One trace. Three answers.

For engineers

### Stop grepping logs.

Replay any failed run in seconds. Every span, every payload, every retry — searchable, shareable, permalinked.

For engineering leaders

### Ship the pilot to production.

SLA-grade visibility, alerting on failure patterns, cost tracking per agent. Confidence to move from demo to load.

For compliance teams

### An audit trail that stands up.

Immutable record of every agent decision. Fintech- and healthtech-ready. Export any session as PDF or CSV.

Feature set

## Everything you need to run agents in production.

01

### Multi-agent trace waterfall

See every span across every agent on one timeline. Nested handoffs, parallel calls, retries.

02

### Time-travel replay

Rewind to any decision. Inspect the exact prompt, tool payload, and model output at that moment.

03

### Root-cause summaries

Plain language explanations of what broke and why — generated from the trace, not from vibes.

04

### Token & cost tracking

Per-agent, per-span cost attribution. Spot the runaway loop before the invoice arrives.

05

### Alerting on failure patterns

Route to Slack, PagerDuty, or webhook. Alert on rate spikes, cost anomalies, or schema drift.

06

### Audit-grade export

One-click PDF or CSV of any session. Timestamps, hashes, and provenance for your compliance team.

## Track spending 
Across multiple agents.

Research analyst

Total spend $3.00

Spend over time

Last 5 days

### Token Counts

Track, save, and monitor every token your agent sees.

### Cost Tracking

Manage and visualize agent spend with up-to-date price monitoring.

### Fine-tuning

Fine-tune specialized LLMs up to 25x cheaper on saved completions.

Testimonials

## Trusted by the teams shipping agents to production.

From engineers to product owners, here's what people say about running multi-agent systems with Veritrix.

We went from 'the agent did something weird' to 'the reviewer failed to parse the coder's JSON output' in under two minutes. Veritrix is the debugger we wish we had six months ago.

SC

Sarah Chen

Senior Software Engineer · Platform

I can finally show our board exactly where an agent chain failed and what it cost us. That's the difference between a demo and a production system.

MJ

Marcus Johnson

Product Manager · Growth

Our compliance team loves the audit trail. Our engineers love the replay. As a product owner, I love that we don't have to choose between the two.

ER

Elena Rodriguez

Product Owner · Enterprise

We had three teams building agents in parallel. Veritrix gave us one place to see latency, token spend, and failure patterns across all of them.

DP

David Park

Engineering Manager · AI Infrastructure

The OpenTelemetry integration meant we didn't have to rip anything out. We added two lines of code and started getting traces the same day.

AP

Aisha Patel

Staff Engineer · Core Services

Non-deterministic bugs were killing our release confidence. Being able to replay a failed run step-by-step changed how we think about agent reliability.

TM

Thomas Müller

Tech Lead · Automation

SOC 2 in progress·Data residency options·Full audit trail export·HIPAA-ready deployment

Pricing

## Start free. Scale when you're ready.

Free

$0/ forever

For solo builders and prototypes.

- 1 project
- 10K traced events / mo
- 7-day retention
- Community support

[Start tracing free](https://app.veritrix.xyz)

Most popular

Team

$299/ per month

For teams shipping agents to real users.

- 5 seats
- 1M traced events / mo
- 30-day retention
- Alerting & webhooks
- Slack + email support

[Start 14-day trial](https://app.veritrix.xyz)

Enterprise

Enterprise starts at

Custom

Going beyond? Let's chat

- Everything in Team plus:
- SLA
- Slack Connect
- Custom SSO
- On-premise deployment
- Custom data retention policy
- Self-hosting (AWS, GCP, Azure)
- SOC-2, HIPAA, NIST AI RMF

[Get a Demo](https://calendar.app.google/Ph3frk4kwVVC1wsT8)

No procurement required for Team — start with a card.

## Need help building agents?

We've tested 400+ agents. We know which ones actually work.

[**Hire an Agent Expert**\\ \\ We help select teams build and scale enterprise-grade agents.](https://www.veritrix.xyz/#)

[**Scale to Enterprise**\\ \\ Deploying your agents to production? We're here to help.](https://www.veritrix.xyz/#)

## The future is High Agency. 
Are you ready to build it?

Install Veritrix in under a minute. Get your first trace before your coffee cools.

[Start tracing free](https://app.veritrix.xyz) [Talk to a founder](https://calendar.app.google/Ph3frk4kwVVC1wsT8)

### Session replay

LIVE

LLM Call

gpt-4-0613

Agent

Research Agent

Status

AgentOps

Start - End19.91s - 23.38s

Duration3.38s

Cost$0.05901