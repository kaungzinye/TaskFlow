---
title: "Architecture"
tags: ["architecture", "system"]
links: ["Data Model", "Auth API", "Tasks API"]
created: 2024-03-28T08:00:00.000Z
modified: 2024-03-28T09:00:00.000Z
---
# Architecture

## Overview
Build TaskFlow as a pragmatic full-stack web app optimized for local setup and one-shot generation.

## Recommended Stack
- Frontend: Next.js + TypeScript + Tailwind CSS
- Backend: Next.js route handlers or API routes
- Database: Supabase Postgres
- Auth: Supabase Auth with email/password
- ORM: Prisma or Supabase client helpers

## System Modules
- Dashboard UI for projects, tasks, and recent activity
- Auth module for sign in, sign out, and session validation
- Project and task API layer
- Notification service for in-app notifications
- Database layer for users, projects, tasks, comments, and notifications

## Request Flow
1. Browser sends authenticated request to route handler.
2. Route validates session.
3. Route reads or writes database records.
4. Response updates dashboard state.
5. Mutation triggers activity log and notification creation when relevant.

## Constraints
- Prefer server simplicity over microservices
- Keep everything runnable locally
- Prioritize working CRUD and auth over pixel-perfect design