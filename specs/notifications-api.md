---
title: "Notifications API"
tags: ["api", "notifications"]
links: []
created: 2024-03-28T08:00:00.000Z
modified: 2024-03-28T09:00:00.000Z
---
# Notifications API

## Overview
Support an in-app notification center for assignment and workflow updates.

## Endpoints
### GET /api/notifications
Return notifications for the current user ordered newest first.

### POST /api/notifications/mark-read
Request: `{ notificationIds: string[] }`
Response: `{ ok: true }`

## Trigger Rules
- Create notification when a task is assigned to a user
- Create notification when a watched task changes status
- Create notification when a comment is added to a task assigned to the user

## UI Requirements
- Notification bell in app chrome
- Unread count badge
- Mark one or many notifications as read