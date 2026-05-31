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
* Notes
* Status (Not Started, Working, Complete)
* Start Date and End Date (not used if Dynamic Dates are used, which takes the Start Date of the earliest task and the End Date of the latest task)

#### database actions
Create, Read, Update, Delete
A project can't be deleted if there are underlying tasks

### task
Tasks are small chunks of work that can realistically be accomplished during a single session (evening, weekend, etc.). A project is made up of multiple tasks. 

A task contains the following tracking artifcats:
* Name
* Notes
* Status (Not Started, Working, Complete)
* Start Date and End Date

#### database actions
Create, Read, Update, Delete

## ui/ux
### home
The home tab will contain in the first card tasks that are past due and coming due in the next week (7 days). Each card will have the task name, the due date, the project associated and a designator to show it's "past due" (red) or "coming due" (brown). The task should be able to be completed from the dashboard by tapping on an empty checkbox on the left-hand side.

The second card will show projects that are past due and coming due in the next week (7 days). Each card will have the project name, the due date, and a designator to show it's "past due" (red) or "coming due" (brown).

The third card will show recently completed tasks (past 7 days, including today). Each card will have the task name, the due date, and the project associated.

### projects
The projects tab will list all projects, with their start and end date, their status, and the % complete (based on task completion). Projects should be sorted by descending by start date (earliest start date first). I should be able to change views to see what projects are due in calendar year quarters (Q1, Q2, etc.)

### settings
The settings page will contain dark mode / light mode setting. 
