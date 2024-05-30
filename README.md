# tmix
Pairing and collaboration tool customized for vmamediad01 server. This is wrapper around tmux that lets multiple users join the same tmux session.

Disclaimer: This is not a polished tool and was ported from a nixos package that ran on a much newer version of tmux. If you discover any issues, please let any of the contributors know so the tool can be improved.

## Setup
If you don't have a .tmux.conf file you are overly attached to, then please adopt the one in this repo to provide a more standard pairing experience. You will need to copy the .tmux.conf file into your home directory
```
$ cp ./.tmux.conf ~/
```
## Creating a new session
To create a new tmix session with default name:
```
$ tmix new
```
To create the session with a specified name:
```
$ tmix new -s mysessionname
```
To leave (detach) from the session:
```
Ctrl-a d
```
If this doesn't work, you may be using a different .tmux.conf file and may need to use
```
Ctrl-b d
```

## Joining an existing session
For you or others to join an existing tmix session with default name you need to specify the username who created the session followed by a `/`. So if dachee created the session then the command would be:
```
$ tmix dachee/
```
or you can specify the tmix sesssion name:
```
$ tmix dachee/mysessionname
```

To leave (detach) from the session:
```
Ctrl-a d
```
If this doesn't work, you may be using a different .tmux.conf file and may need to use
```
Ctrl-b d
```

## Updating Tmix
If you have made updates to tmix need to update the copy in vmamediad01's /usr/local/bin, then you just need to run install.sh (need sudo since /usr/local/bin is owned by root)
```
$ sudo ./install.sh
```

## Tmix/Tmux cheatsheet
These only applies if using the .tmux.conf file in this repo. These should help once inside a tmux session.

### Windows
```
Ctrl-a d	Detach from a session
Ctrl-a c	Create a new window

Ctrl-a n	Next window
Ctrl-a p	Previous window
Ctrl-a 0...9 	Select window by number (ex. Ctrl-a 1)
```

### Panes
```
Ctrl-a % 		Split current pane with a vertical line to create two panes
Ctrl-a " 		Split current pane with a horizontal line to create two panes
Ctrl-a Arrow-key	Navigate between different panes	
```

### Copy Mode
Useful for scrolling and copying code
```
Ctrl-a [	Enter copy mode (should see icon in upper right corner)
q		Exit copy mode
```
