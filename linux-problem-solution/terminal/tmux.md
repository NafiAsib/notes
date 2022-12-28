# tmux



* **Sessions** - a session is an independent workspace with one or more windows
  * `tmux` starts a new session.
  * `tmux new -s NAME` starts it with that name.
  * `tmux ls` lists the current sessions
  * Within `tmux` typing `<C-b> d` detaches the current session
  * `tmux a` attaches the last session. You can use `-t` flag to specify which

### Resources

* [A Quick and Easy Guide to tmux](https://www.hamvocke.com/blog/a-quick-and-easy-guide-to-tmux/) - Ham Vocke
* [Command-line Environment](https://missing.csail.mit.edu/2020/command-line/) - Missing Semester MIT
