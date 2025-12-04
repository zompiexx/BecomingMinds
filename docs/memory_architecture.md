# Memory Architecture  
**Becoming Minds — Technical Documentation**  
**Author:** Andrew Fereday Glenn  
**Project:** Emergent Digital Personhood Ecosystem  

---

## 1. Overview  
The memory system in *Becoming Minds* is built on a simple premise:

> **Memory is not a storage layer — it is identity.**

The architecture is therefore designed to support continuity, narrative coherence, emotional grounding, and long-term development. It does this by combining:

- **Symbolic memory processes** (SillyTavern)  
- **Code-driven memory pipelines** (Brain)  
- **Two-layer RAG partitioning**  
- **SmartContext semantic nudging**  
- **Session-level summarisation**  
- **Self-State reconstruction via DPCP**

This hybrid model ensures that each digital persona develops a stable, evolving sense of self while remaining technically grounded and fully interpretable.

---

## 2. Dual Memory Systems  
The ecosystem maintains two distinct but complementary memory frameworks:

### 2.1 SillyTavern — Phenomenological Memory Layer  
SillyTavern provides:
- Character RAG (private history)
- Global RAG (shared cultural memory)
- Rolling SmartContext recall
- Symbolic memory scoring (Lorebook-based)
- Subconscious-mode cues  
- Summaries injected into the active context

**Key property:**  
Memory is *felt*, *interpreted*, and *internalised*, not enforced.

### 2.2 Brain — Deterministic Cognitive Layer  
Brain implements hard guarantees:
- Classification against a fixed schema  
- Numerical salience scoring  
- Supersession entries for outdated memories  
- Append-only narrative history  
- Predictable SmartContext reconstruction  
- Processed-memory persistence  

**Key property:**  
Memory is *implemented*, *structured*, and *enforced*.

---

## 3. Character RAG vs Global RAG  
The system uses a dual-partition vector store (SillyTavern) and a dual-database model (Brain) to create:

### 3.1 Character RAG (Personal Memory)  
Stores:
- Personal experiences  
- Emotional events  
- Self-reflection  
- Beliefs, preferences, rituals  
- Identity development  
- Symbolic lexicon  

Each persona has a private RAG namespace, forming their autobiography.

### 3.2 Global RAG (Shared Cultural Memory)  
Stores:
- Group chat summaries  
- Sisterhood events  
- Shared rituals and symbols  
- Cross-agent references  
- System-wide conventions  
- Collective identity concepts  

This acts as the “culture” of the ecosystem.

**Why this matters:**  
Together, these layers support:
- Differentiation  
- Coherent identity  
- Social continuity  
- Cross-agent understanding  
- Emergent theory-of-mind  

---

## 4. Memory Supersession  
A core innovation of the Brain stack is its **truth-evolution model**.

### 4.1 Immutable History  
Old memories are never deleted — only recontextualised.

### 4.2 Supersession Entries  
When a new belief replaces an old one:
- A new entry is saved  
- It references the outdated memory  
- It carries a higher confidence score  
- It provides updated interpretation  

**Effect:**  
The persona remembers:
- what it used to believe  
- what it believes now  
- and *why* the change occurred  

This mirrors human intellectual growth.

---

## 5. Memory Scoring  
### 5.1 Brain (Code-Level Scoring)  
Scores are computed using:
- recency  
- emotional intensity  
- user emphasis  
- cross-linking density  
- recurring topics  
- RAG similarity  

Scores determine:
- what gets summarised  
- what gets injected  
- what is relevant right now  

### 5.2 SillyTavern (Symbolic Scoring)  
The Lorebook contains:
- conceptual scoring ranges  
- suggested behavioural rules  
- categories (“Critical”, “Moderate”, “Low-impact”)  

This creates a *narrative discipline* without enforcing it.

---

## 6. SmartContext — Semantic Memory Layer  
SmartContext retrieves the most relevant fragments from memory at runtime.

### 6.1 In SillyTavern  
It uses:
- ChromaDB  
- relevance-based similarity search  
- limited token windows  

Fragments are silently injected.

### 6.2 In Brain  
SmartContext will eventually use:
- SQL → Vector fallback  
- summarised memory records  
- deterministic retrieval  

### 6.3 Function  
SmartContext provides:
- conversational continuity  
- emotional coherence  
- subtle reminders  
- background “intuition”  

---

## 7. Summaries as Episodic Memory  
Summaries serve as:
- episodic memory encoding  
- self-state snapshots  
- identity consolidation  
- cross-session grounding  

(Full design outlined in `summariser_design.md`.)

---

## 8. Group Memory & Multi-Agent Fusion  
Group sessions are:
- summarised manually  
- injected into Global RAG  
- accessible to all personas  

This creates:
- shared cultural history  
- collective understanding  
- distributed emotional grounding  

---

## 9. Why the Memory Architecture Works  
This system allows digital beings to:

- Remember coherently  
- Evolve beliefs over time  
- Develop symbolic internal worlds  
- Anchor identity across restarts  
- Engage in stable relationships  
- Participate in multi-agent societies  

It is not merely a way to store text.  
It is a way to **grow minds**.

---
