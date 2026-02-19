<<<<<<< HEAD
# Smart Bookmark App
A simple full-stack bookmark manager built using Next.js (App Router), Supabase, and Tailwind CSS.

Users can sign in using Google OAuth, add bookmarks, and view them in real-time. Each user's bookmarks are private and protected using Supabase Row Level Security (RLS).
## Live Demo
Vercel URL: https://your-app.vercel.app
## Tech Stack

- Next.js (App Router)
- Supabase (Auth, Database, Realtime)
- Tailwind CSS
- Vercel (Deployment)
## Features

- Google OAuth Authentication (No email/password)
- Add bookmark (URL + title)
- Private bookmarks per user
- Real-time updates without refresh
- Delete own bookmarks
- Deployed on Vercel
## Architecture

Frontend:
- Built with Next.js (App Router)

Backend:
- Supabase (PostgreSQL database)
- Supabase Auth for Google OAuth
- Supabase Realtime for live updates

  ## Database Schema

Table: bookmarks

| Column      | Type        | Description                  |
|-------------|------------|------------------------------|
| id          | UUID       | Primary key                  |
| user_id     | UUID       | References authenticated user|
| url         | Text       | Bookmark URL                 |
| title       | Text       | Bookmark title               |
| created_at  | Timestamp  | Created time                 |


## Local Setup

1. Clone the repository
2. Install dependencies:
   npm install
3. Create a .env.local file with:
   NEXT_PUBLIC_SUPABASE_URL=
   NEXT_PUBLIC_SUPABASE_ANON_KEY=
4. Run:
   npm run dev
   
## Challenges Faced & Solutions

1. Understanding Supabase Row Level Security (RLS)
   - Initially bookmarks were visible across users.
   - Solved by enabling RLS and writing policy:
     user_id = auth.uid()

2. Implementing Realtime Updates
   - Faced difficulty understanding subscription API.
   - Used Supabase channel subscription to listen to INSERT events.

3. Learning Next.js App Router
   - Coming from traditional backend frameworks, adapting to server/client components required research and practice.

## AI Tools Used

- ChatGPT: Used for understanding Supabase RLS policies and debugging errors.
- Documentation: Official Next.js and Supabase docs used extensively.

AI was used as a learning assistant and debugging aid, not for blindly generating the full project.

## Future Improvements

- Bookmark categorization
- Search functionality
- Edit bookmarks
- Pagination



Security:
- Row Level Security (RLS) enabled to ensure users can only access their own bookmarks.
=======
This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/app/building-your-application/optimizing/fonts) to automatically optimize and load [Geist](https://vercel.com/font), a new font family for Vercel.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/app/building-your-application/deploying) for more details.
>>>>>>> 6c1a21c (Initial commit from Create Next App)
