# Timetracking
## Dependencies 
* [taskwarrior](https://taskwarrior.org/)
* [timewarrior](https://timewarrior.net/)
## Installation
```
sudo apt install taskwarrior -y
sudo apt install timewarrior -y
git clone https://github.com/manununu/timetracking.git
```
## Setup
### Create .taskrc file 
```
echo "data.location=~/timetracking/.task" > ~/.taskrc
```
### Create alias for task 
```
echo "alias task='task rc.data.location=~/timetracking/.task'" >> ~/.bashrc
```
## Create symlink for timewarrior
```
ln -s ~/timetracking/.timewarrior ~/.timewarrior
```
## Set up hook script 
```
cp /usr/share/doc/timewarrior/ext/on-modify.timewarrior ~/.task/hooks/
chmod +x ~/.task/hooks/on-modify.timewarrior
```
## Useful .bashrc alias
```
echo "alias timewday='timew day rc.reports.day.lines=4'" >> ~/.bashrc
```
## Some commands
### taskwarrior
```
task add project:homework due:today "Water the plants" +TAG1 +TAG2 # create task
task list # list pending tasks
task all # list all tasks
task 1 mod +TAG3 # add tag to task
task 1 mod "Water the flowers" # rename task
task 1 mod priority:H # set priority
task add project:homework "Throw out the trash"
task 2 mod depends:1 # set dependency
task 2 mod depends: # remove dependency
task 2 mod status:pending # set status
task 2 delete # delete task
task 1 done # complete task

task calendar # show calendar view
task burndown # show barchart
task burndown.daily # show daily barchart
task project:homework count # count number of tasks in project
task status:pending count # count number of tasks pending
task +TAG1 count # count number of tasks with tag
```
### timewarrior
```
# Tags
timew start Presentation 'Prepare Slides'
timew # show tracking
timew stop 
timew summary 
timew tags

# Backdating
timew start 15:00 'Clean house'
timew cancel
timew start 90mins ago 'Clean house'
timew stop 10mins ago 'Clean house'
timew start 3hours ago 'Another task'

# Recording closed intervals
timew track 09:00 - 11:00 'Brunch'
timew track :yesterday 'External training' # using hints

# Summary Report
timew summary
timew summary today
timew summary yesterday - today
timew 2020-10-01T00:00 - 2020-10-10T00:00:00
timew summary 18th
timew summary saturday
timew summary :year
timew summary :quarter
timew summary :ids # get id's
timew summary TAG
timew day 
timew day rc.reports.day.hours=auto rc.reports.day.lines=4

# Corrections
timew untag @1 Presentation
timew tag @1 Presentation
timew lengthen @1 20mins
timew shorten @1 PT5M30S
timew move @1 08:30am # set new start time
```
