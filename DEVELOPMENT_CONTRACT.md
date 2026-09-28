# MeetingMind — Development Contract

## 1. Project Overview

MeetingMind is an AI-powered Meeting Intelligence Agent that uses persistent memory to help users prepare for future meetings.

The system should remember important information from previous meetings and use that information when preparing the user for later meetings.

### Core Workflow

```text
Meeting Input
      ↓
AI Analysis
      ↓
Important Information Extraction
      ↓
Hindsight RETAIN
      ↓
Persistent Memory
      ↓
Future Meeting Preparation
      ↓
Hindsight RECALL
      ↓
Personalized Meeting Brief
```

---

## 2. Core Project Principle

Hindsight memory is a core part of MeetingMind.

Memory must not be treated as an optional feature.

The project should demonstrate that the system can:

* Remember information from previous meetings.
* Recall relevant information later.
* Use recalled information to prepare the user.
* Adapt responses based on previous interactions.
* Connect current meeting context with historical meeting context.

The final demonstration should clearly show the difference between responses with and without persistent memory.

---

## 3. Team Development Rules

### 3.1 Main Branch

The `main` branch contains the stable version of the project.

Team members must NOT directly push to `main`.

Changes should be made through feature branches and Pull Requests.

### 3.2 Feature Branches

Each team member should work on their assigned branch.

Branch naming format:

```text
feature/<area>
```

Examples:

```text
feature/backend
feature/frontend
feature/ai-agent
feature/hindsight
feature/data-qa
feature/integration
```

### 3.3 Before Starting Work

Always update the local main branch before creating or continuing work:

```bash
git checkout main
git pull origin main
```

Then switch to your feature branch:

```bash
git checkout feature/backend
```

---

## 4. Commit Rules

Commits should be small and meaningful.

Use clear commit messages.

Examples:

```text
feat: add meeting creation API
feat: add Hindsight recall service
fix: handle invalid meeting input
docs: update API documentation
test: add meeting service tests
refactor: simplify meeting controller
```

Avoid commit messages such as:

```text
update
changes
final
final2
done
asdf
```

---

## 5. Pull Request Rules

Before merging code into `main`:

1. Push the feature branch.
2. Create a Pull Request.
3. Explain what was changed.
4. Mention important dependencies or changes.
5. Ask another team member to review.
6. Fix review comments if required.
7. Merge only after approval.

Example:

```text
feature/backend
       ↓
Pull Request
       ↓
Code Review
       ↓
main
```

---

## 6. Integration Rules

Team members must communicate before changing shared interfaces.

The following should not be changed without informing the relevant team members:

* API endpoints
* Request JSON structures
* Response JSON structures
* Database schema
* Hindsight memory structure
* Shared environment variables
* Authentication structure
* Important folder/module structure

If an API changes, update the relevant documentation.

---

## 7. Backend Contract

The backend is responsible for providing APIs required by the frontend and communicating with the AI/memory components where applicable.

Backend responsibilities include:

* Meeting creation
* Meeting retrieval
* Meeting updates
* Meeting-related data management
* Participant information
* Communication with AI/memory services
* Input validation
* Error handling

Backend APIs should be documented before frontend integration.

---

## 8. AI Agent Contract

The AI Agent is responsible for:

* Understanding meeting notes
* Extracting important information
* Identifying decisions
* Identifying commitments
* Identifying unresolved issues
* Identifying relevant participant information
* Generating meeting preparation content
* Using recalled memory when preparing the user

The AI component should not silently change the agreed API format.

---

## 9. Hindsight Memory Contract

Hindsight is responsible for persistent memory operations.

The system should support the equivalent of:

```text
RETAIN
↓
Store important meeting information

RECALL
↓
Retrieve relevant historical information
```

Memory should focus on useful information such as:

* Previous decisions
* Commitments
* Unresolved issues
* Participant preferences
* Important discussion points
* Meeting history

The exact Hindsight implementation may be updated as the team integrates the technology.

---

## 10. Frontend Contract

The frontend should communicate with the backend through the agreed API contracts.

Expected core screens include:

1. Dashboard
2. Add Meeting
3. Meeting Details
4. Meeting Preparation
5. AI Chat
6. Optional Memory View

Frontend developers should use mock data when backend APIs are not yet available.

---

## 11. Data and Testing Rules

The project should use realistic but fictional meeting data for demonstrations.

Testing should include:

* Valid meeting input
* Invalid input
* Empty input
* Multiple meetings
* Repeated participants
* Previous decisions
* Unresolved issues
* Commitments
* Memory recall
* No-memory scenarios
* Conflicting or updated information

---

## 12. Security Rules

Never commit:

* API keys
* Passwords
* Database credentials
* Hindsight credentials
* `.env` files containing secrets
* Personal access tokens

Use environment variables.

Provide a safe example file:

```text
.env.example
```

Example:

```text
DATABASE_URL=
DATABASE_USERNAME=
DATABASE_PASSWORD=
HINDSIGHT_API_KEY=
LLM_API_KEY=
```

---

## 13. Definition of Done

A task is considered complete only when:

* The implementation works.
* The code is committed.
* The code is pushed to the correct branch.
* Required tests are completed.
* Relevant documentation is updated.
* Integration requirements are communicated.
* The Pull Request has been reviewed.
* The change is merged into `main`.

---

## 14. Scope Control

The team should prioritize one clear workflow:

> Remember previous meetings and use that memory to prepare the user for future meetings.

Avoid unnecessary scope expansion such as:

* Full CRM systems
* Video conferencing platforms
* Complete calendar systems
* Complex voice assistants
* Large enterprise dashboards
* Unrelated AI features

Additional features should only be added if the core workflow is stable.

---

## 15. Communication

Team members should communicate when:

* An API changes.
* A database structure changes.
* A dependency changes.
* Another team's work is blocked.
* A major implementation decision is made.
* A task cannot be completed as planned.

Short regular updates are preferred.

Example:

```text
Yesterday:
Implemented meeting CRUD APIs.

Today:
Working on meeting preparation endpoint.

Blocked:
Waiting for AI response JSON structure.
```

---

## 16. Team Ownership

Each major project area should have one primary owner.

| Area                               | Primary Owner |
| ---------------------------------- | ------------- |
| AI Agent                           | Member 1      |
| Hindsight / Memory                 | Member 2      |
| Backend                            | Member 3      |
| Frontend                           | Member 4      |
| Data / QA                          | Member 5      |
| Integration / Documentation / Demo | Member 6      |

Each owner is responsible for keeping their component functional and communicating integration requirements.

---

## 17. Final Principle

Build the smallest complete version first.

The priority is:

```text
Working Core Workflow
        ↓
Hindsight Memory
        ↓
AI Meeting Preparation
        ↓
Frontend + Backend Integration
        ↓
Testing
        ↓
Polish
        ↓
Demo
```

Do not optimize features before the core MeetingMind workflow works end-to-end.
