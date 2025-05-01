# Project Title
NadaMart

## Overview
NadaMart is a community-driven platform that connects people looking to give away unused items with those who need them—for free.

### Problem Space

Decluttering can be emotionally and logistically challenging. Many individuals struggle to part with items—not necessarily because they still need them, but because of sentimental value or a desire to avoid waste. At the same time, countless others are in search of specific items or simply looking for useful things at no cost. However, there's often no convenient or trusted way to connect these two groups. NadaMart addresses this gap by acting as a bridge between people looking to give away items and those seeking free goods.

### User Profile

User can be one or both:

- Hunter: 
 - Individuals actively seeking free items—whether out of need, curiosity, or the thrill of discovering something useful without cost.

- Givist:
 - Generous community members looking to part with items they no longer need, aiming to give them a second life in the hands of someone who does.

### Features

- As a user, I want to be able to search for specific free items listed on NadaMart
- As a user, I want to be able to find free items closest to a given location
- As a user, I want to be able to discover the most popular or most claimed items near a specific area
- As a user, I want to be able to create an account to manage the items I've claimed or listed

- As a logged-in user, I want to be able to rate my experience with a Givist after receiving an item (out of 5 stars)
- As a logged-in user, I want to be able to see the list of items I’ve claimed or given away
- As a logged-in user, I want to be able to filter my past transactions by location

## Implementation

### Tech Stack

- NextJS
- PostgresQL
- Client libraries: 
    - TailwindCSS
    - axios
    - AceternityUI
    - shadcn
    - zustand
- Server libraries:
    - prisma
    - next-auth
    - jsonwebtoken
    - bcrypt for password hashing
    - nodemailer
    - zod
    - Supabase

### APIs

- No external APIs will be used

### Sitemap

- Home page
- List of Posts
- Post description
- Register
- Login

### Mockups


### Data

- **Users**
    - Users can take on the role of either:
        - **Givists** – users who list free items to give away
        - **Hunters** – users who claim free items
    
    A user can:
        - Post multiple items (as a Givist)
        - Claim multiple items (as a Hunter)
        - Leave ratings for other users (typically Givists)

- **Items/Posts**
    - Items are posted by Users **(Givists)**.
        Each item has:
            - A title, description, category, and location
            - A status: available, claimed, or removed
            - A one-to-one relationship with the User who posted it
    
- **Claims**
    - A Claim represents a Hunter expressing interest in or receiving an item.
        Each claim:
            - Is linked to one Item
            - Is made by one User **(Hunter)**
            - Has a status: **pending, completed, or cancelled**
    

### Endpoints

**POST /users/register**

- Add a user account

**POST /users/login**

- Login a user

**GET /posts**

- Get list of posts by Givists

**GET /posts/:id**

- Get specific post by ID

**POST /posts/:id/comment**

- Post comment on a specific post

**PUT /posts/:id/interest**

- Cast an 'interest' (similar to 'like') on a post

## Roadmap

### Project Setup
- [x] Initialize GitHub repo and project structure
- [x] Set up endpoints with NextJS Backend and PostgreSQL/Prisma
- [x] Set up frontend with NextJS Frontend and TailwindCSS
- [x] Set up Supabase/Cloudinary for image storage

### Core Features (MVP)
- [x] Build endpoints for:
  - [x] Posting free items (Givists)
  - [x] Browsing and filtering items (Hunters)
  - [x] Claiming an item
  - [x] Viewing claimed and listed items (per user)
- [x] Connect frontend with backend via Axios
- [x] Allow image uploads for items
- [x] Add search and location-based filtering
- [x] Implement item status updates (`available`, `claimed`, `removed`)

### Authentication & Authorization
- [x] Build user registration and login endpoints
    - Email verification link
- [x] Secure routes with JWT or session-based auth
    - User's profile route

### Rating System
- [x] Allow Hunters to rate Givists after claiming an item
- [x] Display average ratings for Givists

### Polish and Deploy
- [x] Add input validation and error handling
- [x] Responsive design and UI polish
- [x] Deploy frontend/backend (Vercel)
---

## Future Implementations
- Real-time messaging between Givists and Hunters
- Admin dashboard for managing reports and flagged content
- Gamification features (e.g., badges for Givists)
- Integration with a map API for geolocation and directions
