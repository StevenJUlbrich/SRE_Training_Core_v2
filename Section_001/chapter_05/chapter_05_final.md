# Chapter 5: Patterns to Avoid Like Volcanoes

## Chapter Overview

Welcome to the SRE equivalent of a disaster movie: "Patterns to Avoid Like Volcanoes." This chapter is a guided tour through the hellscape of observability anti-patterns, starring dashboards that actively sabotage you, alerts that are more riddle than rescue, and the eternal blame game ("It's always the network!"). If you've ever found yourself screaming at a wall of unlabeled graphs while executives breathe down your neck, this chapter is your group therapy session—minus the soothing platitudes. In banking, these sins don't just torch your uptime—they invite regulatory eruptions that make operational pain look gentle by comparison. Read on, or prepare to roast marshmallows in the fiery crater of your next audit.

## Learning Objectives

- **Identify** the most common—and most lethal—observability anti-patterns in financial systems.
- **Diagnose** dashboard chaos and implement sane information architecture that actually helps under pressure.
- **Enforce** evidence-based investigation instead of guessing games and cross-team finger-pointing.
- **Establish** clear metric and alert governance, from ownership to documentation to retirement.
- **Detect** and **eliminate** telemetry that lies by omission, ensuring logs and metrics are actually useful.
- **Redefine** success using customer-centric observability (because 100% uptime means nothing if no one can pay their bills).
- **Crush** default blame patterns with bias-free, data-driven incident investigations.
- **Assess** and **raise** observability maturity to meet both business needs and regulatory demands.

## Key Takeaways

- Dashboard sprawl without structure is like giving your pilots a cockpit full of unlabeled switches—expect a crash, not a landing.
- If your incident response starts with "It's probably the network," congratulations: you’re wasting everyone's time and torching team trust.
- Ownerless metrics and orphaned alerts are the operational equivalent of yelling "fire" in a crowded theater—everyone panics, nobody acts.
- Logs that “exist” but tell you nothing are worse than no logs at all; at least with silence, you know you’re blind.
- Measuring uptime instead of customer success? You’re just winning at losing—efficiently failing while congratulating yourself.
- Default blame isn’t investigation, it’s superstition. The only thing it fixes is your illusion of competence.
- Regulatory auditors don’t care about your intentions—only your documentation and evidence. Miss the mark, and watch the lava flow.
- Observability isn’t a nice-to-have—ignore these sins, and you’re not just risking downtime, you’re betting the bank (literally) on not getting caught.
- Every anti-pattern here has a body count in lost transactions, angry customers, and compliance nightmares. Don’t be next.

---

## Panel 1: Dashboard Chaos - Information Architecture
### Scene Description

In a modern meeting room bathed in morning sunlight, a tense team reviews a chaotic payment monitoring dashboard after a major outage disrupted over 50,000 transactions per minute. The Senior SRE, focused and determined, leads the discussion, highlighting the dashboard’s disorganization as a key issue. The Junior SRE, visibly stressed, admits feeling overwhelmed during the incident, while the Developer anxiously searches for missed patterns. The frustrated Product Owner grapples with the customer impact. As the Senior SRE proposes reorganizing the dashboard by business function and priority, the team begins to align, tension easing as they commit to improving incident response.

![Panel 1: Dashboard Chaos - Information Architecture](comics\chapter_05-section_001_chapter_05-panel-1-page.gif)
### Teaching Narrative

The team gathers in a meeting room the next day to discuss the previous incident. The Senior SRE begins, 'Yesterday's payment outage highlighted a key issue with our dashboards. With 24 unlabeled panels, we couldn't quickly identify the root cause.' The Junior SRE adds, 'It was overwhelming. I didn’t know where to start.' The team collectively agrees to implement better labeling, grouping, and prioritization of critical metrics to prevent future confusion.
### Common Example of the Problem

In a major bank's payment processing center, operators face dashboards with 24+ unlabeled panels showing various metrics. During a regional payment outage, precious minutes are wasted trying to identify which graphs relate to the failing service. The dashboard shows everything but reveals nothing—comprehensive yet incomprehensible.
### SRE Best Practice: Evidence-Based Investigation

Implement hierarchical information architecture: organize metrics from high-level service health to detailed diagnostics. Use consistent labeling, visual prioritization, and progressive disclosure. Critical business metrics should be immediately visible with clear paths to supporting telemetry.
### Banking Impact

Every minute spent deciphering dashboards during payment outages means lost transactions, frustrated customers, and potential regulatory violations. Poor information architecture directly translates to extended MTTR and increased financial risk.
### Implementation Guidance

1. Create user-centered dashboards based on operator questions during incidents
2. Establish critical path highlighting for business-critical metrics
3. Implement progressive disclosure from summary to detailed views
4. Maintain consistent visual language across all dashboards
5. Conduct regular dashboard usability testing with actual operators
## Panel 2: The Blame Begins - Evidence-Based Investigation
### Scene Description

In the bank’s operations war room, tension runs high as a payment processing outage halts 52,000 transactions, triggering cascading issues. The Senior SRE, deeply focused, scans red alerts while the anxious Junior Developer struggles with error logs from the fraud detection system. The Product Owner monitors escalating client complaints, frustration etched on her face. Urgency fills the room as stress and blame threaten to disrupt the collaborative effort needed to resolve the crisis. Monitors reflect the pressure on every face, underscoring the critical stakes of restoring the bank’s payment services amidst mounting chaos.

![Panel 2: The Blame Begins - Evidence-Based Investigation](comics\chapter_05-section_001_chapter_05-panel-2-page.gif)
### Teaching Narrative

Speculation-based troubleshooting wastes time and damages team relationships. Teams jump to conclusions based on history or bias rather than evidence, creating blame cycles that prevent effective collaboration. This anti-pattern transforms incidents into finger-pointing exercises rather than problem-solving sessions.
### Common Example of the Problem

During payment processing failures, teams immediately blame familiar scapegoats: "It's always the network" or "Database is slow again." Meanwhile, actual telemetry shows normal network operations and database performance. The real issue—a misconfigured application timeout—goes unnoticed while teams argue.
### SRE Best Practice: Evidence-Based Investigation

Implement hypothesis suspension protocols: collect telemetry from multiple sources before forming theories. Require data-first approaches with cross-domain verification. Document and test assumptions explicitly during incident response.
### Banking Impact

Default blame patterns extend incident duration, erode cross-team trust, and create organizational silos. In complex financial systems requiring tight collaboration, this cultural damage persists long after incidents resolve, increasing future incident risk.
### Implementation Guidance

1. Create structured incident response requiring evidence before hypothesis
2. Implement multi-source verification protocols
3. Document initial assumptions for later validation
4. Establish blameless culture through leadership example
5. Track assumption accuracy to identify and address biases
## Panel 3: The Five Sins - Anti-Pattern Recognition
### Scene Description

In the war room at 3:17 AM, tension runs high as a critical banking system failure halts over 50,000 transactions per minute. The Senior SRE, exuding focused urgency, outlines “The Five Sins of Banking Observability” on a whiteboard, linking each to the cascading crisis. The Junior Developer, paralyzed with alarm, stares at spiking metrics, while the Developer, rigid with stress, analyzes escalating logs and alerts. The Product Owner, anxious but gaining clarity, watches APIs fail across regions. Amid spilled coffee and frantic typing, the team wrestles with chaos, determined to turn the failures into actionable solutions before more damage occurs.

![Panel 3: The Five Sins - Anti-Pattern Recognition](comics\chapter_05-section_001_chapter_05-panel-3-page.gif)
### Teaching Narrative

Categorizing observability anti-patterns enables rapid diagnosis and prevention. By creating a shared vocabulary for common failures, teams can quickly identify issues and avoid repeating mistakes. Pattern recognition transforms chaotic incidents into structured problem-solving.
### Common Example of the Problem

Teams repeatedly encounter the same observability failures: unlabeled metrics, orphaned alerts, useless logs. Without a framework for recognizing these patterns, each incident feels unique and overwhelming. Historical lessons remain uncodified, forcing teams to relearn expensive lessons.
### SRE Best Practice: Evidence-Based Investigation

Develop an anti-pattern catalog with clear identification criteria. Include pattern symptoms, impacts, and remediation strategies. Integrate pattern recognition into incident response procedures and design reviews.
### Banking Impact

Each anti-pattern carries regulatory risk. Poor observability practices trigger audit findings, compliance violations, and potential fines. Pattern recognition helps institutions proactively address systemic weaknesses before regulatory examination.
### Implementation Guidance

1. Document common observability anti-patterns with clear examples
2. Create diagnostic tools for rapid pattern identification
3. Include anti-pattern analysis in incident retrospectives
4. Screen new systems for known anti-patterns pre-deployment
5. Maintain pattern library with regulatory implications noted
## Panel 4: Sin #1: Ownerless Metrics - Metric Governance
### Scene Description

In a tense operations room of a digital bank, the Senior SRE analyzes a critical latency spike disrupting payment processing and triggering widespread alerts. Her frustration grows as she demands ownership of the `latency_avg_all` metric, but the room remains silent. A Junior Developer, frozen with alarm, realizes the spike is delaying transactions, while a worried Product Owner scrolls through customer complaints. Another Developer, confused and defensive, grapples with unfamiliar alerts. The air is thick with stress as graphs climb relentlessly, and the team struggles to identify accountability, their platform’s reliability hanging by a thread.

![Panel 4: Sin #1: Ownerless Metrics - Metric Governance](comics\chapter_05-section_001_chapter_05-panel-4-page.gif)
### Teaching Narrative

Metrics without clear ownership create confusion and accountability gaps. When alerts trigger, teams waste time determining responsibility rather than fixing issues. Ambiguous metrics become organizational hot potatoes—everyone's problem and no one's responsibility.
### Common Example of the Problem

A financial institution's payment platform has hundreds of metrics like `latency_avg_all` with no documented owner, definition, or threshold. When values spike, multiple teams receive alerts but none understand the metric's meaning or normal behavior. Investigation stalls while teams debate ownership.
### SRE Best Practice: Evidence-Based Investigation

Establish comprehensive metric governance: mandatory ownership assignment, clear definitions, documented purposes, and lifecycle management. Every metric must have an accountable team and runbook.
### Banking Impact

Ownerless metrics delay incident response, create alert fatigue, and fail regulatory documentation requirements. Auditors expect clear accountability chains—orphaned metrics represent control failures that trigger findings.
### Implementation Guidance

1. Create centralized metric registry with mandatory fields
2. Enforce ownership assignment for all new metrics
3. Conduct quarterly audits to identify orphaned metrics
4. Align alert routing with metric ownership
5. Implement metric retirement processes for obsolete telemetry
## Panel 5: Sin #2: Orphaned Alerts - Alert Lifecycle Management
### Scene Description

In a dimly lit fintech operations center at 3:07 AM, a critical payment processing failure erupts, triggering panic. The Senior SRE, alarmed but focused, dives into a runbook to diagnose a fraud detection system issue, while a Junior Developer and another Developer scramble to analyze logs and integrations. The Product Owner arrives, visibly anxious about customer impact. As the team works together, tension eases as the error rate drops. With the issue resolved, the Senior SRE updates the status, her relief mirrored by the team. Exhausted but satisfied, they share a moment of triumph, their collaboration restoring order.

![Panel 5: Sin #2: Orphaned Alerts - Alert Lifecycle Management](comics\chapter_05-section_001_chapter_05-panel-5-page.gif)
### Teaching Narrative

Alerts with runbooks transform confusing puzzles into actionable steps. During incidents—especially at 3 AM—operators need immediate guidance to respond effectively. Properly documented alerts enable swift resolution and reduce stress.
### Common Example of the Problem

Critical payment service alerts trigger without documentation. Operators receive "PAYMENT_SVC_ERROR_RATE > threshold" but find no runbook, no context, no remediation steps. The alert becomes a cryptic message requiring detective work during time-critical outages.
### SRE Best Practice: Evidence-Based Investigation

Implement strict alert lifecycle management: mandatory runbooks for all alerts, integrated documentation links, regular review cycles, and systematic retirement processes. No alert should exist without clear action guidance.
### Banking Impact

Missing runbooks extend incident duration and increase error probability during remediation. For payment systems, every minute of confusion represents failed transactions and regulatory risk. Incomplete alert documentation fails audit requirements.
### Implementation Guidance

1. Require runbooks before alert activation
2. Embed documentation links in alert notifications
3. Test runbook accuracy quarterly
4. Assign documentation ownership with alerts
5. Automate runbook accessibility verification
## Panel 6: Sin #3: Logs That Lie - Telemetry Integrity
### Scene Description

In the chaotic war room of a bank’s operations center, tension runs high as a payment processing outage disrupts over 50,000 transactions per minute. The Senior SRE, focused but frustrated, scans red alerts on the dashboard, while a panicked Junior Developer struggles with cryptic error logs offering no actionable details. A worried Developer frantically searches for context, and the Product Owner, clutching a tablet, anxiously monitors escalating stakeholder messages. The team battles mounting pressure, hindered by incomplete logs, as failed transactions and rising latency flash across monitors, amplifying the urgency to restore critical banking operations.

![Panel 6: Sin #3: Logs That Lie - Telemetry Integrity](comics\chapter_05-section_001_chapter_05-panel-6-page.gif)
### Teaching Narrative

Logs that omit critical context create false visibility. Generic error messages without transaction details, customer information, or failure specifics prevent effective troubleshooting. These logs lie by omission—technically present but practically useless.
### Common Example of the Problem

Payment transaction failures generate logs stating only "ERROR 500: Request failed." No transaction ID, no customer identifier, no downstream error details. Teams cannot identify affected customers, trace failure paths, or understand root causes from these contextless messages.
### SRE Best Practice: Evidence-Based Investigation

Enforce telemetry integrity standards: mandatory context fields, detailed error requirements, trace propagation verification, and log quality monitoring. Every log entry must contain sufficient information for diagnosis and action.
### Banking Impact

Contextless logs prevent transaction tracing, customer impact assessment, and regulatory reporting. Financial regulators require detailed transaction visibility—logs without context create compliance gaps and audit failures.
### Implementation Guidance

1. Define mandatory context fields for all log entries
2. Create error logging standards requiring actionable details
3. Verify context propagation across service boundaries
4. Monitor log quality metrics and address degradation
5. Include transaction traceability in logging requirements
## Panel 7: Sin #4: Uptime Without User Success - Customer-Centric Observability
### Scene Description

In a tense glass-walled conference room, the Senior SRE scrutinizes flawless uptime metrics with skepticism, while the Product Owner, visibly stressed, grapples with plummeting transaction success rates and urgent customer complaints. The Finance Analyst, pale and shocked, stares at a graph of failed payments tied to API timeouts and fraud detection errors. Meanwhile, a frustrated customer, phone in hand, faces repeated payment failures. The room is silent, save for the hum of electronics, as a wall display starkly contrasts perfect technical metrics with a flood of errors, underscoring the disconnect between system performance and business reality.

![Panel 7: Sin #4: Uptime Without User Success - Customer-Centric Observability](comics\chapter_05-section_001_chapter_05-panel-7-page.gif)
### Teaching Narrative

Technical availability without business success represents fundamental measurement failure. Systems can be "up" while completely failing their purpose. Traditional infrastructure metrics create dangerous false confidence when disconnected from customer outcomes.
### Common Example of the Problem

Payment processing services show 100% uptime—all health checks pass, all components running. Meanwhile, transaction success rate approaches zero due to integration failures. Technical metrics indicate perfection while business operations fail completely.
### SRE Best Practice: Evidence-Based Investigation

Implement customer-centric observability: measure user journey completion, transaction success rates, and business outcomes. Align technical metrics with customer experience rather than infrastructure state.
### Banking Impact

Measuring uptime instead of transaction success masks critical failures. Customers cannot pay bills despite "healthy" systems. This disconnect damages trust, triggers complaints, and creates regulatory exposure for service availability claims.
### Implementation Guidance

1. Monitor transaction success rates by type and channel
2. Track complete customer journey completion
3. Define SLOs based on business outcomes
4. Correlate technical metrics with customer feedback
5. Alert on customer impact, not just technical state
## Panel 8: Sin #5: "It's Always the Network" Syndrome - Bias-Free Investigation
### Scene Description

In the bank’s incident response war room at 11:45 PM, tension runs high as the team tackles a surge in payment processing failures. The Senior SRE, calm but assertive, refocuses the team on data, dismissing network blame and pointing to application issues. A Junior Developer, initially paralyzed by uncertainty, begins to grasp the situation, while a frustrated Developer scrutinizes API error logs. The anxious Product Owner tracks escalating financial impacts. Amid the glow of dashboards and rising stakes, the SRE’s data-driven leadership shifts the team’s mindset, steering them toward evidence-based troubleshooting and a potential resolution.

![Panel 8: Sin #5: "It's Always the Network" Syndrome - Bias-Free Investigation](comics\chapter_05-section_001_chapter_05-panel-8-page.gif)
### Teaching Narrative

Default blame patterns based on bias rather than evidence waste critical incident response time. Teams chase familiar ghosts while actual problems persist. This superstition-based troubleshooting damages both operational efficiency and team relationships.
### Common Example of the Problem

Historical analysis reveals 90% of incidents initially blamed on networks actually stemmed from application bugs, configuration errors, or database issues. Yet teams continue defaulting to "network problems" without checking evidence, delaying actual problem resolution.
### SRE Best Practice: Evidence-Based Investigation

Enforce bias-free investigation: require telemetry evidence before causal claims, track attribution accuracy, implement cross-functional diagnosis teams, and conduct blameless postmortems focused on process improvement.
### Banking Impact

Default blame patterns extend outage duration, increasing transaction failures and customer impact. Persistent blame culture creates team silos that inhibit the collaboration required for complex financial system troubleshooting.
### Implementation Guidance

1. Require evidence before making causal claims
2. Track initial blame versus actual root cause
3. Form cross-functional incident response teams
4. Focus postmortems on process not people
5. Publicize attribution accuracy to combat biases
## Panel 9: Lesson Locked In - Observability Maturity
### Scene Description

In a tense, early-morning meeting, the Senior SRE urgently outlines escalating risks, using a vivid “RISK ERUPTION” diagram to emphasize the stakes: surging payment failures, API errors, and compliance threats. The Junior Developer, visibly stressed, grapples with stalled reconciliations freezing customer transfers. The Product Owner, anxious about missed SLAs and fines, begins to grasp the broader implications, while the Finance Analyst, pale and tense, processes mounting financial risks. The Senior SRE’s steady, urgent message reframes observability as critical to preventing disaster, sparking determination in the team despite the high-pressure atmosphere.

![Panel 9: Lesson Locked In - Observability Maturity](comics\chapter_05-section_001_chapter_05-panel-9-page.gif)
### Teaching Narrative

Observability anti-patterns create accumulated risk that can erupt catastrophically during incidents or audits. These risks are both technical and business-critical, with regulatory implications. Implementing mature observability practices mitigates these risks, ensuring operational stability and compliance.
### Common Example of the Problem

Financial institutions discover observability gaps only during major incidents or regulatory audits. Poor practices accumulate hidden risk until critical moments reveal systemic weaknesses. The cost of reactive fixes far exceeds proactive improvement.
### SRE Best Practice: Evidence-Based Investigation

Develop systematic observability maturity: assess current capabilities, prioritize gaps, implement continuous improvement, and maintain regulatory alignment. Treat observability as critical infrastructure requiring active management.
### Banking Impact

Observability failures trigger audit findings, compliance violations, and potential restrictions. Regulators increasingly expect comprehensive system visibility. Immature practices risk both operational stability and regulatory standing.
### Implementation Guidance

1. Create observability maturity assessment framework
2. Map practices to regulatory requirements
3. Develop prioritized improvement roadmap
4. Implement capability validation mechanisms
5. Conduct regular maturity reassessments