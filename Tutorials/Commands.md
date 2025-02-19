## Git
1.  **UNDO** local file changes and **KEEP** your last commit
	- git reset --hard <hash>
    
2.  **UNDO** local file changes and **REMOVE** your last commit
	- git reset --hard HEAD^
    
3.  **KEEP** local file changes and **REMOVE** your last commit
	- git reset --soft HEAD^
4. Commit logs
	- git log --reflog


## Tmux commands
- tmux attach
- tmux detach 
- tmux ls
- tmux new -s Session_Name      # create new server with name
- tmux new -s Session_Name -d  # create new server with name detached
- tmux a -t SESSION_NAME         # attach to server with name
- tmux kill-session -t Session_name # kill server with name
- tmux kill-server                         # kill all servers


## Linux
- clear history
	- cat /dev/null > ~/.bash_history && history -c && exit

# Windows
### create shortcuts for command line commands
```
"C:\Windows\System32\cmd.exe" /k echo hello & echo world
```
