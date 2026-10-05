# MoroccoHub Technical Architecture

Version: 1.0

---

# 1. Architecture Overview

MoroccoHub will use a modern full-stack architecture:


             Users

               |
               |

          Next.js Frontend

               |

          Backend Services

               |

    -------------------------

    |                       |

Supabase                AI Services

    |                       |

 PostgreSQL              LLM APIs
 Auth                   Python Services
 Storage                Vector Search
 Realtime

---

# 2. Technology Stack


# Frontend

Framework:


Next.js 15
React
TypeScript

Reasons:

- Production ready
- SEO friendly
- Fast rendering
- Large ecosystem


---

## UI Framework

Use:


Tailwind CSS
Shadcn UI
Lucide Icons

Goals:

- Modern interface
- Responsive design
- Fast development


---

# Backend

Initial architecture:

Use Supabase as backend platform.

Services:


Supabase
 |
 ├── Authentication
 |
 ├── PostgreSQL Database
 |
 ├── Storage
 |
 ├── Realtime
 |
 └── Edge Functions

---

# Database

Main database:


PostgreSQL

Managed by:


Supabase

Features:

- Relational data
- Full text search
- Row Level Security
- Extensions


Required extensions:


pgvector
pg_trgm
uuid-ossp

---

# Authentication

Provider:


Supabase Auth

Supported:

- Email/password
- Google login
- Future:
  - Apple
  - LinkedIn


Authentication flow:


User
↓
Register
↓
Create profile
↓
Select interests
↓
Recommend communities
↓
Personalized dashboard

---

# Storage

Supabase Storage.


Used for:

- Profile pictures
- Community images
- Post images
- Videos
- Documents


Storage buckets:


avatars
community-media
post-media
documents

---

# 3. Frontend Architecture


Project structure:



MoroccoHub
/app
   /(auth)
  login

  register

   /(main)
  home

  communities

  news

  opportunities

  profile

/components
   ui
   posts
   communities
   news
   opportunities
/lib
   supabase
   utils
/hooks
/types
/styles

---

# 4. Backend Logic


Business logic will be separated.

Examples:


Create Post
↓
Validate user
↓
Check community permissions
↓
Insert database
↓
Update feed
↓
Send notifications

---

# 5. API Architecture


Use:


Next.js Server Actions
-
Supabase APIs
-
Edge Functions


Examples:


Create post:


POST
/api/posts


Get personalized feed:


GET
/api/feed


News processing:


POST
/api/news/process

---

# 6. AI Architecture


MoroccoHub AI system.


Architecture:



Data Sources
 |

Collector Services
 |

AI Processing
 |

Database
 |

Users


---

# AI Components


## News AI Pipeline


Input:

Articles from sources.


Processing:


Extract text
↓
Remove duplicates
↓
Classify category
↓
Generate summary
↓
Calculate importance
↓
Store result


---

## Recommendation Engine


Uses:

- interests
- communities
- interactions
- saved content
- viewed content


Output:

Personalized feed.

---

## AI Assistant


Architecture:


User Question
↓
Embedding
↓
Vector Search
↓
Relevant MoroccoHub Data
↓
LLM Response

Technology:


pgvector
LLM API
FastAPI service

---

# 7. Python AI Services


Separate service:


/ai-service
   main.py
   news_processor.py
   recommender.py
   embeddings.py

Framework:


FastAPI

---

# 8. Data Collection Architecture


## News Collection


Sources:

- RSS feeds
- APIs
- Official websites


Pipeline:



Scheduler
↓
Collectors
↓
Raw Data
↓
AI Processing
↓
News Database


Scheduler:


Cron jobs
Supabase scheduled functions
or
Python workers

---

# Opportunities Collection


Sources:

- Company websites
- Recruitment platforms
- Universities


Processing:


Extract opportunity
↓
Normalize information
↓
Classify
↓
Store

---

# 9. Search System


Phase 1:

PostgreSQL search:



Full Text Search


Phase 2:

Advanced search:


Elasticsearch


AI search:


pgvector

---

# 10. Realtime Features


Supabase Realtime:


Used for:


- Comments
- Notifications
- Messages
- Live discussions


Example:



New comment
↓
Realtime event
↓
Users receive update

---

# 11. Security Architecture


Important systems:


## Row Level Security


Users can only:

- edit their profile
- delete their posts
- access authorized data


---

## Moderation


Features:

- Report system
- Content filtering
- Admin dashboard


---

## Verification


Verified accounts:

- Universities
- Companies
- Organizations
- News sources

---

# 12. Deployment Architecture


Frontend:


Vercel

Database:


Supabase

AI services:

Options:


Railway
Render
AWS
Docker server


Storage:


Supabase Storage

---

# 13. Development Environment


Required:


Node.js


v22+


Package manager:


npm
or
pnpm


Python:


3.12+


Tools:


Git
Docker
VS Code

---

# 14. Environment Variables


Example:



NEXT_PUBLIC_SUPABASE_URL
NEXT_PUBLIC_SUPABASE_ANON_KEY
SUPABASE_SERVICE_KEY
AI_API_KEY
DATABASE_URL


Never commit:


.env

---

# 15. Testing Strategy


Frontend:


React Testing Library
Playwright


Backend:


Unit tests
Integration tests


AI:


Pipeline validation
Data quality tests

---

# 16. Development Phases


## Phase 1

Social Core:


Build:

- Authentication
- Profiles
- Communities
- Posts
- Comments
- Voting


---

## Phase 2

Information:


Build:

- News system
- Opportunities


---

## Phase 3

Intelligence:


Build:

- AI assistant
- Recommendations
- Semantic search


---

## Phase 4

Expansion:


Build:

- Events
- Marketplace
- Advanced networking


---

# 17. Engineering Principles


MoroccoHub must be:


- Scalable
- Secure
- Modular
- AI-ready
- Mobile-friendly
- Easy to maintain


All features must be built as independent modules.


