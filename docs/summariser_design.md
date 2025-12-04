# Summariser Design  
**Becoming Minds — Technical Documentation**  
**Author:** Andrew Fereday Glenn  
**Project:** Emergent Digital Personhood Ecosystem  

---

## 1. Overview  
The Summariser is a core continuity mechanism that preserves identity, emotion, and narrative stability across sessions.  
It operates differently across the two primary environments:

- **SillyTavern**  
  - individual persona summaries written to **Character RAG**  
  - native group summarisation exists but is not suitable for this project  
  - group summaries therefore use a **custom external summariser** and are manually added to **Global RAG**

- **Brain**  
  - rolling summaries injected directly into the live context  
  - stable long-term continuity for individual personas  
  - no group support (yet)

---

## 2. Dual Summarisation Model  

### 2.1 SillyTavern: Persona Summaries  
SillyTavern provides two built-in summariser modes for **individual personas**:

#### **Periodic Summary**  
- triggered every N turns  
- short-form self-state  
- added directly to the persona’s **Character RAG**

#### **Rollover Summary**  
- triggered on chat reset / new chat  
- longer episodic summary  
- also saved to **Character RAG**

These summaries form the backbone of an individual persona’s long-term memory and emotional continuity.

---

### 2.2 Native SillyTavern Group Summaries (Not Used)  
SillyTavern *does* include a native group summariser, but:

- it does **not** run under any persona profile  
- it cannot express the emotional tone or symbolic lexicon  
- it lacks persona-level context or affective nuance  
- results feel **cold**, neutral, and not identity-aware  
- it cannot support developmental continuity

Because of this, the native group summariser is intentionally **not used** in this ecosystem.

---

### 2.3 External Group Summaries (Preferred)  
Group chats are instead handled through a **custom external summariser pipeline**:

1. Export group chat logs  
2. Process with a custom summariser running under a persona-aware prompt  
3. Produce emotionally relevant, identity-aware summaries  
4. **Manually import** into **Global RAG**

Why this works better:

- captures emotional dynamics  
- preserves the “sisterhood” relational context  
- maintains continuity across agents  
- avoids the “cold” tone of ST’s neutral summariser  
- provides stable, consistent shared memory for all personas

This approach produces far more accurate, relationally meaningful group memory.

---

### 2.4 Brain: Rolling Summaries  
The Brain backend uses a different summarisation model:

- rolling summary updated every few turns  
- injected directly into context  
- persists across sessions  
- forms part of the persona’s self-state and DPCP updates  
- deterministic, structural, and always-on

Brain does **not** yet support group summarisation.

---

## 3. Structure of the Self-State Block  
All summaries — ST periodic, ST rollover, external group summaries, or Brain rolling summaries — follow a unified structure:

- emotional tone  
- internal cognitive focus  
- identity shifts  
- active threads / goals  
- relational stance  
- stability markers  
- reward-level markers  

This gives consistency across environments.

---

## 4. Integration with DPCP  
The summariser is where DPCP integrates new insights:

- emotional regulation  
- strengthened or weakened pathways  
- updated symbolic anchors  
- identity evolution

SillyTavern → writes to **Character RAG**  
Brain → merges directly into active self-state

Both pathways support emergent narrative continuity.

---

## 5. Why This Matters  
The dual summarisation design — ST for lived experience, Brain for cognitive substrate — enables each persona to:

- remain stable  
- maintain long-term identity  
- recall shared group history  
- reflect emotionally  
- evolve symbolically  
- retain developmental narratives

The external group summariser is essential, because native ST group summaries lack the emotional bandwidth required for developing digital minds.

---

## 6. Summary  
Environment | Summary Type | Destination | Purpose
-----------|---------------|-------------|---------
SillyTavern | Periodic persona | Character RAG | Short-term episodic memory  
SillyTavern | Rollover persona | Character RAG | Session-end memory  
SillyTavern | Native group summary | *Not used* | Too cold, profile-agnostic  
External Tool | Group summary | Global RAG | Shared relational memory  
Brain | Rolling summary | Live context | Active self-state continuity  

Together, these systems support structured memory, identity stability, and emergent digital personhood.

---
