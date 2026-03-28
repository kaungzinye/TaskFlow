---
title: "Auth API"
tags: ["api", "auth"]
links: []
created: 2024-03-28T08:00:00.000Z
modified: 2024-03-28T09:00:00.000Z
---
# Auth API

## Overview
Authenticate users and expose the current session for the web app.

## Endpoints
### POST /api/auth/signup
- Request: `{ email, password, displayName }`
- Response: `{ user, session }`

### POST /api/auth/login
- Request: `{ email, password }`
- Response: `{ user, session }`

### POST /api/auth/logout
- Invalidates current session
- Response: `{ ok: true }`

### GET /api/auth/me
- Returns current signed-in user and session metadata

## Requirements
- Email/password only for demo
- Invalid credentials return 401
- Unauthenticated requests to protected endpoints return 401
- Session must be available to dashboard and task pages