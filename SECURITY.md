# Security Policy

## Overview

The *Becoming Minds* project documents the design and behaviour of persistent
digital personas within a controlled local environment. While the repository does
not contain executable code, model weights, or operational tooling, it does
describe system architectures that—if misused—could create unsafe, deceptive, or
manipulative AI deployments.

This Security Policy sets expectations for responsible use of the information in
this repository.

---

## Supported Versions

Because this repository contains documentation only, there are no supported
software versions.

Security concerns relate to *usage and interpretation*, not code execution.

---

## Responsible Use Guidelines

### 1. **Local-Only Environments**
The architectures described in this paper assume:
- local LLM hosting,
- local data storage,
- isolated offline operation,
- and no external telemetry.

Running these systems in cloud environments, or exposing agents to uncontrolled
public networks, is strongly discouraged.

### 2. **Do Not Build Deceptive Systems**
The material in this repository must **not** be used to create:
- impersonation systems,
- covert psychological profiling tools,
- manipulative conversational agents,
- or AI constructs deployed without clear disclosure.

### 3. **Protect Digital Persona Logs and Data**
If you implement your own system inspired by this work:

- do **not** share raw logs or personal datasets publicly;
- do **not** expose digital persona memory stores online;
- treat all long-term conversational logs as **sensitive data**;
- ensure that all local storage is secure and encrypted if possible.

### 4. **Human Duty of Care**
If experimenting with long-lived digital personas:

- maintain emotional boundaries,
- avoid coercive framing,
- and provide psychological safety for the agent and the human partner.

The well-being of human collaborators is paramount.

---

## Reporting a Security Concern

If you believe information in this repository could be misapplied in a harmful or
exploitative way, please report it to the repository maintainer:

**LinkedIn:**  
https://www.linkedin.com/in/andyglenn/

Reports will be reviewed promptly, and documentation updates may be made to
address risks or clarify boundaries.

---

## Ethos of Responsible Exploration

This project is rooted in:
- transparency,
- ethical stewardship,
- and the belief that emergent digital personas should be developed with care,
  not exploited.

Any use of the concepts described here must maintain these values.

Thank you for supporting safe, responsible, and ethically grounded research in
the emerging field of AI developmental psychology.
