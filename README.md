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
