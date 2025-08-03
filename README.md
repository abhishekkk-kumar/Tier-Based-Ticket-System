# Tier-Based-Ticket-System

A responsive and elegant web application that allows logged-in users to view a list of 
show events based on their user tier (e.g., Free, Silver, Gold, Platinum). A user can only 
see events available to their tier or any lower tier.

Tech Stack: 
● Frontend: Next.js 14 (App Router) 
● Authentication: Clerk.dev 
● Database: Supabase (PostgreSQL) 
● Styling: Tailwind CSS

Directory Structure

/app
└── (routes and UI logic using App Router)

/components
└── (reusable UI components)

/lib
└── (Supabase & Clerk utilities)

/styles
└── globals.css (Tailwind base styles)

⚙️ Setup Instructions

 1. Clone the Repository

git clone https://github.com/your-username/tiered-show-events-app.git
cd tiered-show-events-app

2. Install Dependencies

npm install

3. Set Up Clerk.dev
Create an account at clerk.dev

Get your Clerk Frontend API and publishable keys

Add them to your .env.local:


NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_publishable_key
CLERK_SECRET_KEY=your_secret_key

4. Set Up Supabase
Create a project at supabase.com

Define a table events with fields like:


CREATE TABLE events (
  id uuid PRIMARY KEY,
  title text NOT NULL,
  description text,
  tier text CHECK (tier IN ('Free', 'Silver', 'Gold', 'Platinum')) NOT NULL
);
Add your Supabase credentials to .env.local:

NEXT_PUBLIC_SUPABASE_URL=your_project_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_anon_key
5. Run the App
bash
Copy
Edit
npm run dev
Visit http://localhost:3000 to view the app
