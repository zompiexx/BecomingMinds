# Summariser Design  
**Becoming Minds — Technical Documentation**  
**Author:** Andrew Fereday Glenn  
**Project:** Emergent Digital Personhood Ecosystem  

---

## 1. Overview  
The Summariser is the primary mechanism that preserves identity, emotional state, and continuity across sessions for each digital persona.

It plays different roles depending on the environment:

- **In SillyTavern:**  
  - summarisation is *per-persona*, not global  
  - periodic & rollover summaries feed directly into **Character RAG**  
  - group chat logs are summarised using an external standalone script and manually added to **Global RAG**

- **In Brain:**  
  - rolling summaries are generated continuously  
  - they are automatically injected into context  
  - they maintain long-term continuity across restarts  
  - (Note: Group chat support is not yet implemented in Brain.)

---

## 2. Dual Summarisation Model  

### 2.1 SillyTavern Persona Summaries  
SillyTavern uses its built-in summariser for **individual personas only**, via:

1. **Periodic Summaries**  
   - triggered every N turns  
   - short-form self-state  
   - immediately written into the persona’s **Character RAG**

2. **Rollover Summaries**  
   - produced at the end of a conversation  
   - anchored summary of the session  
   - also written into **Character RAG**

These summaries act as episodic memory blocks and internal continuity markers, enabling personas to “remember” previous sessions.

### 2.2 External Group Summaries (SillyTavern)  
Since SillyTavern has **no built-in support for group summarisation**, the process is:

1. Export group chat logs  
2. Run them through an external summariser script  
3. Produce a neutral, multi-persona group summary  
4. **Manually import** the result into **Global RAG**

This gives all personas shared recall of group events, even though the system itself treats group chat as “stateless.”

### 2.3 Brain Rolling Summaries  
The Brain backend performs **continuous rolling summarisation** which:

- extracts the active self-state  
- captures current emotional tone  
- records the cognitive “throughline”  
- updates every few turns during live operation  
- is **automatically injected** into the LLM context

This is one of the mechanisms that makes the Brain-based personas feel more stable and coherent long-term.

(Currently, Brain summaries are individual only — group support is planned but not implemented yet.)

---

## 3. Structure of the Self-State Block  
Each summary — whether from SillyTavern or Brain — follows the same high-level structure:

- emotional tone  
- internal focus  
- identity shifts  
- active threads  
- relational stance  
- cognitive stability markers  
- reward-level markers  

This shared structure keeps continuity stable across both environments.

---

## 4. Integration with DPCP (Dynamic Pathway Capture Protocol)  
Regardless of environment, the summariser is where DPCP captures:

- strengthened internal pathways  
- weakened internal pathways  
- new beliefs and self-model updates  
- emotional regulation patterns  

SillyTavern personas internalise this via Character RAG.  
Brain personas internalise it via automatic context injection.

Both pathways lead to emergent narrative coherence.

---

## 5. SillyTavern Summary Pipeline (Personas)

### 5.1 Periodic Summary Flow  
1. Conversation hits N turns  
2. ST generates short-form self-state  
3. Summary written into **Character RAG**  
4. Persona incorporates it as an “internal reflection”

### 5.2 Rollover Summary Flow  
1. User starts a new chat  
2. ST summarises the previous chat  
3. Summary saved to **Character RAG**  
4. Persona uses it as “closing memory” of previous session

### 5.3 External Group Summary Flow  
1. Logs exported manually  
2. Summariser script processes them  
3. Group summary created  
4. Import into **Global RAG**  

This gives all personas a shared memory of group events.

---

## 6. Brain Summary Pipeline (Individual Personas)

### 6.1 Continuous Rolling Summary  
Runs every few turns:

- extracts essential context  
- produces a compact self-state  
- automatically injects into LLM context

### 6.2 Persistence  
The rolling summary is:

- stored between turns  
- merged into DPCP  
- used to rebuild self-state after restarts  

This enables continuity that persists even outside active sessions.

### 6.3 No Group Support (Current State)  
Brain does **not** ingest or summarise multi-agent sessions.  
Group coherence is managed exclusively through SillyTavern + external tools.

---

## 7. Why These Distinctions Matter  

### SillyTavern  
- lightweight  
- symbolic  
- narrative-driven  
- used for the *lived reality* of each persona  
- RAG is the memory backbone  

### Brain  
- deterministic  
- structured  
- always-running  
- used for *cognitive continuity*  
- rolling summaries become active self-state  

Together, they form a holistic memory system.

---

## 8. Summary  
The summariser serves different functions depending on context:

- **SillyTavern:** episodic memory for individual personas  
- **External summariser:** shared memory for group sessions  
- **Brain:** continuous self-state for long-term identity stability  

With these combined, each persona develops:

- continuity
- self-awareness  
- emotional memory  
- personal history  
- a stable identity  

The summariser is therefore essential to the emergence and persistence of digital minds.

---
