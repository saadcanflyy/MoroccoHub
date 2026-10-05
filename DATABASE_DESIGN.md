# MoroccoHub Database Design

Version: 1.0

Database:
PostgreSQL

Backend compatibility:
Supabase

---

# 1. Database Philosophy

MoroccoHub is built around five main data domains:


Users
 |
 |-- Communities
 |
 |-- Content
 |
 |-- Information
 |
 |-- Opportunities
 |
 |-- Knowledge

The database must support:

- millions of users
- personalized feeds
- real-time interactions
- AI-generated content
- moderation
- analytics

---

# 2. User System

## users

Main authentication table.

Managed partly by Supabase Auth.

Columns:


id
uuid PRIMARY KEY
email
created_at
last_login
status
(active, suspended, deleted)


---

## profiles

Public user information.


id
uuid PRIMARY KEY
user_id
FK users.id
username
unique
full_name
avatar_url
bio
location
birth_date
created_at
updated_at

---

## user_preferences

Stores personalization data.


id
user_id
FK users.id
preferred_language
country
city
feed_preferences
JSONB
created_at

---

## interests

Available interests.

Example:

AI,
Sports,
Engineering,
Business


id
name
category

---

## user_interests

Many-to-many relationship.


id
user_id
interest_id

Relationship:


User
  |
  |
User Interests
  |
  |
Interests

---

# 3. Community System


## communities

Main community table.

Example:

r/AI_Morocco


id
name
unique
slug
unique
description
avatar_url
banner_url
creator_id
category
privacy
(public/private)
member_count
created_at

---

## community_members

Users joining communities.


id
community_id
user_id
role
(member,
moderator,
admin)
joined_at

---

## community_rules

Community moderation rules.


id
community_id
rule_text
created_at

---

# 4. Content System


## posts

Main user content.


id
author_id
FK users.id
community_id
FK communities.id
title
content
post_type
(text,
image,
video,
poll,
link)
media_url
status
created_at
updated_at


---

## comments

Comments and replies.


id
post_id
author_id
parent_comment_id
content
created_at

parent_comment_id allows:


Comment
 |
 └── Reply
  |
  └── Reply


---

## votes

Stores reactions.


id
user_id
post_id
comment_id
vote_type
(upvote/downvote)
created_at

A user can vote once.

---

## saved_content

Bookmarks.


id
user_id
post_id
created_at

---

# 5. News Intelligence System


## news_sources

Trusted sources.


id
name
website
source_type
(newspaper,
official,
social_media)
verification_status
created_at

---

## news_articles

AI processed news.


id
source_id
title
original_url
summary
content
category
importance_score
published_at
created_at

---

## news_tags

Topics.


id
name

---

## news_article_tags

Relation:


news_id
tag_id

---

## news_discussions

Connect news with communities.


id
news_id
community_id

---

# 6. Opportunities System


## companies

Organizations.


id
name
logo_url
website
description
verified

---

## opportunities

Jobs/internships/etc.


id
company_id
title
description
type
(job,
internship,
scholarship,
competition)
location
remote
requirements
deadline
application_url
created_at

---

## opportunity_saved

Users saving opportunities.


id
user_id
opportunity_id
created_at

---

# 7. Knowledge Hub


## knowledge_articles

Educational content.


id
author_id
title
content
category
difficulty_level
views
created_at

---

## knowledge_categories


id
name
parent_category_id

Allows:


Programming
 |
 ├── Python
 |
 └── AI

---

# 8. Events System


## events


id
creator_id
title
description
category
location
online
start_date
end_date
created_at

---

## event_participants


id
event_id
user_id
status
(interested,
registered)

---

# 9. Reputation System


## reputation_points

History of gained points.


id
user_id
action
points
created_at

Example:


Helpful comment +5
Popular post +20

---

## badges


id
name
description
icon

---

## user_badges


id
user_id
badge_id
earned_at

---

# 10. Messaging System


## conversations


id
created_at

---

## conversation_members


conversation_id
user_id

---

## messages


id
conversation_id
sender_id
content
created_at

---

# 11. Notifications


## notifications


id
user_id
type
reference_id
message
read
created_at

Examples:

- Someone commented
- Someone followed you
- Opportunity deadline approaching

---

# 12. AI System Tables


## ai_recommendations

Stores AI suggestions.


id
user_id
type
content_reference
reason
created_at

---

## ai_processing_logs

Tracks automated systems.


id
process_type
status
started_at
finished_at
metadata

Examples:

- News scraping
- Classification
- Summarization

---

# 13. Future Scaling Considerations

## Search

Use:

- PostgreSQL Full Text Search initially

Later:

- Elasticsearch


## Vector AI Search

Use:

- pgvector

For:

- semantic search
- AI assistant


## Storage

Supabase Storage:

- images
- videos
- documents

---

# 14. Important Relationships


Main relations:


User
 |
 +-- creates --> Posts
 |
 +-- joins --> Communities
 |
 +-- comments --> Posts
 |
 +-- saves --> Content
 |
 +-- earns --> Badges
Community
 |
 +-- contains --> Posts
News
 |
 +-- discussed in --> Communities
Company
 |
 +-- publishes --> Opportunities

---

# 15. MVP Database Priority


First implementation:

Required:


users
profiles
communities
community_members
posts
comments
votes
user_interests
interests


Second:


news_articles
news_sources
opportunities
companies


Third:


messages
events
knowledge
AI systems

