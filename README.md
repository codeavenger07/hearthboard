# hearthboard

## summary
Hearthboard combines professional project management and the honey-do list into a single structure to track, manage, and prioritize your home projects. 

Oftentimes, home projects are much larger than initially thought and they grwow in scope and time. Before you know it, your 2 week project turns into a 2 month project and, even after that time, the end isn't in site.

Hearthboard empowers you to track your projects together into one view so that you can prioritize the "what's next" and not overcrowd your schedule into disappointment and failure.

## structure
### project
These are large efforts that span across multiple days, weeks, or even months to complete (i.e. build a new chicken coop). 

#### data
* Name
* Notes timeline (timestamped)
* Status (Not Started, Working, Complete)
* Start Date and Target Completion Date (not used if Dynamic Dates are used, which takes the Start Date of the earliest task and the Target Completion Date of the latest task)
* Priority (Low, Medium, High)
* Cateogry (managed on the settings page)
* Health (green: On track, yellow: Due within 14 days and <75% complete, red: Past due)
* Next Action: the task that is currently scheduled or next (earliest start date that isn't completed)

#### database actions
Create, Read, Update, Delete, Archive
A project can't be deleted if there are underlying tasks

### task
Tasks are small chunks of work that can realistically be accomplished during a single session (evening, weekend, etc.). A project is made up of multiple tasks. 

A task contains the following tracking artifcats:
* Name
* Notes
* Status (Not Started, Working, Complete)
* Planned Date and End Date
* Effort: Small (<1 hour), Medium (1–4 hours), Large (4+ hours)

#### database actions
Create, Read, Update, Delete

## ui/ux
### home
The home tab will contain multiple cards to display data:
* card 1: top 5 tasks by priority and due date
* card 2: tasks that are overdue
* card 3: projects currently working
* card 4: recently completed tasks in the last 7 days

### projects
The projects tab will list all projects, with their start and end date, their status, and the % complete (based on task completion). Projects should be sorted by descending by start date (earliest start date first). I should be able to change views to see what projects are due in calendar year quarters (Q1, Q2, etc.)

### settings
The settings page will contain 
* dark mode / light mode setting
* category management (CRUD, can't delete if being used)

