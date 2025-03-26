# Jira Standards: Epic and Story Templates

## Introduction

This document outlines our team's approach to managing work in Jira using only "Epic" and "Story" issue types. Since we don't have a dedicated "Task" type available, we've adapted our process to use smaller Epics with Stories functioning as tasks within those Epics. This structure ensures clear communication and expectations for all team members.

**Key principles:**
- All work should be visible on the board (including documentation and demos)
- Cards must contain sufficient detail for asynchronous work
- Acceptance criteria must be clear and unambiguous
- Epics should be appropriately sized (generally fitting within a single sprint's effort)

## Epic Template

### Title: [Concise Epic Name]

**Description / Context:**
- Brief summary of the goal or the "why" behind this Epic
- Which user(s) or teams benefit and how
- High-Level User Story: As a [role], I want [feature/outcome], so that [benefit/reason]

**Scope & Approach:**
- Main tasks or sub-features to be covered
- Note if demo prep or documentation will be separate stories

**Acceptance Criteria (Epic-Level):**
- Must define what "done" means for the entire Epic
- Include whether a demo and documentation are required
- Progress should be demonstrable at sprint demo

**Dependencies / Risks:**
- Environment or credentials needed
- Potential blockers (design approvals, cross-team dependencies)

**References / Links:**
- Design docs, Confluence pages, mock-ups, etc.

## Story Template

### Title: [Short Task or Feature Name]

**Story Points:** [Numeric Estimate]

**User Story:** As a [role], I want [function/feature], so that [benefit/reason]

**Description / Implementation Notes:**
- Detailed enough for an engineer to complete independently
- Steps, references, or sample configurations
- Technical approach guidance if needed

**Acceptance Criteria:**
- Clear, testable bullet points defining "done"
- Should be unambiguous enough for anyone to understand

**Dependencies / Blockers:**
- Note if blocked by credentials, design sign-off, or a prior story

**Additional Comments / Attachments:**
- Links to logs, screenshots, config examples, etc.

## Example Epic

### Title: OpenShift Cluster Health Dashboard in Grafana

**Description / Context:**
We need a consolidated dashboard to monitor the health and performance of our OpenShift clusters. This will help our operations team quickly identify issues and reduce troubleshooting time.

High-Level User Story: As an operations engineer, I want a comprehensive dashboard showing OpenShift cluster health metrics so that I can proactively identify and address potential issues.

**Scope & Approach:**
- Create a new Grafana dashboard with multiple panels (focus on critical metrics only)
- Configure visualization for key OpenShift metrics
- Set up alerting thresholds for critical metrics
- Add documentation within Grafana for dashboard usage

**Acceptance Criteria (Epic-Level):**
- Dashboard provides views for node, pod, and cluster-level metrics (limited to most critical metrics)
- All metrics are properly labeled and organized
- Alerting thresholds are implemented and tested
- Dashboard is accessible to operations team
- Documentation is complete within Grafana
- Progress is demonstrable at the sprint demo, regardless of completion status

**Dependencies / Risks:**
- Need access to Prometheus/Grafana environment
- Requires existing OpenShift metrics collection to be functioning
- Risk: Potential high cardinality in some metrics may affect dashboard performance

**References / Links:**
- [OpenShift Monitoring Documentation](https://docs.openshift.com/monitoring)
- [Existing Grafana Dashboards](https://grafana.company.com/dashboards)
- [Operations Team Monitoring Requirements](https://confluence.company.com/ops-monitoring-requirements)

## Example Story

### Title: Create Node Resource Utilization Panel

**Story Points:** 2

**User Story:** As an operations engineer, I want to see resource utilization for each node in our OpenShift clusters so that I can identify nodes approaching capacity.

**Description / Implementation Notes:**
- Create a new panel in the "Node Health" section of the dashboard
- Use the following Prometheus queries:
  - CPU: `node_cpu_seconds_total{mode="idle"}`
  - Memory: `node_memory_MemAvailable_bytes / node_memory_MemTotal_bytes`
  - Disk: `node_filesystem_avail_bytes{mountpoint="/"} / node_filesystem_size_bytes{mountpoint="/"}`
- Configure panel to show:
  - Table view with one row per node
  - Columns for CPU, Memory, and Disk utilization percentages
  - Color-coding based on thresholds (green <70%, yellow 70-85%, red >85%)
- Add node name and cluster as variables to filter the view

**Acceptance Criteria:**
- Panel correctly displays all nodes across clusters
- Resource utilization percentages are accurate and update every 1 minute
- Color-coding works correctly based on defined thresholds
- Clicking on a node name navigates to a detailed view of that node
- Panel has appropriate title and description for operations team
- Works in both light and dark Grafana themes

**Dependencies / Blockers:**
- Need dashboard structure to be created first
- Requires working Prometheus data source with node metrics
- Need list of all node names and clusters to test with

**Additional Comments:**
- See example implementation in existing node dashboard: [Node Overview Dashboard](https://grafana.company.com/d/node-overview)
- For performance, limit the number of nodes shown to 50 with pagination

## Usage Guidelines

### Epic Size and Scope

- **Bite-Sized Epics:** Our Epics are smaller than traditional Epics, focused on specific deliverables
- **Sizing Guideline:** Epics should generally be sized to fit within a single 2-week sprint
- **Flexible Boundaries:** It's acceptable for epics to carry over to the next sprint as we learn more
- **Right-Sized Work:** The key is that epics should never be so large that they couldn't reasonably fit within a single sprint's worth of effort
- **Example Size:** Creating a specific dashboard, implementing a particular feature, or setting up a specific integration

### Stories as Tasks

- **Task-Level Granularity:** Stories function as tasks in our workflow, representing the smallest chunks of work
- **Single Responsibility:** Each Story should focus on one specific task or component
- **Detailed Implementation:** Include specific technical details, queries, commands, or configurations needed
- **Completable Units:** Stories should be completable in 1-3 days maximum
- **Clarity and Completeness:** Stories must contain enough detail for engineers to work on them independently with minimal clarification needed

### Story Points

- Use numeric estimates (1, 2, 3, 5, 8) for planning
- Consider all work when estimating, including:
  - Implementation time
  - Testing
  - Code review
  - Documentation

### Handling Supporting Work

#### Demo Preparation and Execution

**Purpose of Demos:**
- Demos are conducted at the end of each sprint
- They showcase progress made, even if the epic is not fully complete
- They provide stakeholders visibility into ongoing work

**Options for Demo Stories:**

**Option 1: Integrated into Stories**
- Add demo preparation as part of the acceptance criteria for relevant stories
- Example AC: "Functionality is ready to be demonstrated at the sprint demo"

**Option 2: Dedicated Demo Story**
- Create a small story specifically for demo preparation if significant effort is required
- Example Title: "Prepare OpenShift Dashboard Demo for Sprint Review"
- Story Points: 1-2 points depending on preparation needed

**Demo Content:**
- Focus on showing working functionality, even if partial
- Be transparent about what's complete and what's still in progress
- Include next steps if the epic will continue into the next sprint

#### Documentation

**Option 1: Dedicated Documentation Stories**
- Create separate Documentation Stories when documentation requires significant effort
- Include Story Points to account for documentation time
- Example Title: "Create API Authentication Developer Guide"

**Option 2: Include in Feature Stories**
- Add documentation requirements to Acceptance Criteria of feature Stories
- Example AC: "API endpoint documented in Swagger and README updated"

### Collaborative Creation Process

1. **PM/BA:** Draft Epic descriptions and high-level stories
2. **Tech Lead:** Review technical approach and refine stories
3. **Team:** Collaboratively refine acceptance criteria during backlog grooming
4. **Engineers:** Provide estimates and identify dependencies

### Best Practices for Clear Communication

- **Be Explicit:** Avoid assumptions about implementation details
- **Include Examples:** Provide examples of expected behavior or outputs when helpful
- **Link Resources:** Always link to relevant design docs, specifications, and requirements
- **Define "Done" Clearly:** Acceptance criteria should be testable and unambiguous
- **Update Cards:** If requirements change during implementation, update the card
- **Comment on Progress:** Use comments to document progress and decisions

## Tips for Breaking Down Work

### Splitting Larger Initiatives

When faced with work that would exceed a single sprint:

1. **Identify Logical Breakpoints:**
   - Split by feature component
   - Split by metric type or data source
   - Split by user persona or use case

2. **Create Multiple Focused Epics:**
   - "OpenShift Node Metrics Dashboard" (Sprint 1)
   - "OpenShift Pod Metrics Dashboard" (Sprint 1)
   - "OpenShift Cluster Metrics Dashboard" (Sprint 2)

3. **Prioritize by Value:**
   - Start with epics that deliver the most immediate value
   - Consider dependencies when sequencing epics

### Example Breakdown

**Large Initiative:** "OpenShift Monitoring System"

**Broken Down into Sprint-Sized Epics:**
1. "Core Node Health Dashboard in Grafana" (Sprint 1)
2. "Pod Performance Dashboard in Grafana" (Sprint 1)
3. "Alerting Configuration for Critical Metrics" (Sprint 2)
4. "Historical Trend Analysis Dashboard" (Sprint 2)

Each epic contains stories (tasks) that can be completed within days, not weeks.

## Jira Tips

### Linking Stories to Epics

- Always set the "Epic Link" field when creating Stories
- This maintains the hierarchical relationship and improves reporting

### Using Labels

- Add consistent labels to group related Stories across Epics
- Example labels: `frontend`, `backend`, `documentation`, `testing`

### Using Custom Fields

- If available, use custom fields to track additional information:
  - Target release
  - Test requirements
  - Customer impact

### Tracking Time

- Comment on Stories with progress updates
- Log time spent directly on Stories to improve future estimates

## Conclusion

Following these guidelines will help our team create clear, actionable Jira issues that enable effective asynchronous work. Regular review and refinement of these templates will help us continuously improve our process.

Remember that the goal is effective communication and alignment - if a template doesn't fit a particular situation, adjust as needed while maintaining clarity and detail.
