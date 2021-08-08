# E#5 (21/05/2021) - Jump like a rabbit!
[Link to log entry](https://github.com/hnvy/blog-1/blob/main/software/vim/logs/vim_1_logs.md#e5-21052021---jump-like-a-rabbit)
* Vim has several different modes. You use Normal mode to navigate through your text. Whereas you use Insert mode to insert text (obviously). Typing `:` will activate Command mode.
* `w` to jump FORWARD to the start of the next word in a sentence (thinks that hyphens, dots, commas, etc. are actually spaces, and will hence treat them as such). For example, "Vim-is-a-modal-text-editor" will be treated as having 11 words.
    * `e` will do the same thing, except it will jump to the end of the current word.
    * `b` will do the same thing, except it goes BACKWARD.
* `W` to jump FORWARD to the start of the next word in a sentence (thinks that ONLY the words separated by spaces are true words). For example, "Vim-is-a-modal-text-editor" will be treated as having only one word.
    * `E` will do the same thing, except it will jump to the end of the current word.
    * `B` will do the same thing, except it goes BACKWARD.
* Save and exit. See this [pearl entry](https://github.com/hnvy/blog-1/blob/main/software/vim/pearls/vim_1_pearls.md#e3-21042021---notepad--vim) to learn more about a third method.:
   * `:x` will do the same thing as `:wq` except that it will not save the file if you have not made a change.
   * `ZZ` will do the same thing as `:x` (and hence `:wq`).

# E#4 (10/05/2021) - a clipboard dilemma.
[Link to log entry](https://github.com/hnvy/blog-1/blob/main/software/vim/logs/vim_1_logs.md#e4-10052021---a-clipboard-dilemma)
* `yy` to yank (copy) the line into the Vim register.
    * Combine this with `p` to get `yyp` and hence duplicate the current line.
* `yw` to yank (copy) the word under the cursor into the Vim register.
* `p` to paste the content stored in the Vim register AFTER the cursor.
* `P` to paste the content stored in the Vim register BEFORE the cursor.
* `u` to undo a change.
* `U` to undo all changes on the CURRENT line.
* `Ctrl+r` to redo.
* Go to line X
    * `:` and then any number of your choice. This will take you to that particular line in your current file. So, `:33` will take me to line 33.
    * Type a number followed by `G` (e.g., the example above would be `33G`) to get the same result.
    * Type a number followed by `gg` (e.g., the example above would be `33gg`) to get the same result.
* `/` followed by any word of your choice to search FORWARD. After that, you can press `n` to cycle through the matches (use `N` to search in the opposite direction).
* `?` followed by any word of your choice to search BACKWARD. After that, you can press `n` to cycle through the matches (use `N` to search in the opposite direction).

# E#3 (21/04/2021) - Notepad++ > Vim?!
[Link to log entry](https://github.com/hnvy/blog-1/blob/main/software/vim/logs/vim_1_logs.md#e3-21042021---notepad--vim)
* `x` to delete the character AFTER the cursor.
* `X` to delete the character BEFORE the cursor.
* `A` to insert text at the end of the line.
* `I` to insert text at the start of the line.
* `a` to insert text AFTER the cursor.
* `i` to insert text BEFORE the cursor.
* `dd` to delete the whole line.
* `d$` or `D` to delete from the current position to the end of the line.
* `:wq` to write (hence the `w`) the changes, and then quit Vim (hence the `q`). This will save your buffer whether or not you made a change.

# E#2 (20/04/2021) - vimtutor.
[Link to log entry](https://github.com/hnvy/blog-1/blob/main/software/vim/logs/vim_1_logs.md#e2-20042021---vimtutor)
* The `vimtutor` file is located in `\Vim\vim82\tutor`.
* `:set: guifont=*` to change the font of the interface.
* `i` to enter Insert mode.
* Use the Escape button, `Esc`, to return to Normal mode.
* Whilst in Normal mode, you can move up, down, right, and left by using the following keys: `k`, `j`, `l`, and `h`, respectively (remember, `j` looks like a down arrow!).

# E#1 (19/04/2021) - day 0.
[Link to log entry](https://github.com/hnvy/blog-1/blob/main/software/vim/logs/vim_1_logs.md#e1-19042021---day-0)
* To enter commands into Vim, you should write `:`. After doing so, you will notice that your cursor has moved to the bottom of the screen.
* `:q!` to quit Vim without saving the changes.
