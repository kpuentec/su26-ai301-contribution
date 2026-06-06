# Contribution 1: [Security] XSS — Multiple unencoded fields in documentManager/addedithtmldocument.jsp (claude assist)
 #2315

**Contribution Number:** 1  
**Student:** Kevin Cortez  
**Issue:** [[GitHub issue link]](https://github.com/carlos-emr/carlos/issues/2315)  
**Status:** Phase I Complete

---

## Why I Chose This Issue

I chose this issue because it sits at the intersection of web security and real-world software. These are two areas I genuinely care about. I have a solid cybersecurity foundation backed by hands-on projects, so XSS vulnerabilities are something I understand at a technical level, not just in theory. I wanted a contribution where my security background would actually matter, not just my ability to follow a tutorial.

The issue is also well-scoped for a first contribution: one file, five specific lines, a clear fix pattern using the **carlos:encode** taglib, and exact line numbers provided. I know what "done" looks like before I write a single line of code, which makes it a strong fit for a focused weekly cycle.

---

## Understanding the Issue

### Problem Description

**addedithtmldocument.jsp** renders database-sourced fields including free-text source fields and provider names directly into HTML attributes, HTML body, and a JavaScript array literal without any encoding. This allows stored XSS payloads to execute for any user who opens the document edit form.

### Expected Behavior

All user-supplied or database-sourced values rendered into HTML or JavaScript should be HTML-encoded using the **carlos:encode** taglib before output, preventing any injected markup or scripts from executing.

### Current Behavior

Five fields across the file output raw values with no encoding applied. A malicious value like **<script>alert(1)</script>** stored in the source field would execute in the browser when the form loads.

### Affected Components

**src/main/webapp/WEB-INF/jsp/documentManager/addedithtmldocument.jsp**: lines 287, 373, 404, 408, and 428.

---

## Reproduction Process

### Environment Setup

[Notes on setting up your local development environment - challenges you faced, how you solved them]

### Steps to Reproduce

1. [Step 1]
2. [Step 2]
3. [Observed result]

### Reproduction Evidence

- **Commit showing reproduction:** [Link to commit in your fork]
- **Screenshots/logs:** [If applicable]
- **My findings:** [What you discovered during reproduction]

---

## Solution Approach

### Analysis

[Your analysis of the root cause - what's causing the issue?]

### Proposed Solution

[High-level description of your fix approach]

### Implementation Plan

Using UMPIRE framework (adapted):

**Understand:** [Restate the problem]

**Match:** [What similar patterns/solutions exist in the codebase?]

**Plan:** [Step-by-step implementation plan]
1. [Modify file X to do Y]
2. [Add function Z]
3. [Update tests]

**Implement:** [Link to your branch/commits as you work]

**Review:** [Self-review checklist - does it follow the project's contribution guidelines?]

**Evaluate:** [How will you verify it works?]

---

## Testing Strategy

### Unit Tests

- [ ] Test case 1: [Description]
- [ ] Test case 2: [Description]
- [ ] Test case 3: [Description]

### Integration Tests

- [ ] Integration scenario 1
- [ ] Integration scenario 2

### Manual Testing

[What you tested manually and results]

---

## Implementation Notes

### Week [X] Progress

[What you built this week, challenges faced, decisions made]

### Week [Y] Progress

[Continue documenting as you work]

### Code Changes

- **Files modified:** [List]
- **Key commits:** [Links to important commits]
- **Approach decisions:** [Why you chose certain approaches]

---

## Pull Request

**PR Link:** [GitHub PR URL when submitted]

**PR Description:** [Draft or final PR description - much of the content above can be adapted]

**Maintainer Feedback:**
- [Date]: [Summary of feedback received]
- [Date]: [How you addressed it]

**Status:** [Awaiting review / Iterating / Approved / Merged]

---

## Learnings & Reflections

### Technical Skills Gained

[What you learned technically]

### Challenges Overcome

[What was hard and how you solved it]

### What I'd Do Differently Next Time

[Reflection on your process]

---

## Resources Used

- [Link to helpful documentation]
- [Tutorial or Stack Overflow post that helped]
- [GitHub issues or discussions that helped]
