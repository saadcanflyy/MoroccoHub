# MoroccoHub UI Design Specification

Version: 1.0

---

# 1. Design Philosophy

MoroccoHub interface should combine:

- Reddit community structure
- X/Twitter interaction speed
- LinkedIn professional feeling
- Modern SaaS design


Main principles:

- Clean
- Fast
- Mobile-first
- Information dense but organized
- Trustworthy
- Moroccan identity


---

# 2. Global Layout


The application uses a 3-column desktop layout.



Navbar
Sidebar        Main Content        Right Panel
Navigation     Feed                Trending
Communities    Posts               Suggestions
Profile        Pages               Recommendations


Responsive behavior:

Desktop:
3 columns


Tablet:
2 columns


Mobile:
single column + bottom navigation



---

# 3. Global Components


## Navbar


Contains:


Left:

MoroccoHub logo


Center:

Global search bar


Search examples:

"AI internships"

"Casablanca events"

"CPGE resources"



Right:

- Notifications
- Messages
- Profile menu



---

## Sidebar


Navigation:



Home
Communities
News
Opportunities
Knowledge
Events
Saved
Messages
Settings


User section:



Joined Communities
r/AI_Morocco
r/CPGE_Maroc
r/Entrepreneurs_MA


---

## Right Panel


Contains:


## Trending Topics


Example:



🔥 Trending
#AI_Morocco
#CAN2027
#StartupMorocco


## Suggested Communities


AI recommendation:



You may like:
r/Robotics_MA
r/Engineering


---

# 4. Landing Page


URL:


/


Purpose:

Convert visitors into users.


Sections:


## Hero


Title:


"Everything Morocco, in one place."


Description:


"Communities, news, opportunities and knowledge."


Buttons:


Primary:

Join MoroccoHub


Secondary:

Explore communities



---

## Feature Section


Cards:



Communities
Connect with Moroccans
News
Understand what happens
Opportunities
Find your future
Knowledge
Learn together


---

## Community Preview


Display examples:



r/AI_Morocco
25k members
r/CPGE_Maroc
40k members


---

# 5. Authentication Flow


## Register Page


Fields:


- Full name
- Email
- Password
- Username


Button:


Create account


---

# Interest Selection Page


After registration:


Title:


"What are you interested in?"


Cards:



Technology
Sports
Education
Business
Finance
Culture
Gaming
Science


Users select multiple.



---

# Community Recommendation Page


AI suggests communities:


Example:



Based on your interests:
✓ AI Morocco
✓ Engineering Students Morocco
✓ Entrepreneurship Morocco
Join selected


---

# 6. Home Dashboard


URL:


/home


Main purpose:

Personalized content.


Layout:


## Feed Composer


Component:



Create a post...
[Text]
[Image]
[Poll]
[Link]
Post


---

## Post Card


Structure:



User avatar
Username
Community
Time
Post title
Content
Image/video
Actions:
⬆ Vote
💬 Comment
↗ Share
🔖 Save


---

# 7. Community Page


URL:



/community/:slug


Example:



/community/AI_Morocco



Header:


Contains:


- Banner
- Avatar
- Name
- Description
- Members
- Join button



Tabs:



Posts
About
Members
Rules


---

Post sorting:



Hot
New
Top



---

# 8. News Page


URL:



/news


Purpose:

AI-powered Moroccan news.


Layout:


Categories:



All
Politics
Economy
Technology
Education
Sports
Culture


---

News Card:



Headline
AI Summary
Source:
MAP
Medias24
Importance:
★★★★★
Comments


Users can discuss news below.


---

# 9. Opportunities Page


URL:



/opportunities


Categories:



Jobs
Internships
Scholarships
Competitions


Filters:



Field
Location
Remote
Deadline


Opportunity card:



Company logo
Position
Company
Location
Requirements
Deadline
Apply button


---

# 10. Knowledge Hub


URL:



/knowledge


Structure:


Categories:



Programming
Engineering
Education
Career
Science


Article card:



Title
Author
Difficulty
Views
Save


---

# 11. Events Page


URL:



/events


Event card:



Image
Event name
Date
Location
Participants
Register


---

# 12. User Profile Page


URL:



/profile/:username


Header:



Avatar
Username
Bio
Location
Reputation score
Badges


Tabs:



Posts
Comments
Communities
Saved


---

# 13. Messaging Interface


URL:



/messages


Layout:


Left:

Conversations


Right:

Chat window



Features:


- Real-time messages
- Attachments
- Notifications


---

# 14. Admin Dashboard


Purpose:

Platform management.


Pages:


## Users

- Verify users
- Ban users


## Communities

- Moderate communities


## News Sources

- Verify sources


## Reports

- Review reported content



---

# 15. Mobile Navigation


Bottom bar:



Home
Communities
Create
News
Profile


---

# 16. Design System


## Colors


Primary:

MoroccoHub green/red inspired palette.


Neutral:

White

Gray

Dark mode support



---

## Typography


Use:



Inter


---

## Components Library


Use:



Shadcn UI
Tailwind CSS


Reusable components:


- Button
- Card
- Modal
- Dropdown
- Tabs
- Avatar
- Badge
- Input
- Search



---

# 17. UX Rules


Every action should require minimum clicks.


Examples:


Create post:

Maximum 2 clicks.


Join community:

1 click.


Save opportunity:

1 click.


Search:

Always available globally.


---

# 18. MVP Screens Priority


Build first:


1. Landing page

2. Authentication

3. Home feed

4. Community page

5. Profile page


Then:


6. News

7. Opportunities

8. Knowledge

9. Events

10. Messaging



---

# 19. Future UI Features


Later:


- Dark mode
- AI assistant panel
- Voice search
- Mobile application
- Personalized dashboards


