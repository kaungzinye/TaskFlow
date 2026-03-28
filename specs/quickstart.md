---
title: "Quickstart"
tags: ["setup", "build"]
links: []
created: 2024-03-28T08:00:00.000Z
modified: 2024-03-28T09:00:00.000Z
---
# Quickstart

## Goal
Generate a working full-stack web app for TaskFlow from these specs.

## Required Stack
- Next.js App Router
- TypeScript
- Tailwind CSS
- Supabase Postgres
- Supabase Auth for email/password

## Required Screens
- Sign in / sign up
- Dashboard
- Project detail page
- Task detail panel or page
- Notification center

## Build Priorities
1. Working auth
2. Working project/task CRUD
3. Dashboard summaries
4. Notifications
5. Seed data for demo

## Implementation Guidance
- Prefer simple server-side route handlers over microservices
- Keep schema and API names aligned with these specs
- Return clear errors for invalid input
- Generate a README with setup commands
- Optimize for reliability over perfect design