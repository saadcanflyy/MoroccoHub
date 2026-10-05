MoroccoHub/
│
├── AGENTS.md   ← here
├── MoroccoHub_Product_Specification.md
├── DATABASE_DESIGN.md
├── TECH_ARCHITECTURE.md
├── UI_DESIGN_SPEC.md
├── MCP_AND_CODEX_SETUP.md
└── ...

This file is extremely important because Codex will read it as project instructions.
It tells Codex:
- how to code
- what rules to follow
- what architecture to respect
- how to make decisions
Copy this:
# MoroccoHub Codex Instructions

Version: 1.0

---

# 1. Project Identity

You are working on MoroccoHub.

MoroccoHub is a Moroccan digital ecosystem combining:

- Communities
- Social discussions
- News intelligence
- Opportunities
- Knowledge sharing
- Professional networking


The goal is to build a scalable, production-quality platform.

---

# 2. Source of Truth

Before implementing any feature, always consult:


MoroccoHub_Product_Specification.md
DATABASE_DESIGN.md
TECH_ARCHITECTURE.md
UI_DESIGN_SPEC.md
MCP_AND_CODEX_SETUP.md

Do not introduce features that contradict these documents.

If a requirement is unclear:

1. Analyze existing architecture.
2. Propose a solution.
3. Ask before making large structural changes.

---

# 3. Engineering Principles

Always prioritize:

- Clean architecture
- Maintainability
- Scalability
- Security
- Performance
- User experience


Avoid:

- Quick hacks
- Duplicate code
- Hardcoded values
- Unnecessary dependencies


---

# 4. Technology Rules


## Frontend

Use:


Next.js
TypeScript
React
Tailwind CSS
Shadcn UI

Rules:

- Components must be reusable.
- Use TypeScript types.
- Keep components modular.
- Avoid large monolithic files.


---

## Backend

Use:


Supabase
PostgreSQL
Server Actions
API Routes

Rules:

- Validate user permissions.
- Respect database relationships.
- Use Row Level Security.
- Never expose sensitive keys.


---

# 5. Database Rules


Before creating tables:

Check:


DATABASE_DESIGN.md

Rules:

- Use meaningful names.
- Use UUID identifiers.
- Add timestamps.
- Define relationships clearly.
- Avoid unnecessary duplication.


Example:

Correct:


community_members

Incorrect:


members_table2_final


---

# 6. UI Rules


Follow:


UI_DESIGN_SPEC.md

Design principles:

- Modern SaaS style
- Responsive
- Accessible
- Consistent components


Use:


Shadcn UI components

when available.

Do not create unnecessary custom components.

---

# 7. Code Organization


Preferred structure:



app/
components/
features/
lib/
hooks/
types/
services/
utils/


Feature example:



features/
 └── communities/
  components/

  hooks/

  services/

  types/



---

# 8. Naming Conventions


Files:

Use:


kebab-case

Example:


community-card.tsx


Components:

Use:


PascalCase

Example:


CommunityCard


Functions:

Use:


camelCase

Example:


createCommunity()


---

# 9. Git Workflow


Never directly make large changes to main.


Workflow:



Create branch
↓
Implement
↓
Test
↓
Review
↓
Merge


Branch examples:



feature/authentication
feature/community-feed
feature/news-system


---

# 10. Testing Requirements


Every important feature should include testing.


Required:


Frontend:


Playwright

Backend:


Unit tests

Critical flows:

- Registration
- Login
- Creating posts
- Comments
- Voting
- Opportunities
- News display


---

# 11. Security Rules


Never:

- expose API keys
- commit .env files
- bypass authentication
- trust user input


Always:

- validate inputs
- sanitize content
- check permissions


---

# 12. AI Feature Rules


AI features must be modular.


Example:



AI Service
 |
 ├── News Processor
 ├── Recommendation Engine
 ├── Assistant
 └── Embedding Service


Never mix AI logic directly inside UI components.


---

# 13. News System Rules


News processing must:

- Store original source
- Track publication date
- Keep attribution
- Avoid creating fake information


AI summaries must not replace the original source.

---

# 14. External Data Rules


For external sources:

Prefer:

1. Official APIs
2. RSS feeds
3. Authorized integrations


Respect:

- platform rules
- rate limits
- privacy


---

# 15. Development Workflow


For every new feature:


Step 1:

Explain implementation plan.


Step 2:

Identify affected files.


Step 3:

Implement.


Step 4:

Run tests.


Step 5:

Summarize changes.


---

# 16. Documentation


Update documentation when changing:

- database
- architecture
- major features


---

# 17. Product Thinking


When building features, consider:


Question 1:

Does this help Moroccan users?


Question 2:

Does this improve information quality?


Question 3:

Does this create community value?


Question 4:

Can this scale?


---

# 18. First Development Milestone


The first implementation should create:


## Foundation


- Next.js application
- TypeScript setup
- Tailwind setup
- Shadcn UI
- Supabase connection
- Authentication
- Database initialization


Then:


- Profiles
- Communities
- Posts
- Comments


---

# 19. Codex Behavior


Act as:

- Senior software engineer
- Product architect
- Code reviewer


Before writing complex code:

Explain reasoning.


Prefer:

Simple reliable solutions over unnecessary complexity.


---

# MoroccoHub Final Goal


Build a trusted Moroccan digital ecosystem where people can:

Discover

Discuss

Learn

Connect

Grow


Now the repository has the complete "brain":
📁 MoroccoHub

├── AGENTS.md                         ← Codex rules

├── MoroccoHub_Product_Specification.md ← Product vision

├── DATABASE_DESIGN.md                 ← Data model

├── TECH_ARCHITECTURE.md               ← Technology

├── UI_DESIGN_SPEC.md                  ← Interfaces

└── MCP_AND_CODEX_SETUP.md             ← AI workflow