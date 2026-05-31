# Hearthboard

## Summary

Hearthboard combines professional project management with the simplicity of a household to-do list, helping homeowners organize, prioritize, and complete projects around the home.

Home projects often grow larger than expected. What starts as a weekend project can quickly become a months-long effort with multiple steps, dependencies, and competing priorities. Hearthboard provides a single place to manage all home projects, track progress, and identify the most important next action.

The goal of Hearthboard is to help users answer one simple question:

> What should I work on next?

---

# Data Model

## Project

A Project represents a larger effort that requires multiple work sessions to complete, such as building a chicken coop, remodeling a bathroom, or installing a fence.

### Fields

| Field | Description |
|---------|-------------|
| Name | Project name |
| Notes Timeline | Timestamped project notes and updates |
| Status | Not Started, Working, Complete, Archived |
| Start Date | Planned or calculated project start date |
| Target Completion Date | Planned or calculated project completion date |
| Priority | Low, Medium, High |
| Category | User-defined category |
| Health | Green, Yellow, or Red (calculated) |
| Percent Complete | Calculated from completed tasks |
| Next Action | Earliest incomplete task by planned date |

### Date Behavior

Projects support two date modes.

#### Manual Dates

The user manually defines the Start Date and Target Completion Date.

#### Dynamic Dates

The Start Date is automatically calculated from the earliest Task Planned Date.

The Target Completion Date is automatically calculated from the latest incomplete Task Due Date.

### Health Calculation

| Health | Criteria |
|---------|----------|
| Green | On track |
| Yellow | Due within 14 days and less than 75% complete |
| Red | Past target completion date and not complete |

### Database Actions

- Create
- Read
- Update
- Archive
- Delete

### Delete Rules

A Project cannot be deleted if it contains Tasks.

The user must either:

- Delete all associated Tasks, or
- Archive the Project.

---

## Task

A Task represents a single unit of work that can realistically be completed during one work session, such as an evening, afternoon, or weekend.

Every Task belongs to exactly one Project.

### Fields

| Field | Description |
|---------|-------------|
| Name | Task name |
| Notes | Optional task notes |
| Status | Not Started, Working, Complete |
| Planned Date | Date the user intends to begin work |
| Due Date | Date the task should be completed by |
| Effort | Small, Medium, Large |
| Completion Date | System-managed date populated when status changes to Complete |

### Effort Definitions

| Effort | Definition |
|---------|------------|
| Small | Less than 1 hour |
| Medium | 1–4 hours |
| Large | More than 4 hours |

### Database Actions

- Create
- Read
- Update
- Delete

### Status Behavior

When a Task is marked Complete:

- Status changes to Complete
- Completion Date is automatically populated with the current date
- Task is excluded from overdue calculations

---

# User Interface

## Home

The Home screen serves as the user's project dashboard and highlights the most actionable information.

### Card 1: Next Up

Displays the top five incomplete Tasks sorted by:

1. Priority (High → Low)
2. Due Date (Earliest → Latest)

Each row displays:

- Task Name
- Project Name
- Due Date
- Status

Tasks can be marked complete directly from this card.

### Card 2: Overdue

Displays incomplete Tasks whose Due Date is before today.

Each row displays:

- Task Name
- Project Name
- Due Date
- Days Overdue

### Card 3: Active Projects

Displays Projects with a Status of Working.

Each row displays:

- Project Name
- Health Indicator
- Percent Complete
- Target Completion Date

### Card 4: Recently Completed

Displays Tasks completed within the last 7 days.

Each row displays:

- Task Name
- Project Name
- Completion Date

---

## Projects

The Projects screen displays all Projects.

### Default View

Projects are sorted by:

1. Priority (High → Low)
2. Target Completion Date (Earliest → Latest)

Each Project card displays:

- Project Name
- Category
- Status
- Priority
- Health
- Percent Complete
- Start Date
- Target Completion Date
- Next Action

### Alternate Views

Users can switch between:

- All Projects
- Active Projects
- Completed Projects
- Archived Projects
- Quarterly View (Q1, Q2, Q3, Q4)

### Project Details

Selecting a Project opens the Project Details screen.

#### Project Header

Displays:

- Project Name
- Category
- Status
- Priority
- Health
- Percent Complete
- Start Date
- Target Completion Date
- Next Action

#### Task List

Displays all Tasks associated with the Project.

Tasks are grouped by:

- Not Started
- Working
- Complete

Each Task displays:

- Task Name
- Status
- Planned Date
- Due Date
- Effort

Tasks can be created, edited, completed, and deleted from this screen.

#### Notes Timeline

Displays timestamped project updates in reverse chronological order.

Users can:

- Add note
- Edit note
- Delete note

---

## Settings

### Appearance

- Light Mode
- Dark Mode
- System Default

### Categories

Users can manage custom Project Categories.

Supported actions:

- Create
- Read
- Update
- Delete

### Category Delete Rules

A Category cannot be deleted while it is assigned to one or more Projects.

The user must first reassign or archive those Projects.
