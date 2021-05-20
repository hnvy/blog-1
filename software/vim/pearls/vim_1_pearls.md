# E#4 (10/05/2021) - a clipboard dilemma.
[Link to the relevent log entry](https://github.com/hnvy/blog-1/blob/main/software/vim/logs/vim_1_logs.md#e4-10052021---a-clipboard-dilemma)
* `yy` to yank (copy) the line into the Vim register.
* `yw` to yank (copy) the word under the cursor into the Vim register.
* `p` to paste the content stored in the Vim register AFTER the cursor.
* `P` to paste the content stored in the Vim register BEFORE the cursor.
* `u` to undo a change.
* `U` to undo all changes on the CURRENT line.
* `Ctrl+r` to redo.
* `:` and then any number of your choice. This will take you to that particular line in your current file. So, `:33` will take me to line 33. Alternatively, you can type a number, followed by `G` (e.g., the example above would be `33G`). Another way is by typing a number followed by `gg` (e.g., the example above would be `33gg`).
* `/` followed by any word of your choice to search FORWARD. After that, you can press `n` to cycle through the matches (use `N` to search in the opposite direction).
* `?` followed by any word of your choice to search BACKWARD. After that, you can press `n` to cycle through the matches (use `N` to search in the opposite direction).

# E#3 (21/04/2021) - Notepad++ > Vim?!
[Link to the relevent log entry](https://github.com/hnvy/blog-1/blob/main/software/vim/logs/vim_1_logs.md#e3-21042021---notepad--vim)
* `x` to delete the character AFTER the cursor.
* `X` to delete the character BEFORE the cursor.
* `A` to insert text at the end of the line.
* `I` to insert text at the start of the line.
* `a` to insert text AFTER the cursor.
* `i` to insert text BEFORE the cursor.
* `dd` to delete the whole line.
* `d$` or `D` to delete from the current position to the end of the line.
* `:wq` to write (hence the `w`) the changes, and then quit Vim (hence the `q`).

# E#2 (20/04/2021) - vimtutor.
[Link to the relevent log entry](https://github.com/hnvy/blog-1/blob/main/software/vim/logs/vim_1_logs.md#e2-20042021---vimtutor)
* The `vimtutor` file is located in `\Vim\vim82\tutor`.
* `:set: guifont=*` to change the font of the interface.
* `i` to enter Insert mode.
* Use the Escape button, `Esc`, to return to Normal mode.
* Whilst in Normal mode, you can move up, down, right, and left by using the following keys: `k`, `j`, `l`, and `h`, respectively (remember, `j` looks like a down arrow!).

# E#1 (19/04/2021) - day 0.
[Link to the relevent log entry](https://github.com/hnvy/blog-1/blob/main/software/vim/logs/vim_1_logs.md#e1-19042021---day-0)
* To enter commands into Vim, you should write `:`. After doing so, you will notice that your cursor has moved to the bottom of the screen.
* `:q!` to quit Vim without saving the changes.
