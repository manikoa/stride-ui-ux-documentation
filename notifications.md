# Notifications & Activity Tracking

## Feature Overview

The Notifications and Activity Tracking features in Stride keep users informed about relevant activities, changes, and events across the platform. This system ensures that users are aware of updates that require their attention or are relevant to their work, while also providing a comprehensive history of activities for auditing and reference.

## Data Models

### Notification
- **User**: User receiving the notification
- **Source**: The item generating the notification (task, note, etc.)
- **Type**: Type of notification (mention, assignment, update, etc.)
- **Content**: Text description of the notification
- **Read Status**: Whether the notification has been read
- **Created timestamp**: When the notification was created
- **Action URL**: Link to the relevant item

### Activity
- **Source Type**: Type of entity where the activity occurred (space, team, project, etc.)
- **Source ID**: ID of the specific entity
- **Actor**: User who performed the action
- **Action Type**: Type of action performed
- **Details**: Additional information about the action
- **Created timestamp**: When the activity occurred
- **Visibility**: Who can see this activity (public, space, team, or private)

## Notification Types

### User Notifications
- **Mentions**: When a user is mentioned in a comment or note
- **Assignments**: When a task is assigned to a user
- **Due Date Reminders**: Reminders about upcoming or overdue tasks
- **Comments**: New comments on items the user is following
- **Shares**: When content is shared with the user
- **Security Events**: Login attempts, password changes, etc.

### Space/Team Notifications
- **Member Changes**: New members added or removed
- **Content Creation**: New projects, notes, or important tasks
- **Updates**: Significant updates to existing content
- **Milestones**: Important project milestones or deadlines

## Activity Categories

### Content Activities
- **Creation**: New items created (projects, notes, tasks)
- **Updates**: Changes to existing content
- **Deletion**: Items removed from the system
- **Archiving**: Items archived or restored

### Collaboration Activities
- **Comments**: New comments added
- **Reactions**: Reactions added to content
- **Mentions**: Users mentioned in content
- **Shares**: Content shared with other users

### Membership Activities
- **Joins/Leaves**: Users joining or leaving spaces/teams
- **Role Changes**: Changes to user roles or permissions
- **Invitations**: New invitations sent