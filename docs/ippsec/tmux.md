### tmux runs as a process and not tied to a session, so if you make a tmux session it will not die when your ssh connection get closed, so you cna reconnect easily to earlier session without losing anything

### Create New tmux session

\# tmux new -s \<name\>

example: 

\# tmux new -s HTB

### Prefix key

Ctrl + b === Prefix key

### To create a new window

(prefixKey) c

(prefixKey)0 or (prefixKey)1 to switch to different sessions

### tmux config

\#vi ~/.tmux.conf


\#Remap prefix to screens
set -g prefix C-a
bind C-a send-prefix
unbind C-b

\#Quality of life stuff
set -g history-limit 10000
set -g aloow-rename off

\## Join Windows
bind-key j commnad-prompt -p "join pane from:" "join-pane -s '%%'"
bind-key s commnad-prompt -p "send pane to:" "join-pane -t '%%'"

\# Search Mode VI (default is emac)
set-window-option -g mode-keys vi

run-shell /opt/tmux-logging/logging.tmux


### To Attach to a Session

\#tmux ls

\# tmux attach -t \<session\_name\>

### To Detach from a Session

(prefixKey)d

### Rename a session

(prefixKey),

### Send window to a pane

(prefixKey)s

### Move to Copy Mode

(prefixKey)[

now you can use page up and page down to move around

Hit \<space\> to enter into copy mode, select text, hit \<enter\> to copy into the vim buffer

Now open vim

(prefixKey)]      --  and it paste


### TO Save logs

(prefixKey) + Alt+Shift+P

### Veritcal split

(prefixKey)%

### Horizontal Split

(prefixKey)"
 
### To move around in windows
(prefixKey)\<arrow\_key\>

### Zoom in to any windows

(prefixKey)z  --- Do this again to zoom out


### TO resize a window

(prefixKey) + \<Arrows\>             --- hold ctrl in this case 

(prefixKey){            -- to move the window to other layout

(prefixKey)}           -- move the window to other layout

(prefixKey)\<space\>     -- to change the layout
