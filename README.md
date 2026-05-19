# Band Scheduler

A shared availability calendar for bands. Built with React + Supabase.

## Setup

1. Install dependencies:
   ```
   npm install
   ```

2. Run locally:
   ```
   npm start
   ```

## Deploy to Vercel

1. Push this folder to a GitHub repo
2. Go to vercel.com → New Project → Import your repo
3. Click Deploy — done!

## Supabase Tables Required

**availability**
- id (uuid, primary key)
- day_key (text)
- member_index (int)
- available (boolean)
- unique constraint on (day_key, member_index)

**events**
- id (uuid, primary key)
- day_key (text)
- title (text)
- type (text)
- time (text, nullable)
- notes (text, nullable)
- created_at (timestamp, default now())

## Notes
- Member names save per-device (localStorage)
- Availability and events sync via Supabase
- Make sure RLS is disabled or permissive policies are set on both tables
