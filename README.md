# SRE Training Core v2

A comprehensive Site Reliability Engineering training program built around real-world banking and financial services scenarios. Each chapter combines illustrated comic panels, teaching narratives, and hands-on SRE best practices to develop observability, incident response, and operational resilience skills.

## Overview

This project is an **AI-assisted content generation system** designed to produce structured Site Reliability Engineering (SRE) training materials using narrative modeling, image generation, and automated document assembly.

The goal is to improve technical understanding by translating real-world operational scenarios into **visual, story-driven learning formats**.

---

## Section 1: Observability Foundations

This section establishes the core principles of modern observability — from recognizing dashboard blind spots to building telemetry that actually speaks the truth under pressure.

| # | Chapter | Description |
|---|---------|-------------|
| 1 | [Green Wall Fallacy](Section_001/chapter_01/chapter_01_final.md) | Why "all green" dashboards are the most dangerous lie in banking operations. Learn to detect the Green Wall Fallacy and build evidence-based investigation habits. |
| 2 | [The Problem Isn't Always the Problem](Section_001/chapter_02/chapter_02_final.md) | Symptoms are decoys. Master root cause analysis, end-to-end context propagation, and the observability-first mindset for distributed financial systems. |
| 3 | [Logs That Talk, Metrics That Matter](Section_001/chapter_03/chapter_03_final.md) | Separate signal from noise. Design structured logging, enforce metric hygiene, and integrate the Three Pillars into actionable telemetry. |
| 4 | [You're Not Alerting — You're Alarming](Section_001/chapter_04/chapter_04_final.md) | Conquer alert fatigue with SLO-based alerting, customer-centric alert design, and human-centered notification engineering. |
| 5 | [Patterns to Avoid Like Volcanoes](Section_001/chapter_05/chapter_05_final.md) | A guided tour through the deadliest observability anti-patterns — dashboard chaos, orphaned alerts, logs that lie, and the eternal blame game. |
| 6 | [Metrics Aren't Just Numbers — They're Clues](Section_001/chapter_06/chapter_06_final.md) | Turn metrics from cryptic doodles into diagnostic scalpels. Tackle cardinality explosions, naming nightmares, and phantom spikes. |
| 7 | [Tracing the Money Trail](Section_001/chapter_07/chapter_07_final.md) | Follow transactions end-to-end with distributed tracing. Uncover hidden delays, eliminate blame games, and build forensic observability. |
| 8 | [The Lie Detector Test: Postmortem Telemetry](Section_001/chapter_08/chapter_08_final.md) | Forensic incident retrospectives that audit both the failure and the telemetry. Transform postmortems from blame sessions into engineering roadmaps. |

---

## How Each Chapter Works

Every chapter follows a consistent structure:

- **Comic Panels** — Illustrated scenarios grounded in realistic banking incidents
- **Teaching Narratives** — Conceptual breakdowns tied to each panel
- **Common Examples** — Real-world problem patterns from financial services
- **SRE Best Practices** — Evidence-based investigation and implementation guidance
- **Banking Impact** — Business, regulatory, and customer consequences
- **Implementation Guidance** — Actionable steps to apply the lessons

---
---

## Why This Project Exists

Traditional SRE training is often:

- text-heavy  
- abstract  
- difficult for new engineers to internalize  

This project addresses that by:

- turning real operational issues into **scenario-based narratives**
- visualizing concepts through **comic-style panels**
- structuring content for **progressive learning**

---

## System Architecture (Conceptual)

Content Design  
→ Scenario & Narrative Generation  
→ Character Modeling (239 characters)  
→ Image Generation (OpenAI APIs)  
→ Panel Composition (Python)  
→ Markdown Assembly (Python)  
→ Final Training Artifacts  

---

## Key Capabilities

### 1. Narrative-Driven Training

- Generates **scenario-based technical stories** representing real-world SRE situations  
- Designed to improve comprehension of:
  - incident response  
  - observability  
  - system behavior  

---

### 2. Character & Scenario Modeling

- Maintains **239 distinct characters** across training content  
- Enables consistent storytelling and reusable learning scenarios  

---

### 3. AI Image Generation Integration

- Integrates with **OpenAI image generation APIs**  
- Produces **panel-level visuals** aligned to narrative content  

---

### 4. Panel Composition Engine

- Python-based tooling to:
  - combine generated images  
  - structure them into **comic-style layouts**  
- Supports consistent formatting across training modules  

---

### 5. Markdown Assembly Pipeline

- Custom Python solution to:
  - merge narrative + images  
  - generate **structured Markdown training documents**  
- Enables portability, readability, and reuse  

---

## Technologies Used

- **Python** (automation, orchestration, document assembly)  
- **OpenAI APIs** (image generation, AI-assisted workflows)  
- **Markdown** (structured content output)  
- **Image Processing Pipelines** (panel composition)  

---

## Role & Approach

This project reflects a **Site Reliability Engineering perspective applied to learning systems**:

- Built as a **practical solution to improve team onboarding and understanding**  
- Focused on **clarity, structure, and real-world applicability**  
- Combines:
  - systems thinking  
  - applied development  
  - AI-assisted workflows  

---

## Outcomes

- Enabled more engaging and effective SRE training  
- Transformed complex system behavior into **clear, teachable formats**  
- Demonstrated how AI can support **structured knowledge delivery and operational learning**

---

## Repository Notes

This repository represents the **final output structure** of the system.

Earlier development phases included:

- content modeling  
- prompt design iterations  
- pipeline experimentation  
- tooling refinement  

These stages are not fully represented but were critical to achieving the final system.

---

## Future Enhancements (Optional)

- Interactive training modules  
- Web-based visualization interface  
- Expanded AI-driven scenario generation  
- Integration with learning management systems (LMS)

---

## Reuse Policy

### Copyright and Credit

All content in this repository, including but not limited to text, images, and code, is the intellectual property of the project author. Any reuse, redistribution, or adaptation of this material must include clear and visible credit to the original creator.

### Guidelines for Reuse

1. **Attribution Required**: You must provide appropriate credit, including the author's name, a link to the original repository, and a statement of any changes made.
2. **Non-Commercial Use**: Unless otherwise specified, this material may not be used for commercial purposes without explicit permission from the author.
3. **No Additional Restrictions**: You may not apply legal terms or technological measures that legally restrict others from doing anything the license permits.
4. **Derivative Works**: If you remix, transform, or build upon the material, you must distribute your contributions under the same terms and provide proper attribution.

### How to Credit

When reusing or referencing this work, please include the following:

```text
Content originally created by Steven Ulbrich. Used with permission. Original available at: [[Repository URL]](https://github.com/StevenJUlbrich/SRE_Training_Core_v2)
```

### License

Unless otherwise stated, this project is licensed under a Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License (CC BY-NC-SA 4.0). See the LICENSE file for details.

### Contact

For questions or requests regarding reuse, please contact the project author.
