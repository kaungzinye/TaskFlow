---
title: "Tasks API"
tags: ["api", "tasks"]
links: ["Notifications API"]
created: 2024-03-28T08:00:00.000Z
modified: 2024-03-28T09:00:00.000Z
---
# Tasks API

## Overview
Provide all project, task, comment, and dashboard read/write operations.

## Endpoints
### GET /api/projects
Return all visible projects for the signed-in user.

### POST /api/projects
Create a new project with `{ name, description }`.

### GET /api/projects/:projectId/tasks
Return tasks for a single project.

### POST /api/tasks
Create a task with `{ projectId, title, description, assigneeId, dueDate, priority }`.

### PATCH /api/tasks/:taskId
Update title, description, assignee, due date, priority, or status.

### POST /api/tasks/:taskId/comments
Append a comment with `{ body }`.

### GET /api/dashboard
Return `assignedTasks`, `overdueTasks`, `recentActivity`, and `projectSummaries`.

## Rules
- Only authenticated users can access task endpoints
- Task updates must write `updatedAt`
- Status changes create activity entries
- Assignment changes can trigger notifications