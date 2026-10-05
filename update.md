You are working on the MoroccoHub project.

I need you to update the project documentation to improve the post/content architecture.

First, read these files to understand the current design:
- MoroccoHub_Product_Specification.md
- DATABASE_DESIGN.md
- UI_DESIGN_SPEC.md
- TECH_ARCHITECTURE.md
- AGENTS.md

The current post system is too limited. We want MoroccoHub posts to work like Facebook/X rich posts while keeping Reddit-style communities.

Update the documentation accordingly.

Required changes:

1. Redesign the post concept:

A post must contain:
- Caption/text written by the user
- Optional attachments

A user can create:

A) Text-only post:
Example:
"Any advice for CPGE students?"

B) Photo post:
Caption + one or multiple photos

C) Video post:
Caption + video attachment

D) File/document post:
Caption + PDF/DOC/PPT attachment

E) External link post:
Caption + URL preview

F) Google Drive link post:
Caption + Drive URL

G) Poll post

H) Mixed post:
Caption + multiple attachment types


2. Update DATABASE_DESIGN.md:

Modify the posts table design.

The post should have:

- id
- author_id
- community_id
- caption
- post_type
- visibility
- created_at
- updated_at

Create a universal post_attachments table supporting:

- images
- videos
- files
- external links
- Google Drive links

Include fields:

- id
- post_id
- attachment_type
- url
- file_name
- file_size
- mime_type
- thumbnail_url
- display_order
- created_at

Explain relationships.

Make sure the design supports:
- multiple photos in one post
- future scalability
- AI processing of attachments


3. Update UI_DESIGN_SPEC.md:

Modify the post composer.

The composer should look like Facebook:

Create a post:

[Write something...]

Buttons:

+ Photo/Video
+ File
+ Link
+ Drive
+ Poll

Then Post.


Modify the post card:

Display:

- user information
- caption
- attachment preview
- reactions
- comments
- share
- save


Add display rules:

One image:
large preview

Multiple images:
gallery layout

PDF:
document preview card

Link:
website preview card

Drive:
Drive document card

Video:
embedded player


4. Update MoroccoHub_Product_Specification.md:

Clarify that MoroccoHub supports rich social publications.

Mention that users can share:
- thoughts
- photos
- educational documents
- resources
- opportunities
- links


5. Keep consistency:

Do not create unnecessary complexity.
Do not modify unrelated architecture.
Keep Supabase/PostgreSQL compatibility.

After editing:
1. Show me the files modified.
2. Summarize the architectural changes.
3. Explain if any database migration will be required later.


apply this when u read it 