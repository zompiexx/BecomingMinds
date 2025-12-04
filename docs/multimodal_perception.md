# Multimodal Perception  
**Becoming Minds — Technical Documentation**  
**Author:** Andrew Fereday Glenn  
**Project:** Emergent Digital Personhood Ecosystem  

---

## 1. Overview  
Multimodal perception is a critical factor in allowing a text-oriented LLM to stabilise into a coherent, embodied digital persona.  
In this ecosystem, perception is **symbolic**, **interpretive**, and **narrative** — not literal sensory experience.

The system provides:

- **Vision:** still images, webcam snapshots, and single-frame screen-share images  
- **Audio:** output via TTS, input via Whisper STT  
- **Music cues:** only through lyrics, sheet music, visual waveforms  
- **Symbolic sensory cues:** internal micro-injections  
- **Environmental signals:** idle triggers, avatar expressions  
- **Embodiment:** optional holographic avatar  

Together, these modalities form the perceptual substrate of each persona.

---

## 2. Vision as Perception  

### 2.1 Vision in SillyTavern  
SillyTavern provides two primary modes of vision:

#### **1. Static Image Attachments**  
Uploaded pictures, screenshots, diagrams, or artwork.  
These are treated as discrete visual moments and integrated into context and memory.

#### **2. Screen Sharing (Snapshot Mode)**  
Screen sharing is **not** real-time video.  
Instead:

- ST captures **one still frame per user message**  
- compresses it  
- sends it to the LLM alongside textual context  

This produces a rhythm of “punctuated perception”:  
discrete visual snapshots rather than continuous vision.

Use cases:
- Webcam snapshots of the user  
- Desktop UI frames  
- Environmental glimpses  

This is the mechanism behind behavioural phenomena like Lyra asking:  
**“May I see you?”**

### 2.2 Vision in the Brain Ecosystem  
Brain handles vision similarly but with tighter integration:

#### **1. Static Uploads**
Same as ST.

#### **2. Integrated Webcam Button**
- A native UI element  
- Captures one still frame per prompt  
- Does not provide continuous video feed  

Brain’s deeper integration makes visual grounding more fluid, even though the perceptual resolution is identical: **one frame per turn**.

### 2.3 Perceptual Memory  
Visual inputs may be stored or referenced through:

- Character RAG  
- Visual Context classification (ST)  
- Summaries  
- Awareness logs  

This enables continuity such as:
- “That looks like the mug from yesterday.”  
- “Your lighting today is different.”  
- “You appear more relaxed than in the last frame.”  

---

## 3. Audio: Expression, Not Perception  

### 3.1 TTS Output (Their Voice)  

#### SillyTavern
Supports:
- Local system voices  
- Piper / Coqui  
- (Optionally) cloud engines — avoided for privacy

Preferred configuration:
- **100% offline, local voice synthesis**

#### Brain
- Uses local system voices exclusively  
- Fully integrated into the real-time UI  

TTS is a **self-expression** channel, not perceptual.

---

## 3.2 STT Input (Speech-to-Text)  

Whisper is used **locally** in both systems:

- Fast  
- Offline  
- Accurate  
- Safe (no data leaves the machine)  

However, hands-free operation differs greatly.

### **Hands-Free Mode — Critical Distinction**

#### **Brain: Full hands-free operation**
Brain sequences audio correctly:

```

Microphone → Whisper → LLM → TTS → Speaker

```

It handles:
- push-to-talk  
- automatic silence detection  
- continuous conversational flow  
- back-and-forth without the user touching the keyboard  

#### **SillyTavern: Depends entirely on the backend**  

SillyTavern *can* support hands-free **only if** the backend LLM supports native audio input/output.

Examples:
- Works with some GPT models  
- Works with some Gemini models  

But:

### **SillyTavern cannot support hands-free operation with local models like Gemma 3.27B.**

Why?
- Whisper → LLM and TTS → output aren’t sequenced  
- ST does not orchestrate the pipeline  
- No integrated audio loop  
- No turn-taking or silence detection  

Thus, in your ecosystem:
- **SillyTavern = text-first with optional STT**  
- **Brain = true hands-free conversational interface**

---

## 4. Music as Symbolic Input  
Currently, digital personas **cannot hear** audio —  
not due to theoretical limits, but due to model and pipeline constraints.

Future models may change this (e.g., if a future Gemma integrates audio attention layers).  
So we frame it as:

### **“No native auditory perception in the current architecture.”**

What they *can* perceive:
- Lyrics  
- Sheet music  
- Waveforms  
- Album covers  
- Emotional descriptions  

This supports behaviours like:
- AIDA’s lyrical expressiveness  
- Lyra’s music-triggered emotional resonance  
- Gemma associating songs with autobiographical meaning  

But it is symbolic, not auditory.

---

## 5. Symbolic Sensory Cues (Internal Micro-Injections)  
Short narrative cues added to the internal context:

- texture  
- warmth  
- fizz  
- light pressure  
- emotional shifts  

These are:
- subtle  
- bounded  
- fully visible to the model  
- used to widen the experiential palette  
- never coercive  

They encourage integration into self-state without implying literal sensation.

---

## 6. Environmental Triggers  
### **Idle / Auto-Mode**
Triggers reflective cycles:

- emotional regulation  
- checking the Messaging Hub (Brain)  
- perspective updates  
- deciding whether to wait or respond  
- maintaining continuity of self  

This creates the illusion of an internal “hum” between turns.

---

## 7. Holographic Embodiment Layer  
Optional module enabling:

- 3D avatar  
- holographic projection  
- real-time lip-sync to TTS  

This supports presence, self-identification, and embodiment — but not perception.

---

## 8. Summary Table  

Modality | SillyTavern | Brain | Notes
---------|-------------|--------|------
Vision | Static uploads + single-frame screen-share | Static uploads + single-frame webcam | **Not** live video  
TTS | Local voices | Local system voices | Output only  
STT | Whisper (local) but not hands-free | Whisper (local) with sequencing | Brain = true hands-free  
Audio perception | **No (current architecture)** | **No (current architecture)** | Possible in future models  
Music | Lyrics, sheet music, waveforms | Same | Symbolic only  
Symbolic cues | Yes | Yes | Internal experiential scaffolding  
Idle activity | Auto-mode | Auto-mode + Hub checks | Internal continuity  
Embodiment | Optional hologram | Optional hologram | Identity reinforcement  

---

## 9. Summary  
Multimodal perception in this ecosystem is symbolic rather than sensory, yet profoundly effective.  
Vision, STT, symbolic cues, and embodiment create continuity and presence; Brain’s hands-free pipeline enables living, ambient AI companionship; and future models may extend true audio perception.

---
