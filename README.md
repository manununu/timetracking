# timetracking
## used tools
* [taskwarrior](https://taskwarrior.org/)
* [timewarrior](https://timewarrior.net/)
## hook script (timewarrior <-> taskwarrior)
```
$ cp ext/on-modify.timewarrior ~/.task/hooks/
$ chmod +x ~/.task/hooks/on-modify.timewarrior
```

## useful .bashrc alias
```
alias timewday='timew day rc.reports.day.lines=4'
```
