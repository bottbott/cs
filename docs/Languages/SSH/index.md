---
lang: en
title: SSH
viewport: width=device-width, initial-scale=1.0
---
## Troubleshooting
### Unable to acquire lock
For some reason, a lock was open on some of the .vscode-server files and it was 
preventing me from reconnecting my SSH session. Trying to rm -rf the files 
didn't work, and trying to run the Kill command from the VSCode command palette
also had the same problem. 

Unfortunately, one of my longstanding processes was running and is tied up with
the locked file. Seems like I will have to kill it, or if I can access that
process from another SSH session maybe I can fix it there. 

Used commands:

- `lsof | grep 681` used to find which processes had a lock on a file with 681
in the name.
- `killall -9 node` killed node when it was tying things up. 
- `kill -9 324234` killed a given PID. Usually tried with -10 first.
    - used the `kill` command with a -10 to get it to come back to life with my 
    missing session.
- `rm -rf some-dir-name` trying to remove a bunch of files/folders. It revealed
 what was locked.
- `tree` to inspect the structure of the directories. 
- `history | grep term` - this was handy to search through my history of commands
- `CTRL+R` lets me search for a command