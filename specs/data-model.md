---
title: "Data Model"
tags: ["data", "schema"]
links: ["Auth API", "Tasks API", "Notifications API"]
created: 2024-03-28T08:00:00.000Z
modified: 2024-03-28T09:00:00.000Z
---
# Data Model

## Entities

### User
- `id: UUID`
- `email: string`
- `displayName: string`
- `role: owner | member`
- `createdAt: datetime`

### Project
- `id: UUID`
- `name: string`
- `description: text`
- `ownerId: UUID`
- `status: active | archived`
- `createdAt: datetime`

### Task
- `id: UUID`
- `projectId: UUID`
- `title: string`
- `description: text`
- `status: todo | in_progress | done`
- `priority: low | medium | high | urgent`
- `assigneeId: UUID | null`
- `dueDate: datetime | null`
- `createdById: UUID`
- `createdAt: datetime`
- `updatedAt: datetime`

### Comment
- `id: UUID`
- `taskId: UUID`
- `authorId: UUID`
- `body: text`
- `createdAt: datetime`

### Notification
- `id: UUID`
- `userId: UUID`
- `type: assignment | status_change | comment`
- `title: string`
- `body: string`
- `readAt: datetime | null`
- `createdAt: datetime`

## Relationships
- A user owns many projects
- A project has many tasks
- A task has many comments
- A user has many notifications

## Validation Rules
- Task title is required and max 160 chars
- Due date may be null but cannot be before project creation
- Only owner/member roles exist for this demo
- Archived projects are read-only