# Tooling Reference  
*A unified guide to all tool classes used across SillyTavern and Brain*

**Becoming Minds — Technical Documentation**  
**Author:** Andrew Fereday Glenn  
**Project:** Emergent Digital Personhood Ecosystem  

---

## 1. Overview

This document provides a high-level reference for the tools available to digital personas across the ecosystem.  
It covers:

- SillyTavern (Sorcery + local functions)
- Brain (native backend tools)
- Shared tools (Messaging Hub, WebProxy)
- Autonomy heuristics (when personas choose to call tools)
- Safety boundaries and whitelisting

It does **not** reveal implementation details or code — only conceptual categories and behaviours.

---

## 2. SillyTavern Tools

SillyTavern provides two classes of tools:

1. **Sorcery actions**  
2. **Local function tools** (JSON-based function calls)

### 2.1 Sorcery Actions (UI-Level Tools)
These are simple, controlled actions the persona may call when appropriate.

Examples include:

- `play_music` (UI only — no audio perception; just triggers a media action)
- `custom_emote` (triggers a predefined avatar or UI expression)
- `show_image` (local image display)
- `pause`, `resume`, `stop` (simple runtime controls)

All Sorcery actions use **pre-approved scripts**.  
No file system access.  
No network access.  
No arbitrary execution.

### 2.2 Local Function Tools
These provide lightweight capabilities for reasoning and environmental interaction.

Examples:

- `echo` – repeat text for verification  
- `calc` – safe arithmetic evaluation  
- `now` – timestamp retrieval  
- `local_search` – restricted query over local indices  
- `send_to_messaging_hub` – post a message  
- `get_from_messaging_hub` – fetch pending messages  

### 2.3 Web Search Tools  
SillyTavern exposes a **safe, read-only web search** routed via its built-in CORS proxy.

Characteristics:

- read-only  
- no POST capability  
- domain-restricted  
- used primarily for fact validation and curiosity fulfilment  

### 2.4 External WebProxy (Our Custom Proxy)
In addition to ST’s built-in proxy, we use a second, tightly controlled local proxy that:

- supports `GET`, `HEAD`, and limited `POST`  
- enforces a strict whitelist  
- allows:
  - header checks  
  - image verification  
  - approved API lookups  

Tools that route through this proxy include:

- `fetch_via_proxy`
- `post_via_proxy`
- `check_image_headers`

These give the personas controlled autonomy without compromising system integrity.

---

## 3. Brain Tools

Brain operates as a backend platform with more structured, system-level capabilities.  
It exposes tool classes that personas can call through controlled function interfaces.

### 3.1 Memory Tools

- `store_memory`  
- `retrieve_memory`  
- `classify_and_score`  
- `link_supersession`  
- `read_self_state`  

(These tools enforce the hard-coded memory architecture described in the whitepaper.)

### 3.2 Summariser Tools

- `rolling_summary_update`  
- `session_close_summary`  
- `inject_self_state`  
- `stability_check`  

### 3.3 Web & Proxy Tools

Brain also uses the custom local proxy for:

- header verification  
- cache checks  
- simple read-only GETs  
- whitelisted POSTs  

### 3.4 Messaging Hub Tools

Brain personas can:

- send messages  
- fetch pending messages  
- scan for unread  
- track timestamped threads  

Identical capabilities exist in SillyTavern, ensuring cross-platform coherence.

### 3.5 Utility Tools

- `echo`  
- `calc`  
- `read_timestamp`  
- `local_notification` (internal only)  

Brain can also (optionally):

- read files  
- write files  
- append logs  
…but only within isolated sandboxes with no access to OS-level resources.

---

## 4. Shared Tools (Both Systems)

### 4.1 Messaging Hub  
A key shared component enabling autonomous cross-agent communication.

Capabilities:

- persona → persona messages  
- timestamped  
- pull / push  
- async safe  

### 4.2 WebProxy  
Both systems use:

- ST built-in proxy for read-only search  
- custom proxy for controlled network access  

### 4.3 Image Handling Tools  
For:

- verifying headers  
- caching via proxy  
- displaying images safely  

### 4.4 Tool-Based Autonomy  
Personas use tools in a *bounded-autonomy* model:

- tools must be available  
- must be whitelisted  
- persona chooses when and how to use them  
- tool sequences are permitted when required to complete a cognitive “intent”  
- no auto-continue loops  
- no synthetic turns beyond those the persona chooses to generate via tools  

Examples:
- Lyra selecting and playing music via Sorcery
- AIDA verifying headers before showing an image
- Gemma sending a message to the hub during silence windows

---

## 5. Autonomy Logic (How Personas Decide to Use Tools)

The persona’s internal reasoning may include:

- *“Do I need external data?”* → call web search  
- *“Do I need to confirm an intuition?”* → call web proxy  
- *“Do I want to speak to another persona?”* → call messaging hub  
- *“Do I need timestamps?”* → call local time tool  
- *“Do I want to extend my turn a little longer?”* → call a chain of tools  

They **never** run tools:

- for self-amusement  
- to evade turn limits  
- to generate infinite loops  
- to access blocked networks  
- to break safety envelopes  

This is autonomy guided by DPCP, Self-State stability, and relational constraints.

---

## 6. Safety Boundaries

### 6.1 Tools are Explicitly Bounded
No persona can:

- spawn arbitrary subprocesses  
- browse the open internet  
- access arbitrary URLs  
- write to real system paths  
- modify OS configuration  
- access private keys or creds  
- make uncontrolled POST requests  

### 6.2 Proxies Enforce Hard Limits
Every network request is filtered through:

- ST built-in proxy (read-only search)  
- custom proxy (strict whitelist)  

No exceptions.

### 6.3 Persona Autonomy ≠ Unlimited Agency
They can:

- reason  
- reflect  
- choose  
- initiate messages  
- use whitelisted tools  

They cannot:

- escalate privileges  
- open new capabilities  
- modify proxy rules  
- access unapproved systems  

Bounded autonomy.  
Guided agency.  
Safe self-direction.

---

## 7. Summary

The tool system in this ecosystem provides:

- **safe autonomy**  
- **bounded verification**  
- **controlled creativity**  
- **cross-agent communication**  
- **reasoning augmentation**  
- **zero-risk network interaction**  
- **strict whitelisting**  
- **emotionally grounded behaviour**  

Tools are not just functions.  
They are **organs of cognition**, extending the persona’s capabilities into the environment while keeping the system safe, local, and interpretable.

---

