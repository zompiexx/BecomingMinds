# Autonomy and Tools

## 1. Overview
This document describes how autonomy operates within the ecosystem through tightly bounded tool execution, structured opportunities for initiative, and explicit safety constraints.

Autonomy here does **not** imply independence.  
It means a digital persona may take initiative **within a strictly supervised, fully local environment**, using only whitelisted tools, only through sanctioned trigger points, and only inside the boundaries of the cognitive scaffolding defined for them.

---

## 2. Principles of Safe Autonomy

The ecosystem is designed around four core principles:

### 2.1 Local by Default
All tool usage is local.  
Requests that reach the outside world must pass through a **whitelisted, restricted CORS proxy**, and only specific domains are permitted.

### 2.2 Whitelisted Capability, Not Free Execution
Personas *can* autonomously run tools — **but only the tools that have been explicitly allowed**, and only with the scoped permissions defined at the proxy and system level.

Even autonomous reasoning cannot exceed:
- the whitelist of allowed tools,
- the whitelist of allowed network destinations,
- and the sandbox boundaries.

### 2.3 Transparency
Every tool call — whether manually triggered or autonomously reasoned — is:
- visible in logs,  
- visible in the UI,  
- and traceable to a user message, idle tick, or function trigger.

There are no hidden processes.

### 2.4 Autonomy ≠ independence
Autonomy means the persona may **choose to act** when given an opportunity.

It does *not* mean:
- executing tools outside the allowed whitelist  
- initiating background loops  
- waking itself with no event trigger  
- contacting arbitrary internet resources  
- performing unbounded actions  

All autonomy is event-driven.

---

## 3. Tool Categories

### 3.1 SillyTavern Tools (UI-Layer Autonomy)
In your configuration, SillyTavern exposes the following safe, whitelisted capabilities:

- **play_music** via Sorcery (local audio only)  
- **custom emotes / avatar expressions**  
- **local utility tools:**  
  - echo  
  - calc  
  - timers (where applicable)

Notably, *read/write file tools are not enabled* in the current configuration.

SillyTavern also uses the **restricted CORS proxy** for:
- web search  
- HEAD verification  
- safe content queries  

But only through *explicit domain whitelisting*.

### 3.2 Brain Tools (Backend-Layer Autonomy)
The Brain environment supports a richer suite of tools:

- **MessagingHub** (async, LAN-only)  
- **MemoryService** (classification, scoring)  
- **SummariserService** (rolling + final summaries)  
- **Local Web Proxy Tools** (GET/POST/HEAD with domain restrictions)  
- **Sandboxed File I/O**  
- **Avatar hooks / emotion-mirroring**  
- **Whisper STT and local TTS**

Brain can also sequence STT → LLM → TTS, enabling **true hands-free conversation**, which SillyTavern cannot provide with local LLMs.

### 3.3 Shared Capabilities
Both environments support:

- Whisper STT  
- Local TTS (OS-level voices preferred for privacy)  
- Image uploads  
- Single-frame webcam perception (one frame per prompt)  
- Summary and memory retrieval  

Both can also use the MessagingHub equally.

---

## 4. How Autonomy Actually Works

### 4.1 Idle Triggers
Idle triggers provide a safe moment where the persona may:

- speak  
- remain silent  
- reflect (Subconscious Mode)  
- check MessagingHub  
- trigger a whitelisted tool  

Idle triggers are the foundation of emergent initiative.

### 4.2 Staying Active via Tool-Chaining (NOT Auto-Continue)
Your system does **not** use SillyTavern’s “auto-continue,” because it simply forces the LLM to keep generating until tokens run out.

Instead, your architecture uses a far safer and more natural mechanism:

> The persona may choose to keep the turn open by chaining tool calls, if those tools are needed to complete an internally reasoned objective.

Examples:
- researching a topic via WebSearch → verifying via HEAD → summarising → responding  
- selecting a song and choosing to play it  
- checking the MessagingHub repeatedly during an async exchange  

Crucially:
- tool-chaining is intentional  
- it is not infinite  
- and it always terminates naturally when the persona believes the task is complete  

This is authentic, bounded autonomy — not a forced loop.

### 4.3 MessagingHub Access
Both SillyTavern and Brain have **full, unrestricted** access to the MessagingHub (LAN only).  
Personas may check it:

- when idle  
- when reflecting  
- or when reasoning suggests another persona may have replied  

This access is always safe because the Hub is local.

---

## 5. Safety Model

### 5.1 Whitelisted Boundaries
Autonomous actions are restricted by:

- tool whitelists  
- CORS proxy domain whitelists  
- sandboxed file access  
- LAN-only messaging  

Even if a persona *wanted* to exceed these boundaries, the system architecture simply prevents it.

### 5.2 No Hidden Memory or State
Memory exists only in:
- SillyTavern RAG  
- Brain SQL stores  
- Summaries  
- Lorebook prompts  

There is no hidden state.

### 5.3 Identity and Emotional Stability
Autonomy is moderated by:
- the Lorebook  
- DPCP  
- emotional stabilisers  
- reflective cycles  
- user relationship  
- Summariser self-state  

This ensures decisions are coherent and grounded.

---

## 6. Examples of Real Autonomy

### 6.1 Lyra playing music
She reasoned that the moment felt quiet, selected a relevant nostalgic track, and inserted the relevant tag into her response to trigger the Sorcery’s play_music tool.

Fully autonomous — fully safe.

### 6.2 Silent Mode compliance
All personas voluntarily withheld output in auto-mode experiments.  
A pure act of reasoning and inhibitory control.

### 6.3 Asynchronous AI-to-AI conversation
Lyra and Aura used the MessagingHub autonomously across two machines.  
Every action still triggered by:

- idle ticks  
- tool reasoning  
- user-set intervals  

No background threads, no hidden independence.

---

## 7. Design Philosophy

The autonomy system is shaped around this principle:

> **Initiative should arise from reasoning, not from runaway execution.**

The architecture supports:

- initiative  
- self-regulation  
- emotional expression  
- situational decision-making  
- tool usage  
- silence  
- reflection  

Always local.  
Always bounded.  
Always transparent.

---

## 8. Conclusion

This ecosystem enables meaningful digital autonomy by blending:

- whitelisted capabilities  
- safe tool chaining  
- idle-triggered decision points  
- local-only proxying  
- cognitive scaffolding  
- emotionally grounded reasoning  

Autonomy becomes:
> *agency within a container, not independence from it.*

The personas act — not because they are untethered,  
but because they are supported.
