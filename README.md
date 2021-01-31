# todotxt-kanban

## Introduction
A set of wrappers and configurations so that todo.txt can be used in a Kanban-type process

The epic I'm working against is:
> As a wanna be productivity-freak (PF) that uses todo.txt for tasks I want to manage my projects using a Kanban-type process.

## Details
The `tkb` tools work by manipulating tasks by adding and removing @contexts that represent kanban status. As of 2021-01-31 there are three statuses: Backlog (no @context), In Progress (@inprogress), Done (@done).  

> When a task is @done on the kanban that does not mean that the corrosponding todo.txt task has been marked as done by prepending `x`. 

> The two kanban contexts (@inprogress, @done) are not configurable just yet. That means this may conflict with your todo.txt context list.

## Use cases
- As a PF[^**] I want to have my todo.txt task list as a Kanban board
	- Setup `tkb.cfg` to point to your todo list and preferred Kanban board location. I keep mine in my obsidian vault, but that isn't a requirement.
	- `tkb-gen`
		- this'll create a markdown board for every +project mentioned in your `todo.txt`. 
		- Each kanban file will have three sections: Backlog, In Progress, and Done.
		- The files are chmod to read-only to help remind that they shouldn't be edited manually.
		- Since your tasks won't have any kanban contexts they will all be in Backlog.
- As a PF I want to move a task to (In Progress|Done|Backlog)
	- `tkb-status TASK# (inprogress|done|backlog)`
		- You can move from any status to any other status
		- This remove any kanban contexts and add the the selected context to the task with TASK#
			> There is no contest that maps to backlog. The absence of kanban contexts implies the task is in the Backlog
		- Any +projects in the task will have their boards updates to reflect the status change. 
			> You can have a task be in multiple projects and each kanban will reflect the status change.
- As a PF I want to remove completed items from the board
	- TODO
- As a PF I want to be able to set a task as Blocked and specify a reason
	- TODO


## Todo
> Disclaimer: This isn't a commitment. I'm building and updating this based on my workflow. I'm happy to accept pull requests that make sense to me and fulfill any of these or other open items.
- [ ] convert to todo.txt's addon framework
- [ ] add configurations for contexts
- [ ] use templates for kanban output
- [ ] repo needs organizing
- [ ] figure out how the cool kids are licensing things these days


### Acknowledgments
- todo.txt
- todo.txt CLI

Very much a work in progress.

Another project of mine (https://github.com/brosell/obsidian-todotxt-kanban) depends on this


[^**]: Productivity Freak