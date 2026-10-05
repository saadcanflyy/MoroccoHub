# MoroccoHub MCP and Codex Setup

Version: 1.0

---

# 1. Development Philosophy

Codex is used as a software engineering assistant.

It should:

- Understand the product specifications
- Respect the architecture
- Write maintainable code
- Create modular components
- Explain important decisions
- Avoid unnecessary complexity


Before implementing any feature:

Codex must consult:


MoroccoHub_Product_Specification.md
DATABASE_DESIGN.md
TECH_ARCHITECTURE.md
UI_DESIGN_SPEC.md

These files are the source of truth.

---

# 2. Development Environment


## Main tools


Required:


VS Code
Git
Node.js
npm/pnpm
Python
Docker


---

# 3. Codex Role


Codex responsibilities:


## Frontend

Create:

- React components
- Pages
- UI systems
- Hooks
- State management


## Backend

Create:

- Database queries
- API routes
- Server actions
- Authentication logic


## AI

Create:

- AI services
- Data pipelines
- Automation scripts


## Testing

Create:

- Unit tests
- Integration tests
- End-to-end tests


---

# 4. MCP Architecture


MoroccoHub MCP ecosystem:



             Codex


               |

 GitHub MCP
 Supabase MCP
 Figma MCP
 Playwright MCP
 Documentation MCP
 Browser MCP


---

# 5. GitHub MCP


Priority:

★★★★★


Purpose:

Repository management.


Capabilities:


- Read repository
- Create branches
- Review changes
- Manage issues
- Create pull requests
- Understand project history


Workflow:



Codex
↓
Create branch
↓
Implement feature
↓
Run tests
↓
Commit
↓
Pull request
↓
Merge


Repository:


https://github.com/saadcanflyy/MoroccoHub.git


---

# 6. Supabase MCP


Priority:

★★★★★


Purpose:

Database and backend.


Capabilities:


- Create tables
- Modify schema
- Run SQL
- Inspect database
- Manage authentication
- Manage storage


Used for:


Database:


PostgreSQL


Authentication:


Supabase Auth


Storage:


Supabase Storage


Realtime:


Supabase Realtime


---

# 7. Figma MCP


Priority:

★★★★★


Purpose:

Convert designs into components.


Workflow:



Figma Design
↓
Figma MCP
↓
Codex
↓
React Components


Used for:


- Landing page
- Dashboard
- Community pages
- Mobile UI


Design system:



Tailwind CSS
Shadcn UI
Lucide Icons


---

# 8. Playwright MCP


Priority:

★★★★★


Purpose:

Automatic browser testing.


Capabilities:


- Open website
- Click elements
- Fill forms
- Take screenshots
- Test user flows


Examples:


Registration test:



Open website
↓
Create account
↓
Select interests
↓
Verify dashboard


Post creation:



Login
↓
Create post
↓
Comment
↓
Vote


---

# 9. Documentation MCP


Priority:

★★★★☆


Purpose:


Access official documentation.


Important sources:


## Next.js

For:

- routing
- server components
- API


## React

For:

- components
- hooks


## Supabase

For:

- database
- authentication
- realtime


## Tailwind

For:

- styling


---

# 10. Browser Automation MCP


Priority:

★★★☆☆


Useful for:


- Testing external websites
- Checking references
- Monitoring sources


Potential usage:


News sources:


Check official pages
Extract public information
Validate sources


---

# 11. AI Development Tools


Required:


## LLM API


Used for:


- News summaries
- Classification
- Recommendations
- AI assistant


---

## Vector Database


Technology:



pgvector


Used for:


- Semantic search
- AI assistant memory
- Similar content


---

# 12. Project Workflow


Every feature follows:


## Step 1

Read specifications.


## Step 2

Create technical plan.


## Step 3

Implement.


## Step 4

Test.


## Step 5

Review.


## Step 6

Commit.


---

# 13. Branch Strategy


Main branch:



main


Production ready.


Development:



develop


Feature branches:


Example:



feature/authentication
feature/community-system
feature/news-ai


---

# 14. Code Quality Rules


All code must:


- Use TypeScript
- Follow naming conventions
- Avoid duplicated logic
- Have clear comments
- Use reusable components


---

# 15. Environment Management


Files:



.env.local
.env.example


Never commit:



.env.local


Example:



NEXT_PUBLIC_SUPABASE_URL=
NEXT_PUBLIC_SUPABASE_KEY=
AI_API_KEY=
DATABASE_URL=


---

# 16. Initial MCP Priority


Install first:


## Level 1 (Mandatory)


1.

GitHub MCP


2.

Supabase MCP


3.

Figma MCP


4.

Playwright MCP



---

## Level 2


5.

Documentation MCP


6.

Browser MCP



---

# 17. First Codex Tasks


After configuration:


Task 1:

Analyze repository.


Task 2:

Create project structure.


Task 3:

Connect Supabase.


Task 4:

Create database schema.


Task 5:

Build authentication.


Task 6:

Build first dashboard.


---

# 18. Security Rules


Never expose:


- API keys
- Service keys
- Database passwords


Use:


- Environment variables
- Row Level Security
- Authentication checks


---

# 19. Long-Term Infrastructure


Future:


Containerization:


Docker


CI/CD:


GitHub Actions


Monitoring:


Sentry
Analytics


Cloud scaling:


AWS / Google Cloud


---

# Final Architecture Goal


MoroccoHub should evolve into:



Users
   |
Frontend
   |
Supabase Core
   |
AI Infrastructure
   |
External Data Sources
   |
Intelligent Moroccan Digital Ecosystem


Now our documentation layer is complete:
✅ Product vision
✅ Database design
✅ Technical architecture
✅ UI specification
✅ Codex + MCP workflow  
Next step: we move from documentation to actual repository initialization.
We will open VS Code in:
C:\Users\tahae\Documents\MoroccoHub

Then configure:
1. Node project
2. Next.js
3. TypeScript
4. Tailwind
5. Shadcn UI
6. Supabase connection
7. Git workflow
8. Codex instructions (AGENTS.md)
The next file we should create before coding is:
AGENTS.md

This is the file Codex reads automatically to know how to behave inside this repository.