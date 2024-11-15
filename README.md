# tmix
This is a wrapper around tmux that lets multiple users join the same tmux session.

Disclaimer: This is not a polished tool and was ported from a nixos package that ran on a much newer version of tmux. If you discover any issues, please let any of the contributors know so the tool can be improved.

## Setup
If you don't have a tmux.conf file you are overly attached to, then please adopt the one in this repo to provide a more standard pairing experience. To install this in your local user tmux config: 

```
$ cp ./tmux.conf ~/.tmux.conf
```
To install it to your system tmux config:

```
$ sudo cp ./tmux.conf /etc/tmux.conf
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
If this doesn't work, you may be using a different tmux.conf file and may need to use
```
Ctrl-b d
```

## Joining an existing session
For you or others to join an existing tmix session with default name you need to specify the username who created the session followed by a `/`. So if myuser created the session then the command would be:
```
$ tmix myuser/
```
or you can specify the tmix sesssion name:
```
$ tmix myuser/mysessionname
```

To leave (detach) from the session:
```
Ctrl-a d
```
If this doesn't work, you may be using a different tmux.conf file and may need to use
```
Ctrl-b d
```

## Updating Tmix
If you have made updates to tmix then you can run install.sh to install in /usr/local/bin (need sudo since /usr/local/bin is owned by root)
```
$ sudo ./install.sh
```

## Tmix/Tmux cheatsheet
These only applies if using the tmux.conf file in this repo. These should help once inside a tmux session. There are many more commands, so if these don't suffice you should be able to find more thorough tmux cheatsheets online.

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
