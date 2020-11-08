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
